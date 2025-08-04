# Excel Cheatsheet

## 📋 İçindekiler
- [Temel Formüller](#temel-formüller)
- [Veri Analizi](#veri-analizi)
- [Pivot Tablolar](#pivot-tablolar)
- [Koşullu Biçimlendirme](#koşullu-biçimlendirme)
- [Veri Doğrulama](#veri-doğrulama)
- [Makrolar](#makrolar)
- [Klavye Kısayolları](#klavye-kısayolları)

## 🎯 Ne İşe Yarar
Excel, veri analizi, hesaplama, raporlama ve iş süreçlerini otomatikleştirmek için kullanılan güçlü bir elektronik tablo uygulamasıdır.

## ⚡ Ne Yapar
- Veri girişi ve düzenleme
- Matematiksel hesaplamalar
- Veri analizi ve görselleştirme
- Raporlama ve dashboard oluşturma
- Otomatik işlemler (makrolar)
- Veri doğrulama ve temizleme

---

## 📊 Temel Formüller

### Matematiksel Formüller

#### TOPLA (SUM)
**Ne İşe Yarar:** Belirtilen hücre aralığındaki sayıları toplar
**Ne Yapar:** Seçilen hücrelerdeki tüm sayısal değerleri birleştirir

```excel
=TOPLA(A1:A10)
=SUM(A1:A10)
```

#### ORTALAMA (AVERAGE)
**Ne İşe Yarar:** Belirtilen hücre aralığındaki sayıların ortalamasını hesaplar
**Ne Yapar:** Seçilen hücrelerdeki sayıların aritmetik ortalamasını bulur

```excel
=ORTALAMA(A1:A10)
=AVERAGE(A1:A10)
```

#### MAK (MAX)
**Ne İşe Yarar:** Belirtilen hücre aralığındaki en büyük değeri bulur
**Ne Yapar:** Seçilen hücreler arasından maksimum değeri döndürür

```excel
=MAK(A1:A10)
=MAX(A1:A10)
```

#### MİN (MIN)
**Ne İşe Yarar:** Belirtilen hücre aralığındaki en küçük değeri bulur
**Ne Yapar:** Seçilen hücreler arasından minimum değeri döndürür

```excel
=MİN(A1:A10)
=MIN(A1:A10)
```

### Metin Formülleri

#### BİRLEŞTİR (CONCATENATE)
**Ne İşe Yarar:** Birden fazla metin değerini birleştirir
**Ne Yapar:** Farklı hücrelerdeki metinleri tek bir hücrede birleştirir

```excel
=BİRLEŞTİR(A1," ",B1)
=CONCATENATE(A1," ",B1)
=A1&" "&B1
```

#### SOL (LEFT)
**Ne İşe Yarar:** Metnin sol tarafından belirtilen sayıda karakter alır
**Ne Yapar:** Bir metin değerinin başından itibaren karakter sayısı kadar kısmını döndürür

```excel
=SOL(A1,5)
=LEFT(A1,5)
```

#### SAĞ (RIGHT)
**Ne İşe Yarar:** Metnin sağ tarafından belirtilen sayıda karakter alır
**Ne Yapar:** Bir metin değerinin sonundan itibaren karakter sayısı kadar kısmını döndürür

```excel
=SAĞ(A1,3)
=RIGHT(A1,3)
```

#### ORTA (MID)
**Ne İşe Yarar:** Metnin ortasından belirtilen konumdan itibaren karakter alır
**Ne Yapar:** Bir metin değerinin belirtilen pozisyondan başlayarak karakter sayısı kadar kısmını döndürür

```excel
=ORTA(A1,3,5)
=MID(A1,3,5)
```

### Arama ve Referans Formülleri

#### DÜŞEYARA (VLOOKUP)
**Ne İşe Yarar:** Bir tabloda dikey olarak arama yapar
**Ne Yapar:** Belirtilen değeri tablonun ilk sütununda arar ve aynı satırdaki başka bir sütundaki değeri döndürür

```excel
=DÜŞEYARA(A1,B1:D10,3,YANLIŞ)
=VLOOKUP(A1,B1:D10,3,FALSE)
```

#### YATAYARA (HLOOKUP)
**Ne İşe Yarar:** Bir tabloda yatay olarak arama yapar
**Ne Yapar:** Belirtilen değeri tablonun ilk satırında arar ve aynı sütundaki başka bir satırdaki değeri döndürür

```excel
=YATAYARA(A1,B1:D10,3,YANLIŞ)
=HLOOKUP(A1,B1:D10,3,FALSE)
```

#### İNDİS (INDEX)
**Ne İşe Yarar:** Bir diziden belirtilen konumdaki değeri döndürür
**Ne Yapar:** Belirtilen satır ve sütun numarasına göre diziden değer alır

```excel
=İNDİS(A1:D10,3,2)
=INDEX(A1:D10,3,2)
```

#### KAÇINCI (MATCH)
**Ne İşe Yarar:** Bir dizide belirtilen değerin konumunu bulur
**Ne Yapar:** Belirtilen değerin dizideki satır veya sütun numarasını döndürür

```excel
=KAÇINCI(A1,A1:A10,0)
=MATCH(A1,A1:A10,0)
```

### Mantık Formülleri

#### EĞER (IF)
**Ne İşe Yarar:** Koşula göre farklı değerler döndürür
**Ne Yapar:** Belirtilen koşul doğruysa bir değer, yanlışsa başka bir değer döndürür

```excel
=EĞER(A1>10,"Büyük","Küçük")
=IF(A1>10,"Büyük","Küçük")
```

#### VE (AND)
**Ne İşe Yarar:** Birden fazla koşulun hepsinin doğru olup olmadığını kontrol eder
**Ne Yapar:** Tüm koşullar doğruysa DOĞRU, değilse YANLIŞ döndürür

```excel
=VE(A1>10,B1<20)
=AND(A1>10,B1<20)
```

#### VEYA (OR)
**Ne İşe Yarar:** Birden fazla koşuldan en az birinin doğru olup olmadığını kontrol eder
**Ne Yapar:** En az bir koşul doğruysa DOĞRU, hiçbiri doğru değilse YANLIŞ döndürür

```excel
=VEYA(A1>10,B1<20)
=OR(A1>10,B1<20)
```

#### DEĞİL (NOT)
**Ne İşe Yarar:** Bir koşulun tersini alır
**Ne Yapar:** Koşul doğruysa YANLIŞ, yanlışsa DOĞRU döndürür

```excel
=DEĞİL(A1>10)
=NOT(A1>10)
```

### Tarih ve Saat Formülleri

#### BUGÜN (TODAY)
**Ne İşe Yarar:** Bugünün tarihini döndürür
**Ne Yapar:** Sistem tarihini seri numarası olarak döndürür

```excel
=BUGÜN()
=TODAY()
```

#### ŞİMDİ (NOW)
**Ne İşe Yarar:** Şu anki tarih ve saati döndürür
**Ne Yapar:** Sistem tarihini ve saatini seri numarası olarak döndürür

```excel
=ŞİMDİ()
=NOW()
```

#### TARİH (DATE)
**Ne İşe Yarar:** Belirtilen yıl, ay ve günden tarih oluşturur
**Ne Yapar:** Verilen yıl, ay ve gün değerlerinden geçerli bir tarih seri numarası oluşturur

```excel
=TARİH(2024,1,15)
=DATE(2024,1,15)
```

#### GÜN (DAY)
**Ne İşe Yarar:** Bir tarihten gün numarasını alır
**Ne Yapar:** Belirtilen tarihin gün kısmını sayı olarak döndürür

```excel
=GÜN(A1)
=DAY(A1)
```

---

## 📈 Veri Analizi

### Filtreleme

#### Otomatik Filtre
**Ne İşe Yarar:** Veri aralığında hızlı filtreleme yapar
**Ne Yapar:** Sütun başlıklarına filtre okları ekler ve verileri kategorilere göre filtreler

**Kullanım:**
1. Veri aralığını seç
2. `Ctrl + Shift + L` (Windows) / `Cmd + Shift + F` (Mac)
3. Sütun başlığındaki oku tıkla
4. İstediğin kriterleri seç

#### Gelişmiş Filtre
**Ne İşe Yarar:** Karmaşık filtreleme kriterleri uygular
**Ne Yapar:** Birden fazla koşul ve kriter ile veri filtreleme yapar

**Kullanım:**
1. `Veri` > `Gelişmiş`
2. Filtre kriterlerini belirle
3. `Tamam` ile uygula

### Sıralama

#### Tek Sütun Sıralama
**Ne İşe Yarar:** Verileri tek sütuna göre sıralar
**Ne Yapar:** Seçilen sütundaki değerlere göre tüm veriyi düzenler

**Kullanım:**
1. Sütunu seç
2. `Veri` > `Sırala`
3. Artan/Azalan seç

#### Çoklu Sıralama
**Ne İşe Yarar:** Birden fazla sütuna göre sıralama yapar
**Ne Yapar:** Öncelik sırasına göre birden fazla kriterle sıralama

**Kullanım:**
1. `Veri` > `Sırala`
2. `Seviye Ekle` ile kriter ekle
3. Her seviye için sütun ve sıralama seç

---

## 📊 Pivot Tablolar

### Pivot Tablo Oluşturma
**Ne İşe Yarar:** Büyük veri setlerini özetlemek ve analiz etmek için kullanılır
**Ne Yapar:** Verileri kategorilere göre gruplar ve istatistiksel özetler oluşturur

**Adımlar:**
1. Veri aralığını seç
2. `Ekle` > `Pivot Tablo`
3. Alanları sürükle:
   - **Satırlar:** Kategoriler
   - **Sütunlar:** Alt kategoriler
   - **Değerler:** Hesaplanacak veriler
   - **Filtreler:** Genel filtreler

### Pivot Tablo Alanları

#### Satır Alanları
**Ne İşe Yarar:** Verileri dikey olarak gruplar
**Ne Yapar:** Seçilen alana göre verileri satırlarda kategorize eder

#### Sütun Alanları
**Ne İşe Yarar:** Verileri yatay olarak gruplar
**Ne Yapar:** Seçilen alana göre verileri sütunlarda kategorize eder

#### Değer Alanları
**Ne İşe Yarar:** Hesaplanacak sayısal verileri belirler
**Ne Yapar:** Toplam, ortalama, sayım gibi hesaplamalar yapar

#### Filtre Alanları
**Ne İşe Yarar:** Tüm pivot tabloyu filtreler
**Ne Yapar:** Seçilen kritere göre tüm veriyi filtreler

---

## 🎨 Koşullu Biçimlendirme

### Temel Koşullu Biçimlendirme
**Ne İşe Yarar:** Belirli koşullara göre hücrelerin görünümünü değiştirir
**Ne Yapar:** Koşulları karşılayan hücreleri renklendirir, kalın yapar veya farklı stiller uygular

**Kullanım:**
1. Biçimlendirilecek hücreleri seç
2. `Giriş` > `Koşullu Biçimlendirme`
3. İstediğin kuralı seç

### Koşullu Biçimlendirme Türleri

#### Hücre Kuralları
**Ne İşe Yarar:** Belirli değerlere göre hücreleri biçimlendirir
**Ne Yapar:** Sayısal değerler, metin, tarihler için özel kurallar uygular

- **Büyüktür/Küçüktür:** Belirli değerlerden büyük/küçük olanları
- **Eşittir:** Belirli değere eşit olanları
- **Metin İçerir:** Belirli metni içerenleri

#### Veri Çubukları
**Ne İşe Yarar:** Sayısal değerleri görsel çubuklarla gösterir
**Ne Yapar:** Hücre içinde değerin büyüklüğüne göre çubuk oluşturur

#### Renk Ölçekleri
**Ne İşe Yarar:** Değer aralığını renk geçişleriyle gösterir
**Ne Yapar:** En düşük değerden en yüksek değere doğru renk geçişi yapar

#### Simge Kümeleri
**Ne İşe Yarar:** Değerleri simgelerle kategorize eder
**Ne Yapar:** Ok, yıldız, trafik ışığı gibi simgelerle değerleri gösterir

---

## ✅ Veri Doğrulama

### Veri Doğrulama Kuralları
**Ne İşe Yarar:** Hücrelere girilecek verilerin türünü ve aralığını sınırlar
**Ne Yapar:** Yanlış veri girişini önler ve kullanıcıya uyarı verir

**Kullanım:**
1. Doğrulanacak hücreleri seç
2. `Veri` > `Veri Doğrulama`
3. Kural türünü ve kriterleri belirle

### Doğrulama Türleri

#### Liste
**Ne İşe Yarar:** Hücreye sadece belirli değerlerin girilmesine izin verir
**Ne Yapar:** Açılır liste oluşturur ve sadece listedeki değerlerin seçilmesini sağlar

**Örnek:** Departman listesi, ülke listesi

#### Sayı
**Ne İşe Yarar:** Sayısal değerler için aralık belirler
**Ne Yapar:** Minimum ve maksimum değerler arasında sayı girişine izin verir

**Örnek:** 0-100 arası, negatif olmayan sayılar

#### Tarih
**Ne İşe Yarar:** Tarih değerleri için aralık belirler
**Ne Yapar:** Belirli tarih aralığında tarih girişine izin verir

**Örnek:** Bugünden sonraki tarihler, belirli ay aralığı

#### Metin Uzunluğu
**Ne İşe Yarar:** Metin uzunluğunu sınırlar
**Ne Yapar:** Minimum ve maksimum karakter sayısı belirler

**Örnek:** 5-10 karakter arası, en az 3 karakter

---

## 🤖 Makrolar

### Makro Kaydetme
**Ne İşe Yarar:** Tekrarlanan işlemleri otomatikleştirir
**Ne Yapar:** Yapılan işlemleri kaydeder ve tek tuşla tekrar çalıştırır

**Adımlar:**
1. `Geliştirici` > `Makro Kaydet`
2. Makro adı ver
3. İşlemleri yap
4. `Durdur` ile kaydetmeyi bitir

### Makro Çalıştırma
**Ne İşe Yarar:** Kaydedilen makroyu çalıştırır
**Ne Yapar:** Kaydedilen tüm işlemleri otomatik olarak tekrarlar

**Yöntemler:**
- `Alt + F8` ile makro listesinden çalıştır
- Klavye kısayolu atayarak çalıştır
- Buton ekleyerek çalıştır

### VBA (Visual Basic for Applications)
**Ne İşe Yarar:** Gelişmiş makro programlama imkanı sağlar
**Ne Yapar:** Karmaşık işlemleri programlama ile otomatikleştirir

**Temel Komutlar:**
```vba
Sub MakroAdi()
    ' Kod buraya
End Sub

Range("A1").Value = "Merhaba"
Cells(1, 1).Value = "Merhaba"
```

### Makro Güvenliği
**Ne İşe Yarar:** Makroların güvenli çalışmasını sağlar
**Ne Yapar:** Makro çalıştırma izinlerini kontrol eder

**Ayarlar:**
- `Dosya` > `Seçenekler` > `Güven Merkezi`
- Makro ayarlarını yapılandır

---

## ⌨️ Klavye Kısayolları

### Temel İşlemler
| Kısayol | İşlem |
|---------|-------|
| `Ctrl + C` | Kopyala |
| `Ctrl + V` | Yapıştır |
| `Ctrl + X` | Kes |
| `Ctrl + Z` | Geri Al |
| `Ctrl + Y` | Yinele |
| `Ctrl + S` | Kaydet |
| `Ctrl + O` | Aç |
| `Ctrl + N` | Yeni |

### Hücre İşlemleri
| Kısayol | İşlem |
|---------|-------|
| `F2` | Hücreyi düzenle |
| `Enter` | Aşağı git |
| `Tab` | Sağa git |
| `Shift + Enter` | Yukarı git |
| `Shift + Tab` | Sola git |
| `Ctrl + Enter` | Seçili hücrelere aynı değeri gir |
| `Ctrl + D` | Aşağı doldur |
| `Ctrl + R` | Sağa doldur |

### Seçim İşlemleri
| Kısayol | İşlem |
|---------|-------|
| `Ctrl + A` | Tümünü seç |
| `Ctrl + Shift + *` | Mevcut bölgeyi seç |
| `Ctrl + Space` | Sütunu seç |
| `Shift + Space` | Satırı seç |
| `Ctrl + Shift + L` | Filtre ekle/kaldır |

### Formül İşlemleri
| Kısayol | İşlem |
|---------|-------|
| `Ctrl + Shift + Enter` | Dizi formülü gir |
| `F4` | Referans türünü değiştir |
| `Ctrl + Shift + A` | Fonksiyon argümanlarını ekle |
| `Alt + =` | Otomatik toplam |

### Biçimlendirme
| Kısayol | İşlem |
|---------|-------|
| `Ctrl + B` | Kalın |
| `Ctrl + I` | İtalik |
| `Ctrl + U` | Altı çizili |
| `Ctrl + 1` | Hücre biçimlendirme |
| `Ctrl + Shift + ~` | Genel format |
| `Ctrl + Shift + $` | Para birimi formatı |
| `Ctrl + Shift + %` | Yüzde formatı |

---

## 📚 Faydalı İpuçları

### Veri Temizleme
- **Yinelenen Değerleri Kaldır:** `Veri` > `Yinelenen Değerleri Kaldır`
- **Metni Sütunlara Dönüştür:** `Veri` > `Metni Sütunlara Dönüştür`
- **Boşlukları Temizle:** `TRIM()` fonksiyonu

### Performans Optimizasyonu
- Gereksiz formülleri kaldır
- Büyük veri setlerinde filtreleme kullan
- Pivot tabloları kullanarak özetleme yap

### Hata Kontrolü
- `EĞERHATA()` fonksiyonu ile hata kontrolü
- `EĞERSAY()` ile boş hücreleri say
- `DOĞRULAMA()` ile veri doğruluğunu kontrol et

---

*Bu cheatsheet Excel'in temel özelliklerini kapsar. Daha detaylı bilgi için Microsoft Excel resmi dokümantasyonunu inceleyebilirsiniz.* 