# Azure Cheatsheet - Kapsamlı Azure ve Python Entegrasyonu Rehberi

Bu rehber Azure kullanımını, Azure CLI ile kimlik doğrulamayı, **Python ile Azure SQL Database'e bağlanmayı**, veri yazma/okuma, Excel ve CSV gibi farklı formatlardan veri yükleme ve ileri senaryoları sıfırdan ileri seviyeye Türkçe açıklamalarla kapsar.

### Bu Cheatsheet Ne İşe Yarar?
- Azure hesabı ve CLI kurulumu
- Parola yerine **token** ile güvenli Azure SQL bağlantısı
- Python’da **pyodbc** ve **SQLAlchemy** ile Azure SQL kullanımı
- **Excel / CSV** dosyalarını Azure SQL tablolarına yükleme
- Azure SQL’den veri okuma ve sistem bilgisi sorgulama
- Büyük veri yazarken **2100 parametre limiti** ve chunk kullanımı

### Hızlı Başlangıç (Python + Azure SQL)
```bash
# 1. Azure CLI kur (macOS)
brew install azure-cli

# 2. Bir kez giriş yap (tarayıcı açılır)
az login

# 3. Python paketleri
pip install pyodbc pandas sqlalchemy openpyxl

# 4. Script'i çalıştır (token otomatik alınır)
python your_script.py
```

## İçindekiler

