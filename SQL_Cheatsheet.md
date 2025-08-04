# SQL Cheatsheet - Kapsamlı SQL Referans Rehberi

Bu rehber SQL'in temel ve ileri seviye konularını kapsar. Her komutun Türkçe açıklaması bulunmaktadır.

**Not:** Bu rehberde MySQL ve SQLite komutları ayrı ayrı belirtilmiştir. Her bölümde önce MySQL komutları, sonra SQLite komutları verilmiştir.

## İçindekiler

1. [Veritabanı İşlemleri](#1-veritabanı-işlemleri)
2. [Tablo İşlemleri](#2-tablo-işlemleri)
3. [Veri İşlemleri (CRUD)](#3-veri-işlemleri-crud)
4. [WHERE Koşulları](#4-where-koşulları)
5. [Sıralama ve Limit](#5-sıralama-ve-limit)
6. [Fonksiyonlar](#6-fonksiyonlar)
7. [GROUP BY ve HAVING](#7-group-by-ve-having)
8. [JOIN İşlemleri](#8-join-işlemleri)
9. [Alt Sorgular (Subqueries)](#9-alt-sorgular-subqueries)
10. [İndeksler](#10-indeksler)
11. [Görünümler (Views)](#11-görünümler-views)
12. [Stored Procedures](#12-stored-procedures)
13. [Triggers](#13-triggers)
14. [Transactions](#14-transactions)
15. [Kullanıcı ve İzin Yönetimi](#15-kullanıcı-ve-izin-yönetimi)
16. [Veritabanı Yedekleme ve Geri Yükleme](#16-veritabanı-yedekleme-ve-geri-yükleme)
17. [Performans Optimizasyonu](#17-performans-optimizasyonu)
18. [Yaygın Hatalar ve Çözümleri](#18-yaygın-hatalar-ve-çözümleri)
19. [Veri Tipleri](#19-veri-tipleri)
20. [Kısıtlamalar (Constraints)](#20-kısıtlamalar-constraints)
21. [UNION ve Set İşlemleri](#21-union-ve-set-işlemleri)
22. [Window Functions](#22-window-functions)
23. [Common Table Expressions (CTE)](#23-common-table-expressions-cte)
24. [Pivot ve Unpivot](#24-pivot-ve-unpivot)
25. [JSON İşlemleri](#25-json-işlemleri)
26. [Regular Expressions](#26-regular-expressions)
27. [Temporal Tables](#27-temporal-tables)
28. [Partitioning](#28-partitioning)
29. [Replication](#29-replication)
30. [Security ve Encryption](#30-security-ve-encryption)
31. [Monitoring ve Logging](#31-monitoring-ve-logging)
32. [Advanced SQL Patterns](#32-advanced-sql-patterns)
33. [SQL Best Practices](#33-sql-best-practices)
34. [Database Design Patterns](#34-database-design-patterns)
35. [SQL Injection Prevention](#35-sql-injection-prevention)
36. [Performance Tuning](#36-performance-tuning)
37. [Database Migration](#37-database-migration)
38. [Data Warehousing](#38-data-warehousing)
39. [Big Data SQL](#39-big-data-sql)
40. [Cloud Database Services](#40-cloud-database-services)
41. [MERGE Statement (UPSERT)](#41-merge-statement-upsert)
42. [FULLTEXT Search](#42-fulltext-search)
43. [Spatial Data (Coğrafi Veri)](#43-spatial-data-coğrafi-veri)
44. [Materialized Views](#44-materialized-views)
45. [Database Events (Zamanlanmış Görevler)](#45-database-events-zamanlanmış-görevler)
46. [Cursors (İmleçler)](#46-cursors-imleçler)
47. [Error Handling (Hata Yönetimi)](#47-error-handling-hata-yönetimi)
48. [Dynamic SQL](#48-dynamic-sql)
49. [Database Variables ve System Variables](#49-database-variables-ve-system-variables)
50. [Advanced Data Types](#50-advanced-data-types)
51. [Database Optimization Techniques](#51-database-optimization-techniques)
52. [Database Maintenance](#52-database-maintenance)
53. [Database Monitoring ve Diagnostics](#53-database-monitoring-ve-diagnostics)
54. [Database Backup Strategies](#54-database-backup-strategies)
55. [Database Recovery](#55-database-recovery)
56. [Database Security Best Practices](#56-database-security-best-practices)
57. [Database Scalability](#57-database-scalability)
58. [Database Integration](#58-database-integration)
59. [Database Testing](#59-database-testing)
60. [Database Documentation](#60-database-documentation)
61. [Graph Databases ve SQL](#61-graph-databases-ve-sql)
62. [Machine Learning SQL](#62-machine-learning-sql)
63. [Time Series Data](#63-time-series-data)
64. [Blockchain ve Distributed Databases](#64-blockchain-ve-distributed-databases)
65. [Real-time Analytics](#65-real-time-analytics)
66. [Advanced Analytics ve Business Intelligence](#66-advanced-analytics-ve-business-intelligence)
67. [Data Quality ve Data Governance](#67-data-quality-ve-data-governance)
68. [Advanced Security Features](#68-advanced-security-features)
69. [Database Automation](#69-database-automation)
70. [Future SQL Trends](#70-future-sql-trends)
71. [SQL Injection Bypass Techniques (Güvenlik Testleri İçin)](#71-sql-injection-bypass-techniques-güvenlik-testleri-için)
72. [Obfuscated SQL (Gizli SQL)](#72-obfuscated-sql-gizli-sql)
73. [Undocumented SQL Features](#73-undocumented-sql-features)
74. [Performance Hacks ve Tricks](#74-performance-hacks-ve-tricks)
75. [Advanced SQL Tricks](#75-advanced-sql-tricks)
76. [SQL Puzzles ve Brain Teasers](#76-sql-puzzles-ve-brain-teasers)
77. [SQL Anti-Patterns (Kaçınılması Gerekenler)](#77-sql-anti-patterns-kaçınılması-gerekenler)
78. [SQL Easter Eggs ve Hidden Features](#78-sql-easter-eggs-ve-hidden-features)
79. [SQL Debugging ve Troubleshooting](#79-sql-debugging-ve-troubleshooting)
80. [SQL Black Magic (En Gelişmiş Teknikler)](#80-sql-black-magic-en-gelişmiş-teknikler)

---

## 1. Veritabanı İşlemleri

### Veritabanı Oluşturma

**MySQL:**
```sql
CREATE DATABASE veritabani_adi;
```

**SQLite:**
```sql
-- SQLite'da veritabanı dosyası otomatik oluşturulur
-- Veritabanına bağlanmak yeterlidir
```

**Açıklama:** Yeni bir veritabanı oluşturur

### Veritabanı Silme

**MySQL:**
```sql
DROP DATABASE veritabani_adi;
```

**SQLite:**
```bash
# Dosyayı silmek yeterlidir
rm veritabani_adi.db
```

**Açıklama:** Veritabanını ve içindeki tüm verileri siler

### Veritabanı Kullanma

**MySQL:**
```sql
USE veritabani_adi;
```

**SQLite:**
```sql
-- SQLite'da tek veritabanı kullanılır, USE komutu yoktur
-- Bağlantı sırasında veritabanı dosyası belirtilir
```

**Açıklama:** Belirtilen veritabanını aktif hale getirir

### Veritabanlarını Listeleme

**MySQL:**
```sql
SHOW DATABASES;
```

**SQLite:**
```sql
-- SQLite'da tek veritabanı kullanılır
-- .databases komutu ile mevcut veritabanlarını görebilirsiniz
.databases
```

**Açıklama:** Mevcut tüm veritabanlarını listeler

---

## 2. Tablo İşlemleri

### Tablo Oluşturma

**MySQL:**
```sql
CREATE TABLE tablo_adi (
    id INT PRIMARY KEY AUTO_INCREMENT,
    ad VARCHAR(50) NOT NULL,
    soyad VARCHAR(50),
    yas INT,
    email VARCHAR(100) UNIQUE,
    kayit_tarihi TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

**SQLite:**
```sql
CREATE TABLE tablo_adi (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    ad TEXT NOT NULL,
    soyad TEXT,
    yas INTEGER,
    email TEXT UNIQUE,
    kayit_tarihi DATETIME DEFAULT CURRENT_TIMESTAMP
);
```

**Açıklama:** Yeni bir tablo oluşturur ve sütunları tanımlar

### Tablo Silme

**MySQL:**
```sql
DROP TABLE tablo_adi;
```

**SQLite:**
```sql
DROP TABLE tablo_adi;
```

**Açıklama:** Tabloyu ve içindeki tüm verileri siler

### Tablo Yapısını Görüntüleme

**MySQL:**
```sql
DESCRIBE tablo_adi;
-- veya
DESC tablo_adi;
```

**SQLite:**
```sql
PRAGMA table_info(tablo_adi);
-- veya
.schema tablo_adi
```

**Açıklama:** Tablonun sütun yapısını ve veri tiplerini gösterir

### Tabloları Listeleme

**MySQL:**
```sql
SHOW TABLES;
```

**SQLite:**
```sql
SELECT name FROM sqlite_master WHERE type='table';
-- veya
.tables
```

**Açıklama:** Mevcut veritabanındaki tüm tabloları listeler

### Tablo Adını Değiştirme

**MySQL:**
```sql
RENAME TABLE eski_adi TO yeni_adi;
```

**SQLite:**
```sql
ALTER TABLE eski_adi RENAME TO yeni_adi;
```

**Açıklama:** Tablo adını değiştirir

### Sütun Ekleme

**MySQL:**
```sql
ALTER TABLE tablo_adi ADD COLUMN yeni_sutun VARCHAR(50);
```

**SQLite:**
```sql
ALTER TABLE tablo_adi ADD COLUMN yeni_sutun TEXT;
```

**Açıklama:** Mevcut tabloya yeni sütun ekler

### Sütun Silme

**MySQL:**
```sql
ALTER TABLE tablo_adi DROP COLUMN sutun_adi;
```

**SQLite:**
```sql
-- SQLite'da sütun silme desteklenmez
-- Yeni tablo oluşturup veriyi taşımak gerekir
CREATE TABLE yeni_tablo AS SELECT id, ad, soyad FROM eski_tablo;
DROP TABLE eski_tablo;
ALTER TABLE yeni_tablo RENAME TO eski_tablo;
```

**Açıklama:** Tablodan sütun siler

### Sütun Değiştirme

**MySQL:**
```sql
ALTER TABLE tablo_adi MODIFY COLUMN sutun_adi VARCHAR(100);
```

**SQLite:**
```sql
-- SQLite'da sütun değiştirme desteklenmez
-- Yeni tablo oluşturup veriyi taşımak gerekir
```

**Açıklama:** Sütunun veri tipini değiştirir

### Sütun Adını Değiştirme

**MySQL:**
```sql
ALTER TABLE tablo_adi CHANGE eski_adi yeni_adi VARCHAR(50);
```

**SQLite:**
```sql
-- SQLite'da sütun adı değiştirme desteklenmez
-- Yeni tablo oluşturup veriyi taşımak gerekir
```

**Açıklama:** Sütun adını değiştirir

---

## 3. Veri İşlemleri (CRUD)

### VERİ EKLEME (CREATE)

**MySQL:**
```sql
INSERT INTO tablo_adi (sutun1, sutun2, sutun3) VALUES (deger1, deger2, deger3);
INSERT INTO tablo_adi VALUES (deger1, deger2, deger3);
```

**SQLite:**
```sql
INSERT INTO tablo_adi (sutun1, sutun2, sutun3) VALUES (deger1, deger2, deger3);
INSERT INTO tablo_adi VALUES (deger1, deger2, deger3);
```

**Açıklama:** Tabloya yeni veri ekler

### Çoklu Veri Ekleme

**MySQL:**
```sql
INSERT INTO tablo_adi (sutun1, sutun2) VALUES 
    (deger1, deger2),
    (deger3, deger4),
    (deger5, deger6);
```

**SQLite:**
```sql
INSERT INTO tablo_adi (sutun1, sutun2) VALUES 
    (deger1, deger2),
    (deger3, deger4),
    (deger5, deger6);
```

**Açıklama:** Birden fazla veriyi tek seferde ekler

### VERİ OKUMA (READ)

**MySQL:**
```sql
SELECT * FROM tablo_adi;
```

**SQLite:**
```sql
SELECT * FROM tablo_adi;
```

**Açıklama:** Tablodaki tüm verileri getirir

**MySQL:**
```sql
SELECT sutun1, sutun2 FROM tablo_adi;
```

**SQLite:**
```sql
SELECT sutun1, sutun2 FROM tablo_adi;
```

**Açıklama:** Belirtilen sütunları getirir

**MySQL:**
```sql
SELECT DISTINCT sutun1 FROM tablo_adi;
```

**SQLite:**
```sql
SELECT DISTINCT sutun1 FROM tablo_adi;
```

**Açıklama:** Tekrarlayan değerleri filtreleyerek getirir

### VERİ GÜNCELLEME (UPDATE)

**MySQL:**
```sql
UPDATE tablo_adi SET sutun1 = yeni_deger WHERE kosul;
```

**SQLite:**
```sql
UPDATE tablo_adi SET sutun1 = yeni_deger WHERE kosul;
```

**Açıklama:** Koşula uyan verileri günceller

**MySQL:**
```sql
UPDATE tablo_adi SET sutun1 = yeni_deger1, sutun2 = yeni_deger2 WHERE kosul;
```

**SQLite:**
```sql
UPDATE tablo_adi SET sutun1 = yeni_deger1, sutun2 = yeni_deger2 WHERE kosul;
```

**Açıklama:** Birden fazla sütunu günceller

### VERİ SİLME (DELETE)

**MySQL:**
```sql
DELETE FROM tablo_adi WHERE kosul;
```

**SQLite:**
```sql
DELETE FROM tablo_adi WHERE kosul;
```

**Açıklama:** Koşula uyan verileri siler

**MySQL:**
```sql
DELETE FROM tablo_adi;
```

**SQLite:**
```sql
DELETE FROM tablo_adi;
```

**Açıklama:** Tablodaki tüm verileri siler

**MySQL:**
```sql
TRUNCATE TABLE tablo_adi;
```

**SQLite:**
```sql
-- SQLite'da TRUNCATE yoktur, DELETE kullanılır
DELETE FROM tablo_adi;
-- Veya tabloyu yeniden oluştur
DELETE FROM sqlite_sequence WHERE name='tablo_adi';
```

**Açıklama:** Tablodaki tüm verileri hızlıca siler

---

## 4. WHERE Koşulları

### Temel Karşılaştırma Operatörleri
```sql
SELECT * FROM tablo_adi WHERE sutun = deger;
SELECT * FROM tablo_adi WHERE sutun != deger;
SELECT * FROM tablo_adi WHERE sutun > deger;
SELECT * FROM tablo_adi WHERE sutun < deger;
SELECT * FROM tablo_adi WHERE sutun >= deger;
SELECT * FROM tablo_adi WHERE sutun <= deger;
```

### Mantıksal Operatörler
```sql
SELECT * FROM tablo_adi WHERE kosul1 AND kosul2;
SELECT * FROM tablo_adi WHERE kosul1 OR kosul2;
SELECT * FROM tablo_adi WHERE NOT kosul;
```

### IN Operatörü
```sql
SELECT * FROM tablo_adi WHERE sutun IN (deger1, deger2, deger3);
```
**Açıklama:** Belirtilen değerlerden herhangi birine eşit olanları getirir

### BETWEEN Operatörü
```sql
SELECT * FROM tablo_adi WHERE sutun BETWEEN deger1 AND deger2;
```
**Açıklama:** İki değer arasındaki verileri getirir

### LIKE Operatörü (Metin Arama)
```sql
SELECT * FROM tablo_adi WHERE sutun LIKE 'pattern%';
SELECT * FROM tablo_adi WHERE sutun LIKE '%pattern';
SELECT * FROM tablo_adi WHERE sutun LIKE '%pattern%';
```
**Açıklama:** Metin kalıplarına göre arama yapar (% joker karakter)

### IS NULL / IS NOT NULL
```sql
SELECT * FROM tablo_adi WHERE sutun IS NULL;
SELECT * FROM tablo_adi WHERE sutun IS NOT NULL;
```
**Açıklama:** NULL değerleri kontrol eder

### CASE WHEN ile Koşullu Filtreleme
```sql
SELECT 
    ad,
    yas,
    CASE 
        WHEN yas < 18 THEN 'Çocuk'
        WHEN yas < 65 THEN 'Yetişkin'
        ELSE 'Yaşlı'
    END as yas_grubu
FROM kullanicilar;
```
**Açıklama:** Koşullu değer atama ve filtreleme

### EXISTS ve NOT EXISTS
```sql
-- Alt sorgu sonuç döndürüyorsa
SELECT * FROM musteriler m 
WHERE EXISTS (SELECT 1 FROM siparisler s WHERE s.musteri_id = m.id);

-- Alt sorgu sonuç döndürmüyorsa
SELECT * FROM musteriler m 
WHERE NOT EXISTS (SELECT 1 FROM siparisler s WHERE s.musteri_id = m.id);
```
**Açıklama:** Alt sorgu varlığını kontrol eder

### ANY ve ALL Operatörleri
```sql
-- ANY: Alt sorgudan herhangi biri doğruysa
SELECT * FROM urunler 
WHERE fiyat > ANY (SELECT fiyat FROM urunler WHERE kategori = 'Elektronik');

-- ALL: Alt sorgudan hepsi doğruysa
SELECT * FROM urunler 
WHERE fiyat > ALL (SELECT fiyat FROM urunler WHERE kategori = 'Kitap');
```
**Açıklama:** Alt sorgu karşılaştırmaları

### Pattern Matching (Gelişmiş)
```sql
-- _ tek karakter için
SELECT * FROM kullanicilar WHERE ad LIKE 'A_m_t';

-- [] karakter aralığı
SELECT * FROM kullanicilar WHERE ad REGEXP '^[A-C]';

-- [^] hariç karakter aralığı
SELECT * FROM kullanicilar WHERE ad REGEXP '^[^A-C]';

-- {n} tam n kez tekrarlama
SELECT * FROM kullanicilar WHERE telefon REGEXP '[0-9]{10}';

-- {n,m} n ile m arası tekrarlama
SELECT * FROM kullanicilar WHERE ad REGEXP '[a-z]{3,10}';
```
**Açıklama:** Gelişmiş metin eşleştirme

---

## 5. Sıralama ve Limit

### Sıralama (ORDER BY)
```sql
SELECT * FROM tablo_adi ORDER BY sutun ASC;
SELECT * FROM tablo_adi ORDER BY sutun DESC;
```
**Açıklama:** Verileri belirtilen sütuna göre sıralar (ASC: artan, DESC: azalan)

### Çoklu Sıralama
```sql
SELECT * FROM tablo_adi ORDER BY sutun1 ASC, sutun2 DESC;
```
**Açıklama:** Birden fazla sütuna göre sıralama yapar

### Limit

**MySQL:**
```sql
SELECT * FROM tablo_adi LIMIT 10;
```

**SQLite:**
```sql
SELECT * FROM tablo_adi LIMIT 10;
```

**Açıklama:** İlk 10 kaydı getirir

### Offset ile Limit

**MySQL:**
```sql
SELECT * FROM tablo_adi LIMIT 10 OFFSET 20;
```

**SQLite:**
```sql
SELECT * FROM tablo_adi LIMIT 10 OFFSET 20;
```

**Açıklama:** 20. kayıttan sonraki 10 kaydı getirir (sayfalama için)

### Kısa Yazım

**MySQL:**
```sql
SELECT * FROM tablo_adi LIMIT 20, 10;
```

**SQLite:**
```sql
SELECT * FROM tablo_adi LIMIT 20, 10;
```

**Açıklama:** Yukarıdaki ile aynı (offset, limit)

---

## 6. Fonksiyonlar

### Metin Fonksiyonları

**MySQL:**
```sql
SELECT UPPER(sutun) FROM tablo_adi;
SELECT LOWER(sutun) FROM tablo_adi;
SELECT LENGTH(sutun) FROM tablo_adi;
SELECT CONCAT(sutun1, ' ', sutun2) FROM tablo_adi;
SELECT SUBSTRING(sutun, 1, 5) FROM tablo_adi;
SELECT TRIM(sutun) FROM tablo_adi;
```

**SQLite:**
```sql
SELECT UPPER(sutun) FROM tablo_adi;
SELECT LOWER(sutun) FROM tablo_adi;
SELECT LENGTH(sutun) FROM tablo_adi;
SELECT sutun1 || ' ' || sutun2 FROM tablo_adi; -- CONCAT yerine ||
SELECT SUBSTR(sutun, 1, 5) FROM tablo_adi; -- SUBSTRING yerine SUBSTR
SELECT TRIM(sutun) FROM tablo_adi;
```

**Açıklama:** Metin işlemleri için kullanılır

### Gelişmiş Metin Fonksiyonları
```sql
-- REPLACE
SELECT REPLACE(ad, 'Ahmet', 'Mehmet') FROM kullanicilar;

-- REPEAT
SELECT REPEAT('*', 5) as yildizlar;

-- REVERSE
SELECT REVERSE(ad) as ters_ad FROM kullanicilar;

-- LEFT ve RIGHT
SELECT LEFT(ad, 3) as ilk_3_harf, RIGHT(ad, 3) as son_3_harf FROM kullanicilar;

-- LPAD ve RPAD
SELECT LPAD(ad, 10, '*') as sol_doldurma, RPAD(ad, 10, '*') as sag_doldurma FROM kullanicilar;

-- POSITION ve LOCATE
SELECT POSITION('a' IN ad) as a_pozisyonu FROM kullanicilar;
SELECT LOCATE('a', ad, 2) as a_pozisyonu_2den_sonra FROM kullanicilar;

-- INSERT (metin değiştirme)
SELECT INSERT(ad, 1, 3, 'Yeni') as degistirilmis_ad FROM kullanicilar;

-- ELT (belirli pozisyondaki eleman)
SELECT ELT(2, 'bir', 'iki', 'uc') as ikinci_eleman;

-- FIELD (elemanın pozisyonu)
SELECT FIELD('iki', 'bir', 'iki', 'uc') as pozisyon;
```
**Açıklama:** Gelişmiş metin işleme fonksiyonları

### Metin Arama ve Değiştirme
```sql
-- REGEXP_REPLACE (PostgreSQL)
SELECT REGEXP_REPLACE(ad, '[aeiou]', '*', 'g') as degistirilmis_ad FROM kullanicilar;

-- REGEXP_SUBSTR
SELECT REGEXP_SUBSTR(email, '@[^.]+') as domain FROM kullanicilar;

-- Metin temizleme
SELECT 
    TRIM(BOTH ' ' FROM ad) as temizlenmis_ad,
    REPLACE(ad, '  ', ' ') as tek_bosluk
FROM kullanicilar;
```
**Açıklama:** Düzenli ifadelerle metin işleme

### Sayısal Fonksiyonlar
```sql
SELECT ABS(sutun) FROM tablo_adi;
SELECT ROUND(sutun, 2) FROM tablo_adi;
SELECT CEIL(sutun) FROM tablo_adi;
SELECT FLOOR(sutun) FROM tablo_adi;
SELECT RAND() FROM tablo_adi;
```
**Açıklama:** Matematiksel işlemler için kullanılır

### Tarih Fonksiyonları

**MySQL:**
```sql
SELECT NOW() FROM tablo_adi;
SELECT CURDATE() FROM tablo_adi;
SELECT CURTIME() FROM tablo_adi;
SELECT YEAR(tarih_sutunu) FROM tablo_adi;
SELECT MONTH(tarih_sutunu) FROM tablo_adi;
SELECT DAY(tarih_sutunu) FROM tablo_adi;
SELECT DATE_ADD(tarih, INTERVAL 1 DAY) FROM tablo_adi;
```

**SQLite:**
```sql
SELECT datetime('now') FROM tablo_adi; -- NOW() yerine
SELECT date('now') FROM tablo_adi; -- CURDATE() yerine
SELECT time('now') FROM tablo_adi; -- CURTIME() yerine
SELECT strftime('%Y', tarih_sutunu) FROM tablo_adi; -- YEAR() yerine
SELECT strftime('%m', tarih_sutunu) FROM tablo_adi; -- MONTH() yerine
SELECT strftime('%d', tarih_sutunu) FROM tablo_adi; -- DAY() yerine
SELECT datetime(tarih, '+1 day') FROM tablo_adi; -- DATE_ADD() yerine
```

**Açıklama:** Tarih ve saat işlemleri için kullanılır

### Gelişmiş Tarih Fonksiyonları
```sql
-- Tarih formatlama
SELECT DATE_FORMAT(NOW(), '%Y-%m-%d %H:%i:%s') as formatli_tarih;
SELECT DATE_FORMAT(NOW(), '%d/%m/%Y') as gun_ay_yil;
SELECT DATE_FORMAT(NOW(), '%W, %d %M %Y') as tam_tarih;

-- Tarih hesaplamaları
SELECT DATE_ADD(NOW(), INTERVAL 1 MONTH) as bir_ay_sonra;
SELECT DATE_SUB(NOW(), INTERVAL 1 WEEK) as bir_hafta_once;
SELECT DATEDIFF('2023-12-31', '2023-01-01') as gun_farki;
SELECT TIMESTAMPDIFF(DAY, '2023-01-01', '2023-12-31') as gun_farki;

-- Tarih parçalama
SELECT 
    YEAR(tarih) as yil,
    MONTH(tarih) as ay,
    DAY(tarih) as gun,
    HOUR(saat) as saat,
    MINUTE(saat) as dakika,
    SECOND(saat) as saniye
FROM tablo_adi;

-- Hafta işlemleri
SELECT WEEK(tarih) as hafta_numarasi;
SELECT WEEKDAY(tarih) as hafta_gunu; -- 0=Pazartesi, 6=Pazar
SELECT DAYOFWEEK(tarih) as hafta_gunu; -- 1=Pazar, 7=Cumartesi

-- Tarih aralıkları
SELECT 
    DATE(tarih) as sadece_tarih,
    TIME(tarih) as sadece_saat,
    QUARTER(tarih) as ceyrek
FROM tablo_adi;
```
**Açıklama:** Gelişmiş tarih ve saat işlemleri

### Tarih Karşılaştırma ve Filtreleme
```sql
-- Belirli tarih aralığı
SELECT * FROM siparisler 
WHERE siparis_tarihi BETWEEN '2023-01-01' AND '2023-12-31';

-- Son 30 gün
SELECT * FROM siparisler 
WHERE siparis_tarihi >= DATE_SUB(CURDATE(), INTERVAL 30 DAY);

-- Bu ay
SELECT * FROM siparisler 
WHERE YEAR(siparis_tarihi) = YEAR(CURDATE()) 
AND MONTH(siparis_tarihi) = MONTH(CURDATE());

-- Hafta sonu siparişleri
SELECT * FROM siparisler 
WHERE DAYOFWEEK(siparis_tarihi) IN (1, 7);
```
**Açıklama:** Tarih bazlı filtreleme

### Agregasyon Fonksiyonları

**MySQL:**
```sql
SELECT COUNT(*) FROM tablo_adi;
SELECT SUM(sutun) FROM tablo_adi;
SELECT AVG(sutun) FROM tablo_adi;
SELECT MAX(sutun) FROM tablo_adi;
SELECT MIN(sutun) FROM tablo_adi;
```

**SQLite:**
```sql
SELECT COUNT(*) FROM tablo_adi;
SELECT SUM(sutun) FROM tablo_adi;
SELECT AVG(sutun) FROM tablo_adi;
SELECT MAX(sutun) FROM tablo_adi;
SELECT MIN(sutun) FROM tablo_adi;
```

**Açıklama:** Veri grupları üzerinde hesaplama yapar

### Gelişmiş Agregasyon Fonksiyonları
```sql
-- COUNT DISTINCT
SELECT COUNT(DISTINCT kategori) FROM urunler;

-- GROUP_CONCAT (MySQL)
SELECT departman, GROUP_CONCAT(ad SEPARATOR ', ') as calisanlar
FROM calisanlar GROUP BY departman;

-- GROUP_CONCAT (SQLite)
SELECT departman, GROUP_CONCAT(ad, ', ') as calisanlar
FROM calisanlar GROUP BY departman;

-- STRING_AGG (PostgreSQL)
SELECT departman, STRING_AGG(ad, ', ') as calisanlar
FROM calisanlar GROUP BY departman;

-- PERCENTILE_CONT (PostgreSQL)
SELECT PERCENTILE_CONT(0.5) WITHIN GROUP (ORDER BY maas) as median_maas
FROM calisanlar;

-- VARIANCE ve STDDEV
SELECT 
    VARIANCE(maas) as maas_varyansi,
    STDDEV(maas) as maas_standart_sapma
FROM calisanlar;
```
**Açıklama:** Gelişmiş istatistiksel fonksiyonlar

### Koşullu Agregasyon
```sql
-- SUM ile CASE
SELECT 
    departman,
    SUM(CASE WHEN cinsiyet = 'E' THEN maas ELSE 0 END) as erkek_maas_toplami,
    SUM(CASE WHEN cinsiyet = 'K' THEN maas ELSE 0 END) as kadin_maas_toplami
FROM calisanlar
GROUP BY departman;

-- COUNT ile CASE
SELECT 
    COUNT(CASE WHEN yas < 30 THEN 1 END) as genç_calisan,
    COUNT(CASE WHEN yas >= 30 THEN 1 END) as yetişkin_calisan
FROM calisanlar;
```
**Açıklama:** Koşullu hesaplamalar

### Window Functions ile Agregasyon
```sql
-- Running average
SELECT 
    tarih,
    satis,
    AVG(satis) OVER (ORDER BY tarih ROWS BETWEEN 6 PRECEDING AND CURRENT ROW) as haftalik_ortalama
FROM gunluk_satislar;

-- Cumulative sum
SELECT 
    departman,
    maas,
    SUM(maas) OVER (PARTITION BY departman ORDER BY maas) as kumulatif_maas
FROM calisanlar;
```
**Açıklama:** Pencere fonksiyonları ile hesaplama

---

## 7. GROUP BY ve HAVING

### GROUP BY
```sql
SELECT kategori, COUNT(*) FROM tablo_adi GROUP BY kategori;
SELECT departman, AVG(maas) FROM calisanlar GROUP BY departman;
```
**Açıklama:** Verileri gruplar ve her grup için hesaplama yapar

### HAVING
```sql
SELECT kategori, COUNT(*) FROM tablo_adi 
GROUP BY kategori 
HAVING COUNT(*) > 5;
```
**Açıklama:** GROUP BY sonuçlarını filtreler (WHERE gibi ama gruplar için)

### Çoklu Gruplama
```sql
SELECT departman, pozisyon, AVG(maas) 
FROM calisanlar 
GROUP BY departman, pozisyon;
```
**Açıklama:** Birden fazla sütuna göre gruplama yapar

---

## 8. JOIN İşlemleri

### INNER JOIN
```sql
SELECT a.sutun1, b.sutun2 
FROM tablo1 a 
INNER JOIN tablo2 b ON a.id = b.tablo1_id;
```
**Açıklama:** İki tabloda eşleşen kayıtları getirir

### LEFT JOIN
```sql
SELECT a.sutun1, b.sutun2 
FROM tablo1 a 
LEFT JOIN tablo2 b ON a.id = b.tablo1_id;
```
**Açıklama:** Sol tablodaki tüm kayıtları ve eşleşen sağ tablo kayıtlarını getirir

### RIGHT JOIN
```sql
SELECT a.sutun1, b.sutun2 
FROM tablo1 a 
RIGHT JOIN tablo2 b ON a.id = b.tablo1_id;
```
**Açıklama:** Sağ tablodaki tüm kayıtları ve eşleşen sol tablo kayıtlarını getirir

### FULL OUTER JOIN (MySQL'de UNION ile)
```sql
SELECT a.sutun1, b.sutun2 
FROM tablo1 a 
LEFT JOIN tablo2 b ON a.id = b.tablo1_id
UNION
SELECT a.sutun1, b.sutun2 
FROM tablo1 a 
RIGHT JOIN tablo2 b ON a.id = b.tablo1_id;
```
**Açıklama:** Her iki tablodaki tüm kayıtları getirir

### CROSS JOIN
```sql
SELECT a.sutun1, b.sutun2 
FROM tablo1 a 
CROSS JOIN tablo2 b;
```
**Açıklama:** İki tablonun kartezyen çarpımını yapar

### Self JOIN
```sql
SELECT 
    e1.ad as calisan,
    e2.ad as yonetici
FROM calisanlar e1
LEFT JOIN calisanlar e2 ON e1.yonetici_id = e2.id;
```
**Açıklama:** Aynı tabloyu kendisiyle birleştirir

### Multiple JOINs
```sql
SELECT 
    m.ad as musteri,
    u.ad as urun,
    k.ad as kategori
FROM musteriler m
JOIN siparisler s ON m.id = s.musteri_id
JOIN siparis_detaylari sd ON s.id = sd.siparis_id
JOIN urunler u ON sd.urun_id = u.id
JOIN kategoriler k ON u.kategori_id = k.id;
```
**Açıklama:** Birden fazla tabloyu birleştirir

### JOIN ile Aggregation
```sql
SELECT 
    d.ad as departman,
    COUNT(c.id) as calisan_sayisi,
    AVG(c.maas) as ortalama_maas
FROM departmanlar d
LEFT JOIN calisanlar c ON d.id = c.departman_id
GROUP BY d.id, d.ad;
```
**Açıklama:** JOIN ile birlikte gruplama

### Conditional JOIN
```sql
SELECT 
    m.ad as musteri,
    s.tutar
FROM musteriler m
LEFT JOIN siparisler s ON m.id = s.musteri_id 
    AND s.siparis_tarihi >= '2023-01-01'
    AND s.durum = 'tamamlandi';
```
**Açıklama:** Koşullu birleştirme

### LATERAL JOIN (PostgreSQL)
```sql
SELECT 
    d.ad as departman,
    c.ad as en_yuksek_maasli
FROM departmanlar d
CROSS JOIN LATERAL (
    SELECT ad FROM calisanlar 
    WHERE departman_id = d.id 
    ORDER BY maas DESC 
    LIMIT 1
) c;
```
**Açıklama:** Yan yana sorgu çalıştırma

---

## 9. Alt Sorgular (Subqueries)

### WHERE İçinde Alt Sorgu
```sql
SELECT * FROM tablo1 
WHERE sutun1 IN (SELECT sutun1 FROM tablo2 WHERE kosul);
```
**Açıklama:** WHERE koşulunda başka bir sorgu kullanır

### FROM İçinde Alt Sorgu
```sql
SELECT * FROM (SELECT * FROM tablo1 WHERE kosul) AS alt_tablo;
```
**Açıklama:** FROM kısmında geçici tablo oluşturur

### SELECT İçinde Alt Sorgu
```sql
SELECT sutun1, (SELECT MAX(sutun2) FROM tablo2) AS max_deger 
FROM tablo1;
```
**Açıklama:** SELECT kısmında hesaplama için alt sorgu kullanır

### EXISTS ile Alt Sorgu
```sql
SELECT * FROM tablo1 
WHERE EXISTS (SELECT 1 FROM tablo2 WHERE tablo2.id = tablo1.id);
```
**Açıklama:** Alt sorgunun sonuç döndürüp döndürmediğini kontrol eder

---

## 10. İndeksler

### İndeks Oluşturma

**MySQL:**
```sql
CREATE INDEX index_adi ON tablo_adi (sutun_adi);
```

**SQLite:**
```sql
CREATE INDEX index_adi ON tablo_adi (sutun_adi);
```

**Açıklama:** Belirtilen sütun için indeks oluşturur

### Çoklu Sütun İndeksi

**MySQL:**
```sql
CREATE INDEX index_adi ON tablo_adi (sutun1, sutun2);
```

**SQLite:**
```sql
CREATE INDEX index_adi ON tablo_adi (sutun1, sutun2);
```

**Açıklama:** Birden fazla sütun için bileşik indeks oluşturur

### Benzersiz İndeks

**MySQL:**
```sql
CREATE UNIQUE INDEX index_adi ON tablo_adi (sutun_adi);
```

**SQLite:**
```sql
CREATE UNIQUE INDEX index_adi ON tablo_adi (sutun_adi);
```

**Açıklama:** Benzersiz değerler için indeks oluşturur

### İndeks Silme

**MySQL:**
```sql
DROP INDEX index_adi ON tablo_adi;
```

**SQLite:**
```sql
DROP INDEX index_adi;
```

**Açıklama:** İndeksi siler

### İndeksleri Listeleme

**MySQL:**
```sql
SHOW INDEX FROM tablo_adi;
```

**SQLite:**
```sql
PRAGMA index_list(tablo_adi);
-- veya
SELECT name FROM sqlite_master WHERE type='index' AND tbl_name='tablo_adi';
```

**Açıklama:** Tablodaki tüm indeksleri gösterir

---

## 11. Görünümler (Views)

### Görünüm Oluşturma

**MySQL:**
```sql
CREATE VIEW view_adi AS 
SELECT sutun1, sutun2 FROM tablo_adi WHERE kosul;
```

**SQLite:**
```sql
CREATE VIEW view_adi AS 
SELECT sutun1, sutun2 FROM tablo_adi WHERE kosul;
```

**Açıklama:** Sanal tablo oluşturur

### Görünüm Kullanma

**MySQL:**
```sql
SELECT * FROM view_adi;
```

**SQLite:**
```sql
SELECT * FROM view_adi;
```

**Açıklama:** Görünümü normal tablo gibi kullanır

### Görünüm Güncelleme

**MySQL:**
```sql
CREATE OR REPLACE VIEW view_adi AS 
SELECT sutun1, sutun2, sutun3 FROM tablo_adi WHERE kosul;
```

**SQLite:**
```sql
-- SQLite'da CREATE OR REPLACE VIEW desteklenmez
DROP VIEW IF EXISTS view_adi;
CREATE VIEW view_adi AS 
SELECT sutun1, sutun2, sutun3 FROM tablo_adi WHERE kosul;
```

**Açıklama:** Mevcut görünümü günceller

### Görünüm Silme

**MySQL:**
```sql
DROP VIEW view_adi;
```

**SQLite:**
```sql
DROP VIEW view_adi;
```

**Açıklama:** Görünümü siler

---

## 12. Stored Procedures

### Stored Procedure Oluşturma

**MySQL:**
```sql
DELIMITER //
CREATE PROCEDURE procedure_adi(IN parametre1 INT, OUT sonuc VARCHAR(50))
BEGIN
    SELECT sutun1 INTO sonuc FROM tablo_adi WHERE id = parametre1;
END //
DELIMITER ;
```

**SQLite:**
```sql
-- SQLite'da stored procedure desteklenmez
-- Bunun yerine fonksiyonlar kullanılabilir
CREATE TEMP TABLE temp_sonuc (deger TEXT);
INSERT INTO temp_sonuc SELECT sutun1 FROM tablo_adi WHERE id = ?;
```

**Açıklama:** Yeniden kullanılabilir kod bloğu oluşturur

### Stored Procedure Çağırma

**MySQL:**
```sql
CALL procedure_adi(1, @sonuc);
SELECT @sonuc;
```

**SQLite:**
```sql
-- SQLite'da stored procedure çağırma yoktur
-- Bunun yerine doğrudan SQL sorguları kullanılır
```

**Açıklama:** Oluşturulan prosedürü çalıştırır

### Stored Procedure Silme

**MySQL:**
```sql
DROP PROCEDURE procedure_adi;
```

**SQLite:**
```sql
-- SQLite'da stored procedure yoktur
```

**Açıklama:** Prosedürü siler

---

## 13. Triggers

### Trigger Oluşturma

**MySQL:**
```sql
DELIMITER //
CREATE TRIGGER trigger_adi 
BEFORE INSERT ON tablo_adi
FOR EACH ROW
BEGIN
    SET NEW.otomatik_alan = NOW();
END //
DELIMITER ;
```

**SQLite:**
```sql
CREATE TRIGGER trigger_adi 
BEFORE INSERT ON tablo_adi
FOR EACH ROW
BEGIN
    UPDATE tablo_adi SET otomatik_alan = datetime('now') WHERE id = NEW.id;
END;
```

**Açıklama:** Belirli olaylarda otomatik çalışan kod bloğu oluşturur

### Trigger Türleri

**MySQL ve SQLite:**
- **BEFORE INSERT:** Ekleme öncesi
- **AFTER INSERT:** Ekleme sonrası
- **BEFORE UPDATE:** Güncelleme öncesi
- **AFTER UPDATE:** Güncelleme sonrası
- **BEFORE DELETE:** Silme öncesi
- **AFTER DELETE:** Silme sonrası

### Trigger Silme

**MySQL:**
```sql
DROP TRIGGER trigger_adi;
```

**SQLite:**
```sql
DROP TRIGGER trigger_adi;
```

**Açıklama:** Trigger'ı siler

---

## 14. Transactions

### Transaction Başlatma
```sql
START TRANSACTION;
-- veya
BEGIN;
```

### İşlemler
```sql
INSERT INTO tablo1 VALUES (1, 'deger1');
UPDATE tablo2 SET sutun = 'yeni_deger' WHERE id = 1;
```

### Commit (İşlemleri Onaylama)
```sql
COMMIT;
```

### Rollback (İşlemleri Geri Alma)
```sql
ROLLBACK;
```

### Otomatik Commit'i Kapatma
```sql
SET autocommit = 0;
```
**Açıklama:** İşlemlerin otomatik onaylanmasını engeller

### Savepoint Oluşturma
```sql
SAVEPOINT nokta_adi;
```
**Açıklama:** Geri dönülebilir nokta oluşturur

### Savepoint'e Geri Dönme
```sql
ROLLBACK TO nokta_adi;
```
**Açıklama:** Belirtilen noktaya geri döner

---

## 15. Kullanıcı ve İzin Yönetimi

### Kullanıcı Oluşturma

**MySQL:**
```sql
CREATE USER 'kullanici_adi'@'localhost' IDENTIFIED BY 'sifre';
```

**SQLite:**
```sql
-- SQLite'da kullanıcı yönetimi yoktur
-- Dosya izinleri ile kontrol edilir
```

**Açıklama:** Yeni kullanıcı oluşturur

### Kullanıcıya İzin Verme

**MySQL:**
```sql
GRANT SELECT, INSERT, UPDATE, DELETE ON veritabani_adi.* TO 'kullanici_adi'@'localhost';
```

**SQLite:**
```sql
-- SQLite'da izin sistemi yoktur
-- Dosya sistemi izinleri kullanılır
```

**Açıklama:** Kullanıcıya belirli izinler verir

### Tüm İzinleri Verme

**MySQL:**
```sql
GRANT ALL PRIVILEGES ON veritabani_adi.* TO 'kullanici_adi'@'localhost';
```

**SQLite:**
```sql
-- SQLite'da izin sistemi yoktur
```

**Açıklama:** Kullanıcıya tüm izinleri verir

### İzinleri Geri Alma

**MySQL:**
```sql
REVOKE SELECT ON veritabani_adi.* FROM 'kullanici_adi'@'localhost';
```

**SQLite:**
```sql
-- SQLite'da izin sistemi yoktur
```

**Açıklama:** Kullanıcının belirli izinlerini geri alır

### İzinleri Uygulama

**MySQL:**
```sql
FLUSH PRIVILEGES;
```

**SQLite:**
```sql
-- SQLite'da izin sistemi yoktur
```

**Açıklama:** İzin değişikliklerini aktif hale getirir

### Kullanıcı Silme

**MySQL:**
```sql
DROP USER 'kullanici_adi'@'localhost';
```

**SQLite:**
```sql
-- SQLite'da kullanıcı yönetimi yoktur
```

**Açıklama:** Kullanıcıyı siler

---

## 16. Veritabanı Yedekleme ve Geri Yükleme

### Veritabanı Yedekleme

**MySQL:**
```bash
mysqldump -u kullanici_adi -p veritabani_adi > yedek.sql
```

**SQLite:**
```bash
# Dosyayı kopyalamak yeterlidir
cp veritabani.db yedek.db
# veya
sqlite3 veritabani.db ".backup yedek.db"
```

**Açıklama:** Veritabanını SQL dosyasına yedekler

### Veritabanı Geri Yükleme

**MySQL:**
```bash
mysql -u kullanici_adi -p veritabani_adi < yedek.sql
```

**SQLite:**
```bash
# Dosyayı geri yüklemek
cp yedek.db veritabani.db
# veya SQL formatında
sqlite3 veritabani.db < yedek.sql
```

**Açıklama:** SQL dosyasından veritabanını geri yükler

### Tablo Yedekleme

**MySQL:**
```bash
mysqldump -u kullanici_adi -p veritabani_adi tablo_adi > tablo_yedek.sql
```

**SQLite:**
```bash
sqlite3 veritabani.db ".dump tablo_adi" > tablo_yedek.sql
```

**Açıklama:** Belirli tabloyu yedekler

### Sadece Veri Yapısı Yedekleme

**MySQL:**
```bash
mysqldump -u kullanici_adi -p --no-data veritabani_adi > yapi_yedek.sql
```

**SQLite:**
```bash
sqlite3 veritabani.db ".schema tablo_adi" > yapi_yedek.sql
```

**Açıklama:** Sadece tablo yapılarını yedekler

### Sadece Veri Yedekleme

**MySQL:**
```bash
mysqldump -u kullanici_adi -p --no-create-info veritabani_adi > veri_yedek.sql
```

**SQLite:**
```bash
sqlite3 veritabani.db "SELECT * FROM tablo_adi;" > veri_yedek.sql
```

**Açıklama:** Sadece verileri yedekler

---

## 17. Performans Optimizasyonu

### Sorgu Analizi

**MySQL:**
```sql
EXPLAIN SELECT * FROM tablo_adi WHERE sutun = 'deger';
```

**SQLite:**
```sql
EXPLAIN QUERY PLAN SELECT * FROM tablo_adi WHERE sutun = 'deger';
```

**Açıklama:** Sorgunun nasıl çalıştığını gösterir

### Sorgu Optimizasyonu İpuçları:
1. WHERE koşullarında indeksli sütunlar kullanın
2. SELECT * yerine gerekli sütunları belirtin
3. LIMIT kullanın
4. JOIN'lerde doğru indeksler kullanın
5. Alt sorgular yerine JOIN kullanın
6. GROUP BY'da indeksli sütunlar kullanın

### Tablo Analizi

**MySQL:**
```sql
ANALYZE TABLE tablo_adi;
```

**SQLite:**
```sql
ANALYZE tablo_adi;
-- veya tüm tablolar için
ANALYZE;
```

**Açıklama:** Tablo istatistiklerini günceller

### Tablo Optimizasyonu

**MySQL:**
```sql
OPTIMIZE TABLE tablo_adi;
```

**SQLite:**
```sql
-- SQLite'da VACUUM kullanılır
VACUUM;
-- veya belirli tablo için
VACUUM tablo_adi;
```

**Açıklama:** Tabloyu optimize eder

---

## 18. Yaygın Hatalar ve Çözümleri

### Hata: "Table doesn't exist"
**Çözüm:** `SHOW TABLES;` ile tabloları kontrol edin

### Hata: "Column doesn't exist"
**Çözüm:** `DESCRIBE tablo_adi;` ile sütunları kontrol edin

### Hata: "Duplicate entry"
**Çözüm:** UNIQUE kısıtlaması olan sütunda aynı değer eklenmeye çalışılıyor

### Hata: "Cannot add foreign key constraint"
**Çözüm:** Referans verilen tablo ve sütunların var olduğundan emin olun

### Hata: "Access denied"
**Çözüm:** Kullanıcı izinlerini kontrol edin

### Hata: "Connection timeout"
**Çözüm:** Bağlantı ayarlarını kontrol edin

---

## 19. Veri Tipleri

### Sayısal Tipler

**MySQL:**
- **INT, INTEGER:** Tam sayı (-2147483648 to 2147483647)
- **BIGINT:** Büyük tam sayı
- **SMALLINT:** Küçük tam sayı
- **TINYINT:** Çok küçük tam sayı
- **DECIMAL(10,2):** Ondalıklı sayı (toplam 10 hane, 2 ondalık)
- **FLOAT:** Kayan noktalı sayı
- **DOUBLE:** Çift hassasiyetli kayan noktalı sayı

**SQLite:**
- **INTEGER:** Tam sayı (8 byte)
- **REAL:** Kayan noktalı sayı (8 byte)
- **NUMERIC:** Ondalıklı sayı

### Metin Tipleri

**MySQL:**
- **VARCHAR(255):** Değişken uzunlukta metin (max 255 karakter)
- **CHAR(10):** Sabit uzunlukta metin (10 karakter)
- **TEXT:** Uzun metin
- **LONGTEXT:** Çok uzun metin
- **TINYTEXT:** Kısa metin

**SQLite:**
- **TEXT:** Metin (sınırsız uzunluk)
- **VARCHAR(n):** Metin (n karakter)
- **CHAR(n):** Sabit uzunlukta metin (n karakter)

### Tarih ve Saat Tipleri

**MySQL:**
- **DATE:** Tarih (YYYY-MM-DD)
- **TIME:** Saat (HH:MM:SS)
- **DATETIME:** Tarih ve saat (YYYY-MM-DD HH:MM:SS)
- **TIMESTAMP:** Zaman damgası
- **YEAR:** Yıl

**SQLite:**
- **DATETIME:** Tarih ve saat
- **DATE:** Tarih
- **TIME:** Saat
- **TIMESTAMP:** Zaman damgası

### Binary Tipler

**MySQL:**
- **BLOB:** Binary large object
- **LONGBLOB:** Uzun binary veri
- **VARBINARY(255):** Değişken uzunlukta binary veri

**SQLite:**
- **BLOB:** Binary large object

### Diğer Tipler

**MySQL:**
- **BOOLEAN, BOOL:** Mantıksal değer (TRUE/FALSE)
- **ENUM('a','b','c'):** Numaralandırma
- **SET('a','b','c'):** Çoklu seçim kümesi
- **JSON:** JSON veri tipi

**SQLite:**
- **BOOLEAN:** Mantıksal değer (0/1)
- **JSON:** JSON veri tipi (SQLite 3.38+)

---

## 20. Kısıtlamalar (Constraints)

### PRIMARY KEY (Birincil Anahtar)
```sql
CREATE TABLE tablo_adi (
    id INT PRIMARY KEY,
    ad VARCHAR(50)
);
```
**Açıklama:** Benzersiz ve NULL olmayan sütun

### FOREIGN KEY (Yabancı Anahtar)
```sql
CREATE TABLE siparisler (
    id INT PRIMARY KEY,
    musteri_id INT,
    FOREIGN KEY (musteri_id) REFERENCES musteriler(id)
);
```
**Açıklama:** Başka tablodaki PRIMARY KEY'e referans

### UNIQUE (Benzersiz)
```sql
CREATE TABLE kullanicilar (
    id INT PRIMARY KEY,
    email VARCHAR(100) UNIQUE
);
```
**Açıklama:** Sütundaki değerlerin benzersiz olmasını sağlar

### NOT NULL (Boş Olmayan)
```sql
CREATE TABLE urunler (
    id INT PRIMARY KEY,
    ad VARCHAR(100) NOT NULL
);
```
**Açıklama:** Sütunun NULL değer alamamasını sağlar

### DEFAULT (Varsayılan Değer)
```sql
CREATE TABLE kayitlar (
    id INT PRIMARY KEY,
    tarih TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```
**Açıklama:** Sütun için varsayılan değer belirler

### CHECK (Kontrol)
```sql
CREATE TABLE urunler (
    id INT PRIMARY KEY,
    fiyat DECIMAL(10,2) CHECK (fiyat > 0)
);
```
**Açıklama:** Sütun değerlerini kontrol eder

### AUTO_INCREMENT (Otomatik Artış)
```sql
CREATE TABLE tablo_adi (
    id INT PRIMARY KEY AUTO_INCREMENT,
    ad VARCHAR(50)
);
```
**Açıklama:** Sütun değerini otomatik artırır

---

## Örnek Kullanım Senaryoları

### Örnek 1: E-ticaret Veritabanı
```sql
-- Müşteriler tablosu
CREATE TABLE musteriler (
    id INT PRIMARY KEY AUTO_INCREMENT,
    ad VARCHAR(50) NOT NULL,
    soyad VARCHAR(50) NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL,
    telefon VARCHAR(15),
    kayit_tarihi TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Ürünler tablosu
CREATE TABLE urunler (
    id INT PRIMARY KEY AUTO_INCREMENT,
    ad VARCHAR(100) NOT NULL,
    aciklama TEXT,
    fiyat DECIMAL(10,2) NOT NULL CHECK (fiyat > 0),
    stok_miktari INT DEFAULT 0,
    kategori_id INT,
    FOREIGN KEY (kategori_id) REFERENCES kategoriler(id)
);

-- Siparişler tablosu
CREATE TABLE siparisler (
    id INT PRIMARY KEY AUTO_INCREMENT,
    musteri_id INT NOT NULL,
    siparis_tarihi TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    toplam_tutar DECIMAL(10,2),
    durum ENUM('beklemede', 'onaylandi', 'kargoda', 'tamamlandi') DEFAULT 'beklemede',
    FOREIGN KEY (musteri_id) REFERENCES musteriler(id)
);
```

### Örnek 2: Çalışan Yönetim Sistemi
```sql
-- Departmanlar tablosu
CREATE TABLE departmanlar (
    id INT PRIMARY KEY AUTO_INCREMENT,
    ad VARCHAR(50) NOT NULL,
    yonetici_id INT,
    FOREIGN KEY (yonetici_id) REFERENCES calisanlar(id)
);

-- Çalışanlar tablosu
CREATE TABLE calisanlar (
    id INT PRIMARY KEY AUTO_INCREMENT,
    tc_no VARCHAR(11) UNIQUE NOT NULL,
    ad VARCHAR(50) NOT NULL,
    soyad VARCHAR(50) NOT NULL,
    dogum_tarihi DATE,
    ise_giris_tarihi DATE NOT NULL,
    maas DECIMAL(10,2) NOT NULL,
    departman_id INT,
    FOREIGN KEY (departman_id) REFERENCES departmanlar(id)
);
```

---

## Faydalı Komutlar

### Sistem Bilgileri

**MySQL:**
```sql
-- MySQL versiyonu
SELECT VERSION();

-- Mevcut kullanıcı
SELECT USER();

-- Mevcut veritabanı
SELECT DATABASE();

-- Sunucu durumu
SHOW STATUS;

-- Süreç listesi
SHOW PROCESSLIST;
```

**SQLite:**
```sql
-- SQLite versiyonu
SELECT sqlite_version();

-- Mevcut kullanıcı (yoktur)
-- SQLite'da kullanıcı sistemi yoktur

-- Mevcut veritabanı
PRAGMA database_list;

-- Sunucu durumu
PRAGMA integrity_check;

-- Süreç listesi (yoktur)
-- SQLite tek kullanıcılıdır
```

### Tablo Bilgileri

**MySQL:**
```sql
-- Tablo boyutu
SELECT 
    table_name,
    ROUND(((data_length + index_length) / 1024 / 1024), 2) AS 'Boyut (MB)'
FROM information_schema.tables 
WHERE table_schema = 'veritabani_adi';

-- Tablo satır sayısı
SELECT 
    table_name,
    table_rows
FROM information_schema.tables 
WHERE table_schema = 'veritabani_adi';
```

**SQLite:**
```sql
-- Tablo boyutu (yaklaşık)
SELECT 
    name as table_name,
    ROUND((length * 1.0 / 1024 / 1024), 2) AS 'Boyut (MB)'
FROM sqlite_master 
WHERE type='table';

-- Tablo satır sayısı
SELECT 
    name as table_name,
    (SELECT COUNT(*) FROM sqlite_master WHERE type='table' AND name=table_name) as row_count
FROM sqlite_master 
WHERE type='table';
```

---

## 21. UNION ve Set İşlemleri

### UNION
```sql
SELECT sutun1, sutun2 FROM tablo1
UNION
SELECT sutun1, sutun2 FROM tablo2;
```
**Açıklama:** İki sorgunun sonuçlarını birleştirir (tekrarlayan satırları kaldırır)

### UNION ALL
```sql
SELECT sutun1, sutun2 FROM tablo1
UNION ALL
SELECT sutun1, sutun2 FROM tablo2;
```
**Açıklama:** İki sorgunun sonuçlarını birleştirir (tekrarlayan satırları korur)

### INTERSECT
```sql
SELECT sutun1 FROM tablo1
INTERSECT
SELECT sutun1 FROM tablo2;
```
**Açıklama:** Her iki sorguda da bulunan satırları getirir

### EXCEPT (MINUS)
```sql
SELECT sutun1 FROM tablo1
EXCEPT
SELECT sutun1 FROM tablo2;
```
**Açıklama:** İlk sorguda olup ikinci sorguda olmayan satırları getirir

### Set İşlemleri Kuralları
- UNION, INTERSECT, EXCEPT için sütun sayıları eşit olmalı
- Sütun veri tipleri uyumlu olmalı
- ORDER BY sadece son sorguda kullanılabilir

---

## 22. Window Functions

### ROW_NUMBER()
```sql
SELECT 
    ad, 
    maas,
    ROW_NUMBER() OVER (ORDER BY maas DESC) as sira
FROM calisanlar;
```
**Açıklama:** Her satıra benzersiz sıra numarası verir

### RANK()
```sql
SELECT 
    ad, 
    maas,
    RANK() OVER (ORDER BY maas DESC) as rank
FROM calisanlar;
```
**Açıklama:** Aynı değerlere aynı rank verir, sonraki rank atlanır

### DENSE_RANK()
```sql
SELECT 
    ad, 
    maas,
    DENSE_RANK() OVER (ORDER BY maas DESC) as dense_rank
FROM calisanlar;
```
**Açıklama:** Aynı değerlere aynı rank verir, sonraki rank atlanmaz

### LAG() ve LEAD()
```sql
SELECT 
    tarih,
    satis,
    LAG(satis, 1) OVER (ORDER BY tarih) as onceki_satis,
    LEAD(satis, 1) OVER (ORDER BY tarih) as sonraki_satis
FROM gunluk_satislar;
```
**Açıklama:** Önceki ve sonraki satırlardaki değerleri getirir

### PARTITION BY ile Gruplama
```sql
SELECT 
    departman,
    ad,
    maas,
    ROW_NUMBER() OVER (PARTITION BY departman ORDER BY maas DESC) as departman_sirasi
FROM calisanlar;
```
**Açıklama:** Her departman içinde ayrı sıralama yapar

### Running Total
```sql
SELECT 
    tarih,
    satis,
    SUM(satis) OVER (ORDER BY tarih) as toplam_satis
FROM gunluk_satislar;
```
**Açıklama:** Kümülatif toplam hesaplar

---

## 23. Common Table Expressions (CTE)

### Basit CTE
```sql
WITH yuksek_maasli AS (
    SELECT * FROM calisanlar WHERE maas > 5000
)
SELECT * FROM yuksek_maasli;
```
**Açıklama:** Geçici sonuç kümesi oluşturur

### Çoklu CTE
```sql
WITH 
    erkek_calisanlar AS (
        SELECT * FROM calisanlar WHERE cinsiyet = 'E'
    ),
    yuksek_maasli_erkekler AS (
        SELECT * FROM erkek_calisanlar WHERE maas > 5000
    )
SELECT * FROM yuksek_maasli_erkekler;
```
**Açıklama:** Birden fazla geçici tablo oluşturur

### Recursive CTE
```sql
WITH RECURSIVE hiyerarsi AS (
    -- Anchor member
    SELECT id, ad, yonetici_id, 1 as seviye
    FROM calisanlar
    WHERE yonetici_id IS NULL
    
    UNION ALL
    
    -- Recursive member
    SELECT c.id, c.ad, c.yonetici_id, h.seviye + 1
    FROM calisanlar c
    INNER JOIN hiyerarsi h ON c.yonetici_id = h.id
)
SELECT * FROM hiyerarsi;
```
**Açıklama:** Hiyerarşik veri yapılarını sorgular

---

## 24. Pivot ve Unpivot

### Pivot (Satırları Sütunlara Çevirme)
```sql
SELECT 
    departman,
    SUM(CASE WHEN yil = 2020 THEN satis END) as satis_2020,
    SUM(CASE WHEN yil = 2021 THEN satis END) as satis_2021,
    SUM(CASE WHEN yil = 2022 THEN satis END) as satis_2022
FROM yillik_satislar
GROUP BY departman;
```
**Açıklama:** Satır verilerini sütunlara dönüştürür

### Unpivot (Sütunları Satırlara Çevirme)
```sql
SELECT departman, '2020' as yil, satis_2020 as satis
FROM pivot_tablo
UNION ALL
SELECT departman, '2021' as yil, satis_2021 as satis
FROM pivot_tablo
UNION ALL
SELECT departman, '2022' as yil, satis_2022 as satis
FROM pivot_tablo;
```
**Açıklama:** Sütun verilerini satırlara dönüştürür

---

## 25. JSON İşlemleri

### JSON Veri Ekleme
```sql
CREATE TABLE kullanicilar (
    id INT PRIMARY KEY,
    ad VARCHAR(50),
    ozellikler JSON
);

INSERT INTO kullanicilar VALUES (1, 'Ahmet', '{"yas": 30, "sehir": "Istanbul", "hobiler": ["spor", "muzik"]}');
```
**Açıklama:** JSON veri tipi ile esnek veri saklama

### JSON Değer Çıkarma
```sql
SELECT 
    ad,
    JSON_EXTRACT(ozellikler, '$.yas') as yas,
    JSON_EXTRACT(ozellikler, '$.sehir') as sehir
FROM kullanicilar;
```
**Açıklama:** JSON'dan belirli değerleri çıkarır

### JSON Path Sözdizimi
```sql
SELECT 
    ozellikler->'$.yas' as yas,
    ozellikler->'$.hobiler[0]' as ilk_hobi,
    ozellikler->'$.hobiler' as tum_hobiler
FROM kullanicilar;
```
**Açıklama:** JSON path ile değer erişimi

### JSON Güncelleme
```sql
UPDATE kullanicilar 
SET ozellikler = JSON_SET(ozellikler, '$.yas', 31)
WHERE id = 1;
```
**Açıklama:** JSON içindeki değerleri günceller

### JSON Arama
```sql
SELECT * FROM kullanicilar 
WHERE JSON_CONTAINS(ozellikler, '"spor"', '$.hobiler');
```
**Açıklama:** JSON içinde değer arar

---

## 26. Regular Expressions

### REGEXP Operatörü
```sql
SELECT * FROM musteriler WHERE ad REGEXP '^A.*n$';
SELECT * FROM musteriler WHERE telefon REGEXP '^[0-9]{10}$';
```
**Açıklama:** Düzenli ifadelerle arama

### Regex Fonksiyonları
```sql
SELECT 
    REGEXP_REPLACE(ad, '([A-Z])', ' $1') as formatli_ad,
    REGEXP_SUBSTR(email, '@[^.]+') as domain
FROM kullanicilar;
```
**Açıklama:** Regex ile metin işleme

### Yaygın Regex Kalıpları
```sql
-- Email doğrulama
WHERE email REGEXP '^[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Za-z]{2,}$'

-- Telefon doğrulama
WHERE telefon REGEXP '^[0-9]{3}-[0-9]{3}-[0-9]{4}$'

-- URL doğrulama
WHERE url REGEXP '^https?://[^\s/$.?#].[^\s]*$'
```

---

## 27. Temporal Tables

### System Versioned Tables
```sql
CREATE TABLE urunler (
    id INT PRIMARY KEY,
    ad VARCHAR(100),
    fiyat DECIMAL(10,2),
    valid_from TIMESTAMP GENERATED ALWAYS AS ROW START,
    valid_to TIMESTAMP GENERATED ALWAYS AS ROW END,
    PERIOD FOR SYSTEM_TIME (valid_from, valid_to)
) WITH SYSTEM VERSIONING;
```
**Açıklama:** Zaman bazlı veri değişikliklerini takip eder

### Geçmiş Veri Sorgulama
```sql
-- Mevcut veri
SELECT * FROM urunler FOR SYSTEM_TIME AS OF CURRENT_TIMESTAMP;

-- Belirli tarihteki veri
SELECT * FROM urunler FOR SYSTEM_TIME AS OF '2023-01-01 10:00:00';

-- Değişiklik geçmişi
SELECT * FROM urunler FOR SYSTEM_TIME ALL;
```
**Açıklama:** Zaman içindeki veri değişikliklerini görüntüler

---

## 28. Partitioning

### Range Partitioning
```sql
CREATE TABLE siparisler (
    id INT,
    musteri_id INT,
    siparis_tarihi DATE,
    tutar DECIMAL(10,2)
)
PARTITION BY RANGE (YEAR(siparis_tarihi)) (
    PARTITION p2020 VALUES LESS THAN (2021),
    PARTITION p2021 VALUES LESS THAN (2022),
    PARTITION p2022 VALUES LESS THAN (2023),
    PARTITION p_future VALUES LESS THAN MAXVALUE
);
```
**Açıklama:** Veriyi aralıklara göre böler

### Hash Partitioning
```sql
CREATE TABLE kullanicilar (
    id INT,
    ad VARCHAR(50),
    email VARCHAR(100)
)
PARTITION BY HASH(id) PARTITIONS 4;
```
**Açıklama:** Hash fonksiyonu ile veriyi böler

### List Partitioning
```sql
CREATE TABLE satislar (
    id INT,
    bolge VARCHAR(20),
    tutar DECIMAL(10,2)
)
PARTITION BY LIST COLUMNS(bolge) (
    PARTITION p_istanbul VALUES IN ('Istanbul'),
    PARTITION p_ankara VALUES IN ('Ankara'),
    PARTITION p_izmir VALUES IN ('Izmir'),
    PARTITION p_diger VALUES IN ('Bursa', 'Antalya', 'Adana')
);
```
**Açıklama:** Belirli değerlere göre veriyi böler

---

## 29. Replication

### Master-Slave Replication
```sql
-- Master sunucuda
GRANT REPLICATION SLAVE ON *.* TO 'repl_user'@'%' IDENTIFIED BY 'password';
SHOW MASTER STATUS;

-- Slave sunucuda
CHANGE MASTER TO
    MASTER_HOST='master_ip',
    MASTER_USER='repl_user',
    MASTER_PASSWORD='password',
    MASTER_LOG_FILE='mysql-bin.000001',
    MASTER_LOG_POS=154;
START SLAVE;
```
**Açıklama:** Veri kopyalama ve yük dengeleme

### Replication Monitoring
```sql
SHOW SLAVE STATUS\G
SHOW PROCESSLIST;
```
**Açıklama:** Replication durumunu kontrol eder

---

## 30. Security ve Encryption

### Veri Şifreleme
```sql
-- AES şifreleme
SELECT AES_ENCRYPT('gizli_veri', 'anahtar') as sifreli_veri;
SELECT AES_DECRYPT(sifreli_veri, 'anahtar') as orijinal_veri;

-- MD5 hash
SELECT MD5('sifre') as hash_sifre;

-- SHA2 hash
SELECT SHA2('sifre', 256) as sha256_hash;
```
**Açıklama:** Veri güvenliği için şifreleme

### SSL Bağlantısı
```sql
-- SSL sertifikası ile bağlantı
mysql --ssl-ca=ca.pem --ssl-cert=client-cert.pem --ssl-key=client-key.pem
```
**Açıklama:** Güvenli bağlantı kurulumu

### Audit Logging
```sql
-- Audit log etkinleştirme
SET GLOBAL audit_log = ON;
SET GLOBAL audit_log_file = '/var/log/mysql/audit.log';
```
**Açıklama:** Veritabanı aktivitelerini kaydetme

---

## 31. Monitoring ve Logging

### Performance Schema
```sql
-- Aktif bağlantıları görüntüleme
SELECT * FROM performance_schema.threads;

-- Sorgu istatistikleri
SELECT * FROM performance_schema.events_statements_summary_by_digest;

-- Tablo I/O istatistikleri
SELECT * FROM performance_schema.table_io_waits_summary_by_table;
```
**Açıklama:** Performans izleme

### Slow Query Log
```sql
-- Slow query log etkinleştirme
SET GLOBAL slow_query_log = ON;
SET GLOBAL long_query_time = 2;
SET GLOBAL slow_query_log_file = '/var/log/mysql/slow.log';
```
**Açıklama:** Yavaş sorguları kaydetme

### Error Log
```sql
-- Error log konumu
SHOW VARIABLES LIKE 'log_error';
```
**Açıklama:** Hata kayıtlarını görüntüleme

---

## 32. Advanced SQL Patterns

### Hierarchical Data (Nested Sets)
```sql
CREATE TABLE kategoriler (
    id INT PRIMARY KEY,
    ad VARCHAR(100),
    left_bound INT,
    right_bound INT
);

-- Alt kategorileri getirme
SELECT * FROM kategoriler 
WHERE left_bound > 2 AND right_bound < 9;
```
**Açıklama:** Hiyerarşik veri yapıları

### Pivot Table Pattern
```sql
SELECT 
    departman,
    SUM(CASE WHEN ay = 1 THEN satis END) as ocak,
    SUM(CASE WHEN ay = 2 THEN satis END) as subat,
    SUM(CASE WHEN ay = 3 THEN satis END) as mart
FROM aylik_satislar
GROUP BY departman;
```
**Açıklama:** Dinamik pivot tablolar

### Gaps and Islands
```sql
-- Eksik değerleri bulma
WITH sayilar AS (
    SELECT 1 as n UNION ALL SELECT 2 UNION ALL SELECT 3 UNION ALL SELECT 4 UNION ALL SELECT 5
)
SELECT s.n as eksik_sayi
FROM sayilar s
LEFT JOIN tablo t ON s.n = t.id
WHERE t.id IS NULL;
```
**Açıklama:** Eksik veri tespiti

---

## 33. SQL Best Practices

### Naming Conventions
```sql
-- Tablo adları: çoğul, küçük harf, alt çizgi
CREATE TABLE kullanicilar ();

-- Sütun adları: tekil, küçük harf, alt çizgi
CREATE TABLE siparisler (
    id INT PRIMARY KEY,
    musteri_id INT,
    siparis_tarihi TIMESTAMP
);

-- İndeks adları: tablo_sutun_idx
CREATE INDEX kullanicilar_email_idx ON kullanicilar(email);
```
**Açıklama:** Tutarlı isimlendirme kuralları

### Query Optimization
```sql
-- SELECT * yerine gerekli sütunları belirt
SELECT id, ad, email FROM kullanicilar;

-- LIMIT kullan
SELECT * FROM buyuk_tablo LIMIT 1000;

-- WHERE koşullarında indeksli sütunlar kullan
SELECT * FROM kullanicilar WHERE email = 'test@example.com';
```
**Açıklama:** Sorgu performansı için ipuçları

### Data Integrity
```sql
-- Foreign key kısıtlamaları
ALTER TABLE siparisler 
ADD CONSTRAINT fk_musteri 
FOREIGN KEY (musteri_id) REFERENCES musteriler(id);

-- Check kısıtlamaları
ALTER TABLE urunler 
ADD CONSTRAINT chk_fiyat 
CHECK (fiyat > 0);
```
**Açıklama:** Veri bütünlüğü sağlama

---

## 34. Database Design Patterns

### Normalization
```sql
-- 1NF: Atomic values
CREATE TABLE kullanicilar (
    id INT PRIMARY KEY,
    ad VARCHAR(50),
    soyad VARCHAR(50)
);

-- 2NF: No partial dependencies
CREATE TABLE siparisler (
    id INT PRIMARY KEY,
    musteri_id INT,
    urun_id INT,
    miktar INT,
    FOREIGN KEY (musteri_id) REFERENCES musteriler(id),
    FOREIGN KEY (urun_id) REFERENCES urunler(id)
);

-- 3NF: No transitive dependencies
CREATE TABLE sehirler (
    id INT PRIMARY KEY,
    ad VARCHAR(50)
);

CREATE TABLE musteriler (
    id INT PRIMARY KEY,
    ad VARCHAR(50),
    sehir_id INT,
    FOREIGN KEY (sehir_id) REFERENCES sehirler(id)
);
```
**Açıklama:** Veritabanı normalizasyon kuralları

### Star Schema
```sql
-- Fact table
CREATE TABLE satis_fact (
    id INT PRIMARY KEY,
    musteri_id INT,
    urun_id INT,
    tarih_id INT,
    miktar INT,
    tutar DECIMAL(10,2)
);

-- Dimension tables
CREATE TABLE musteri_dim (
    id INT PRIMARY KEY,
    ad VARCHAR(50),
    sehir VARCHAR(50)
);

CREATE TABLE urun_dim (
    id INT PRIMARY KEY,
    ad VARCHAR(100),
    kategori VARCHAR(50)
);

CREATE TABLE tarih_dim (
    id INT PRIMARY KEY,
    tarih DATE,
    ay VARCHAR(20),
    yil INT
);
```
**Açıklama:** Data warehouse tasarım pattern'i

---

## 35. SQL Injection Prevention

### Prepared Statements
```sql
-- Güvenli sorgu
PREPARE stmt FROM 'SELECT * FROM kullanicilar WHERE id = ?';
SET @id = 1;
EXECUTE stmt USING @id;
DEALLOCATE PREPARE stmt;
```
**Açıklama:** SQL injection saldırılarını önler

### Parameterized Queries
```sql
-- PHP örneği
$stmt = $pdo->prepare("SELECT * FROM kullanicilar WHERE email = ?");
$stmt->execute([$email]);
```
**Açıklama:** Parametreli sorgular kullanma

### Input Validation
```sql
-- Girdi doğrulama
SELECT * FROM kullanicilar 
WHERE email REGEXP '^[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Za-z]{2,}$'
AND LENGTH(email) <= 100;
```
**Açıklama:** Girdi verilerini doğrulama

---

## 36. Performance Tuning

### Query Execution Plan
```sql
-- EXPLAIN ile sorgu analizi
EXPLAIN SELECT * FROM kullanicilar WHERE email = 'test@example.com';

-- EXPLAIN ANALYZE (PostgreSQL)
EXPLAIN (ANALYZE, BUFFERS) SELECT * FROM kullanicilar;
```
**Açıklama:** Sorgu performansını analiz etme

### Index Optimization
```sql
-- Composite index
CREATE INDEX idx_kullanici_email_aktif ON kullanicilar(email, aktif);

-- Covering index
CREATE INDEX idx_kullanici_cover ON kullanicilar(email, ad, soyad);

-- Partial index
CREATE INDEX idx_aktif_kullanicilar ON kullanicilar(email) WHERE aktif = 1;
```
**Açıklama:** İndeks optimizasyonu

### Query Rewriting
```sql
-- IN yerine EXISTS kullan
SELECT * FROM musteriler m 
WHERE EXISTS (SELECT 1 FROM siparisler s WHERE s.musteri_id = m.id);

-- DISTINCT yerine GROUP BY
SELECT musteri_id FROM siparisler GROUP BY musteri_id;
```
**Açıklama:** Sorgu yeniden yazma teknikleri

---

## 37. Database Migration

### Schema Migration
```sql
-- Version control için migration tablosu
CREATE TABLE schema_migrations (
    version VARCHAR(255) PRIMARY KEY,
    applied_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Migration örneği
-- 001_create_users_table.sql
CREATE TABLE kullanicilar (
    id INT PRIMARY KEY AUTO_INCREMENT,
    ad VARCHAR(50) NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

INSERT INTO schema_migrations (version) VALUES ('001_create_users_table');
```
**Açıklama:** Veritabanı şema değişikliklerini yönetme

### Data Migration
```sql
-- Veri taşıma
INSERT INTO yeni_tablo (id, ad, email)
SELECT id, ad, email FROM eski_tablo;

-- Batch processing
SET @batch_size = 1000;
SET @offset = 0;

REPEAT
    INSERT INTO hedef_tablo (sutun1, sutun2)
    SELECT sutun1, sutun2 FROM kaynak_tablo
    LIMIT @batch_size OFFSET @offset;
    
    SET @offset = @offset + @batch_size;
    
    SELECT SLEEP(0.1); -- Rate limiting
UNTIL ROW_COUNT() < @batch_size END REPEAT;
```
**Açıklama:** Büyük veri setlerini taşıma

---

## 38. Data Warehousing

### ETL Process
```sql
-- Extract: Veri çıkarma
CREATE TABLE staging_satislar AS
SELECT * FROM kaynak_sistem.satislar;

-- Transform: Veri dönüştürme
CREATE TABLE dim_musteriler AS
SELECT 
    musteri_id,
    ad,
    soyad,
    CASE 
        WHEN yas < 25 THEN 'Genç'
        WHEN yas < 50 THEN 'Orta'
        ELSE 'Yaşlı'
    END as yas_grubu
FROM staging_musteriler;

-- Load: Veri yükleme
INSERT INTO fact_satislar (musteri_id, urun_id, tarih_id, tutar)
SELECT 
    s.musteri_id,
    s.urun_id,
    d.id as tarih_id,
    s.tutar
FROM staging_satislar s
JOIN dim_tarihler d ON DATE(s.siparis_tarihi) = d.tarih;
```
**Açıklama:** ETL süreçleri

### OLAP Operations
```sql
-- Roll-up (Yukarı toplama)
SELECT 
    yil,
    ay,
    SUM(satis) as toplam_satis
FROM fact_satislar f
JOIN dim_tarihler t ON f.tarih_id = t.id
GROUP BY yil, ay WITH ROLLUP;

-- Drill-down (Aşağı detaylandırma)
SELECT 
    yil,
    ay,
    gun,
    SUM(satis) as toplam_satis
FROM fact_satislar f
JOIN dim_tarihler t ON f.tarih_id = t.id
WHERE yil = 2023 AND ay = 1
GROUP BY yil, ay, gun;

-- Slice (Dilimleme)
SELECT 
    musteri_kategori,
    SUM(satis) as toplam_satis
FROM fact_satislar f
JOIN dim_musteriler m ON f.musteri_id = m.id
WHERE yil = 2023
GROUP BY musteri_kategori;
```
**Açıklama:** OLAP operasyonları

---

## 39. Big Data SQL

### Distributed Queries
```sql
-- Sharding örneği
SELECT * FROM kullanicilar_2023 WHERE id BETWEEN 1 AND 1000000
UNION ALL
SELECT * FROM kullanicilar_2024 WHERE id BETWEEN 1000001 AND 2000000;
```
**Açıklama:** Dağıtık sorgular

### MapReduce Pattern
```sql
-- Map: Veriyi grupla
WITH map_result AS (
    SELECT 
        departman,
        COUNT(*) as calisan_sayisi,
        AVG(maas) as ortalama_maas
    FROM calisanlar
    GROUP BY departman
)
-- Reduce: Sonuçları topla
SELECT 
    'Toplam' as kategori,
    SUM(calisan_sayisi) as toplam_calisan,
    AVG(ortalama_maas) as genel_ortalama
FROM map_result;
```
**Açıklama:** MapReduce pattern'i SQL'de

### Streaming Queries
```sql
-- Window functions ile streaming
SELECT 
    zaman_damgasi,
    urun_id,
    satis_miktari,
    SUM(satis_miktari) OVER (
        ORDER BY zaman_damgasi 
        ROWS BETWEEN 5 PRECEDING AND CURRENT ROW
    ) as son_5_dakika_toplam
FROM gercek_zamanli_satislar;
```
**Açıklama:** Gerçek zamanlı veri işleme

---

## 40. Cloud Database Services

### AWS RDS
```sql
-- RDS bağlantı örneği
-- Endpoint: my-db.123456789012.us-east-1.rds.amazonaws.com
-- Port: 3306

-- Backup ve restore
-- Automated backups
-- Point-in-time recovery
-- Multi-AZ deployment
```
**Açıklama:** AWS RDS kullanımı

### Google Cloud SQL
```sql
-- Cloud SQL özellikleri
-- Automatic backups
-- High availability
-- Read replicas
-- Cloud SQL Proxy
```
**Açıklama:** Google Cloud SQL kullanımı

### Azure SQL Database
```sql
-- Azure SQL özellikleri
-- Elastic pools
-- Geo-replication
-- Advanced threat protection
-- Built-in intelligence
```
**Açıklama:** Azure SQL Database kullanımı

### Serverless Databases
```sql
-- Aurora Serverless
-- DynamoDB
-- Firestore
-- Cosmos DB
```
**Açıklama:** Serverless veritabanı hizmetleri

---

## 41. MERGE Statement (UPSERT)

### MERGE Syntax
```sql
MERGE INTO hedef_tablo AS target
USING kaynak_tablo AS source
ON target.id = source.id
WHEN MATCHED THEN
    UPDATE SET 
        target.ad = source.ad,
        target.email = source.email,
        target.guncelleme_tarihi = NOW()
WHEN NOT MATCHED THEN
    INSERT (id, ad, email, kayit_tarihi)
    VALUES (source.id, source.ad, source.email, NOW());
```
**Açıklama:** INSERT ve UPDATE işlemlerini tek komutta yapar

### MySQL INSERT ... ON DUPLICATE KEY UPDATE
```sql
INSERT INTO kullanicilar (id, ad, email) 
VALUES (1, 'Ahmet', 'ahmet@email.com')
ON DUPLICATE KEY UPDATE 
    ad = VALUES(ad),
    email = VALUES(email),
    guncelleme_tarihi = NOW();
```
**Açıklama:** MySQL'de UPSERT işlemi

### PostgreSQL INSERT ... ON CONFLICT
```sql
INSERT INTO kullanicilar (id, ad, email) 
VALUES (1, 'Ahmet', 'ahmet@email.com')
ON CONFLICT (id) DO UPDATE SET 
    ad = EXCLUDED.ad,
    email = EXCLUDED.email,
    guncelleme_tarihi = NOW();
```
**Açıklama:** PostgreSQL'de UPSERT işlemi

---

## 42. FULLTEXT Search

### FULLTEXT Index Oluşturma
```sql
CREATE TABLE makaleler (
    id INT PRIMARY KEY,
    baslik VARCHAR(200),
    icerik TEXT,
    FULLTEXT(baslik, icerik)
);
```
**Açıklama:** Metin arama için indeks oluşturur

### FULLTEXT Search Kullanımı
```sql
-- Doğal dil arama
SELECT * FROM makaleler 
WHERE MATCH(baslik, icerik) AGAINST('veritabanı yönetimi' IN NATURAL LANGUAGE MODE);

-- Boolean arama
SELECT * FROM makaleler 
WHERE MATCH(baslik, icerik) AGAINST('+veritabanı -oracle' IN BOOLEAN MODE);

-- Query expansion
SELECT * FROM makaleler 
WHERE MATCH(baslik, icerik) AGAINST('veritabanı' WITH QUERY EXPANSION);
```
**Açıklama:** Gelişmiş metin arama özellikleri

---

## 43. Spatial Data (Coğrafi Veri)

### Spatial Data Types
```sql
CREATE TABLE lokasyonlar (
    id INT PRIMARY KEY,
    ad VARCHAR(100),
    konum POINT,
    alan POLYGON,
    yol LINESTRING
);
```
**Açıklama:** Coğrafi veri tipleri

### Spatial Functions
```sql
-- Nokta oluşturma
INSERT INTO lokasyonlar (id, ad, konum) 
VALUES (1, 'İstanbul', POINT(28.9784, 41.0082));

-- Mesafe hesaplama
SELECT 
    a.ad, b.ad,
    ST_Distance(a.konum, b.konum) as mesafe
FROM lokasyonlar a, lokasyonlar b
WHERE a.id != b.id;

-- Alan içinde arama
SELECT * FROM lokasyonlar 
WHERE ST_Contains(alan, POINT(28.9784, 41.0082));
```
**Açıklama:** Coğrafi veri işlemleri

---

## 44. Materialized Views

### Materialized View Oluşturma
```sql
-- PostgreSQL
CREATE MATERIALIZED VIEW gunluk_satis_ozeti AS
SELECT 
    DATE(siparis_tarihi) as tarih,
    COUNT(*) as siparis_sayisi,
    SUM(tutar) as toplam_tutar
FROM siparisler
GROUP BY DATE(siparis_tarihi);

-- Yenileme
REFRESH MATERIALIZED VIEW gunluk_satis_ozeti;
```
**Açıklama:** Fiziksel olarak saklanan görünümler

### MySQL'de Materialized View Benzeri
```sql
-- Tablo olarak materialized view
CREATE TABLE gunluk_satis_ozeti AS
SELECT 
    DATE(siparis_tarihi) as tarih,
    COUNT(*) as siparis_sayisi,
    SUM(tutar) as toplam_tutar
FROM siparisler
GROUP BY DATE(siparis_tarihi);

-- Güncelleme
TRUNCATE TABLE gunluk_satis_ozeti;
INSERT INTO gunluk_satis_ozeti
SELECT 
    DATE(siparis_tarihi) as tarih,
    COUNT(*) as siparis_sayisi,
    SUM(tutar) as toplam_tutar
FROM siparisler
GROUP BY DATE(siparis_tarihi);
```
**Açıklama:** MySQL'de materialized view implementasyonu

---

## 45. Database Events (Zamanlanmış Görevler)

### Event Oluşturma
```sql
-- Event scheduler'ı etkinleştir
SET GLOBAL event_scheduler = ON;

-- Günlük event
CREATE EVENT gunluk_temizlik
ON SCHEDULE EVERY 1 DAY
STARTS CURRENT_TIMESTAMP
DO
    DELETE FROM gecici_veriler WHERE tarih < DATE_SUB(NOW(), INTERVAL 7 DAY);

-- Belirli saatte çalışan event
CREATE EVENT haftalik_rapor
ON SCHEDULE EVERY 1 WEEK
STARTS '2023-01-01 00:00:00'
DO
    CALL haftalik_rapor_olustur();
```
**Açıklama:** Zamanlanmış veritabanı görevleri

### Event Yönetimi
```sql
-- Event'leri listele
SHOW EVENTS;

-- Event'i devre dışı bırak
ALTER EVENT gunluk_temizlik DISABLE;

-- Event'i sil
DROP EVENT gunluk_temizlik;
```
**Açıklama:** Event yönetimi komutları

---

## 46. Cursors (İmleçler)

### Cursor Tanımlama
```sql
DELIMITER //
CREATE PROCEDURE cursor_ornegi()
BEGIN
    DECLARE done INT DEFAULT FALSE;
    DECLARE musteri_id INT;
    DECLARE musteri_adi VARCHAR(100);
    
    -- Cursor tanımla
    DECLARE musteri_cursor CURSOR FOR 
        SELECT id, ad FROM musteriler;
    
    -- Handler tanımla
    DECLARE CONTINUE HANDLER FOR NOT FOUND SET done = TRUE;
    
    -- Cursor'ı aç
    OPEN musteri_cursor;
    
    read_loop: LOOP
        FETCH musteri_cursor INTO musteri_id, musteri_adi;
        IF done THEN
            LEAVE read_loop;
        END IF;
        
        -- İşlem yap
        INSERT INTO islem_log (musteri_id, islem) 
        VALUES (musteri_id, CONCAT('İşlem yapıldı: ', musteri_adi));
    END LOOP;
    
    -- Cursor'ı kapat
    CLOSE musteri_cursor;
END //
DELIMITER ;
```
**Açıklama:** Satır satır veri işleme

---

## 47. Error Handling (Hata Yönetimi)

### Handler Tanımlama
```sql
DELIMITER //
CREATE PROCEDURE hata_yonetimi_ornegi()
BEGIN
    DECLARE EXIT HANDLER FOR SQLEXCEPTION
    BEGIN
        ROLLBACK;
        SELECT 'Hata oluştu, işlem geri alındı' as mesaj;
    END;
    
    DECLARE CONTINUE HANDLER FOR SQLWARNING
    BEGIN
        SELECT 'Uyarı oluştu' as mesaj;
    END;
    
    START TRANSACTION;
        INSERT INTO tablo1 VALUES (1, 'test');
        INSERT INTO tablo2 VALUES (1, 'test');
    COMMIT;
END //
DELIMITER ;
```
**Açıklama:** Hata yakalama ve yönetimi

### SIGNAL ve RESIGNAL
```sql
-- Özel hata fırlatma
CREATE PROCEDURE kullanici_kontrol(p_id INT)
BEGIN
    IF p_id <= 0 THEN
        SIGNAL SQLSTATE '45000'
        SET MESSAGE_TEXT = 'Geçersiz kullanıcı ID';
    END IF;
    
    SELECT * FROM kullanicilar WHERE id = p_id;
END;
```
**Açıklama:** Özel hata mesajları

---

## 48. Dynamic SQL

### Prepared Statements ile Dinamik SQL
```sql
DELIMITER //
CREATE PROCEDURE dinamik_sorgu(p_tablo_adi VARCHAR(100))
BEGIN
    SET @sql = CONCAT('SELECT * FROM ', p_tablo_adi, ' LIMIT 10');
    PREPARE stmt FROM @sql;
    EXECUTE stmt;
    DEALLOCATE PREPARE stmt;
END //
DELIMITER ;
```
**Açıklama:** Çalışma zamanında SQL oluşturma

### Conditional SQL
```sql
CREATE PROCEDURE kosullu_sorgu(
    p_departman VARCHAR(50),
    p_min_maas DECIMAL(10,2)
)
BEGIN
    SET @sql = 'SELECT * FROM calisanlar WHERE 1=1';
    
    IF p_departman IS NOT NULL THEN
        SET @sql = CONCAT(@sql, ' AND departman = ''', p_departman, '''');
    END IF;
    
    IF p_min_maas IS NOT NULL THEN
        SET @sql = CONCAT(@sql, ' AND maas >= ', p_min_maas);
    END IF;
    
    PREPARE stmt FROM @sql;
    EXECUTE stmt;
    DEALLOCATE PREPARE stmt;
END;
```
**Açıklama:** Koşullu SQL oluşturma

---

## 49. Database Variables ve System Variables

### User Variables
```sql
-- Değişken tanımlama
SET @kullanici_adi = 'Ahmet';
SET @toplam_satis = (SELECT SUM(tutar) FROM siparisler);

-- Değişken kullanma
SELECT @kullanici_adi as kullanici, @toplam_satis as toplam;

-- INTO ile değişkene atama
SELECT COUNT(*) INTO @kullanici_sayisi FROM kullanicilar;
```
**Açıklama:** Kullanıcı değişkenleri

### System Variables
```sql
-- Sistem değişkenlerini görüntüleme
SHOW VARIABLES LIKE 'max_connections';
SHOW VARIABLES LIKE 'innodb_buffer_pool_size';

-- Sistem değişkenini değiştirme
SET GLOBAL max_connections = 200;
SET SESSION sql_mode = 'STRICT_TRANS_TABLES';
```
**Açıklama:** Sistem değişkenleri yönetimi

---

## 50. Advanced Data Types

### ENUM ve SET
```sql
-- ENUM: Tek değer seçimi
CREATE TABLE kullanicilar (
    id INT PRIMARY KEY,
    ad VARCHAR(50),
    durum ENUM('aktif', 'pasif', 'askida') DEFAULT 'aktif'
);

-- SET: Çoklu değer seçimi
CREATE TABLE urunler (
    id INT PRIMARY KEY,
    ad VARCHAR(100),
    etiketler SET('yeni', 'populer', 'indirimli', 'stokta_yok')
);
```
**Açıklama:** Özel veri tipleri

### BLOB ve LONGTEXT
```sql
-- Binary data
CREATE TABLE dosyalar (
    id INT PRIMARY KEY,
    dosya_adi VARCHAR(100),
    dosya_verisi LONGBLOB,
    dosya_boyutu INT
);

-- Uzun metin
CREATE TABLE makaleler (
    id INT PRIMARY KEY,
    baslik VARCHAR(200),
    icerik LONGTEXT,
    ozet TEXT
);
```
**Açıklama:** Büyük veri tipleri

---

## 51. Database Optimization Techniques

### Query Cache
```sql
-- Query cache durumu
SHOW VARIABLES LIKE 'query_cache%';

-- Query cache istatistikleri
SHOW STATUS LIKE 'Qcache%';
```
**Açıklama:** Sorgu önbelleği

### Table Compression
```sql
-- Tablo sıkıştırma
CREATE TABLE buyuk_tablo (
    id INT PRIMARY KEY,
    veri TEXT
) ROW_FORMAT=COMPRESSED KEY_BLOCK_SIZE=8;
```
**Açıklama:** Tablo sıkıştırma

### Partition Pruning
```sql
-- Partition pruning için sorgu
SELECT * FROM siparisler 
WHERE siparis_tarihi >= '2023-01-01' 
AND siparis_tarihi < '2023-02-01';
```
**Açıklama:** Partition filtreleme

---

## 52. Database Maintenance

### Table Maintenance
```sql
-- Tablo analizi
ANALYZE TABLE kullanicilar;

-- Tablo kontrolü
CHECK TABLE kullanicilar;

-- Tablo onarımı
REPAIR TABLE kullanicilar;

-- Tablo optimizasyonu
OPTIMIZE TABLE kullanicilar;
```
**Açıklama:** Tablo bakım işlemleri

### Index Maintenance
```sql
-- İndeks yeniden oluşturma
ALTER TABLE kullanicilar DROP INDEX email_idx;
CREATE INDEX email_idx ON kullanicilar(email);

-- İndeks istatistikleri
SHOW INDEX FROM kullanicilar;
```
**Açıklama:** İndeks bakımı

---

## 53. Database Monitoring ve Diagnostics

### Performance Monitoring
```sql
-- Aktif bağlantılar
SHOW PROCESSLIST;

-- InnoDB durumu
SHOW ENGINE INNODB STATUS;

-- Tablo istatistikleri
SELECT 
    table_name,
    table_rows,
    data_length,
    index_length
FROM information_schema.tables 
WHERE table_schema = DATABASE();
```
**Açıklama:** Performans izleme

### Lock Monitoring
```sql
-- Kilit durumu
SHOW STATUS LIKE 'Table_locks%';

-- InnoDB kilitleri
SELECT * FROM information_schema.INNODB_LOCKS;
SELECT * FROM information_schema.INNODB_LOCK_WAITS;
```
**Açıklama:** Kilit izleme

---

## 54. Database Backup Strategies

### Logical Backup
```sql
-- Belirli tabloları yedekleme
mysqldump -u root -p veritabani tablo1 tablo2 > yedek.sql

-- Sadece veri yapısı
mysqldump -u root -p --no-data veritabani > yapi.sql

-- Sadece veri
mysqldump -u root -p --no-create-info veritabani > veri.sql
```
**Açıklama:** Mantıksal yedekleme

### Physical Backup
```sql
-- InnoDB hot backup
-- Percona XtraBackup kullanımı
-- MySQL Enterprise Backup
```
**Açıklama:** Fiziksel yedekleme

---

## 55. Database Recovery

### Point-in-Time Recovery
```sql
-- Binary log'dan kurtarma
mysqlbinlog --start-datetime="2023-01-01 10:00:00" \
           --stop-datetime="2023-01-01 11:00:00" \
           mysql-bin.000001 | mysql -u root -p
```
**Açıklama:** Belirli zamana geri dönme

### Disaster Recovery
```sql
-- Master-slave replikasyon ile kurtarma
-- Otomatik failover
-- Geographic redundancy
```
**Açıklama:** Felaket kurtarma

---

## 56. Database Security Best Practices

### Password Policies
```sql
-- Güçlü şifre politikası
SET GLOBAL validate_password.policy=MEDIUM;
SET GLOBAL validate_password.length=8;
```
**Açıklama:** Şifre politikaları

### SSL/TLS Configuration
```sql
-- SSL sertifikası ile bağlantı
mysql --ssl-ca=ca.pem --ssl-cert=client-cert.pem --ssl-key=client-key.pem
```
**Açıklama:** Güvenli bağlantı

### Audit Logging
```sql
-- Audit log etkinleştirme
SET GLOBAL audit_log = ON;
SET GLOBAL audit_log_file = '/var/log/mysql/audit.log';
```
**Açıklama:** Denetim kayıtları

---

## 57. Database Scalability

### Read Replicas
```sql
-- Read-only replica
-- Load balancing
-- Geographic distribution
```
**Açıklama:** Okuma replikaları

### Sharding
```sql
-- Horizontal partitioning
-- Vertical partitioning
-- Distributed queries
```
**Açıklama:** Veri bölümleme

---

## 58. Database Integration

### External Data Sources
```sql
-- Federated tables
CREATE TABLE uzak_tablo (
    id INT PRIMARY KEY
) ENGINE=FEDERATED 
CONNECTION='mysql://kullanici:sifre@sunucu:3306/veritabani/tablo';

-- External data wrappers
```
**Açıklama:** Dış veri kaynakları

### API Integration
```sql
-- REST API ile entegrasyon
-- GraphQL entegrasyonu
-- Microservices ile entegrasyon
```
**Açıklama:** API entegrasyonu

---

## 59. Database Testing

### Unit Testing
```sql
-- Stored procedure test
DELIMITER //
CREATE PROCEDURE test_kullanici_ekleme()
BEGIN
    DECLARE test_id INT;
    
    -- Test verisi ekle
    INSERT INTO kullanicilar (ad, email) VALUES ('Test', 'test@test.com');
    SET test_id = LAST_INSERT_ID();
    
    -- Test kontrolü
    IF EXISTS(SELECT 1 FROM kullanicilar WHERE id = test_id) THEN
        SELECT 'Test başarılı' as sonuc;
    ELSE
        SIGNAL SQLSTATE '45000' SET MESSAGE_TEXT = 'Test başarısız';
    END IF;
    
    -- Test verisini temizle
    DELETE FROM kullanicilar WHERE id = test_id;
END //
DELIMITER ;
```
**Açıklama:** Birim testleri

### Performance Testing
```sql
-- Load testing
-- Stress testing
-- Benchmark testing
```
**Açıklama:** Performans testleri

---

## 60. Database Documentation

### Schema Documentation
```sql
-- Tablo açıklamaları
ALTER TABLE kullanicilar COMMENT = 'Sistem kullanıcıları tablosu';

-- Sütun açıklamaları
ALTER TABLE kullanicilar MODIFY COLUMN email VARCHAR(100) COMMENT 'Kullanıcı email adresi';

-- Açıklamaları görüntüleme
SELECT 
    table_name,
    table_comment
FROM information_schema.tables 
WHERE table_schema = DATABASE();
```
**Açıklama:** Şema dokümantasyonu

### Data Dictionary
```sql
-- Veri sözlüğü oluşturma
SELECT 
    t.table_name,
    c.column_name,
    c.data_type,
    c.column_default,
    c.is_nullable,
    c.column_comment
FROM information_schema.tables t
JOIN information_schema.columns c ON t.table_name = c.table_name
WHERE t.table_schema = DATABASE()
ORDER BY t.table_name, c.ordinal_position;
```
**Açıklama:** Veri sözlüğü

---

## 61. Graph Databases ve SQL

### Graph Data Types (PostgreSQL)
```sql
-- Graph veri tipi
CREATE TABLE graph_nodes (
    id SERIAL PRIMARY KEY,
    properties JSONB
);

CREATE TABLE graph_edges (
    id SERIAL PRIMARY KEY,
    source_id INTEGER REFERENCES graph_nodes(id),
    target_id INTEGER REFERENCES graph_nodes(id),
    properties JSONB
);
```
**Açıklama:** Graph veritabanı yapısı

### Graph Queries
```sql
-- Recursive CTE ile graph traversal
WITH RECURSIVE graph_path AS (
    -- Anchor: başlangıç düğümü
    SELECT id, properties, 0 as depth
    FROM graph_nodes
    WHERE id = 1
    
    UNION ALL
    
    -- Recursive: komşu düğümler
    SELECT n.id, n.properties, gp.depth + 1
    FROM graph_nodes n
    JOIN graph_edges e ON n.id = e.target_id
    JOIN graph_path gp ON e.source_id = gp.id
    WHERE gp.depth < 3
)
SELECT * FROM graph_path;
```
**Açıklama:** Graph sorguları

---

## 62. Machine Learning SQL

### Statistical Functions
```sql
-- Korelasyon hesaplama
SELECT 
    CORR(maas, deneyim_yili) as maas_deneyim_korelasyonu
FROM calisanlar;

-- Regresyon analizi
SELECT 
    REGR_SLOPE(maas, deneyim_yili) as egim,
    REGR_INTERCEPT(maas, deneyim_yili) as kesme_noktasi
FROM calisanlar;

-- Percentile hesaplama
SELECT 
    PERCENTILE_CONT(0.25) WITHIN GROUP (ORDER BY maas) as q1,
    PERCENTILE_CONT(0.50) WITHIN GROUP (ORDER BY maas) as median,
    PERCENTILE_CONT(0.75) WITHIN GROUP (ORDER BY maas) as q3
FROM calisanlar;
```
**Açıklama:** İstatistiksel analiz fonksiyonları

### Data Mining SQL
```sql
-- Frekans analizi
SELECT 
    departman,
    COUNT(*) as frekans,
    COUNT(*) * 100.0 / SUM(COUNT(*)) OVER() as yuzde
FROM calisanlar
GROUP BY departman
ORDER BY frekans DESC;

-- Outlier detection
WITH stats AS (
    SELECT 
        AVG(maas) as ortalama,
        STDDEV(maas) as standart_sapma
    FROM calisanlar
)
SELECT 
    ad, maas,
    CASE 
        WHEN ABS(maas - ortalama) > 2 * standart_sapma THEN 'Outlier'
        ELSE 'Normal'
    END as durum
FROM calisanlar, stats;
```
**Açıklama:** Veri madenciliği sorguları

---

## 63. Time Series Data

### Time Series Functions
```sql
-- Moving average
SELECT 
    tarih,
    satis,
    AVG(satis) OVER (
        ORDER BY tarih 
        ROWS BETWEEN 6 PRECEDING AND CURRENT ROW
    ) as hareketli_ortalama_7_gun
FROM gunluk_satislar;

-- Time-based aggregation
SELECT 
    DATE_TRUNC('hour', zaman_damgasi) as saat,
    COUNT(*) as islem_sayisi,
    AVG(tutar) as ortalama_tutar
FROM islemler
GROUP BY DATE_TRUNC('hour', zaman_damgasi)
ORDER BY saat;

-- Time window functions
SELECT 
    tarih,
    satis,
    LAG(satis, 1) OVER (ORDER BY tarih) as onceki_gun,
    LEAD(satis, 1) OVER (ORDER BY tarih) as sonraki_gun,
    satis - LAG(satis, 1) OVER (ORDER BY tarih) as degisim
FROM gunluk_satislar;
```
**Açıklama:** Zaman serisi analizi

### Seasonal Analysis
```sql
-- Mevsimsel analiz
SELECT 
    EXTRACT(MONTH FROM tarih) as ay,
    AVG(satis) as ortalama_satis,
    COUNT(*) as gun_sayisi
FROM gunluk_satislar
GROUP BY EXTRACT(MONTH FROM tarih)
ORDER BY ay;

-- Haftalık pattern
SELECT 
    EXTRACT(DOW FROM tarih) as hafta_gunu,
    AVG(satis) as ortalama_satis
FROM gunluk_satislar
GROUP BY EXTRACT(DOW FROM tarih)
ORDER BY hafta_gunu;
```
**Açıklama:** Mevsimsel analiz

---

## 64. Blockchain ve Distributed Databases

### Blockchain Data Structure
```sql
-- Block tablosu
CREATE TABLE blocks (
    block_hash VARCHAR(64) PRIMARY KEY,
    previous_hash VARCHAR(64),
    timestamp TIMESTAMP,
    nonce BIGINT,
    merkle_root VARCHAR(64)
);

-- Transaction tablosu
CREATE TABLE transactions (
    tx_hash VARCHAR(64) PRIMARY KEY,
    block_hash VARCHAR(64) REFERENCES blocks(block_hash),
    from_address VARCHAR(42),
    to_address VARCHAR(42),
    amount DECIMAL(18,8),
    timestamp TIMESTAMP
);
```
**Açıklama:** Blockchain veri yapısı

### Blockchain Queries
```sql
-- Block chain validation
WITH RECURSIVE block_chain AS (
    SELECT block_hash, previous_hash, 1 as depth
    FROM blocks
    WHERE block_hash = 'latest_block_hash'
    
    UNION ALL
    
    SELECT b.block_hash, b.previous_hash, bc.depth + 1
    FROM blocks b
    JOIN block_chain bc ON b.block_hash = bc.previous_hash
    WHERE bc.depth < 100
)
SELECT * FROM block_chain;

-- Transaction analysis
SELECT 
    from_address,
    COUNT(*) as transaction_count,
    SUM(amount) as total_sent
FROM transactions
GROUP BY from_address
HAVING COUNT(*) > 10
ORDER BY total_sent DESC;
```
**Açıklama:** Blockchain sorguları

---

## 65. Real-time Analytics

### Streaming Analytics
```sql
-- Real-time dashboard
SELECT 
    DATE_FORMAT(NOW(), '%Y-%m-%d %H:00:00') as saat,
    COUNT(*) as aktif_kullanici,
    COUNT(DISTINCT kullanici_id) as benzersiz_kullanici
FROM gercek_zamanli_aktivite
WHERE son_aktivite >= DATE_SUB(NOW(), INTERVAL 1 HOUR);

-- Alert system
SELECT 
    kullanici_id,
    COUNT(*) as islem_sayisi
FROM islemler
WHERE islem_tarihi >= DATE_SUB(NOW(), INTERVAL 5 MINUTE)
GROUP BY kullanici_id
HAVING COUNT(*) > 100;
```
**Açıklama:** Gerçek zamanlı analitik

### Event Processing
```sql
-- Event stream processing
SELECT 
    event_type,
    COUNT(*) as event_count,
    AVG(processing_time) as avg_processing_time
FROM event_log
WHERE event_timestamp >= DATE_SUB(NOW(), INTERVAL 1 HOUR)
GROUP BY event_type
ORDER BY event_count DESC;
```
**Açıklama:** Olay işleme

---

## 66. Advanced Analytics ve Business Intelligence

### Cohort Analysis
```sql
-- Cohort retention analysis
WITH cohort_data AS (
    SELECT 
        kullanici_id,
        DATE_TRUNC('month', ilk_siparis_tarihi) as cohort_month,
        DATE_TRUNC('month', siparis_tarihi) as siparis_month,
        COUNT(DISTINCT siparis_id) as siparis_sayisi
    FROM kullanicilar u
    JOIN siparisler s ON u.id = s.kullanici_id
    GROUP BY kullanici_id, cohort_month, siparis_month
)
SELECT 
    cohort_month,
    siparis_month,
    COUNT(DISTINCT kullanici_id) as aktif_kullanici,
    ROUND(COUNT(DISTINCT kullanici_id) * 100.0 / 
          FIRST_VALUE(COUNT(DISTINCT kullanici_id)) OVER (
              PARTITION BY cohort_month 
              ORDER BY siparis_month
          ), 2) as retention_rate
FROM cohort_data
GROUP BY cohort_month, siparis_month
ORDER BY cohort_month, siparis_month;
```
**Açıklama:** Cohort analizi

### Customer Lifetime Value (CLV)
```sql
-- CLV hesaplama
SELECT 
    kullanici_id,
    COUNT(DISTINCT siparis_id) as siparis_sayisi,
    SUM(tutar) as toplam_harcama,
    AVG(tutar) as ortalama_siparis_tutari,
    MAX(siparis_tarihi) - MIN(siparis_tarihi) as musteri_omru,
    SUM(tutar) / COUNT(DISTINCT siparis_id) * 
    COUNT(DISTINCT siparis_id) / 
    DATEDIFF(MAX(siparis_tarihi), MIN(siparis_tarihi)) * 365 as yillik_clv
FROM siparisler
GROUP BY kullanici_id
HAVING COUNT(DISTINCT siparis_id) > 1;
```
**Açıklama:** Müşteri yaşam boyu değeri

---

## 67. Data Quality ve Data Governance

### Data Quality Checks
```sql
-- Data quality validation
SELECT 
    'email_format' as check_type,
    COUNT(*) as failed_records
FROM kullanicilar
WHERE email NOT REGEXP '^[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Za-z]{2,}$'

UNION ALL

SELECT 
    'null_check' as check_type,
    COUNT(*) as failed_records
FROM kullanicilar
WHERE ad IS NULL OR email IS NULL

UNION ALL

SELECT 
    'duplicate_check' as check_type,
    COUNT(*) - COUNT(DISTINCT email) as failed_records
FROM kullanicilar;
```
**Açıklama:** Veri kalitesi kontrolleri

### Data Lineage
```sql
-- Data lineage tracking
CREATE TABLE data_lineage (
    id INT PRIMARY KEY AUTO_INCREMENT,
    source_table VARCHAR(100),
    target_table VARCHAR(100),
    transformation_type VARCHAR(50),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    created_by VARCHAR(50)
);

-- Lineage tracking
INSERT INTO data_lineage (source_table, target_table, transformation_type, created_by)
VALUES ('raw_satislar', 'gunluk_satis_ozeti', 'aggregation', 'ETL_process');
```
**Açıklama:** Veri soyu takibi

---

## 68. Advanced Security Features

### Row Level Security (RLS)
```sql
-- PostgreSQL RLS
ALTER TABLE kullanicilar ENABLE ROW LEVEL SECURITY;

CREATE POLICY kullanici_policy ON kullanicilar
    FOR ALL
    USING (kullanici_id = current_user_id());

-- MySQL RLS benzeri
CREATE VIEW kullanici_view AS
SELECT * FROM kullanicilar 
WHERE kullanici_id = @current_user_id;
```
**Açıklama:** Satır seviyesi güvenlik

### Data Masking
```sql
-- Data masking functions
CREATE FUNCTION mask_email(email VARCHAR(100))
RETURNS VARCHAR(100)
DETERMINISTIC
BEGIN
    RETURN CONCAT(
        LEFT(email, 2),
        '***',
        '@',
        SUBSTRING_INDEX(email, '@', -1)
    );
END;

-- Masked data query
SELECT 
    id,
    mask_email(email) as masked_email,
    CONCAT(LEFT(ad, 1), '***') as masked_name
FROM kullanicilar;
```
**Açıklama:** Veri maskeleme

---

## 69. Database Automation

### Automated Maintenance
```sql
-- Automated index maintenance
CREATE EVENT auto_index_maintenance
ON SCHEDULE EVERY 1 DAY
STARTS CURRENT_TIMESTAMP
DO
BEGIN
    -- Fragmented indexes
    SELECT CONCAT('OPTIMIZE TABLE ', table_name, ';') as maintenance_command
    FROM information_schema.tables 
    WHERE table_schema = DATABASE()
    AND table_rows > 10000;
END;

-- Automated backup
CREATE EVENT auto_backup
ON SCHEDULE EVERY 1 DAY
STARTS '2023-01-01 02:00:00'
DO
BEGIN
    -- Backup logic
    SET @backup_file = CONCAT('/backup/db_', DATE_FORMAT(NOW(), '%Y%m%d'), '.sql');
    SET @backup_cmd = CONCAT('mysqldump -u root -p veritabani > ', @backup_file);
    -- Execute backup command
END;
```
**Açıklama:** Otomatik bakım

### Automated Monitoring
```sql
-- Performance monitoring
CREATE EVENT performance_monitor
ON SCHEDULE EVERY 5 MINUTE
DO
BEGIN
    INSERT INTO performance_log (
        timestamp,
        active_connections,
        slow_queries,
        table_locks
    )
    SELECT 
        NOW(),
        COUNT(*) as active_connections,
        (SELECT COUNT(*) FROM mysql.slow_log WHERE start_time >= DATE_SUB(NOW(), INTERVAL 5 MINUTE)) as slow_queries,
        (SELECT COUNT(*) FROM information_schema.table_locks WHERE table_schema = DATABASE()) as table_locks
    FROM information_schema.processlist
    WHERE command != 'Sleep';
END;
```
**Açıklama:** Otomatik izleme

---

## 70. Future SQL Trends

### AI-Powered SQL
```sql
-- Natural language to SQL (conceptual)
-- AI-generated query optimization
-- Automated query rewriting
```
**Açıklama:** AI destekli SQL

### Edge Computing SQL
```sql
-- Distributed SQL
-- Edge database synchronization
-- Offline-first SQL
```
**Açıklama:** Edge computing SQL

### Quantum Database Concepts
```sql
-- Quantum-inspired algorithms
-- Quantum-safe encryption
-- Quantum database design patterns
```
**Açıklama:** Kuantum veritabanı kavramları

---

## 71. SQL Injection Bypass Techniques (Güvenlik Testleri İçin)

### Encoding Bypass
```sql
-- Hex encoding
SELECT * FROM users WHERE id = 0x31; -- 1 in hex

-- URL encoding
SELECT * FROM users WHERE name = '%61%64%6D%69%6E'; -- admin

-- Double encoding
SELECT * FROM users WHERE name = '%25%36%31%25%36%34%25%36%44%25%36%39%25%36%45'; -- admin
```
**Açıklama:** Encoding bypass teknikleri (sadece güvenlik testleri için)

### Comment Bypass
```sql
-- Inline comments
SELECT * FROM users WHERE id = 1/**/OR/**/1=1;

-- Nested comments
SELECT * FROM users WHERE id = 1/*!OR*/1=1;

-- Version-specific comments
SELECT * FROM users WHERE id = 1/*!50000OR*/1=1;
```
**Açıklama:** Yorum bypass teknikleri

### Whitespace Bypass
```sql
-- Tab character
SELECT*FROM users WHERE id=1%09OR%091=1;

-- Newline character
SELECT*FROM users WHERE id=1%0AOR%0A1=1;

-- Carriage return
SELECT*FROM users WHERE id=1%0DOR%0D1=1;
```
**Açıklama:** Boşluk bypass teknikleri

---

## 72. Obfuscated SQL (Gizli SQL)

### String Concatenation Obfuscation
```sql
-- ASCII concatenation
SELECT * FROM users WHERE name = CHAR(97,100,109,105,110); -- admin

-- XOR obfuscation
SELECT * FROM users WHERE name = 'admin' XOR 0;

-- Bit manipulation
SELECT * FROM users WHERE id = 1 | 0;
SELECT * FROM users WHERE id = 1 & 1;
SELECT * FROM users WHERE id = 1 ^ 0;
```
**Açıklama:** SQL obfuscation teknikleri

### Function Obfuscation
```sql
-- Nested functions
SELECT * FROM users WHERE name = REVERSE(REVERSE('admin'));

-- Case manipulation
SELECT * FROM users WHERE name = LOWER('ADMIN');

-- Substring obfuscation
SELECT * FROM users WHERE name = CONCAT(SUBSTRING('admin',1,1), SUBSTRING('admin',2));
```
**Açıklama:** Fonksiyon obfuscation

---

## 73. Undocumented SQL Features

### MySQL Undocumented Features
```sql
-- Information schema bypass
SELECT * FROM mysql.user WHERE user = 'root';

-- System table access
SELECT * FROM mysql.db WHERE db = 'test';

-- Performance schema access
SELECT * FROM performance_schema.events_statements_summary_by_digest;

-- Memory tables
SELECT * FROM information_schema.tables WHERE engine = 'MEMORY';
```
**Açıklama:** Dokümante edilmemiş özellikler

### PostgreSQL Undocumented Features
```sql
-- System catalogs
SELECT * FROM pg_catalog.pg_user;

-- Internal functions
SELECT * FROM pg_stat_activity;

-- Extension information
SELECT * FROM pg_extension;
```
**Açıklama:** PostgreSQL gizli özellikleri

---

## 74. Performance Hacks ve Tricks

### Query Optimization Hacks
```sql
-- Force index usage
SELECT * FROM users FORCE INDEX (primary) WHERE id = 1;

-- Ignore index
SELECT * FROM users IGNORE INDEX (email_idx) WHERE email = 'test@test.com';

-- Use specific index
SELECT * FROM users USE INDEX (name_idx) WHERE name = 'admin';

-- Query hints
SELECT /*+ INDEX(users primary) */ * FROM users WHERE id = 1;
```
**Açıklama:** Performans hacks

### Memory Optimization
```sql
-- Temporary table optimization
CREATE TEMPORARY TABLE temp_data ENGINE=MEMORY AS SELECT * FROM large_table;

-- Buffer pool optimization
SET GLOBAL innodb_buffer_pool_size = 1073741824; -- 1GB

-- Query cache optimization
SET GLOBAL query_cache_size = 67108864; -- 64MB
```
**Açıklama:** Bellek optimizasyonu

---

## 75. Advanced SQL Tricks

### Recursive CTE Tricks
```sql
-- Fibonacci sequence
WITH RECURSIVE fibonacci AS (
    SELECT 0 as n, 0 as fib UNION ALL SELECT 1, 1
    UNION ALL
    SELECT n + 1, fib + LAG(fib) OVER (ORDER BY n)
    FROM fibonacci
    WHERE n < 10
)
SELECT * FROM fibonacci;

-- Date generation
WITH RECURSIVE dates AS (
    SELECT '2023-01-01' as date
    UNION ALL
    SELECT DATE_ADD(date, INTERVAL 1 DAY)
    FROM dates
    WHERE date < '2023-12-31'
)
SELECT * FROM dates;
```
**Açıklama:** Gelişmiş CTE teknikleri

### Window Function Tricks
```sql
-- Running total with reset
SELECT 
    category,
    amount,
    SUM(amount) OVER (
        PARTITION BY category 
        ORDER BY date 
        ROWS UNBOUNDED PRECEDING
    ) as running_total
FROM transactions;

-- Moving average with custom window
SELECT 
    date,
    sales,
    AVG(sales) OVER (
        ORDER BY date 
        ROWS BETWEEN 2 PRECEDING AND 2 FOLLOWING
    ) as moving_avg_5
FROM daily_sales;
```
**Açıklama:** Gelişmiş window function teknikleri

---

## 76. SQL Puzzles ve Brain Teasers

### Complex Logic Puzzles
```sql
-- Find consecutive numbers
WITH numbers AS (
    SELECT 1 as n UNION ALL SELECT 2 UNION ALL SELECT 3 
    UNION ALL SELECT 4 UNION ALL SELECT 5 UNION ALL SELECT 6
),
consecutive AS (
    SELECT n, 
           n - ROW_NUMBER() OVER (ORDER BY n) as grp
    FROM numbers
    WHERE n IN (1,2,3,5,6,7,9,10,11,15)
)
SELECT MIN(n) as start_num, MAX(n) as end_num, COUNT(*) as length
FROM consecutive
GROUP BY grp
HAVING COUNT(*) >= 3;

-- Find missing numbers
WITH sequence AS (
    SELECT 1 as n UNION ALL SELECT 2 UNION ALL SELECT 3 
    UNION ALL SELECT 4 UNION ALL SELECT 5 UNION ALL SELECT 6
    UNION ALL SELECT 7 UNION ALL SELECT 8 UNION ALL SELECT 9 UNION ALL SELECT 10
),
existing AS (
    SELECT 1 as n UNION ALL SELECT 3 UNION ALL SELECT 5 
    UNION ALL SELECT 7 UNION ALL SELECT 9
)
SELECT s.n as missing_number
FROM sequence s
LEFT JOIN existing e ON s.n = e.n
WHERE e.n IS NULL;
```
**Açıklama:** SQL bulmacaları

### Advanced Data Manipulation
```sql
-- Pivot without CASE
SELECT 
    department,
    MAX(CASE WHEN month = 'Jan' THEN sales END) as Jan,
    MAX(CASE WHEN month = 'Feb' THEN sales END) as Feb,
    MAX(CASE WHEN month = 'Mar' THEN sales END) as Mar
FROM sales_data
GROUP BY department;

-- Unpivot using UNION ALL
SELECT department, 'Jan' as month, Jan as sales FROM sales_pivot
UNION ALL
SELECT department, 'Feb' as month, Feb as sales FROM sales_pivot
UNION ALL
SELECT department, 'Mar' as month, Mar as sales FROM sales_pivot;
```
**Açıklama:** Gelişmiş veri manipülasyonu

---

## 77. SQL Anti-Patterns (Kaçınılması Gerekenler)

### Performance Anti-Patterns
```sql
-- N+1 Query Problem
-- DON'T DO THIS:
SELECT * FROM users;
-- Then for each user:
SELECT * FROM orders WHERE user_id = ?

-- DO THIS INSTEAD:
SELECT u.*, o.* 
FROM users u 
LEFT JOIN orders o ON u.id = o.user_id;

-- SELECT * Anti-Pattern
-- DON'T DO THIS:
SELECT * FROM large_table;

-- DO THIS INSTEAD:
SELECT id, name, email FROM large_table;
```
**Açıklama:** Performans anti-pattern'leri

### Security Anti-Patterns
```sql
-- SQL Injection Vulnerable
-- DON'T DO THIS:
SET @sql = CONCAT('SELECT * FROM users WHERE id = ', user_input);
PREPARE stmt FROM @sql;

-- DO THIS INSTEAD:
PREPARE stmt FROM 'SELECT * FROM users WHERE id = ?';
EXECUTE stmt USING @user_input;
```
**Açıklama:** Güvenlik anti-pattern'leri

---

## 78. SQL Easter Eggs ve Hidden Features

### MySQL Easter Eggs
```sql
-- Version information in comments
SELECT /*!40101 * */ * FROM users;

-- Version-specific features
SELECT /*!50000 VERSION() */;

-- Hidden system variables
SHOW VARIABLES LIKE 'version%';
SHOW VARIABLES LIKE 'innodb%';
```
**Açıklama:** MySQL gizli özellikleri

### PostgreSQL Easter Eggs
```sql
-- System information
SELECT version();
SELECT current_database();
SELECT current_user;

-- Hidden catalogs
SELECT * FROM pg_catalog.pg_stat_database;
SELECT * FROM pg_catalog.pg_stat_bgwriter;
```
**Açıklama:** PostgreSQL gizli özellikleri

---

## 79. SQL Debugging ve Troubleshooting

### Advanced Debugging Techniques
```sql
-- Query execution plan analysis
EXPLAIN FORMAT=JSON SELECT * FROM users WHERE email = 'test@test.com';

-- Performance schema analysis
SELECT 
    digest_text,
    count_star,
    avg_timer_wait/1000000000 as avg_time_seconds
FROM performance_schema.events_statements_summary_by_digest
ORDER BY avg_timer_wait DESC;

-- Lock analysis
SELECT 
    object_schema,
    object_name,
    lock_type,
    lock_duration,
    lock_status
FROM performance_schema.metadata_locks;
```
**Açıklama:** Gelişmiş debugging teknikleri

### Error Analysis
```sql
-- Error log analysis
SELECT 
    error_code,
    COUNT(*) as error_count,
    MAX(timestamp) as last_occurrence
FROM error_log
WHERE timestamp >= DATE_SUB(NOW(), INTERVAL 1 DAY)
GROUP BY error_code
ORDER BY error_count DESC;

-- Deadlock analysis
SHOW ENGINE INNODB STATUS;
```
**Açıklama:** Hata analizi

---

## 80. SQL Black Magic (En Gelişmiş Teknikler)

### Advanced Query Optimization
```sql
-- Query rewrite optimization
-- Original query
SELECT * FROM orders o 
JOIN customers c ON o.customer_id = c.id 
WHERE o.order_date >= '2023-01-01';

-- Optimized version
SELECT o.*, c.name, c.email 
FROM orders o 
INNER JOIN customers c ON o.customer_id = c.id 
WHERE o.order_date >= '2023-01-01'
AND o.customer_id IS NOT NULL;

-- Partition pruning optimization
SELECT * FROM orders 
WHERE order_date >= '2023-01-01' 
AND order_date < '2023-02-01'
AND customer_id BETWEEN 1000 AND 2000;
```
**Açıklama:** En gelişmiş optimizasyon teknikleri

### Advanced Data Analysis
```sql
-- Time series forecasting (simplified)
WITH sales_trend AS (
    SELECT 
        date,
        sales,
        AVG(sales) OVER (ORDER BY date ROWS BETWEEN 6 PRECEDING AND CURRENT ROW) as trend,
        STDDEV(sales) OVER (ORDER BY date ROWS BETWEEN 6 PRECEDING AND CURRENT ROW) as volatility
    FROM daily_sales
)
SELECT 
    date,
    sales,
    trend,
    trend + (2 * volatility) as upper_bound,
    trend - (2 * volatility) as lower_bound
FROM sales_trend;

-- Anomaly detection
WITH stats AS (
    SELECT 
        AVG(amount) as mean,
        STDDEV(amount) as std
    FROM transactions
)
SELECT 
    id,
    amount,
    CASE 
        WHEN ABS(amount - mean) > 3 * std THEN 'Anomaly'
        ELSE 'Normal'
    END as status
FROM transactions, stats;
```
**Açıklama:** En gelişmiş analiz teknikleri

---

## Ek Kaynaklar

### SQL Standartları
- **SQL-92**: Temel SQL standardı
- **SQL:1999**: Object-relational features
- **SQL:2003**: XML support
- **SQL:2008**: MERGE statement
- **SQL:2011**: Temporal tables
- **SQL:2016**: JSON support
- **SQL:2019**: Graph data support
- **SQL:2023**: AI and ML features

### Veritabanı Sistemleri
- **MySQL/MariaDB**: Açık kaynak, web uygulamaları
- **PostgreSQL**: Gelişmiş özellikler, ACID compliance
- **Oracle**: Enterprise, yüksek performans
- **SQL Server**: Microsoft ecosystem
- **SQLite**: Embedded, mobil uygulamalar
- **DB2**: IBM enterprise database
- **MongoDB**: NoSQL document database
- **Redis**: In-memory key-value store
- **Neo4j**: Graph database
- **InfluxDB**: Time series database
- **Cassandra**: Distributed NoSQL
- **DynamoDB**: AWS NoSQL service
- **CockroachDB**: Distributed SQL
- **TiDB**: MySQL compatible distributed database

### Öğrenme Kaynakları
- **W3Schools SQL Tutorial**
- **SQLZoo**
- **LeetCode Database Problems**
- **HackerRank SQL**
- **Mode Analytics SQL Tutorial**
- **SQL Performance Explained**
- **Database Design for Mere Mortals**
- **SQL Antipatterns**
- **SQL Cookbook**
- **Database Internals**
- **High Performance MySQL**
- **PostgreSQL: Up and Running**
- **SQL Server Internals**

### Araçlar
- **phpMyAdmin**: MySQL yönetimi
- **pgAdmin**: PostgreSQL yönetimi
- **DBeaver**: Universal database tool
- **DataGrip**: JetBrains database IDE
- **TablePlus**: Modern database client
- **MySQL Workbench**: MySQL GUI
- **Sequel Pro**: macOS MySQL client
- **HeidiSQL**: Windows database client
- **Navicat**: Premium database tool
- **Toad**: Oracle database tool
- **SQL Developer**: Oracle GUI
- **Azure Data Studio**: Microsoft database tool
- **Beekeeper Studio**: Modern SQL editor
- **DbVisualizer**: Universal database tool

### Sertifikalar
- **Oracle Certified Professional (OCP)**
- **Microsoft Certified: Azure Database Administrator**
- **AWS Certified Database - Specialty**
- **Google Cloud Professional Data Engineer**
- **MongoDB Certified Developer**
- **PostgreSQL Certified Associate**
- **IBM Certified Database Administrator**
- **Cloudera Certified Associate**
- **Databricks Certified Associate Developer**
- **Snowflake SnowPro Core Certification**

### Modern SQL Framework'leri
- **SQLAlchemy**: Python ORM
- **Hibernate**: Java ORM
- **Entity Framework**: .NET ORM
- **Prisma**: Node.js ORM
- **Django ORM**: Python web framework
- **Sequelize**: Node.js ORM
- **TypeORM**: TypeScript ORM
- **Doctrine**: PHP ORM
- **GORM**: Go ORM
- **Active Record**: Ruby ORM

### SQL Security ve Penetration Testing
- **SQLMap**: Automated SQL injection tool
- **Burp Suite**: Web application security testing
- **OWASP ZAP**: Security testing tool
- **Nmap**: Network scanning
- **Metasploit**: Penetration testing framework

---

## Sonuç

Bu kapsamlı SQL cheatsheet, SQL'in tüm temel ve ileri seviye konularını ele almaktadır. Her komutun Türkçe açıklaması ile birlikte pratik örnekler verilmiştir. Bu rehberi referans olarak kullanarak SQL sorgularınızı daha etkili bir şekilde yazabilir ve veritabanı yönetimi konusunda uzmanlaşabilirsiniz.

## MySQL vs SQLite Önemli Farklar

### Veritabanı Yönetimi
- **MySQL:** Çoklu veritabanı desteği, kullanıcı yönetimi, izin sistemi
- **SQLite:** Tek dosya, kullanıcı yönetimi yok, dosya izinleri ile kontrol

### Veri Tipleri
- **MySQL:** Çok sayıda veri tipi (VARCHAR, CHAR, TEXT, LONGTEXT, vb.)
- **SQLite:** Sadece 5 temel tip (NULL, INTEGER, REAL, TEXT, BLOB)

### Sütun İşlemleri
- **MySQL:** ALTER TABLE ile sütun ekleme, silme, değiştirme
- **SQLite:** Sadece sütun ekleme, silme ve değiştirme için yeni tablo oluşturma gerekir

### Stored Procedures
- **MySQL:** Tam destek
- **SQLite:** Desteklenmez

### Fonksiyonlar
- **MySQL:** Zengin fonksiyon kütüphanesi
- **SQLite:** Temel fonksiyonlar, bazı farklı isimler (SUBSTR vs SUBSTRING)

### Yedekleme
- **MySQL:** mysqldump ile SQL formatında
- **SQLite:** Dosya kopyalama veya .dump komutu

### Performans
- **MySQL:** Çok kullanıcılı, yüksek performans
- **SQLite:** Tek kullanıcılı, embedded kullanım için optimize

**Not:** Bu rehber genel SQL standartlarını takip etmekle birlikte, bazı özellikler belirli veritabanı sistemlerine özgü olabilir. Kullandığınız veritabanı sisteminin dokümantasyonunu kontrol etmeyi unutmayın.

---

**SQL Cheatsheet** - MySQL ve SQLite komutları ile SQL'in tüm özelliklerini kapsayan eksiksiz referans rehberi! 🚀