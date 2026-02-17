# PowerBI Cheatsheet - Kapsamlı PowerBI Referans Rehberi

Bu rehber PowerBI'nin tüm temel ve ileri seviye özelliklerini kapsar. Her komutun ve özelliğin Türkçe açıklaması bulunmaktadır.

**Not:** Bu rehber PowerBI Desktop, PowerBI Service ve PowerBI Mobile uygulamalarını kapsar.

## İçindekiler

1. [PowerBI Temelleri](#1-powerbi-temelleri)
2. [Veri Yükleme ve Bağlantılar](#2-veri-yükleme-ve-bağlantılar)
3. [Veri Modelleme](#3-veri-modelleme)
4. [DAX Formülleri](#4-dax-formülleri)
5. [Görselleştirme](#5-görselleştirme)
6. [Raporlama](#6-raporlama)
7. [PowerBI Service](#7-powerbi-service)
8. [Paylaşım ve Güvenlik](#8-paylaşım-ve-güvenlik)
9. [Performans Optimizasyonu](#9-performans-optimizasyonu)
10. [PowerBI Mobile](#10-powerbi-mobile)
11. [PowerBI Premium](#11-powerbi-premium)
12. [PowerBI Embedded](#12-powerbi-embedded)
13. [PowerBI REST API](#13-powerbi-rest-api)
14. [PowerBI Gateway](#14-powerbi-gateway)
15. [PowerBI Template Apps](#15-powerbi-template-apps)
16. [PowerBI Best Practices](#16-powerbi-best-practices)
17. [PowerBI Troubleshooting](#17-powerbi-troubleshooting)
18. [PowerBI Klavye Kısayolları](#18-powerbi-klavye-kısayolları)

---

## 1. PowerBI Temelleri

### PowerBI Nedir?
**Açıklama:** Microsoft'un iş zekası ve veri görselleştirme platformudur. Verileri analiz etmek, raporlar oluşturmak ve içgörüler paylaşmak için kullanılır.

### PowerBI Bileşenleri

#### PowerBI Desktop
**Açıklama:** Ücretsiz masaüstü uygulaması. Raporlar ve veri modelleri oluşturmak için kullanılır.

#### PowerBI Service
**Açıklama:** Bulut tabanlı hizmet. Raporları paylaşmak, dashboard'lar oluşturmak ve işbirliği yapmak için kullanılır.

#### PowerBI Mobile
**Açıklama:** Mobil cihazlar için uygulama. Raporları ve dashboard'ları mobil cihazlarda görüntülemek için kullanılır.

### PowerBI Lisans Türleri

#### PowerBI Free
**Açıklama:** Ücretsiz lisans. Temel özellikler ve sınırlı paylaşım imkanı.

#### PowerBI Pro
**Açıklama:** Aylık ücretli lisans. Tam özellikler ve sınırsız paylaşım.

#### PowerBI Premium
**Açıklama:** Kurumsal lisans. Gelişmiş özellikler ve büyük veri kapasitesi.

---

## 2. Veri Yükleme ve Bağlantılar

### Veri Kaynakları

#### Excel Dosyaları
**Açıklama:** Excel dosyalarından veri yükleme

**Adımlar:**
1. `Giriş` > `Veri Al` > `Excel`
2. Dosyayı seç
3. Tabloları seç
4. `Yükle` veya `Düzenle`

#### SQL Server
**Açıklama:** SQL Server veritabanından veri yükleme

**Bağlantı:**
```
Server: sunucu_adi
Database: veritabani_adi
Authentication: Windows/SQL Server
```

#### Web Kaynakları
**Açıklama:** Web sayfalarından ve API'lerden veri yükleme

**Kullanım:**
1. `Giriş` > `Veri Al` > `Web`
2. URL'yi gir
3. Veri kaynağını seç

#### SharePoint
**Açıklama:** SharePoint listelerinden veri yükleme

**Bağlantı:**
```
Site URL: https://sirket.sharepoint.com/sites/site_adi
List Name: liste_adi
```

### Veri Yükleme Seçenekleri

#### DirectQuery
**Açıklama:** Veriyi doğrudan kaynaktan çeker. Gerçek zamanlı veri.

**Avantajları:**
- Güncel veri
- Küçük model boyutu
- Gerçek zamanlı analiz

**Dezavantajları:**
- Yavaş performans
- Sınırlı DAX fonksiyonları

#### Import
**Açıklama:** Veriyi PowerBI modeline yükler. Hızlı analiz.

**Avantajları:**
- Hızlı performans
- Tüm DAX fonksiyonları
- Offline çalışma

**Dezavantajları:**
- Büyük model boyutu
- Veri güncelleme gerekli

#### Live Connection
**Açıklama:** Analysis Services'e canlı bağlantı.

**Kullanım:**
1. `Giriş` > `Veri Al` > `Analysis Services`
2. Sunucu bilgilerini gir
3. Modeli seç

### Veri Dönüştürme

#### Power Query Editor
**Açıklama:** Veri temizleme ve dönüştürme aracı

**Temel İşlemler:**
- Veri tiplerini değiştirme
- Sütun ekleme/silme
- Filtreleme
- Birleştirme

#### Veri Temizleme
**Açıklama:** Veri kalitesini artırma işlemleri

**Yaygın İşlemler:**
- Boş değerleri kaldırma
- Yinelenen satırları kaldırma
- Veri tiplerini düzeltme
- Metin temizleme

---

## 3. Veri Modelleme

### Tablo İlişkileri

#### One-to-Many (1:N)
**Açıklama:** Bir tablodaki bir kayıt, diğer tablodaki birden fazla kayıtla ilişkilidir.

**Örnek:** Müşteri → Siparişler

#### Many-to-One (N:1)
**Açıklama:** Bir tablodaki birden fazla kayıt, diğer tablodaki bir kayıtla ilişkilidir.

**Örnek:** Siparişler → Müşteri

#### Many-to-Many (N:N)
**Açıklama:** İki tablo arasında çoktan çoğa ilişki.

**Kullanım:** Bridge table ile çözülür.

### İlişki Türleri

#### Active Relationship
**Açıklama:** Varsayılan olarak kullanılan ilişki.

**Özellikler:**
- Tek aktif ilişki
- Otomatik filtreleme
- Varsayılan davranış

#### Inactive Relationship
**Açıklama:** Manuel olarak kullanılan ilişki.

**Kullanım:**
```dax
CALCULATE(
    [Measure],
    USERELATIONSHIP(Table1[Column], Table2[Column])
)
```

### Hesaplanmış Sütunlar

#### Oluşturma
**Açıklama:** Mevcut sütunlardan yeni sütun oluşturma

**Kullanım:**
1. Tabloyu seç
2. `Modelleme` > `Yeni Sütun`
3. DAX formülü yaz

**Örnek:**
```dax
FullName = [FirstName] & " " & [LastName]
```

### Hesaplanmış Tablolar

#### Oluşturma
**Açıklama:** Mevcut tablolardan yeni tablo oluşturma

**Kullanım:**
1. `Modelleme` > `Yeni Tablo`
2. DAX formülü yaz

**Örnek:**
```dax
SalesSummary = 
SUMMARIZE(
    Sales,
    Sales[Product],
    "TotalSales", SUM(Sales[Amount])
)
```

---

## 4. DAX Formülleri

### DAX Nedir?
**Açıklama:** Data Analysis Expressions - PowerBI'da kullanılan formül dili.

### Temel DAX Fonksiyonları

#### SUM
**Açıklama:** Sayısal değerleri toplar

```dax
TotalSales = SUM(Sales[Amount])
```

#### AVERAGE
**Açıklama:** Sayısal değerlerin ortalamasını hesaplar

```dax
AvgSales = AVERAGE(Sales[Amount])
```

#### COUNT
**Açıklama:** Satır sayısını sayar

```dax
OrderCount = COUNT(Sales[OrderID])
```

#### DISTINCTCOUNT
**Açıklama:** Benzersiz değer sayısını sayar

```dax
UniqueCustomers = DISTINCTCOUNT(Sales[CustomerID])
```

### Filtreleme Fonksiyonları

#### FILTER
**Açıklama:** Tabloyu belirtilen koşula göre filtreler

```dax
HighValueSales = 
SUMX(
    FILTER(Sales, Sales[Amount] > 1000),
    Sales[Amount]
)
```

#### CALCULATE
**Açıklama:** Belirtilen filtrelerle hesaplama yapar

```dax
SalesThisYear = 
CALCULATE(
    SUM(Sales[Amount]),
    YEAR(Sales[Date]) = YEAR(TODAY())
)
```

#### ALL
**Açıklama:** Tüm filtreleri kaldırır

```dax
TotalSalesAll = 
CALCULATE(
    SUM(Sales[Amount]),
    ALL(Sales)
)
```

### Zaman Fonksiyonları

#### TODAY
**Açıklama:** Bugünün tarihini döndürür

```dax
CurrentDate = TODAY()
```

#### NOW
**Açıklama:** Şu anki tarih ve saati döndürür

```dax
CurrentDateTime = NOW()
```

#### DATE
**Açıklama:** Belirtilen tarihi oluşturur

```dax
StartDate = DATE(2024, 1, 1)
```

#### YEAR, MONTH, DAY
**Açıklama:** Tarihten yıl, ay, gün çıkarır

```dax
SalesYear = YEAR(Sales[Date])
SalesMonth = MONTH(Sales[Date])
SalesDay = DAY(Sales[Date])
```

### Metin Fonksiyonları

#### CONCATENATE
**Açıklama:** Metinleri birleştirir

```dax
FullName = CONCATENATE([FirstName], " ", [LastName])
```

#### LEFT, RIGHT, MID
**Açıklama:** Metnin belirli kısmını alır

```dax
FirstThree = LEFT([ProductCode], 3)
LastTwo = RIGHT([ProductCode], 2)
MiddlePart = MID([ProductCode], 2, 3)
```

#### LEN
**Açıklama:** Metin uzunluğunu döndürür

```dax
NameLength = LEN([ProductName])
```

### Mantık Fonksiyonları

#### IF
**Açıklama:** Koşullu hesaplama yapar

```dax
SalesCategory = 
IF(
    [TotalSales] > 10000,
    "High",
    "Low"
)
```

#### SWITCH
**Açıklama:** Çoklu koşul kontrolü yapar

```dax
RegionName = 
SWITCH(
    [RegionCode],
    "TR", "Türkiye",
    "US", "Amerika",
    "EU", "Avrupa",
    "Diğer"
)
```

#### AND, OR, NOT
**Açıklama:** Mantıksal operatörler

```dax
HighValueCustomer = 
AND(
    [TotalSales] > 10000,
    [OrderCount] > 5
)
```

### İstatistik Fonksiyonları

#### MIN, MAX
**Açıklama:** Minimum ve maksimum değerleri bulur

```dax
MinSales = MIN(Sales[Amount])
MaxSales = MAX(Sales[Amount])
```

#### MEDIAN
**Açıklama:** Medyan değeri hesaplar

```dax
MedianSales = MEDIAN(Sales[Amount])
```

#### STDEV
**Açıklama:** Standart sapma hesaplar

```dax
SalesStdDev = STDEV(Sales[Amount])
```

### İleri Seviye DAX

#### RANKX
**Açıklama:** Değerleri sıralar

```dax
SalesRank = 
RANKX(
    ALL(Sales[Product]),
    [TotalSales]
)
```

#### TOPN
**Açıklama:** En iyi N kaydı döndürür

```dax
Top5Products = 
TOPN(
    5,
    VALUES(Sales[Product]),
    [TotalSales]
)
```

#### SAMEPERIODLASTYEAR
**Açıklama:** Geçen yılın aynı dönemini döndürür

```dax
SalesLastYear = 
CALCULATE(
    [TotalSales],
    SAMEPERIODLASTYEAR(Sales[Date])
)
```

---

## 5. Görselleştirme

### Görsel Türleri

#### Sütun Grafikleri
**Açıklama:** Kategorik verileri karşılaştırmak için kullanılır

**Kullanım Alanları:**
- Satış karşılaştırmaları
- Kategori analizleri
- Zaman serisi analizleri

#### Çizgi Grafikleri
**Açıklama:** Zaman içindeki değişimleri göstermek için kullanılır

**Kullanım Alanları:**
- Trend analizleri
- Performans takibi
- Zaman serisi verileri

#### Pasta Grafikleri
**Açıklama:** Bütünün parçalarını göstermek için kullanılır

**Kullanım Alanları:**
- Pazar payı analizleri
- Bütçe dağılımları
- Kategori dağılımları

#### Dağılım Grafikleri
**Açıklama:** İki değişken arasındaki ilişkiyi göstermek için kullanılır

**Kullanım Alanları:**
- Korelasyon analizleri
- Regresyon analizleri
- İlişki analizleri

### Görsel Özelleştirme

#### Renkler
**Açıklama:** Görsellerin renklerini özelleştirme

**Seçenekler:**
- Tema renkleri
- Özel renkler
- Koşullu renklendirme

#### Etiketler
**Açıklama:** Görsellerdeki veri etiketlerini özelleştirme

**Seçenekler:**
- Etiket göster/gizle
- Etiket konumu
- Etiket formatı

#### Eksenler
**Açıklama:** Grafik eksenlerini özelleştirme

**Seçenekler:**
- Eksen başlıkları
- Eksen aralıkları
- Eksen formatı

### Etkileşimli Özellikler

#### Cross-Filtering
**Açıklama:** Bir görseldeki seçim diğer görselleri etkiler

**Ayarlar:**
1. Görseli seç
2. `Görselleştirme` > `Etkileşimler`
3. Filtreleme seçeneklerini ayarla

#### Drill-Through
**Açıklama:** Detay sayfasına geçiş

**Kullanım:**
1. Detay sayfası oluştur
2. `Görselleştirme` > `Drill-through`
3. Filtreleri ayarla

#### Bookmarks
**Açıklama:** Belirli görünümleri kaydetme

**Kullanım:**
1. Görünümü ayarla
2. `Görselleştirme` > `Bookmark`
3. Bookmark oluştur

---

## 6. Raporlama

### Rapor Oluşturma

#### Yeni Rapor
**Açıklama:** Boş rapordan başlama

**Adımlar:**
1. `Giriş` > `Yeni Rapor`
2. Sayfa ekle
3. Görselleri ekle

#### Rapor Düzenleme
**Açıklama:** Mevcut raporu düzenleme

**Özellikler:**
- Sayfa ekleme/silme
- Görsel ekleme/düzenleme
- Tema uygulama

### Sayfa Düzenleme

#### Sayfa Boyutları
**Açıklama:** Rapor sayfasının boyutunu ayarlama

**Seçenekler:**
- 16:9 (Varsayılan)
- 4:3
- Özel boyut

#### Sayfa Arka Planı
**Açıklama:** Sayfa arka planını özelleştirme

**Seçenekler:**
- Renk
- Resim
- Şeffaflık

### Rapor Navigasyonu

#### Butonlar
**Açıklama:** Sayfalar arası geçiş için buton ekleme

**Kullanım:**
1. `Giriş` > `Buton`
2. Buton türünü seç
3. Hedef sayfayı belirle

#### Görsel Başlıkları
**Açıklama:** Görsellere başlık ekleme

**Özellikler:**
- Başlık metni
- Başlık konumu
- Başlık formatı

---

## 7. PowerBI Service

### Workspace Yönetimi

#### Workspace Oluşturma
**Açıklama:** Yeni çalışma alanı oluşturma

**Adımlar:**
1. PowerBI Service'e git
2. `Çalışma Alanları` > `Çalışma Alanı Oluştur`
3. Ayarları yapılandır

#### Workspace Ayarları
**Açıklama:** Çalışma alanı ayarlarını düzenleme

**Seçenekler:**
- Üye yönetimi
- İzin ayarları
- Gelişmiş ayarlar

### Dashboard Oluşturma

#### Dashboard Oluşturma
**Açıklama:** Raporlardan dashboard oluşturma

**Adımlar:**
1. Raporu aç
2. `Pin` > `Pin to dashboard`
3. Dashboard seç veya oluştur

#### Dashboard Düzenleme
**Açıklama:** Dashboard'u özelleştirme

**Özellikler:**
- Tile boyutlandırma
- Tile konumlandırma
- Dashboard teması

### Veri Yenileme

#### Otomatik Yenileme
**Açıklama:** Veriyi otomatik olarak yenileme

**Ayarlar:**
1. Dataset'i seç
2. `Ayarlar` > `Zamanlanmış yenileme`
3. Zamanlama ayarla

#### Manuel Yenileme
**Açıklama:** Veriyi manuel olarak yenileme

**Yöntemler:**
- `Yenile` butonu
- API çağrısı
- Gateway üzerinden

---

## 8. Paylaşım ve Güvenlik

### Rapor Paylaşımı

#### Publish to Web
**Açıklama:** Raporu web'de herkese açık paylaşma

**Kullanım:**
1. Raporu seç
2. `Dosya` > `Publish to web`
3. Embed kodu al

#### Share
**Açıklama:** Belirli kişilerle rapor paylaşma

**Seçenekler:**
- E-posta ile paylaşım
- Link ile paylaşım
- İzin seviyeleri

### Güvenlik

#### Row-Level Security (RLS)
**Açıklama:** Satır seviyesinde güvenlik

**Kullanım:**
1. `Modelleme` > `Güvenlik`
2. Rol oluştur
3. Filtre tanımla

**Örnek:**
```dax
[Region] = USERNAME()
```

#### Object-Level Security (OLS)
**Açıklama:** Nesne seviyesinde güvenlik

**Özellikler:**
- Tablo erişimi
- Sütun erişimi
- Görsel erişimi

### İzin Yönetimi

#### Admin Rolleri
**Açıklama:** Yönetici yetkileri

**Roller:**
- Global Admin
- PowerBI Admin
- Workspace Admin

#### Kullanıcı Rolleri
**Açıklama:** Kullanıcı yetkileri

**Roller:**
- Viewer
- Contributor
- Member
- Admin

---

## 9. Performans Optimizasyonu

### Model Optimizasyonu

#### Veri Sıkıştırma
**Açıklama:** Model boyutunu küçültme

**Yöntemler:**
- Gereksiz sütunları kaldır
- Veri tiplerini optimize et
- Sıkıştırma algoritmaları kullan

#### İlişki Optimizasyonu
**Açıklama:** İlişkileri optimize etme

**İpuçları:**
- Gereksiz ilişkileri kaldır
- İlişki yönlerini kontrol et
- Cross-filtering ayarlarını optimize et

### DAX Optimizasyonu

#### Verimli DAX Yazma
**Açıklama:** Performanslı DAX formülleri yazma

**İpuçları:**
- Gereksiz hesaplamaları önle
- Context'i doğru kullan
- Iterator fonksiyonlarını dikkatli kullan

#### Measure vs Calculated Column
**Açıklama:** Hesaplama türü seçimi

**Measure Kullan:**
- Dinamik hesaplamalar
- Filtrelenebilir sonuçlar
- Küçük model boyutu

**Calculated Column Kullan:**
- Statik hesaplamalar
- Filtreleme için
- Karmaşık hesaplamalar

### Görsel Optimizasyonu

#### Görsel Performansı
**Açıklama:** Görsellerin performansını artırma

**Yöntemler:**
- Gereksiz görselleri kaldır
- Veri miktarını sınırla
- Etkileşimleri optimize et

#### Filtreleme
**Açıklama:** Etkili filtreleme kullanma

**İpuçları:**
- Slicer'ları kullan
- Cross-filtering'i ayarla
- Filtre sırasını optimize et

---

## 10. PowerBI Mobile

### Mobil Uygulama

#### Uygulama İndirme
**Açıklama:** PowerBI Mobile uygulamasını indirme

**Platformlar:**
- iOS
- Android
- Windows

#### Giriş Yapma
**Açıklama:** Mobil uygulamaya giriş yapma

**Yöntemler:**
- Microsoft hesabı
- Kurumsal hesap
- PowerBI Service

### Mobil Özellikler

#### Dashboard Görüntüleme
**Açıklama:** Dashboard'ları mobilde görüntüleme

**Özellikler:**
- Touch etkileşimi
- Pinch-to-zoom
- Swipe navigasyonu

#### Rapor Görüntüleme
**Açıklama:** Raporları mobilde görüntüleme

**Özellikler:**
- Responsive tasarım
- Touch etkileşimi
- Offline görüntüleme

### Mobil Paylaşım

#### QR Kod
**Açıklama:** QR kod ile paylaşım

**Kullanım:**
1. Raporu aç
2. `Paylaş` > `QR Kod`
3. QR kodu tarat

#### E-posta Paylaşımı
**Açıklama:** E-posta ile paylaşım

**Özellikler:**
- Otomatik e-posta
- Özelleştirilebilir mesaj
- Ek dosya gönderme

---

## 11. PowerBI Premium

### Premium Özellikleri

#### Büyük Veri Kapasitesi
**Açıklama:** Daha büyük veri modelleri

**Limitler:**
- 100GB model boyutu
- 1M satır/saniye
- Sınırsız kullanıcı

#### Gelişmiş AI
**Açıklama:** Yapay zeka özellikleri

**Özellikler:**
- Q&A
- Key Influencers
- Decomposition Tree

#### Paginated Reports
**Açıklama:** Sayfalanmış raporlar

**Özellikler:**
- PDF export
- Yazdırma optimizasyonu
- Büyük veri setleri

### Premium Yönetimi

#### Capacity Yönetimi
**Açıklama:** Premium kapasitesini yönetme

**Özellikler:**
- Kullanım izleme
- Performans metrikleri
- Kapasite planlama

#### Workspace Atama
**Açıklama:** Workspace'leri Premium'a atama

**Adımlar:**
1. Workspace'i seç
2. `Ayarlar` > `Premium`
3. Capacity seç

---

## 12. PowerBI Embedded

### Embedded Analytics

#### Embed in Applications
**Açıklama:** Uygulamalara PowerBI gömme

**Yöntemler:**
- JavaScript SDK
- REST API
- PowerBI Embedded

#### Authentication
**Açıklama:** Gömülü raporlar için kimlik doğrulama

**Yöntemler:**
- Service Principal
- Master User
- Azure AD

### Embedded Yönetimi

#### Workspace Yönetimi
**Açıklama:** Embedded workspace'leri yönetme

**Özellikler:**
- Otomatik workspace oluşturma
- Kullanıcı yönetimi
- İzin kontrolü

#### Performance Monitoring
**Açıklama:** Embedded performansını izleme

**Metrikler:**
- Load time
- User interactions
- Error rates

---

## 13. PowerBI REST API

### API Temelleri

#### Authentication
**Açıklama:** API kimlik doğrulama

**Yöntemler:**
- OAuth 2.0
- Service Principal
- Master User

#### Base URL
**Açıklama:** API temel URL'si

```
https://api.powerbi.com/v1.0/myorg/
```

### Temel API İşlemleri

#### Datasets
**Açıklama:** Dataset işlemleri

**Endpoints:**
```
GET /datasets
POST /datasets
DELETE /datasets/{datasetId}
```

#### Reports
**Açıklama:** Rapor işlemleri

**Endpoints:**
```
GET /reports
POST /reports/{reportId}/clone
DELETE /reports/{reportId}
```

#### Dashboards
**Açıklama:** Dashboard işlemleri

**Endpoints:**
```
GET /dashboards
POST /dashboards
DELETE /dashboards/{dashboardId}
```

### Gelişmiş API İşlemleri

#### Data Refresh
**Açıklama:** Veri yenileme

```http
POST /datasets/{datasetId}/refreshes
```

#### Export
**Açıklama:** Rapor export

```http
GET /reports/{reportId}/exports/{exportId}
```

#### Embed Token
**Açıklama:** Embed token oluşturma

```http
POST /reports/{reportId}/GenerateToken
```

---

## 14. PowerBI Gateway

### Gateway Nedir?
**Açıklama:** Şirket içi veri kaynaklarına güvenli bağlantı sağlayan araç.

### Gateway Türleri

#### On-premises Data Gateway
**Açıklama:** Şirket içi veri kaynakları için

**Özellikler:**
- SQL Server
- SharePoint
- File systems

#### On-premises Data Gateway (Personal Mode)
**Açıklama:** Kişisel kullanım için

**Özellikler:**
- Tek kullanıcı
- Basit kurulum
- Sınırlı özellikler

### Gateway Kurulumu

#### Kurulum Adımları
**Açıklama:** Gateway kurulum süreci

**Adımlar:**
1. Gateway'i indir
2. Kurulumu yap
3. Yapılandırmayı tamamla
4. Veri kaynaklarını ekle

#### Yapılandırma
**Açıklama:** Gateway ayarları

**Seçenekler:**
- Recovery key
- Network settings
- Data source settings

### Gateway Yönetimi

#### Monitoring
**Açıklama:** Gateway izleme

**Metrikler:**
- Connection status
- Performance metrics
- Error logs

#### Maintenance
**Açıklama:** Gateway bakımı

**İşlemler:**
- Update installation
- Configuration backup
- Troubleshooting

---

## 15. PowerBI Template Apps

### Template Apps Nedir?
**Açıklama:** Hazır PowerBI çözümleri ve şablonları.

### Template Apps Kullanımı

#### App Gallery
**Açıklama:** Microsoft'un resmi app galerisi

**Kategoriler:**
- Sales
- Marketing
- Finance
- HR

#### Custom Template Apps
**Açıklama:** Özel template app oluşturma

**Adımlar:**
1. Raporu hazırla
2. Template app olarak yayınla
3. App Store'a gönder

### Template App Geliştirme

#### App Package
**Açıklama:** Template app paketi

**Bileşenler:**
- Reports
- Datasets
- Dashboards
- Configuration

#### App Configuration
**Açıklama:** App yapılandırması

**Ayarlar:**
- App metadata
- Data source configuration
- User permissions

---

## 16. PowerBI Best Practices

### Model Tasarımı

#### Star Schema
**Açıklama:** Yıldız şeması kullanma

**Avantajları:**
- Basit model
- Hızlı performans
- Kolay anlaşılır

#### Dimension Tables
**Açıklama:** Boyut tabloları tasarımı

**İpuçları:**
- Surrogate keys kullan
- Descriptive columns ekle
- Hierarchies oluştur

### DAX Best Practices

#### Measure Naming
**Açıklama:** Measure isimlendirme kuralları

**Kurallar:**
- Açıklayıcı isimler
- Tutarlı format
- Prefix kullanımı

#### Performance Tips
**Açıklama:** DAX performans ipuçları

**İpuçları:**
- Gereksiz hesaplamaları önle
- Context'i doğru kullan
- Iterator fonksiyonlarını dikkatli kullan

### Görsel Tasarım

#### Dashboard Design
**Açıklama:** Dashboard tasarım prensipleri

**Prensipler:**
- KISS (Keep It Simple, Stupid)
- Consistent layout
- Clear hierarchy

#### Color Usage
**Açıklama:** Renk kullanım kuralları

**Kurallar:**
- Brand colors
- Accessibility
- Meaningful colors

### Güvenlik Best Practices

#### RLS Implementation
**Açıklama:** Row-level security uygulama

**Adımlar:**
1. Security requirements analiz et
2. Roles tanımla
3. Filters oluştur
4. Test et

#### Data Privacy
**Açıklama:** Veri gizliliği

**Önlemler:**
- Sensitive data classification
- Access controls
- Audit logging

---

## 17. PowerBI Troubleshooting

### Yaygın Sorunlar

#### Veri Yükleme Sorunları
**Açıklama:** Veri yükleme hataları

**Çözümler:**
- Connection string kontrol et
- Credentials doğrula
- Network connectivity kontrol et

#### Performans Sorunları
**Açıklama:** Yavaş performans

**Çözümler:**
- Model boyutunu kontrol et
- DAX formüllerini optimize et
- Gereksiz görselleri kaldır

#### Görsel Sorunları
**Açıklama:** Görsel hataları

**Çözümler:**
- Veri tiplerini kontrol et
- İlişkileri doğrula
- Filtreleri kontrol et

### Debugging Araçları

#### Performance Analyzer
**Açıklama:** Performans analiz aracı

**Kullanım:**
1. `Görselleştirme` > `Performance Analyzer`
2. `Start Recording`
3. Raporu kullan
4. Sonuçları analiz et

#### DAX Studio
**Açıklama:** DAX geliştirme aracı

**Özellikler:**
- Query execution
- Performance analysis
- Formula debugging

### Log Analysis

#### PowerBI Service Logs
**Açıklama:** Service log analizi

**Log Türleri:**
- Activity logs
- Error logs
- Performance logs

#### Gateway Logs
**Açıklama:** Gateway log analizi

**Log Konumları:**
- Windows Event Logs
- Gateway logs
- Application logs

---

## 18. PowerBI Klavye Kısayolları

### Temel Kısayollar

| Kısayol | İşlem |
|---------|-------|
| `Ctrl + N` | Yeni rapor |
| `Ctrl + O` | Rapor aç |
| `Ctrl + S` | Rapor kaydet |
| `Ctrl + Z` | Geri al |
| `Ctrl + Y` | Yinele |
| `Ctrl + C` | Kopyala |
| `Ctrl + V` | Yapıştır |
| `Ctrl + X` | Kes |

### Görsel Kısayolları

| Kısayol | İşlem |
|---------|-------|
| `Ctrl + Shift + 1` | Sütun grafik |
| `Ctrl + Shift + 2` | Çizgi grafik |
| `Ctrl + Shift + 3` | Pasta grafik |
| `Ctrl + Shift + 4` | Dağılım grafik |
| `Ctrl + Shift + 5` | Tablo |
| `Ctrl + Shift + 6` | Matris |

### Veri Kısayolları

| Kısayol | İşlem |
|---------|-------|
| `Ctrl + T` | Yeni tablo |
| `Ctrl + Shift + T` | Yeni hesaplanmış tablo |
| `Ctrl + M` | Yeni measure |
| `Ctrl + Shift + M` | Yeni hesaplanmış sütun |

### Navigasyon Kısayolları

| Kısayol | İşlem |
|---------|-------|
| `F11` | Tam ekran |
| `Ctrl + F` | Bul |
| `Ctrl + H` | Değiştir |
| `Ctrl + G` | Git |

---

## Ek Kaynaklar

### Microsoft Dokümantasyonu
- [PowerBI Resmi Dokümantasyonu](https://docs.microsoft.com/power-bi/)
- [DAX Referansı](https://docs.microsoft.com/dax/)
- [Power Query M Referansı](https://docs.microsoft.com/powerquery-m/)

### Topluluk Kaynakları
- [PowerBI Community](https://community.powerbi.com/)
- [PowerBI Blog](https://powerbi.microsoft.com/blog/)
- [PowerBI YouTube Channel](https://www.youtube.com/user/mspowerbi)

### Eğitim Kaynakları
- [PowerBI Learning Path](https://docs.microsoft.com/learn/powerplatform/power-bi)
- [PowerBI Training](https://powerbi.microsoft.com/training/)
- [PowerBI Certification](https://docs.microsoft.com/learn/certifications/power-bi-data-analyst-associate/)

### Araçlar
- [DAX Studio](https://daxstudio.org/)
- [PowerBI Helper](https://powerbihelper.com/)
- [PowerBI Custom Visuals](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals)

---

## Sonuç

Bu kapsamlı PowerBI cheatsheet, PowerBI'nin tüm temel ve ileri seviye özelliklerini ele almaktadır. Her komutun ve özelliğin Türkçe açıklaması ile birlikte pratik örnekler verilmiştir. Bu rehberi referans olarak kullanarak PowerBI projelerinizi daha etkili bir şekilde geliştirebilir ve iş zekası çözümlerinizi optimize edebilirsiniz.

**PowerBI Cheatsheet** - Veri analizi ve iş zekası için eksiksiz referans rehberi! 🚀