1. [Azure'a Giriş ve Temel Kavramlar](#1-azurea-giriş-ve-temel-kavramlar)
2. [Azure CLI Kurulumu ve Yapılandırma](#2-azure-cli-kurulumu-ve-yapılandırma)
3. [Azure Kimlik Doğrulama (az login ve Token)](#3-azure-kimlik-doğrulama-az-login-ve-token)
4. [Azure SQL Database Genel Bilgiler](#4-azure-sql-database-genel-bilgiler)
5. [Python ile Azure SQL Bağlantısı (pyodbc)](#5-python-ile-azure-sql-bağlantısı-pyodbc)
6. [SQLAlchemy ile Azure SQL Engine](#6-sqlalchemy-ile-azure-sql-engine)
7. [Azure SQL'e Veri Yazma (pandas to_sql)](#7-azure-sqle-veri-yazma-pandas-to_sql)
8. [Excel ve CSV'dan Azure SQL'e Veri Yükleme](#8-excel-ve-csvdan-azure-sqle-veri-yükleme)
9. [Azure SQL'den Veri Okuma](#9-azure-sqlden-veri-okuma)
10. [Azure SQL Sistem Görünümleri ve Metadata](#10-azure-sql-sistem-görünümleri-ve-metadata)
11. [Bağlantı Hataları ve Firewall](#11-bağlantı-hataları-ve-firewall)
12. [Güvenlik ve Best Practices](#12-güvenlik-ve-best-practices)
13. [Tam Örnek: Excel'den Azure SQL'e Pipeline](#13-tam-örnek-excelden-azure-sqle-pipeline)

---

## 1. Azure'a Giriş ve Temel Kavramlar

**Ne İşe Yarar:** Azure ekosistemindeki temel kavramları (abonelik, kaynak, portal) anlamanızı sağlar.  
**Ne Yapar:** Hesap yapısı, kaynak grupları ve Azure SQL gibi servislerin nerede durduğunu netleştirir.

### Abonelik (Subscription)
- Azure hizmetlerini kullandığınız ve faturalandırıldığınız sözleşme birimidir.
- Bir Azure hesabında birden fazla abonelik olabilir (örn. üretim, test).

### Kaynak Grubu (Resource Group)
- Azure kaynaklarını (VM, SQL veritabanı, depolama hesabı vb.) mantıksal olarak gruplar.
- Kaynaklar mutlaka bir kaynak grubuna aittir.

### Azure SQL Database
- Bulutta tam yönetilen bir SQL Server veritabanı hizmetidir.
- Bağlantı için **sunucu adı**, **veritabanı adı** ve **kimlik doğrulama** (parola veya Microsoft Entra / Azure AD token) gerekir.

### Sunucu Adı Formatı
Azure SQL için sunucu adı şu formattadır:
```text
tcp:<sunucu-adı>.database.windows.net,1433
```
Örnek: `tcp:myserver.database.windows.net,1433`

---

## 2. Azure CLI Kurulumu ve Yapılandırma

**Ne İşe Yarar:** Komut satırından Azure kaynaklarını yönetmenizi ve **token almanızı** sağlar. Python script'lerinde parola kullanmadan Azure SQL'e bağlanmak için sıklıkla kullanılır.  
**Ne Yapar:** `az` komutunu sisteme kurar; `az login` ile oturum açar, `az account get-access-token` ile belirli bir kaynak için erişim token'ı alır.

### macOS (Homebrew)
```bash
brew update && brew install azure-cli
```

### Windows (PowerShell – yönetici)
```powershell
winget install Microsoft.AzureCLI
# veya
Invoke-WebRequest -Uri https://aka.ms/installazurecliwindows -OutFile .\AzureCLI.msi
Start-Process msiexec.exe -Wait -ArgumentList '/I AzureCLI.msi'
```

### Linux (Debian/Ubuntu)
```bash
curl -sL https://aka.ms/InstallAzureCLIDeb | sudo bash
```

### Kurulum Doğrulama
```bash
az --version
```

### Varsayılan Aboneliği Ayarlama
Birden fazla aboneliğiniz varsa hangisinin kullanılacağını seçersiniz:
```bash
# Abonelikleri listele
az account list --output table

# Varsayılan aboneliği ayarla
az account set --subscription "Abonelik Adı veya ID"
```

---

## 3. Azure Kimlik Doğrulama (az login ve Token)

**Ne İşe Yarar:** Azure'a güvenli şekilde giriş yapmanızı ve Python'dan parola kullanmadan (ör. Azure SQL için) token ile bağlanmanızı sağlar.  
**Ne Yapar:** Tarayıcı veya cihaz kodu ile oturum açar; ardından belirli bir **resource** için erişim token'ı alınabilir.

### Tarayıcı ile Giriş (az login)
```bash
az login
```
- Varsayılan tarayıcı açılır; Microsoft hesabıyla giriş yaparsınız.
- Başarılı olunca terminalde abonelik bilgileri listelenir.

### Cihaz Kodu ile Giriş (headless ortam)
```bash
az login --use-device-code
```
- Terminalde bir URL ve kod gösterilir; tarayıcıda açıp kodu girerek giriş yaparsınız.

### Erişim Token'ı Alma (Azure SQL için)
Python ile Azure SQL'e **Microsoft Entra (Azure AD) token** ile bağlanmak için token'ı Azure CLI üzerinden almak yaygın bir yöntemdir:

```bash
az account get-access-token --resource https://database.windows.net --output tsv --query accessToken
```

| Parametre | Açıklama |
|-----------|----------|
| `--resource https://database.windows.net` | Azure SQL / SQL Database kaynağı için token istenir. |
| `--output tsv` | Çıktı düz metin (tab-separated) olur; script'te kullanmak kolaydır. |
| `--query accessToken` | Sadece `accessToken` alanı döner. |

**Ne İşe Yarar:** Bu token, ODBC/pyodbc bağlantısında parola yerine kullanılır; böylece parolayı kodda veya ortam değişkeninde tutmanız gerekmez (önce bir kez `az login` yapılmış olmalı).

### Token'ın Geçerlilik Süresi
- Token'lar genelde **bir saat** geçerlidir.
- Uzun süren script'lerde gerekirse yeniden `get-access-token` çağrılabilir veya hata durumunda tekrar token alınabilir.

---

## 4. Azure SQL Database Genel Bilgiler

**Ne İşe Yarar:** Azure SQL'e bağlanırken kullanacağınız bilgileri ve kimlik seçeneklerini netleştirir.  
**Ne Yapar:** Bağlantı dizesi bileşenlerini ve kimlik türlerini açıklar.

### Bağlantı İçin Gerekli Bilgiler
| Bilgi | Örnek | Açıklama |
|-------|--------|----------|
| Sunucu | `tcp:myserver.database.windows.net,1433` | Azure SQL sunucu adresi (port 1433). |
| Veritabanı | `mydb` | Hedef veritabanı adı. |
| Kimlik | Kullanıcı adı + parola **veya** Microsoft Entra token | Kimlik doğrulama yöntemi. |
| Şifreleme | `Encrypt=yes` | TLS ile şifreli bağlantı (önerilir). |

### Kimlik Doğrulama Türleri
1. **SQL Authentication:** Kullanıcı adı + parola (connection string'de).
2. **Microsoft Entra (Azure AD) Authentication:**  
   - Parola yerine **access token** kullanılır.  
   - Token, `az account get-access-token --resource https://database.windows.net` ile alınır.  
   - Python'da pyodbc ile `attrs_before={SQL_COPT_SS_ACCESS_TOKEN: token_struct}` şeklinde verilir (aşağıda detay).

### ODBC Driver
- **ODBC Driver 18 for SQL Server** kullanılması önerilir (TLS 1.2, Azure SQL ile uyumlu).
- Windows’ta [Microsoft ODBC Driver for SQL Server](https://docs.microsoft.com/en-us/sql/connect/odbc/download-odbc-driver-for-sql-server) indirilir.
- macOS: `brew install msodbcsql18` (veya ilgili Microsoft dokümantasyonu).

---

## 5. Python ile Azure SQL Bağlantısı (pyodbc)

**Ne İşe Yarar:** Python'dan Azure SQL'e doğrudan bağlanmanızı sağlar; token ile güvenli bağlantı kurar.  
**Ne Yapar:** Azure CLI'dan token alır, pyodbc connection string'i oluşturur ve token'ı bağlantıya ekleyerek `pyodbc.connect` çağırır.

### Gerekli Paketler
```bash
pip install pyodbc
```

### Sabitler ve Connection String
```python
import struct
import subprocess
import pyodbc

SERVER = "tcp:myserver.database.windows.net,1433"
DATABASE = "mydb"
DRIVER = "ODBC Driver 18 for SQL Server"
# SQL Server'da token ile kimlik doğrulama için kullanılan özel seçenek
SQL_COPT_SS_ACCESS_TOKEN = 1256
```

**Ne İşe Yarar:**  
- `SERVER`: Azure SQL sunucu adresi.  
- `DATABASE`: Bağlanılacak veritabanı.  
- `DRIVER`: Yüklü ODBC sürücüsü adı (18 önerilir).  
- `SQL_COPT_SS_ACCESS_TOKEN`: Token'ı bağlantıya vermek için pyodbc'de kullanılan sabit.

### Azure CLI ile Token Alma (Python)
```python
def get_azure_token():
    """Azure CLI ile token al; önce 'az login' yapılmış olmalı."""
    out = subprocess.run(
        [
            "az", "account", "get-access-token",
            "--resource", "https://database.windows.net",
            "--output", "tsv",
            "--query", "accessToken",
        ],
        capture_output=True,
        text=True,
        timeout=30,
    )
    if out.returncode != 0:
        raise RuntimeError(
            "Token alınamadı. Önce 'az login' yapın. " + (out.stderr or out.stdout or "")
        )
    return out.stdout.strip()
```

**Ne Yapar:**  
- `az account get-access-token` komutunu çalıştırır.  
- Çıktıda sadece token string'i döner.  
- Hata durumunda anlamlı bir mesajla `RuntimeError` fırlatır.

### Token'ı pyodbc Formatına Çevirme
SQL Server ODBC sürücüsü token'ı özel bir binary formatta bekler:

```python
token = get_azure_token()
# UTF-16 little-endian byte dizisi
exptoken = token.encode("utf-16-le")
# Önce 4 byte uzunluk (int), sonra token bytes
tokenstruct = struct.pack("=i", len(exptoken)) + exptoken
```

**Ne İşe Yarar:**  
- Token string'i, ODBC'nin beklediği formata çevirir.  
- `attrs_before` ile bu `tokenstruct` verilir.

### pyodbc ile Bağlantı Kurma
```python
def pyodbc_connect():
    """Azure CLI token ile bağlan (az login sonrası)."""
    token = get_azure_token()
    exptoken = token.encode("utf-16-le")
    tokenstruct = struct.pack("=i", len(exptoken)) + exptoken

    conn_str = (
        f"Driver={{{DRIVER}}};Server={SERVER};Database={DATABASE};"
        "Encrypt=yes;TrustServerCertificate=no;Connection Timeout=120;"
    )
    return pyodbc.connect(conn_str, attrs_before={SQL_COPT_SS_ACCESS_TOKEN: tokenstruct})
```

**Ne Yapar:**  
- Token alır, binary formata çevirir.  
- Connection string'de parola yok; şifreleme ve timeout ayarlı.  
- `attrs_before` ile token'ı sürücüye verir ve bağlantıyı açar.

### Bağlantıyı Test Etme
```python
conn = pyodbc_connect()
cursor = conn.cursor()
cursor.execute("SELECT 1 AS test")
print(cursor.fetchone())  # (1,)
conn.close()
```

---

## 6. SQLAlchemy ile Azure SQL Engine

**Ne İşe Yarar:** Pandas `to_sql` / `read_sql` gibi fonksiyonlar SQLAlchemy engine ister; bu bölüm Azure SQL için bu engine'i nasıl üreteceğinizi gösterir.  
**Ne Yapar:** Mevcut pyodbc bağlantı fonksiyonunu kullanarak `mssql+pyodbc` engine'i oluşturur.

### Gerekli Paketler
```bash
pip install sqlalchemy pyodbc pandas
```

### Engine Oluşturma (creator ile)
```python
from sqlalchemy import create_engine

def get_engine():
    """Azure SQL için SQLAlchemy engine (pandas to_sql ile uyumlu)."""
    return create_engine("mssql+pyodbc://", creator=pyodbc_connect)
```

**Açıklama:**  
- `mssql+pyodbc://`: SQL Server için pyodbc kullanılacağını belirtir.  
- `creator=pyodbc_connect`: Her bağlantı isteğinde `pyodbc_connect()` çağrılır; böylece her seferinde güncel token kullanılır.

### Engine ile Bağlantı ve Sorgu
```python
from sqlalchemy import text

engine = get_engine()
with engine.connect() as conn:
    conn.execute(text("SELECT 1"))
    db = conn.execute(text("SELECT DB_NAME()")).scalar()
    user = conn.execute(text("SELECT SUSER_SNAME()")).scalar()
    print(f"Veritabanı: {db}, Kullanıcı: {user}")
```

---

## 7. Azure SQL'e Veri Yazma (pandas to_sql)

**Ne İşe Yarar:** Pandas DataFrame'lerini doğrudan Azure SQL tablolarına yazmanızı sağlar.  
**Ne Yapar:** `to_sql` ile tablo oluşturur veya mevcut tabloya ekler; `chunksize` ve parametre limiti ile büyük verileri güvenli yazar.

### Temel Kullanım
```python
import pandas as pd

engine = get_engine()
df = pd.DataFrame({"id": [1, 2, 3], "ad": ["A", "B", "C"]})

# Tablo yoksa oluşturur, varsa replace ile siler ve yeniden yazar
df.to_sql(
    "tablo_adi",
    engine,
    schema="dbo",
    if_exists="replace",
    index=False,
)
```

| Parametre | Açıklama |
|-----------|----------|
| `schema="dbo"` | Tablonun şeması (varsayılan `dbo`). |
| `if_exists="replace"` | Tabloyu drop edip yeniden oluşturur. |
| `if_exists="append"` | Mevcut tabloya satır ekler (tablo yapısı aynı olmalı). |
| `if_exists="fail"` | Tablo varsa hata verir. |
| `index=False` | DataFrame index'ini tabloya sütun olarak yazmaz. |

### 2100 Parametre Limiti (Önemli)
SQL Server tek bir sorguda en fazla **2100 parametre** kabul eder. `to_sql(..., method="multi")` kullanıldığında her satır için sütun sayısı kadar parametre gider:

- **Satır × Sütun ≤ 2100** olmalı (her batch için).  
- Örnek: 50 sütun varsa, batch başına en fazla `2100 // 50 = 42` satır güvenli olur.

**Chunksize Hesaplama:**
```python
n_cols = len(df.columns)
sql_chunksize = max(1, min(500, 2100 // n_cols))
df.to_sql(
    "tablo_adi",
    engine,
    schema="dbo",
    if_exists="replace",
    index=False,
    method="multi",
    chunksize=sql_chunksize,
)
```

**Ne Yapar:**  
- Çok sütunlu tablolarda tek INSERT'ta 2100'den fazla parametre gönderilmesini engeller.  
- `method="multi"` ile çoklu satır tek INSERT ile yazılır; `chunksize` bu INSERT başına satır sayısını sınırlar.

### Parça Parça Append (Çok Büyük DataFrame)
Hem timeout hem parametre limiti için veriyi parçalara bölerek yazmak iyi bir pratiktir:

```python
CHUNK = 1500  # Her seferinde 1500 satır
total = len(birlesik_df)
n_cols = len(birlesik_df.columns)
sql_chunksize = max(1, min(500, 2100 // n_cols))

for i in range(0, total, CHUNK):
    chunk = birlesik_df.iloc[i : i + CHUNK]
    if_exists = "replace" if i == 0 else "append"
    chunk.to_sql(
        "tablo_adi",
        engine,
        schema="dbo",
        if_exists=if_exists,
        index=False,
        method="multi",
        chunksize=sql_chunksize,
    )
```

**Ne Yapar:**  
- İlk parçada tabloyu `replace` ile oluşturur.  
- Sonraki parçalarda `append` ile ekler.  
- Her parça içinde INSERT'lar yine `sql_chunksize` ile 2100 parametre sınırına uyar.

---

## 8. Excel ve CSV'dan Azure SQL'e Veri Yükleme

**Ne İşe Yarar:** Yerel Excel veya CSV dosyalarını okuyup Azure SQL tablolarına yüklemenizi sağlar.  
**Ne Yapar:** Pandas ile dosyayı okur, gerekirse sütun adlarını/veri tiplerini düzenler ve `to_sql` ile Azure SQL'e yazar.

### Excel Okuma (pandas)
```bash
pip install openpyxl  # .xlsx için
```

```python
import pandas as pd
from pathlib import Path

# Tek sayfa, varsayılan ilk satır header
df = pd.read_excel("dosya.xlsx", sheet_name=0)

# Belirli sayfa, header 2. satırda
df = pd.read_excel("dosya.xlsx", sheet_name="SayfaAdi", header=1)

# İlk satır boşsa header'ı 1. satırdan al
peek = pd.read_excel(path, sheet_name=0, header=None, nrows=1)
header_row = 1 if peek.iloc[0].isna().all() else 0
df = pd.read_excel(path, sheet_name=0, header=header_row)
```

### CSV Okuma
```python
df = pd.read_csv("dosya.csv", encoding="utf-8", sep=";")
# veya
df = pd.read_csv("dosya.csv", encoding="utf-8")  # varsayılan virgül
```

### Tek Dosyayı Tabloya Yazma (Özet Fonksiyon)
```python
def excel_to_table(excel_path, table_name, engine, sheet_name=0):
    """Tek Excel dosyasını okuyup Azure SQL tablosuna yazar (2100 parametre limiti)."""
    df = pd.read_excel(excel_path, sheet_name=sheet_name)
    n_cols = len(df.columns)
    sql_chunk = max(1, min(500, 2100 // n_cols))
    df.to_sql(
        table_name,
        engine,
        schema="dbo",
        if_exists="replace",
        index=False,
        method="multi",
        chunksize=sql_chunk,
    )
    return len(df)
```

### Sütun Adı Normalizasyonu (SQL ile Uyum)
SQL Server sütun adları boşluk ve özel karakterlerde sorun çıkarabilir; Türkçe karakterler farklı ortamlarda tutarsız olabilir. Örnek normalizasyon:

- Küçük harfe çevir.
- Boşlukları alt çizgi yap.
- Türkçe karakterleri ASCII karşılıklarına çevir (ı→i, ğ→g, ü→u, ş→s, ö→o, ç→c).

```python
import re
import unicodedata

def normalize_column_name(raw):
    if raw is None or (isinstance(raw, float) and pd.isna(raw)):
        return ""
    s = str(raw).strip().lower()
    # Türkçe -> ASCII (örnek)
    for tr, ascii_c in [("ı", "i"), ("ğ", "g"), ("ü", "u"), ("ş", "s"), ("ö", "o"), ("ç", "c")]:
        s = s.replace(tr, ascii_c)
    s = re.sub(r"\s+", "_", s)
    s = re.sub(r"[^\w_]", "_", s)
    s = re.sub(r"_+", "_", s).strip("_")
    return s

df.columns = [normalize_column_name(c) for c in df.columns]
```

### Aynı İsimli Sütunları Birleştirme (SQL Server)
SQL Server sütun adlarında büyük/küçük harf ayrımı yoktur; "Mevcut Prt" ile "Mevcut prt" aynı sayılır. Pandas'ta ayrı sütunlar olsa bile tekrar oluşmaması için aynı isimli (case-insensitive) sütunları tek sütunda birleştirebilirsiniz:

```python
def dedupe_columns_for_sql(df):
    df = df.copy()
    cols = list(df.columns)
    seen_lower = {}
    to_drop = []
    for c in cols:
        key = (str(c) or "").strip().lower()
        if not key:
            continue
        if key in seen_lower:
            first_col = seen_lower[key]
            df[first_col] = df[first_col].fillna(df[c])
            to_drop.append(c)
        else:
            seen_lower[key] = c
    if to_drop:
        df = df.drop(columns=to_drop)
    return df
```

---

## 9. Azure SQL'den Veri Okuma

**Ne İşe Yarar:** Azure SQL tablolarından veriyi Python'a (DataFrame veya satır satır) okumanızı sağlar.  
**Ne Yapar:** `read_sql` ile tek seferde tablo/sorgu sonucunu DataFrame yapar; `engine.connect()` ve `text()` ile ham SQL de çalıştırılabilir.

### read_sql ile Tablo veya Sorgu
```python
import pandas as pd
from sqlalchemy import text

engine = get_engine()

# Tüm tablo
df = pd.read_sql("SELECT * FROM dbo.tablo_adi", engine)

# Parametreli sorgu (SQL injection'dan kaçınmak için)
df = pd.read_sql(
    text("SELECT * FROM dbo.tablo_adi WHERE id = :id"),
    engine,
    params={"id": 1},
)

# Sadece belirli sütunlar
df = pd.read_sql(
    "SELECT id, ad FROM dbo.tablo_adi WHERE id > 0",
    engine,
)
```

### SQLAlchemy text() ile Çalıştırma
```python
with engine.connect() as conn:
    result = conn.execute(text("SELECT 1 AS test"))
    row = result.fetchone()
    print(row)  # (1,)

    # Skaler değer
    db_name = conn.execute(text("SELECT DB_NAME()")).scalar()
    user_name = conn.execute(text("SELECT SUSER_SNAME()")).scalar()
```

### pyodbc Cursor ile Okuma
```python
conn = pyodbc_connect()
cursor = conn.cursor()
cursor.execute("SELECT id, ad FROM dbo.tablo_adi")
for row in cursor:
    print(row)
conn.close()
```

---

## 10. Azure SQL Sistem Görünümleri ve Metadata

**Ne İşe Yarar:** Veritabanı adı, oturum açan kullanıcı, katman (tier) ve kaynak kullanımı gibi bilgileri sorgulamanızı sağlar.  
**Ne Yapar:** `sys.database_service_objectives` ve `sys.dm_db_resource_stats` gibi sistem görünümlerinden bilgi çeker.

### Veritabanı ve Oturum Bilgisi
```python
with engine.connect() as conn:
    db = conn.execute(text("SELECT DB_NAME()")).scalar()
    user = conn.execute(text("SELECT SUSER_SNAME()")).scalar()
    print(f"Veritabanı: {db}, Kullanıcı: {user}")
```

### Servis Katmanı (Tier / Edition)
```sql
SELECT service_objective, edition
FROM sys.database_service_objectives;
```

```python
row = conn.execute(text("""
    SELECT service_objective, edition
    FROM sys.database_service_objectives
""")).fetchone()
if row:
    print(f"Katman: {row[0]} ({row[1]})")
```

### Son Kaynak Kullanımı (CPU, Log, Data IO)
```sql
SELECT TOP 1
    avg_cpu_percent,
    avg_log_write_percent,
    avg_data_io_percent
FROM sys.dm_db_resource_stats
ORDER BY end_time DESC;
```

```python
row = conn.execute(text("""
    SELECT TOP 1 avg_cpu_percent, avg_log_write_percent, avg_data_io_percent
    FROM sys.dm_db_resource_stats ORDER BY end_time DESC
""")).fetchone()
if row:
    print(f"CPU %{row[0]:.0f} | Log %{row[1]:.0f} | Data IO %{row[2]:.0f}")
```

---

## 11. Bağlantı Hataları ve Firewall

**Ne İşe Yarar:** Sık görülen Azure SQL bağlantı hatalarını tanımanızı ve firewall ayarını anlamanızı sağlar.  
**Ne Yapar:** Hata mesajlarına göre ne yapılacağını ve Azure portal üzerinden firewall kuralı eklemeyi özetler.

### Yaygın Hatalar
| Hata / Durum | Olası Neden | Çözüm |
|--------------|-------------|--------|
| Token alınamadı | `az login` yapılmamış veya oturum süresi dolmuş | Terminalde `az login` çalıştırın. |
| Login failed for user | Yanlış kullanıcı/parola veya token süresi dolmuş | Token kullanıyorsanız yeniden token alın; SQL auth kullanıyorsanız kullanıcı/parolayı kontrol edin. |
| Cannot open server / firewall | İstemci IP'si Azure SQL firewall'da izinli değil | Azure Portal → SQL sunucusu → Ağ/Firewall → istemci IP'sini ekleyin. |
| Connection timeout | Ağ gecikmesi, çok büyük veri veya firewall | Connection string'de `Connection Timeout=120` artırın; firewall ve ağı kontrol edin. |
| 2100 parameter limit | Tek INSERT'ta çok fazla parametre | `to_sql(..., method="multi", chunksize=...)` ile chunksize'ı 2100/sütun sayısını geçmeyecek şekilde düşürün. |

### Azure Portal'da Firewall Kuralı
1. Azure Portal → SQL sunucunuzu seçin.  
2. **Ayarlar** → **Ağ** (veya **Networking**).  
3. **İstemci IP'sini Ekle** ile mevcut IP'nizi ekleyin veya belirli bir IP aralığı girin.  
4. Kaydedin; birkaç saniye içinde bağlantı denenebilir.

### ODBC Sürücüsü Kontrolü
```python
import pyodbc
print(pyodbc.drivers())
# Listede "ODBC Driver 18 for SQL Server" olmalı
```

---

## 12. Güvenlik ve Best Practices

**Ne İşe Yarar:** Bağlantı bilgilerini ve token kullanımını güvenli tutmanızı sağlar.  
**Ne Yapar:** Parola/token'ı kodda sabit yazmama, ortam değişkeni ve firewall kullanma gibi pratikleri vurgular.

### Bağlantı Bilgilerini Ortam Değişkeninde Tutma
```python
import os

SERVER = os.environ.get("AZURE_SQL_SERVER", "tcp:myserver.database.windows.net,1433")
DATABASE = os.environ.get("AZURE_SQL_DATABASE", "mydb")
```

### Parola ile Bağlantı (Token Yerine)
Parola kullanacaksanız connection string'de **asla** parolayı commit etmeyin; ortam değişkeninden alın:

```python
import os
import pyodbc

conn_str = (
    f"Driver={{{DRIVER}}};Server={SERVER};Database={DATABASE};"
    f"Uid={os.environ['AZURE_SQL_USER']};"
    f"Pwd={os.environ['AZURE_SQL_PASSWORD']};"
    "Encrypt=yes;TrustServerCertificate=no;Connection Timeout=120;"
)
conn = pyodbc.connect(conn_str)
```

### Özet Best Practices
- Mümkünse **Microsoft Entra (token)** kullanın; parolayı script içinde tutmayın.  
- **ODBC Driver 18** ve `Encrypt=yes` kullanın.  
- Büyük veri yazarken **chunksize** ve **2100 parametre** limitini dikkate alın.  
- Sütun adlarını SQL uyumlu ve tekrarsız (case-insensitive dedupe) yapın.  
- Hata mesajlarını loglayın; firewall ve timeout hatalarını ayrı ele alın.

---

## 13. Tam Örnek: Excel'den Azure SQL'e Pipeline

**Ne İşe Yarar:** Birden fazla Excel dosyasını okuyup sütun normalizasyonu ve dönem soneki ekleyerek tek bir Azure SQL tablosunda birleştirmenizi örnekler.  
**Ne Yapar:** Klasördeki Excel dosyalarını tarar, her birini okuyup temizler, birleştirir ve parça parça Azure SQL'e yazar; isteğe bağlı olarak tek bir Excel dosyasını ikinci bir tabloya yükler.

Aşağıdaki örnek, Excel dosyalarını Azure SQL'e yükleyen genel bir pipeline akışını sadeleştirilmiş biçimde yansıtır.

```python
"""
Örnek: Excel dosyalarını Azure SQL'e yükleyen pipeline.
Kullanım: az login → pip install pyodbc pandas sqlalchemy openpyxl tqdm → python script
"""
import struct
import subprocess
from pathlib import Path
import pandas as pd
from sqlalchemy import create_engine, text
from tqdm import tqdm

# --- Yapılandırma ---
SERVER = "tcp:myserver.database.windows.net,1433"
DATABASE = "mydb"
DRIVER = "ODBC Driver 18 for SQL Server"
SQL_COPT_SS_ACCESS_TOKEN = 1256

PROJECT_DIR = Path(__file__).parent
DATA_DIR = PROJECT_DIR / "veri_klasoru"      # Excel dosyalarının bulunduğu klasör
EXCEL_PATTERN = "*.xlsx"                     # Örn. "aylik_*.xlsx" veya "*.xlsx"
TABLE_MAIN = "birlesik_tablo_adi"            # Tüm Excel'lerin yazılacağı tablo
TABLE_EXTRA = "ek_tablo_adi"                 # İsteğe bağlı tek dosya için tablo

def get_azure_token():
    out = subprocess.run(
        ["az", "account", "get-access-token", "--resource", "https://database.windows.net",
         "--output", "tsv", "--query", "accessToken"],
        capture_output=True, text=True, timeout=30,
    )
    if out.returncode != 0:
        raise RuntimeError("Token alınamadı. Önce 'az login' yapın. " + (out.stderr or out.stdout or ""))
    return out.stdout.strip()

def pyodbc_connect():
    token = get_azure_token()
    exptoken = token.encode("utf-16-le")
    tokenstruct = struct.pack("=i", len(exptoken)) + exptoken
    conn_str = (
        f"Driver={{{DRIVER}}};Server={SERVER};Database={DATABASE};"
        "Encrypt=yes;TrustServerCertificate=no;Connection Timeout=120;"
    )
    return pyodbc.connect(conn_str, attrs_before={SQL_COPT_SS_ACCESS_TOKEN: tokenstruct})

def get_engine():
    return create_engine("mssql+pyodbc://", creator=pyodbc_connect)

# Sütun normalizasyonu (özet; tam hali yukarıdaki gibi normalize_column_name + dedupe)
def clean_columns(df):
    df = df.copy()
    df.columns = [str(c).strip().lower().replace(" ", "_") for c in df.columns]
    return df

def main():
    if not DATA_DIR.exists():
        print(f"Hata: '{DATA_DIR}' bulunamadı.")
        return

    excel_files = sorted(DATA_DIR.glob(EXCEL_PATTERN))
    excel_files = [f for f in excel_files if not f.name.startswith("~$")]
    if not excel_files:
        print("Excel dosyası yok.")
        return

    print("Azure SQL'e bağlanılıyor...")
    try:
        engine = get_engine()
        with engine.connect() as conn:
            conn.execute(text("SELECT 1"))
            db = conn.execute(text("SELECT DB_NAME()")).scalar()
            user = conn.execute(text("SELECT SUSER_SNAME()")).scalar()
            print(f"  Veritabanı: {db}, Kullanıcı: {user}")
    except Exception as e:
        print(f"Bağlantı hatası: {e}")
        return

    # Tüm Excel'leri birleştir
    frames = []
    for path in tqdm(excel_files, desc="Excel okunuyor"):
        df = pd.read_excel(path, sheet_name=0)
        df = clean_columns(df)
        # Örnek: dosya adından dönem bilgisi ekle (örn. path.stem → "01.YYYY" veya "Ay_YYYY")
        donem = path.stem
        df.insert(0, "donem", donem)
        frames.append(df)

    birlesik = pd.concat(frames, axis=0, ignore_index=True)
    total = len(birlesik)
    CHUNK = 1500
    n_cols = len(birlesik.columns)
    sql_chunksize = max(1, min(500, 2100 // n_cols))

    print(f"Toplam {total} satır, {n_cols} sütun. Azure'a yazılıyor...")
    for i in tqdm(range(0, total, CHUNK), desc="Yazılıyor"):
        chunk = birlesik.iloc[i : i + CHUNK]
        if_exists = "replace" if i == 0 else "append"
        chunk.to_sql(
            TABLE_MAIN,
            engine,
            schema="dbo",
            if_exists=if_exists,
            index=False,
            method="multi",
            chunksize=sql_chunksize,
        )
    print(f"Tamamlandı: {TABLE_MAIN} -> {total} satır.")

    # İsteğe bağlı: Tek bir Excel dosyasını ayrı tabloya yükle
    ek_excel_path = PROJECT_DIR / "ozet.xlsx"   # veya ek_veri.xlsx
    if ek_excel_path.exists():
        df_ek = pd.read_excel(ek_excel_path)
        df_ek.to_sql(TABLE_EXTRA, engine, schema="dbo", if_exists="replace", index=False, method="multi", chunksize=min(500, 2100 // max(len(df_ek.columns), 1)))
        print(f"Tamamlandı: {TABLE_EXTRA} -> {len(df_ek)} satır.")

if __name__ == "__main__":
    main()
```

Bu örnekte:
- **Azure CLI token** ile güvenli bağlantı kurulur.  
- **Birden fazla Excel** tek tabloda birleştirilir; **donem** sütunu dosya adından eklenir.  
- **2100 parametre** ve **chunk** kullanılarak büyük veri güvenle yazılır.  
- İsteğe bağlı **ek bir Excel** dosyası ayrı bir tabloya yazılır.

---

Bu Azure Cheatsheet, Python ile Azure SQL kullanımını sıfırdan (Azure CLI, token, pyodbc, SQLAlchemy) ileri seviyeye (Excel/CSV yükleme, to_sql limitleri, sistem görünümleri, tam pipeline) kadar tek dokümanda toplar. Tüm ana konular (token alma, pyodbc + token, SQLAlchemy engine, to_sql chunksize/2100, Excel okuma, Azure'dan okuma, sys view'lar) burada açıklanmış ve örneklenmiştir.
