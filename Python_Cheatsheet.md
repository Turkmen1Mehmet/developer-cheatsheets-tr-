# Python Cheatsheet

## İçindekiler

1. [Temel Sözdizimi](#1-temel-sözdizimi)
2. [Veri Tipleri](#2-veri-tipleri)
3. [Kontrol Yapıları](#3-kontrol-yapıları)
4. [Fonksiyonlar](#4-fonksiyonlar)
5. [Sınıflar ve OOP](#5-sınıflar-ve-oop)
6. [Modüller ve Paketler](#6-modüller-ve-paketler)
7. [Dosya İşlemleri](#7-dosya-işlemleri)
8. [Hata Yönetimi](#8-hata-yönetimi)
9. [Liste Anlayışları](#9-liste-anlayışları)
10. [Lambda Fonksiyonları](#10-lambda-fonksiyonları)
11. [Decorator'lar](#11-decoratorlar)
12. [Generator'lar](#12-generatorlar)
13. [Context Manager'lar](#13-context-managerlar)
14. [Asenkron Programlama](#14-asenkron-programlama)
15. [Threading ve Multiprocessing](#15-threading-ve-multiprocessing)
16. [Veri Yapıları](#16-veri-yapıları)
17. [Web Geliştirme](#17-web-geliştirme)
18. [Veri Analizi](#18-veri-analizi)
19. [Machine Learning](#19-machine-learning)
20. [GUI Programlama](#20-gui-programlama)
21. [Network Programming](#21-network-programming)
22. [Database Programming](#22-database-programming)
23. [Testing](#23-testing)
24. [Performance Optimization](#24-performance-optimization)
25. [Security](#25-security)
26. [Deployment](#26-deployment)
27. [Best Practices](#27-best-practices)
28. [Advanced Patterns](#28-advanced-patterns)
29. [Metaclass'lar](#29-metaclasslar)
30. [Python Black Magic](#30-python-black-magic)
31. [Data Classes](#31-data-classes)
32. [Type Hints ve Annotations](#32-type-hints-ve-annotations)
33. [Pattern Matching](#33-pattern-matching)
34. [Walrus Operator](#34-walrus-operator)
35. [Assignment Expressions](#35-assignment-expressions)
36. [Positional-Only Parameters](#36-positional-only-parameters)
37. [Keyword-Only Parameters](#37-keyword-only-parameters)
38. [F-Strings Gelişmiş](#38-f-strings-gelişmiş)
39. [Dictionary Union Operators](#39-dictionary-union-operators)
40. [Type Hints in Standard Collections](#40-type-hints-in-standard-collections)
41. [Structural Pattern Matching](#41-structural-pattern-matching)
42. [Match Statement](#42-match-statement)
43. [Case Statements](#43-case-statements)
44. [Guard Clauses](#44-guard-clauses)
45. [Pattern Matching with Classes](#45-pattern-matching-with-classes)
46. [Dataclass Fields](#46-dataclass-fields)
47. [Post Init Processing](#47-post-init-processing)
48. [Dataclass Inheritance](#48-dataclass-inheritance)
49. [Frozen Dataclasses](#49-frozen-dataclasses)
50. [Slots](#50-slots)
51. [Property Decorators](#51-property-decorators)
52. [Class Methods](#52-class-methods)
53. [Static Methods](#53-static-methods)
54. [Abstract Base Classes](#54-abstract-base-classes)
55. [Protocols](#55-protocols)
56. [TypeVar ve Generic Types](#56-typevar-ve-generic-types)
57. [Union Types](#57-union-types)
58. [Optional Types](#58-optional-types)
59. [Literal Types](#59-literal-types)
60. [TypedDict](#60-typeddict)
61. [NewType](#61-newtype)
62. [Final](#62-final)
63. [Annotated](#63-annotated)
64. [Self Type](#64-self-type)
65. [Callable Types](#65-callable-types)
66. [Iterator Types](#66-iterator-types)
67. [Async Types](#67-async-types)
68. [Context Manager Types](#68-context-manager-types)
69. [Protocol Types](#69-protocol-types)
70. [Generic Protocols](#70-generic-protocols)
71. [Covariant ve Contravariant](#71-covariant-ve-contravariant)
72. [Bounded TypeVar](#72-bounded-typevar)
73. [Multiple TypeVar](#73-multiple-typevar)
74. [TypeVar with Default](#74-typevar-with-default)
75. [TypeVar with Constraints](#75-typevar-with-constraints)
76. [Generic Functions](#76-generic-functions)
77. [Generic Classes](#77-generic-classes)
78. [Generic Methods](#78-generic-methods)
79. [Generic Inheritance](#79-generic-inheritance)
80. [Generic Protocols](#80-generic-protocols)
81. [Type Aliases](#81-type-aliases)
82. [Type Guards](#82-type-guards)
83. [Type Narrowing](#83-type-narrowing)
84. [Type Assertions](#84-type-assertions)
85. [Type Casting](#85-type-casting)
86. [Type Checking](#86-type-checking)
87. [Type Inference](#87-type-inference)
88. [Type Erasure](#88-type-erasure)
89. [Type Preservation](#89-type-preservation)
90. [Type Safety](#90-type-safety)
91. [Type Compatibility](#91-type-compatibility)
92. [Type Coercion](#92-type-coercion)
93. [Type Conversion](#93-type-conversion)
94. [Type Validation](#94-type-validation)
95. [Type Serialization](#95-type-serialization)
96. [Type Deserialization](#96-type-deserialization)
97. [Type Marshalling](#97-type-marshalling)
98. [Type Unmarshalling](#98-type-unmarshalling)
99. [Type Reflection](#99-type-reflection)
100. [Type Introspection](#100-type-introspection)
101. [Type Metaprogramming](#101-type-metaprogramming)
102. [Type Code Generation](#102-type-code-generation)
103. [Type Templates](#103-type-templates)
104. [Type Macros](#104-type-macros)
105. [Type Compilers](#105-type-compilers)
106. [Type Interpreters](#106-type-interpreters)
107. [Type Virtual Machines](#107-type-virtual-machines)
108. [Type Runtime](#108-type-runtime)
109. [Type Compile Time](#109-type-compile-time)
110. [Type Link Time](#110-type-link-time)
111. [Type Load Time](#111-type-load-time)
112. [Type Execution Time](#112-type-execution-time)
113. [Type Static Analysis](#113-type-static-analysis)
114. [Type Dynamic Analysis](#114-type-dynamic-analysis)
115. [Type Profiling](#115-type-profiling)
116. [Type Debugging](#116-type-debugging)
117. [Type Tracing](#117-type-tracing)
118. [Type Logging](#118-type-logging)
119. [Type Monitoring](#119-type-monitoring)
120. [Type Metrics](#120-type-metrics)
121. [Type Benchmarks](#121-type-benchmarks)
122. [Type Performance](#122-type-performance)
123. [Type Optimization](#123-type-optimization)
124. [Type Caching](#124-type-caching)
125. [Type Memoization](#125-type-memoization)
126. [Type Lazy Loading](#126-type-lazy-loading)
127. [Type Eager Loading](#127-type-eager-loading)
128. [Type Preloading](#128-type-preloading)
129. [Type Postloading](#129-type-postloading)
130. [Type Hot Reloading](#130-type-hot-reloading)
131. [Regular Expressions (Regex)](#131-regular-expressions-regex)
132. [JSON İşlemleri](#132-json-işlemleri)
133. [XML İşlemleri](#133-xml-işlemleri)
134. [CSV İşlemleri](#134-csv-işlemleri)
135. [Environment Variables](#135-environment-variables)
136. [Command Line Arguments](#136-command-line-arguments)
137. [Logging Module](#137-logging-module)
138. [Config Files](#138-config-files)
139. [Date/Time İşlemleri](#139-datetime-işlemleri)
140. [Math ve Statistics](#140-math-ve-statistics)
141. [Collections Module](#141-collections-module)
142. [Itertools Module](#142-itertools-module)
143. [Functools Module](#143-functools-module)
144. [Pathlib](#144-pathlib)
145. [Subprocess Module](#145-subprocess-module)
146. [Pickle/Serialization](#146-pickleserialization)
147. [Virtual Environments](#147-virtual-environments)

---

## 1. Temel Sözdizimi

**Ne İşe Yarar:** Python'da kod yazarken kullanılan temel kurallar ve yapıları öğretir. Değişken tanımlama, print işlemleri ve yorum yazma gibi temel konuları kapsar.

**Ne Yapar:** Python kodunun nasıl yazılacağını, değişkenlerin nasıl tanımlanacağını ve kodun nasıl okunabilir hale getirileceğini gösterir.

### Değişken Tanımlama
```python
# Basit değişken tanımlama
isim = "Ahmet"
yas = 25
boy = 1.75
aktif = True

# Çoklu atama
a, b, c = 1, 2, 3
```

### Print ve Format
```python
# F-string (Python 3.6+)
print(f"Merhaba {isim}, yaşın: {yas}")

# Format metodu
print("Merhaba {}, yaşın: {}".format(isim, yas))
```

### Yorumlar
```python
# Tek satır yorum
"""
Çok satırlı
yorum bloğu
"""
```

## 2. Veri Tipleri

**Ne İşe Yarar:** Python'da kullanılan farklı veri tiplerini tanıtır. Sayılar, metinler, boolean değerler, listeler, tuple'lar, sözlükler ve kümeler gibi temel veri yapılarını öğretir.

**Ne Yapar:** Hangi veri tipinin ne zaman kullanılacağını, veri tiplerinin özelliklerini ve nasıl kullanılacağını gösterir.

### Sayılar
```python
# Tam sayı
tam_sayi = 42

# Ondalıklı sayı
ondalik = 3.14

# Karmaşık sayı
karmasik = 3 + 4j
```

### Metin
```python
# String
metin = "Merhaba Dünya"
uzun_metin = """
Bu çok satırlı
bir metindir
"""
```

### Boolean
```python
# Boolean değerler
dogru = True
yanlis = False
```

### Liste
```python
# Liste oluşturma
liste = [1, 2, 3, "dört", 5.0]
bos_liste = []

# Liste erişimi
ilk_eleman = liste[0]  # 1
son_eleman = liste[-1]  # 5.0
```

### Tuple
```python
# Tuple (değişmez liste)
koordinat = (10, 20)
tek_eleman = (42,)
```

### Dictionary
```python
# Sözlük
kisi = {
    "isim": "Ayşe",
    "yas": 30,
    "sehir": "İstanbul"
}

# Değer erişimi
isim = kisi["isim"]
yas = kisi.get("yas", 0)  # Varsayılan değer
```

### Set
```python
# Küme (benzersiz elemanlar)
sayilar = {1, 2, 3, 3, 4}  # {1, 2, 3, 4}
bos_kume = set()
```

## 3. Kontrol Yapıları

**Ne İşe Yarar:** Programın akışını kontrol etmek için kullanılan yapıları öğretir. Koşullu ifadeler, döngüler ve program akışını yönlendiren yapıları kapsar.

**Ne Yapar:** Hangi durumda hangi kodun çalışacağını belirler, tekrarlayan işlemleri otomatikleştirir ve programın mantıklı bir şekilde çalışmasını sağlar.

### If-Elif-Else
```python
yas = 18

if yas < 18:
    print("Reşit değil")
elif yas == 18:
    print("Tam reşit")
else:
    print("Reşit")
```

### For Döngüsü
```python
# Liste üzerinde döngü
for sayi in [1, 2, 3, 4, 5]:
    print(sayi)

# Range ile döngü
for i in range(5):
    print(i)  # 0, 1, 2, 3, 4

# Enumerate ile indeks
for index, deger in enumerate(["a", "b", "c"]):
    print(f"{index}: {deger}")
```

### While Döngüsü
```python
sayac = 0
while sayac < 5:
    print(sayac)
    sayac += 1
```

### Break ve Continue
```python
# Break - döngüden çık
for i in range(10):
    if i == 5:
        break
    print(i)

# Continue - sonraki iterasyona geç
for i in range(10):
    if i % 2 == 0:
        continue
    print(i)  # Sadece tek sayılar
```

## 4. Fonksiyonlar

**Ne İşe Yarar:** Kod tekrarını önlemek ve kodu modüler hale getirmek için kullanılan yapıları öğretir. Fonksiyon tanımlama, parametre geçirme ve değer döndürme konularını kapsar.

**Ne Yapar:** Belirli bir işlevi yerine getiren kod bloklarını paketler, kodun yeniden kullanılabilir olmasını sağlar ve programın daha düzenli ve anlaşılır olmasına yardımcı olur.

### Basit Fonksiyon
```python
def selamla(isim):
    return f"Merhaba {isim}!"

# Fonksiyon çağrısı
mesaj = selamla("Ali")
print(mesaj)  # Merhaba Ali!
```

### Varsayılan Parametreler
```python
def selamla(isim="Dünya"):
    return f"Merhaba {isim}!"

print(selamla())  # Merhaba Dünya!
print(selamla("Ahmet"))  # Merhaba Ahmet!
```

### Çoklu Dönüş
```python
def hesapla(a, b):
    toplam = a + b
    carpim = a * b
    return toplam, carpim

sonuc1, sonuc2 = hesapla(5, 3)
print(sonuc1, sonuc2)  # 8 15
```

### *args ve **kwargs
```python
def topla(*args):
    return sum(args)

def bilgi_yazdir(**kwargs):
    for anahtar, deger in kwargs.items():
        print(f"{anahtar}: {deger}")

print(topla(1, 2, 3, 4))  # 10
bilgi_yazdir(isim="Mehmet", yas=25)
```

## 5. Sınıflar ve OOP

**Ne İşe Yarar:** Nesne yönelimli programlama (OOP) kavramlarını öğretir. Sınıf tanımlama, nesne oluşturma, kalıtım ve encapsulation gibi OOP prensiplerini kapsar.

**Ne Yapar:** Gerçek dünya nesnelerini kodda temsil etmek için kullanılır, kodun daha organize ve yönetilebilir olmasını sağlar ve büyük projelerde kod tekrarını önler.

### Basit Sınıf
```python
class Kisi:
    def __init__(self, isim, yas):
        self.isim = isim
        self.yas = yas
    
    def selamla(self):
        return f"Merhaba, ben {self.isim}"

# Nesne oluşturma
kisi1 = Kisi("Ayşe", 30)
print(kisi1.selamla())
```

### Kalıtım
```python
class Ogrenci(Kisi):
    def __init__(self, isim, yas, ogrenci_no):
        super().__init__(isim, yas)
        self.ogrenci_no = ogrenci_no
    
    def ders_calis(self):
        return f"{self.isim} ders çalışıyor"

ogrenci = Ogrenci("Ali", 20, "12345")
print(ogrenci.ders_calis())
```

### Encapsulation
```python
class BankaHesabi:
    def __init__(self, bakiye):
        self.__bakiye = bakiye  # Private değişken
    
    def bakiye_goster(self):
        return self.__bakiye
    
    def para_cek(self, miktar):
        if miktar <= self.__bakiye:
            self.__bakiye -= miktar
            return True
        return False
```

## 6. Modüller ve Paketler

**Ne İşe Yarar:** Kodun farklı dosyalara bölünmesini ve yeniden kullanılabilir parçalar halinde organize edilmesini öğretir. Modül import etme ve paket yönetimi konularını kapsar.

**Ne Yapar:** Büyük projelerde kodun düzenli olmasını sağlar, hazır kütüphaneleri kullanmayı kolaylaştırır ve kodun modüler bir yapıda organize edilmesine yardımcı olur.

### Modül İçe Aktarma
```python
# Tam modül
import math
print(math.pi)

# Belirli fonksiyon
from math import sqrt
print(sqrt(16))

# Takma ad
import numpy as np
array = np.array([1, 2, 3])
```

### Kendi Modülümüz
```python
# utils.py
def topla(a, b):
    return a + b

def carp(a, b):
    return a * b

# main.py
from utils import topla, carp
print(topla(5, 3))
```

## 7. Dosya İşlemleri

**Ne İşe Yarar:** Bilgisayar dosyalarını okuma, yazma ve yönetme işlemlerini öğretir. Dosya açma, okuma, yazma ve kapatma gibi temel dosya operasyonlarını kapsar.

**Ne Yapar:** Programın dış dünya ile veri alışverişi yapmasını sağlar, kalıcı veri saklama imkanı verir ve dosya tabanlı veri işleme yapmayı mümkün kılar.

### Dosya Okuma
```python
# Dosyayı oku
with open("dosya.txt", "r", encoding="utf-8") as f:
    icerik = f.read()
    print(icerik)

# Satır satır okuma
with open("dosya.txt", "r") as f:
    for satir in f:
        print(satir.strip())
```

### Dosya Yazma
```python
# Dosyaya yaz
with open("yeni_dosya.txt", "w") as f:
    f.write("Merhaba Dünya!")

# Dosyaya ekle
with open("yeni_dosya.txt", "a") as f:
    f.write("\nYeni satır")
```

## 8. Hata Yönetimi

**Ne İşe Yarar:** Program çalışırken oluşabilecek hataları yakalama ve yönetme yöntemlerini öğretir. Try-except blokları, hata türleri ve hata fırlatma konularını kapsar.

**Ne Yapar:** Programın beklenmedik durumlarda çökmesini önler, hataları kontrollü bir şekilde yönetir ve kullanıcı dostu hata mesajları göstermeyi sağlar.

### Try-Except
```python
try:
    sayi = int(input("Bir sayı girin: "))
    sonuc = 10 / sayi
    print(sonuc)
except ValueError:
    print("Geçersiz sayı!")
except ZeroDivisionError:
    print("Sıfıra bölme hatası!")
except Exception as e:
    print(f"Bilinmeyen hata: {e}")
finally:
    print("Bu her zaman çalışır")
```

### Raise ile Hata Fırlatma
```python
def yas_kontrol(yas):
    if yas < 0:
        raise ValueError("Yaş negatif olamaz!")
    if yas > 150:
        raise ValueError("Yaş çok yüksek!")
    return yas

try:
    yas_kontrol(-5)
except ValueError as e:
    print(e)
```

## 9. Liste Anlayışları

**Ne İşe Yarar:** Listeleri daha kısa ve okunabilir bir şekilde oluşturma yöntemlerini öğretir. Geleneksel for döngüleri yerine kullanılan kompakt yazım şekillerini kapsar.

**Ne Yapar:** Kod satır sayısını azaltır, daha Pythonic (Python tarzında) kod yazmayı sağlar ve liste işlemlerini daha hızlı ve verimli hale getirir.

### Basit Liste Anlayışı
```python
# Geleneksel yöntem
sayilar = []
for i in range(10):
    if i % 2 == 0:
        sayilar.append(i ** 2)

# Liste anlayışı
sayilar = [i ** 2 for i in range(10) if i % 2 == 0]
print(sayilar)  # [0, 4, 16, 36, 64]
```

### Sözlük Anlayışı
```python
isimler = ["Ali", "Ayşe", "Mehmet"]
uzunluklar = {isim: len(isim) for isim in isimler}
print(uzunluklar)  # {'Ali': 3, 'Ayşe': 4, 'Mehmet': 6}
```

## 10. Lambda Fonksiyonları

**Ne İşe Yarar:** Tek satırlık basit fonksiyonlar oluşturma yöntemini öğretir. Anonim fonksiyonlar olarak da bilinen lambda fonksiyonlarının kullanımını kapsar.

**Ne Yapar:** Küçük işlemler için hızlı fonksiyon tanımlama imkanı verir, fonksiyonları parametre olarak geçmeyi kolaylaştırır ve fonksiyonel programlama yaklaşımını destekler.

### Basit Lambda
```python
# Normal fonksiyon
def kare(x):
    return x ** 2

# Lambda fonksiyonu
kare = lambda x: x ** 2

print(kare(5))  # 25
```

### Lambda ile Map
```python
sayilar = [1, 2, 3, 4, 5]
kareler = list(map(lambda x: x ** 2, sayilar))
print(kareler)  # [1, 4, 9, 16, 25]
```

### Lambda ile Filter
```python
sayilar = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
cift_sayilar = list(filter(lambda x: x % 2 == 0, sayilar))
print(cift_sayilar)  # [2, 4, 6, 8, 10]

## 11. Decorator'lar

**Ne İşe Yarar:** Fonksiyonları ve sınıfları değiştirmeden ek özellikler ekleme yöntemini öğretir. Fonksiyonları saran ve davranışlarını değiştiren yapıları kapsar.

**Ne Yapar:** Kod tekrarını önler, fonksiyonlara loglama, zamanlama, doğrulama gibi özellikler ekler ve kodun daha modüler ve yeniden kullanılabilir olmasını sağlar.

### Basit Decorator
```python
def zaman_olc(func):
    import time
    def wrapper(*args, **kwargs):
        baslangic = time.time()
        sonuc = func(*args, **kwargs)
        bitis = time.time()
        print(f"{func.__name__} {bitis - baslangic:.4f} saniye sürdü")
        return sonuc
    return wrapper

@zaman_olc
def yavas_fonksiyon():
    import time
    time.sleep(1)
    return "Tamamlandı"

yavas_fonksiyon()
```

### Parametreli Decorator
```python
def tekrar_et(kac_kez):
    def decorator(func):
        def wrapper(*args, **kwargs):
            for _ in range(kac_kez):
                func(*args, **kwargs)
        return wrapper
    return decorator

@tekrar_et(3)
def selamla():
    print("Merhaba!")

selamla()  # 3 kez yazdırır
```

## 12. Generator'lar

**Ne İşe Yarar:** Bellek dostu veri üretme yöntemini öğretir. Büyük veri setlerini parça parça işlemek için kullanılan yapıları kapsar.

**Ne Yapar:** Bellek kullanımını optimize eder, büyük veri setlerini verimli bir şekilde işler ve lazy evaluation (tembel değerlendirme) sağlar.

### Basit Generator
```python
def sayi_uret(baslangic, bitis):
    for i in range(baslangic, bitis):
        yield i

# Generator kullanımı
for sayi in sayi_uret(1, 6):
    print(sayi)  # 1, 2, 3, 4, 5
```

### Generator Expression
```python
# Liste anlayışı (tüm listeyi bellekte tutar)
liste = [x**2 for x in range(1000000)]

# Generator expression (bellek dostu)
generator = (x**2 for x in range(1000000))

for i in generator:
    if i > 100:
        break
    print(i)
```

## 13. Context Manager'lar

**Ne İşe Yarar:** Kaynak yönetimini otomatikleştiren yapıları öğretir. Dosya açma/kapama, veritabanı bağlantıları gibi kaynakların güvenli kullanımını kapsar.

**Ne Yapar:** Kaynakların otomatik olarak temizlenmesini sağlar, hata durumlarında bile kaynakların düzgün kapatılmasını garanti eder ve kodun daha güvenli olmasını sağlar.

### With Statement
```python
class DosyaYoneticisi:
    def __init__(self, dosya_adi):
        self.dosya_adi = dosya_adi
    
    def __enter__(self):
        self.dosya = open(self.dosya_adi, 'w')
        return self.dosya
    
    def __exit__(self, exc_type, exc_val, exc_tb):
        self.dosya.close()

# Kullanım
with DosyaYoneticisi("test.txt") as f:
    f.write("Merhaba Dünya!")
```

### Contextlib ile Decorator
```python
from contextlib import contextmanager

@contextmanager
def zaman_olc():
    import time
    baslangic = time.time()
    yield
    bitis = time.time()
    print(f"Geçen süre: {bitis - baslangic:.4f} saniye")

with zaman_olc():
    import time
    time.sleep(1)
```

## 14. Asenkron Programlama

**Ne İşe Yarar:** Eşzamanlı işlemleri verimli bir şekilde yönetme yöntemini öğretir. I/O işlemlerini bloklamadan paralel olarak çalıştırma konularını kapsar.

**Ne Yapar:** Programın daha hızlı çalışmasını sağlar, ağ istekleri ve dosya işlemleri gibi beklemeli işlemleri verimli yönetir ve kullanıcı deneyimini iyileştirir.

### Async/Await
```python
import asyncio

async def selamla(isim):
    await asyncio.sleep(1)
    return f"Merhaba {isim}!"

async def main():
    sonuc = await selamla("Dünya")
    print(sonuc)

asyncio.run(main())
```

### Asenkron Döngü
```python
import asyncio

async def islem(sayi):
    await asyncio.sleep(1)
    return sayi * 2

async def main():
    islemler = [islem(i) for i in range(5)]
    sonuclar = await asyncio.gather(*islemler)
    print(sonuclar)

asyncio.run(main())
```

## 15. Threading ve Multiprocessing

**Ne İşe Yarar:** Paralel işlem yapma yöntemlerini öğretir. CPU yoğun işlemler için multiprocessing, I/O işlemleri için threading kullanımını kapsar.

**Ne Yapar:** Programın performansını artırır, birden fazla işlemi aynı anda çalıştırır ve sistem kaynaklarını daha verimli kullanır.

### Threading
```python
import threading
import time

def islem(isim):
    for i in range(3):
        print(f"{isim}: {i}")
        time.sleep(1)

# Thread oluşturma
t1 = threading.Thread(target=islem, args=("Thread-1",))
t2 = threading.Thread(target=islem, args=("Thread-2",))

t1.start()
t2.start()
t1.join()
t2.join()
```

### Multiprocessing
```python
from multiprocessing import Process
import time

def islem(isim):
    for i in range(3):
        print(f"{isim}: {i}")
        time.sleep(1)

if __name__ == "__main__":
    p1 = Process(target=islem, args=("Process-1",))
    p2 = Process(target=islem, args=("Process-2",))
    
    p1.start()
    p2.start()
    p1.join()
    p2.join()
```

## 16. Veri Yapıları

**Ne İşe Yarar:** Gelişmiş veri yapılarını öğretir. Collections modülündeki özel veri yapılarını ve bunların kullanım alanlarını kapsar.

**Ne Yapar:** Veri organizasyonunu iyileştirir, bellek kullanımını optimize eder ve veri işleme işlemlerini daha verimli hale getirir.

### Collections - Namedtuple
```python
from collections import namedtuple

# Namedtuple tanımlama
Kisi = namedtuple('Kisi', ['isim', 'yas', 'sehir'])

# Kullanım
kisi = Kisi("Ali", 25, "İstanbul")
print(kisi.isim)  # Ali
print(kisi[1])    # 25
```

### Collections - Defaultdict
```python
from collections import defaultdict

# Varsayılan değerli sözlük
sayac = defaultdict(int)
kelimeler = ["elma", "armut", "elma", "kiraz"]

for kelime in kelimeler:
    sayac[kelime] += 1

print(sayac)  # defaultdict(<class 'int'>, {'elma': 2, 'armut': 1, 'kiraz': 1})
```

### Collections - Counter
```python
from collections import Counter

kelimeler = ["elma", "armut", "elma", "kiraz", "elma"]
sayac = Counter(kelimeler)

print(sayac)  # Counter({'elma': 3, 'armut': 1, 'kiraz': 1})
print(sayac.most_common(2))  # [('elma', 3), ('armut', 1)]
```

## 17. Web Geliştirme

**Ne İşe Yarar:** Web uygulamaları geliştirme yöntemlerini öğretir. Flask ve Django gibi web framework'lerinin kullanımını ve HTTP isteklerini kapsar.

**Ne Yapar:** Web siteleri ve API'ler oluşturmayı sağlar, kullanıcı arayüzleri geliştirmeyi kolaylaştırır ve web tabanlı uygulamalar yapmayı mümkün kılar.

### Flask - Basit Uygulama
```python
from flask import Flask, request, jsonify

app = Flask(__name__)

@app.route('/')
def ana_sayfa():
    return "Merhaba Dünya!"

@app.route('/api/kisi', methods=['POST'])
def kisi_ekle():
    veri = request.get_json()
    return jsonify({"mesaj": "Kişi eklendi", "veri": veri})

if __name__ == '__main__':
    app.run(debug=True)
```

### Requests - HTTP İstekleri
```python
import requests

# GET isteği
yanit = requests.get('https://api.github.com/users/octocat')
veri = yanit.json()
print(veri['login'])

# POST isteği
veri = {'isim': 'Ahmet', 'yas': 25}
yanit = requests.post('https://httpbin.org/post', json=veri)
print(yanit.json())
```

## 18. Veri Analizi

**Ne İşe Yarar:** Büyük veri setlerini analiz etme ve işleme yöntemlerini öğretir. Pandas, NumPy gibi veri analizi kütüphanelerinin kullanımını kapsar.

**Ne Yapar:** Veri temizleme, dönüştürme ve analiz işlemlerini kolaylaştırır, istatistiksel hesaplamalar yapar ve veri görselleştirme imkanı sağlar.

### Pandas - Temel İşlemler
```python
import pandas as pd

# DataFrame oluşturma
df = pd.DataFrame({
    'isim': ['Ali', 'Ayşe', 'Mehmet'],
    'yas': [25, 30, 35],
    'sehir': ['İstanbul', 'Ankara', 'İzmir']
})

print(df.head())
print(df['yas'].mean())  # Ortalama yaş
```

### NumPy - Dizi İşlemleri
```python
import numpy as np

# Dizi oluşturma
dizi = np.array([1, 2, 3, 4, 5])
print(dizi.mean())  # Ortalama
print(dizi.std())   # Standart sapma

# 2D dizi
matris = np.array([[1, 2], [3, 4]])
print(matris.shape)  # (2, 2)
```

## 19. Machine Learning

**Ne İşe Yarar:** Makine öğrenmesi modelleri oluşturma ve eğitme yöntemlerini öğretir. Scikit-learn, TensorFlow gibi ML kütüphanelerinin kullanımını kapsar.

**Ne Yapar:** Veri tabanlı tahminler yapar, sınıflandırma ve regresyon modelleri oluşturur ve yapay zeka uygulamaları geliştirmeyi mümkün kılar.

### Scikit-learn - Basit Model
```python
from sklearn.linear_model import LinearRegression
from sklearn.model_selection import train_test_split
import numpy as np

# Veri oluşturma
X = np.array([[1], [2], [3], [4], [5]])
y = np.array([2, 4, 6, 8, 10])

# Model eğitimi
model = LinearRegression()
model.fit(X, y)

# Tahmin
tahmin = model.predict([[6]])
print(tahmin[0])  # 12.0
```

### Matplotlib - Grafik Çizimi
```python
import matplotlib.pyplot as plt
import numpy as np

x = np.linspace(0, 10, 100)
y = np.sin(x)

plt.plot(x, y)
plt.title('Sinüs Grafiği')
plt.xlabel('x')
plt.ylabel('sin(x)')
plt.show()
```

## 20. GUI Programlama

**Ne İşe Yarar:** Grafiksel kullanıcı arayüzleri (GUI) oluşturma yöntemlerini öğretir. Tkinter, PyQt gibi GUI kütüphanelerinin kullanımını kapsar.

**Ne Yapar:** Masaüstü uygulamaları oluşturmayı sağlar, kullanıcı dostu arayüzler geliştirir ve görsel programlar yapmayı mümkün kılar.

### Tkinter - Basit Pencere
```python
import tkinter as tk
from tkinter import messagebox

def buton_tikla():
    messagebox.showinfo("Bilgi", "Butona tıklandı!")

# Ana pencere
root = tk.Tk()
root.title("Basit Uygulama")
root.geometry("300x200")

# Buton
buton = tk.Button(root, text="Tıkla", command=buton_tikla)
buton.pack(pady=20)

root.mainloop()
```

### PyQt5 - Modern GUI
```python
from PyQt5.QtWidgets import QApplication, QMainWindow, QPushButton, QVBoxLayout, QWidget
import sys

class AnaPencere(QMainWindow):
    def __init__(self):
        super().__init__()
        self.setWindowTitle("PyQt5 Uygulaması")
        self.setGeometry(100, 100, 300, 200)
        
        # Merkezi widget
        merkez = QWidget()
        self.setCentralWidget(merkez)
        
        # Layout
        layout = QVBoxLayout()
        buton = QPushButton("Tıkla")
        buton.clicked.connect(self.buton_tikla)
        layout.addWidget(buton)
        
        merkez.setLayout(layout)
    
    def buton_tikla(self):
        print("Butona tıklandı!")

app = QApplication(sys.argv)
pencere = AnaPencere()
pencere.show()
sys.exit(app.exec_())

## 21. Network Programming

**Ne İşe Yarar:** Ağ programlama ve iletişim protokollerini öğretir. Socket programlama, TCP/UDP iletişimi ve ağ uygulamaları geliştirme konularını kapsar.

**Ne Yapar:** İstemci-sunucu uygulamaları oluşturmayı sağlar, ağ üzerinden veri alışverişi yapar ve dağıtık sistemler geliştirmeyi mümkün kılar.

### Socket - Basit Sunucu
```python
import socket

# Sunucu oluşturma
sunucu = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
sunucu.bind(('localhost', 12345))
sunucu.listen(1)

print("Sunucu dinleniyor...")
baglanti, adres = sunucu.accept()
print(f"Bağlantı: {adres}")

veri = baglanti.recv(1024).decode()
print(f"Gelen veri: {veri}")

baglanti.close()
sunucu.close()
```

### Socket - İstemci
```python
import socket

# İstemci oluşturma
istemci = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
istemci.connect(('localhost', 12345))

mesaj = "Merhaba Sunucu!"
istemci.send(mesaj.encode())

istemci.close()
```

## 22. Database Programming

**Ne İşe Yarar:** Veritabanı işlemleri ve veri saklama yöntemlerini öğretir. SQLite, PostgreSQL gibi veritabanlarıyla çalışma ve ORM kullanımını kapsar.

**Ne Yapar:** Kalıcı veri saklama imkanı verir, veri sorgulama ve güncelleme işlemlerini kolaylaştırır ve uygulama verilerini organize bir şekilde yönetir.

### SQLite - Temel İşlemler
```python
import sqlite3

# Veritabanı bağlantısı
conn = sqlite3.connect('test.db')
cursor = conn.cursor()

# Tablo oluşturma
cursor.execute('''
    CREATE TABLE IF NOT EXISTS kullanicilar (
        id INTEGER PRIMARY KEY,
        isim TEXT NOT NULL,
        yas INTEGER
    )
''')

# Veri ekleme
cursor.execute("INSERT INTO kullanicilar (isim, yas) VALUES (?, ?)", ("Ali", 25))
conn.commit()

# Veri sorgulama
cursor.execute("SELECT * FROM kullanicilar")
kullanicilar = cursor.fetchall()
print(kullanicilar)

conn.close()
```

### SQLAlchemy - ORM
```python
from sqlalchemy import create_engine, Column, Integer, String
from sqlalchemy.ext.declarative import declarative_base
from sqlalchemy.orm import sessionmaker

Base = declarative_base()

class Kullanici(Base):
    __tablename__ = 'kullanicilar'
    
    id = Column(Integer, primary_key=True)
    isim = Column(String)
    yas = Column(Integer)

# Veritabanı bağlantısı
engine = create_engine('sqlite:///test.db')
Base.metadata.create_all(engine)

Session = sessionmaker(bind=engine)
session = Session()

# Kullanıcı ekleme
yeni_kullanici = Kullanici(isim="Ayşe", yas=30)
session.add(yeni_kullanici)
session.commit()

# Kullanıcı sorgulama
kullanicilar = session.query(Kullanici).all()
for k in kullanicilar:
    print(f"{k.isim}, {k.yas}")
```

## 23. Testing

**Ne İşe Yarar:** Kod kalitesini artırmak için test yazma yöntemlerini öğretir. Unit test, integration test ve test-driven development konularını kapsar.

**Ne Yapar:** Kodun doğru çalıştığını garanti eder, hataları erken tespit eder ve kod değişikliklerinin güvenli olmasını sağlar.

### Unit Testing
```python
import unittest

def topla(a, b):
    return a + b

class TestTopla(unittest.TestCase):
    def test_pozitif_sayilar(self):
        self.assertEqual(topla(2, 3), 5)
    
    def test_negatif_sayilar(self):
        self.assertEqual(topla(-1, -2), -3)
    
    def test_sifir(self):
        self.assertEqual(topla(0, 5), 5)

if __name__ == '__main__':
    unittest.main()
```

### Pytest - Basit Test
```python
import pytest

def carp(a, b):
    return a * b

def test_carp():
    assert carp(2, 3) == 6
    assert carp(-2, 3) == -6
    assert carp(0, 5) == 0

# pytest dosya_adi.py -v
```

## 24. Performance Optimization

**Ne İşe Yarar:** Program performansını artırma ve optimize etme yöntemlerini öğretir. Profiling, benchmarking ve performans analizi konularını kapsar.

**Ne Yapar:** Programın daha hızlı çalışmasını sağlar, bellek kullanımını optimize eder ve performans darboğazlarını tespit eder.

### Profiling
```python
import cProfile
import pstats

def yavas_fonksiyon():
    toplam = 0
    for i in range(1000000):
        toplam += i
    return toplam

# Profiling
profiler = cProfile.Profile()
profiler.enable()
yavas_fonksiyon()
profiler.disable()

stats = pstats.Stats(profiler)
stats.sort_stats('cumulative')
stats.print_stats(10)
```

### Memory Profiling
```python
from memory_profiler import profile

@profile
def bellek_yogun():
    liste = []
    for i in range(100000):
        liste.append(i)
    return liste

bellek_yogun()
```

## 25. Security

**Ne İşe Yarar:** Güvenli programlama ve veri koruma yöntemlerini öğretir. Şifreleme, hash işlemleri ve güvenlik best practices konularını kapsar.

**Ne Yapar:** Kullanıcı verilerini korur, güvenlik açıklarını önler ve uygulamanın güvenli olmasını sağlar.

### Password Hashing
```python
import hashlib
import os

def sifre_hash(sifre):
    # Salt oluşturma
    salt = os.urandom(32)
    # Hash oluşturma
    hash_obj = hashlib.pbkdf2_hmac('sha256', sifre.encode(), salt, 100000)
    return salt + hash_obj

def sifre_dogrula(sifre, hash_veri):
    salt = hash_veri[:32]
    hash_obj = hashlib.pbkdf2_hmac('sha256', sifre.encode(), salt, 100000)
    return hash_obj == hash_veri[32:]

# Kullanım
hash_edilmis = sifre_hash("gizli123")
print(sifre_dogrula("gizli123", hash_edilmis))  # True
```

### Input Validation
```python
import re

def email_dogrula(email):
    pattern = r'^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$'
    return re.match(pattern, email) is not None

def sayi_dogrula(sayi_str):
    try:
        sayi = int(sayi_str)
        return 0 <= sayi <= 100
    except ValueError:
        return False

print(email_dogrula("test@example.com"))  # True
print(sayi_dogrula("50"))  # True
```

## 26. Deployment

**Ne İşe Yarar:** Uygulamaları canlı ortama yayınlama ve dağıtma yöntemlerini öğretir. Docker, virtual environment ve deployment stratejilerini kapsar.

**Ne Yapar:** Uygulamaların farklı ortamlarda çalışmasını sağlar, deployment sürecini otomatikleştirir ve uygulama yönetimini kolaylaştırır.

### Docker - Basit Container
```python
# Dockerfile
"""
FROM python:3.9-slim
WORKDIR /app
COPY requirements.txt .
RUN pip install -r requirements.txt
COPY . .
EXPOSE 5000
CMD ["python", "app.py"]
"""

# requirements.txt
"""
flask==2.0.1
requests==2.26.0
"""

# app.py
from flask import Flask
app = Flask(__name__)

@app.route('/')
def hello():
    return "Merhaba Docker!"

if __name__ == '__main__':
    app.run(host='0.0.0.0', port=5000)
```

### Virtual Environment
```python
# Sanal ortam oluşturma
# python -m venv myenv

# Sanal ortamı aktifleştirme (Windows)
# myenv\Scripts\activate

# Sanal ortamı aktifleştirme (Linux/Mac)
# source myenv/bin/activate

# Paket yükleme
# pip install package_name

# Requirements dosyası oluşturma
# pip freeze > requirements.txt
```

## 27. Best Practices

**Ne İşe Yarar:** Kaliteli ve sürdürülebilir kod yazma kurallarını öğretir. PEP 8 standartları, docstring yazımı ve kod organizasyonu konularını kapsar.

**Ne Yapar:** Kodun okunabilirliğini artırır, takım çalışmasını kolaylaştırır ve kod kalitesini yükseltir.

### PEP 8 - Kod Stili
```python
# İyi stil
def hesapla_ortalama(sayilar):
    """Sayıların ortalamasını hesaplar."""
    if not sayilar:
        return 0
    return sum(sayilar) / len(sayilar)

# Kötü stil
def hesaplaOrtalama(sayilar):
    if len(sayilar)==0:
        return 0
    return sum(sayilar)/len(sayilar)
```

### Docstring
```python
def bol(a, b):
    """
    İki sayıyı böler.
    
    Args:
        a (float): Bölünen sayı
        b (float): Bölen sayı
        
    Returns:
        float: Bölüm sonucu
        
    Raises:
        ZeroDivisionError: b sıfır ise
    """
    if b == 0:
        raise ZeroDivisionError("Sıfıra bölme hatası")
    return a / b
```

## 28. Advanced Patterns

**Ne İşe Yarar:** Yazılım tasarım desenlerini ve ileri seviye programlama tekniklerini öğretir. Singleton, Factory gibi tasarım desenlerini kapsar.

**Ne Yapar:** Kodun daha esnek ve genişletilebilir olmasını sağlar, yaygın programlama problemlerine standart çözümler sunar ve kod mimarisini iyileştirir.

### Singleton Pattern
```python
class Singleton:
    _instance = None
    
    def __new__(cls):
        if cls._instance is None:
            cls._instance = super().__new__(cls)
        return cls._instance

# Kullanım
s1 = Singleton()
s2 = Singleton()
print(s1 is s2)  # True
```

### Factory Pattern
```python
class Hayvan:
    def ses_cikar(self):
        pass

class Kopek(Hayvan):
    def ses_cikar(self):
        return "Hav hav!"

class Kedi(Hayvan):
    def ses_cikar(self):
        return "Miyav!"

class HayvanFabrikasi:
    @staticmethod
    def hayvan_olustur(tip):
        if tip == "kopek":
            return Kopek()
        elif tip == "kedi":
            return Kedi()
        else:
            raise ValueError("Bilinmeyen hayvan tipi")

# Kullanım
hayvan = HayvanFabrikasi.hayvan_olustur("kopek")
print(hayvan.ses_cikar())  # Hav hav!
```

## 29. Metaclass'lar

**Ne İşe Yarar:** Sınıfların nasıl oluşturulduğunu kontrol etme yöntemini öğretir. Metaclass'ların sınıf oluşturma sürecini nasıl etkilediğini kapsar.

**Ne Yapar:** Sınıf oluşturma sürecini özelleştirir, otomatik kod üretimi sağlar ve framework geliştirme imkanı verir.

### Basit Metaclass
```python
class MetaSinif(type):
    def __new__(cls, name, bases, attrs):
        # Sınıf oluşturulmadan önce çalışır
        attrs['sinif_adi'] = name
        return super().__new__(cls, name, bases, attrs)

class TestSinif(metaclass=MetaSinif):
    pass

print(TestSinif.sinif_adi)  # TestSinif
```

### Metaclass ile Validation
```python
class ValidatorMeta(type):
    def __new__(cls, name, bases, attrs):
        # Zorunlu alanları kontrol et
        if 'zorunlu_alanlar' in attrs:
            for alan in attrs['zorunlu_alanlar']:
                if alan not in attrs:
                    raise AttributeError(f"Zorunlu alan eksik: {alan}")
        return super().__new__(cls, name, bases, attrs)

class TestSinif(metaclass=ValidatorMeta):
    zorunlu_alanlar = ['metod1']
    
    def metod1(self):
        return "Test"
```

## 30. Python Black Magic

**Ne İşe Yarar:** Python'un gizli özelliklerini ve ileri seviye tekniklerini öğretir. Descriptor protocol, monkey patching gibi gelişmiş konuları kapsar.

**Ne Yapar:** Python'un derinliklerine iner, özel davranışlar oluşturur ve framework geliştirme imkanı sağlar.

### Descriptor Protocol
```python
class PozitifSayi:
    def __init__(self, name):
        self.name = name
    
    def __get__(self, instance, owner):
        return instance.__dict__.get(self.name)
    
    def __set__(self, instance, value):
        if value < 0:
            raise ValueError("Negatif değer olamaz!")
        instance.__dict__[self.name] = value

class Kisi:
    yas = PozitifSayi('yas')
    
    def __init__(self, yas):
        self.yas = yas

# Kullanım
kisi = Kisi(25)
print(kisi.yas)  # 25
# kisi.yas = -5  # ValueError
```

### Monkey Patching
```python
class OrijinalSinif:
    def metod(self):
        return "Orijinal"

def yeni_metod(self):
    return "Yeni metod"

# Monkey patching
OrijinalSinif.metod = yeni_metod

obj = OrijinalSinif()
print(obj.metod())  # Yeni metod

## 31. Data Classes

**Ne İşe Yarar:** Veri tutmak için özel sınıflar oluşturma yöntemini öğretir. Otomatik olarak __init__, __repr__, __eq__ gibi metodları oluşturan dekoratörü kapsar.

**Ne Yapar:** Kod yazımını kısaltır, veri sınıflarını daha temiz hale getirir ve boilerplate kod miktarını azaltır.

### Basit Data Class
```python
from dataclasses import dataclass

@dataclass
class Kisi:
    isim: str
    yas: int
    sehir: str = "İstanbul"

# Otomatik __init__, __repr__, __eq__ oluşturulur
kisi1 = Kisi("Ali", 25)
kisi2 = Kisi("Ayşe", 30, "Ankara")
print(kisi1)  # Kisi(isim='Ali', yas=25, sehir='İstanbul')
```

### Frozen Data Class
```python
from dataclasses import dataclass

@dataclass(frozen=True)
class Koordinat:
    x: int
    y: int

koordinat = Koordinat(10, 20)
# koordinat.x = 30  # FrozenInstanceError
```

## 32. Type Hints ve Annotations

**Ne İşe Yarar:** Kod içinde veri tiplerini belirtme yöntemini öğretir. Fonksiyon parametrelerinin ve dönüş değerlerinin tiplerini açıkça belirtme konularını kapsar.

**Ne Yapar:** Kodun daha okunabilir olmasını sağlar, IDE desteğini artırır, hataları erken tespit eder ve kod dokümantasyonunu iyileştirir.

### Temel Type Hints
```python
def selamla(isim: str) -> str:
    return f"Merhaba {isim}!"

def topla(a: int, b: int) -> int:
    return a + b

def liste_isle(sayilar: list[int]) -> float:
    return sum(sayilar) / len(sayilar)

# Kullanım
mesaj: str = selamla("Dünya")
sonuc: int = topla(5, 3)
```

### Optional ve Union Types
```python
from typing import Optional, Union

def kisi_bul(id: int) -> Optional[str]:
    if id == 1:
        return "Ali"
    return None

def islem_yap(deger: Union[int, float, str]) -> str:
    return str(deger)

# Python 3.10+ için | operatörü
def islem_yap_v2(deger: int | float | str) -> str:
    return str(deger)
```

## 33. Pattern Matching

**Ne İşe Yarar:** Veri yapılarını desen eşleştirme ile analiz etme yöntemini öğretir. Match-case yapısı ve structural pattern matching konularını kapsar.

**Ne Yapar:** Karmaşık koşul ifadelerini basitleştirir, veri analizini daha okunabilir hale getirir ve kod yazımını kolaylaştırır.

### Match Statement (Python 3.10+)
```python
def analiz_et(veri):
    match veri:
        case str():
            return f"String: {veri}"
        case int() if veri > 0:
            return f"Pozitif sayı: {veri}"
        case int():
            return f"Negatif sayı: {veri}"
        case list() as liste if len(liste) > 0:
            return f"Liste: {liste}"
        case _:
            return "Bilinmeyen tip"

print(analiz_et("merhaba"))  # String: merhaba
print(analiz_et(42))         # Pozitif sayı: 42
```

### Structural Pattern Matching
```python
def oyun_analiz(hamle):
    match hamle:
        case ("taş", "makas"):
            return "Taş kazandı"
        case ("kağıt", "taş"):
            return "Kağıt kazandı"
        case ("makas", "kağıt"):
            return "Makas kazandı"
        case (a, b) if a == b:
            return "Berabere"
        case _:
            return "Geçersiz hamle"

print(oyun_analiz(("taş", "makas")))  # Taş kazandı
```

## 34. Walrus Operator

**Ne İşe Yarar:** Atama ve değerlendirme işlemlerini tek satırda yapma yöntemini öğretir. := operatörünün kullanımını ve faydalarını kapsar.

**Ne Yapar:** Kod satır sayısını azaltır, daha kompakt kod yazmayı sağlar ve özellikle döngülerde ve koşullarda kullanışlıdır.

### Assignment Expression (Python 3.8+)
```python
# Geleneksel yöntem
sayilar = [1, 2, 3, 4, 5]
kareler = []
for sayi in sayilar:
    kare = sayi ** 2
    if kare > 10:
        kareler.append(kare)

# Walrus operator ile
kareler = [kare for sayi in sayilar if (kare := sayi ** 2) > 10]
print(kareler)  # [16, 25]
```

### While Döngüsünde Kullanım
```python
# Geleneksel yöntem
while True:
    veri = input("Bir sayı girin (çıkmak için 'q'): ")
    if veri == 'q':
        break
    print(f"Girdiğiniz sayı: {veri}")

# Walrus operator ile
while (veri := input("Bir sayı girin (çıkmak için 'q'): ")) != 'q':
    print(f"Girdiğiniz sayı: {veri}")
```

## 35. Assignment Expressions

**Ne İşe Yarar:** Atama ifadelerinin farklı kullanım alanlarını öğretir. Walrus operatörünün çeşitli senaryolarda nasıl kullanılacağını kapsar.

**Ne Yapar:** Karmaşık hesaplamaları basitleştirir, performansı artırır ve kod okunabilirliğini iyileştirir.

### List Comprehension'da Kullanım
```python
# Karmaşık hesaplama
sayilar = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

# Geleneksel yöntem
sonuclar = []
for sayi in sayilar:
    kare = sayi ** 2
    if kare % 2 == 0:
        sonuclar.append(kare)

# Assignment expression ile
sonuclar = [kare for sayi in sayilar if (kare := sayi ** 2) % 2 == 0]
print(sonuclar)  # [4, 16, 36, 64, 100]
```

### Conditional Expression ile
```python
# Geleneksel yöntem
def hesapla(sayi):
    if sayi > 0:
        kare = sayi ** 2
        return kare
    else:
        return 0

# Assignment expression ile
def hesapla_v2(sayi):
    return (kare := sayi ** 2) if sayi > 0 else 0
```

## 36. Positional-Only Parameters

**Ne İşe Yarar:** Fonksiyon parametrelerinin nasıl geçirileceğini kontrol etme yöntemini öğretir. / operatörü ile positional-only parametreleri kapsar.

**Ne Yapar:** API tasarımını iyileştirir, fonksiyon kullanımını daha net hale getirir ve parametre geçirme kurallarını belirler.

### Positional-Only (Python 3.8+)
```python
def hesapla(a, b, /, c, d, *, e, f):
    """
    / öncesi: sadece positional
    / ve * arası: positional veya keyword
    * sonrası: sadece keyword
    """
    return a + b + c + d + e + f

# Doğru kullanım
sonuc = hesapla(1, 2, 3, 4, e=5, f=6)
sonuc = hesapla(1, 2, c=3, d=4, e=5, f=6)

# Hatalı kullanım
# sonuc = hesapla(a=1, b=2, 3, 4, e=5, f=6)  # TypeError
# sonuc = hesapla(1, 2, 3, 4, 5, 6)  # TypeError
```

## 37. Keyword-Only Parameters

**Ne İşe Yarar:** Fonksiyon parametrelerinin sadece keyword olarak geçirilmesini zorunlu kılma yöntemini öğretir. * operatörü ile keyword-only parametreleri kapsar.

**Ne Yapar:** Fonksiyon çağrılarını daha açık hale getirir, parametre karışıklığını önler ve API kullanımını daha güvenli yapar.

### Keyword-Only
```python
def kisi_olustur(*, isim: str, yas: int, sehir: str = "İstanbul"):
    return {"isim": isim, "yas": yas, "sehir": sehir}

# Doğru kullanım
kisi = kisi_olustur(isim="Ali", yas=25)
kisi = kisi_olustur(isim="Ayşe", yas=30, sehir="Ankara")

# Hatalı kullanım
# kisi = kisi_olustur("Ali", 25)  # TypeError
```

## 38. F-Strings Gelişmiş

**Ne İşe Yarar:** F-string'lerin gelişmiş özelliklerini öğretir. Format belirleyicileri, expression'lar ve debug özelliklerini kapsar.

**Ne Yapar:** String formatlamayı daha güçlü hale getirir, debug işlemlerini kolaylaştırır ve kod yazımını daha verimli yapar.

### F-String Özellikleri
```python
isim = "Ali"
yas = 25
boy = 1.75

# Temel kullanım
print(f"Merhaba {isim}")

# Format belirleyicileri
print(f"Yaş: {yas:03d}")  # Yaş: 025
print(f"Boy: {boy:.2f}m")  # Boy: 1.75m

# Expression'lar
print(f"Gelecek yıl: {yas + 1} yaşında olacak")

# Dictionary erişimi
kisi = {"isim": "Ayşe", "yas": 30}
print(f"Kişi: {kisi['isim']}, {kisi['yas']} yaşında")

# Method çağrıları
print(f"İsim büyük harflerle: {isim.upper()}")
```

### F-String ile Debug
```python
# Python 3.8+ debug özelliği
x = 10
y = 20
print(f"{x=}, {y=}")  # x=10, y=20

# Karmaşık debug
def hesapla(a, b):
    toplam = a + b
    carpim = a * b
    print(f"{a=}, {b=}, {toplam=}, {carpim=}")
    return toplam, carpim

hesapla(5, 3)  # a=5, b=3, toplam=8, carpim=15
```

## 39. Dictionary Union Operators

**Ne İşe Yarar:** Sözlükleri birleştirme işlemlerini kolaylaştıran operatörleri öğretir. | ve |= operatörlerinin sözlük işlemlerinde kullanımını kapsar.

**Ne Yapar:** Sözlük birleştirme işlemlerini basitleştirir, kod yazımını kısaltır ve daha okunabilir kod sağlar.

### Dictionary Union (Python 3.9+)
```python
# Geleneksel yöntem
dict1 = {"a": 1, "b": 2}
dict2 = {"c": 3, "d": 4}
dict3 = {**dict1, **dict2}

# Union operator ile
dict3 = dict1 | dict2
print(dict3)  # {'a': 1, 'b': 2, 'c': 3, 'd': 4}

# In-place union
dict1 |= dict2
print(dict1)  # {'a': 1, 'b': 2, 'c': 3, 'd': 4}
```

### Dictionary Merge
```python
# Çakışan anahtarlar
dict1 = {"a": 1, "b": 2}
dict2 = {"b": 3, "c": 4}

# Son değer kazanır
merged = dict1 | dict2
print(merged)  # {'a': 1, 'b': 3, 'c': 4}

# In-place merge
dict1 |= dict2
print(dict1)  # {'a': 1, 'b': 3, 'c': 4}
```

## 40. Type Hints in Standard Collections

**Ne İşe Yarar:** Standart koleksiyonlarda tip belirtme yöntemlerini öğretir. List, Dict, Set gibi koleksiyonlarda generic type kullanımını kapsar.

**Ne Yapar:** Koleksiyonların içerik tiplerini belirtir, tip güvenliğini artırır ve IDE desteğini iyileştirir.

### Typed Collections
```python
from typing import List, Dict, Set, Tuple, Optional

# Liste type hints
sayilar: List[int] = [1, 2, 3, 4, 5]
isimler: List[str] = ["Ali", "Ayşe", "Mehmet"]

# Sözlük type hints
kullanicilar: Dict[str, int] = {"Ali": 25, "Ayşe": 30}

# Set type hints
benzersiz_sayilar: Set[int] = {1, 2, 3, 4, 5}

# Tuple type hints
koordinat: Tuple[int, int] = (10, 20)
kisi_bilgi: Tuple[str, int, str] = ("Ali", 25, "İstanbul")

# Python 3.9+ built-in types
sayilar: list[int] = [1, 2, 3]
kullanicilar: dict[str, int] = {"Ali": 25}
```

### Generic Types
```python
from typing import TypeVar, Generic

T = TypeVar('T')

class Stack(Generic[T]):
    def __init__(self):
        self.items: List[T] = []
    
    def push(self, item: T) -> None:
        self.items.append(item)
    
    def pop(self) -> T:
        return self.items.pop()

# Kullanım
int_stack: Stack[int] = Stack()
int_stack.push(1)
int_stack.push(2)
print(int_stack.pop())  # 2

## 41. Structural Pattern Matching

**Ne İşe Yarar:** Karmaşık veri yapılarını desen eşleştirme ile analiz etme yöntemini öğretir. Nested pattern matching ve guard clause'ları kapsar.

**Ne Yapar:** Karmaşık veri analizini basitleştirir, kod okunabilirliğini artırır ve veri işleme mantığını daha net hale getirir.

### Match Statement Detaylı
```python
def analiz_et(veri):
    match veri:
        case str() as metin if len(metin) > 5:
            return f"Uzun string: {metin}"
        case str():
            return f"Kısa string: {veri}"
        case int() as sayi if sayi > 0:
            return f"Pozitif sayı: {sayi}"
        case int():
            return f"Negatif sayı: {veri}"
        case list() as liste if len(liste) == 0:
            return "Boş liste"
        case list() as liste:
            return f"Liste uzunluğu: {len(liste)}"
        case _:
            return "Bilinmeyen tip"

print(analiz_et("merhaba"))  # Uzun string: merhaba
print(analiz_et("hi"))       # Kısa string: hi
```

## 42. Match Statement

**Ne İşe Yarar:** Match-case yapısının temel kullanımını öğretir. Basit pattern matching ve case statement'ların kullanımını kapsar.

**Ne Yapar:** Switch-case benzeri yapıları Python'da kullanmayı sağlar, koşul ifadelerini basitleştirir ve kod yazımını kolaylaştırır.

### Basit Match
```python
def gun_analiz(gun):
    match gun.lower():
        case "pazartesi" | "salı" | "çarşamba" | "perşembe" | "cuma":
            return "İş günü"
        case "cumartesi" | "pazar":
            return "Hafta sonu"
        case _:
            return "Geçersiz gün"

print(gun_analiz("Pazartesi"))  # İş günü
print(gun_analiz("Cumartesi"))  # Hafta sonu
```

## 43. Case Statements

**Ne İşe Yarar:** Case statement'ların farklı veri yapılarıyla kullanımını öğretir. Liste, tuple ve diğer veri yapılarında pattern matching kapsar.

**Ne Yapar:** Veri yapılarının analizini kolaylaştırır, karmaşık koşulları basitleştirir ve veri işleme mantığını netleştirir.

### Case ile Veri Yapıları
```python
def liste_analiz(veri):
    match veri:
        case []:
            return "Boş liste"
        case [x]:
            return f"Tek eleman: {x}"
        case [x, y]:
            return f"İki eleman: {x}, {y}"
        case [x, y, z]:
            return f"Üç eleman: {x}, {y}, {z}"
        case [x, *rest]:
            return f"İlk eleman: {x}, kalan: {rest}"

print(liste_analiz([1, 2, 3, 4]))  # İlk eleman: 1, kalan: [2, 3, 4]
```

## 44. Guard Clauses

**Ne İşe Yarar:** Pattern matching'de ek koşullar ekleme yöntemini öğretir. Guard clause'ların if ile birlikte kullanımını kapsar.

**Ne Yapar:** Pattern matching'i daha esnek hale getirir, karmaşık koşulları ifade etmeyi kolaylaştırır ve kod mantığını netleştirir.

### Guard ile Koşullar
```python
def sayi_analiz(sayi):
    match sayi:
        case n if n < 0:
            return "Negatif sayı"
        case n if n == 0:
            return "Sıfır"
        case n if n % 2 == 0:
            return "Çift pozitif sayı"
        case n if n % 2 == 1:
            return "Tek pozitif sayı"

print(sayi_analiz(-5))  # Negatif sayı
print(sayi_analiz(4))   # Çift pozitif sayı
```

## 45. Pattern Matching with Classes

**Ne İşe Yarar:** Sınıf nesnelerini pattern matching ile analiz etme yöntemini öğretir. Dataclass'lar ve özel sınıflarla pattern matching kapsar.

**Ne Yapar:** Nesne analizini kolaylaştırır, OOP ile pattern matching'i birleştirir ve veri işleme mantığını iyileştirir.

### Sınıf Pattern Matching
```python
from dataclasses import dataclass

@dataclass
class Nokta:
    x: int
    y: int

@dataclass
class Cember:
    merkez: Nokta
    yaricap: float

def sekil_analiz(sekil):
    match sekil:
        case Nokta(x, y):
            return f"Nokta: ({x}, {y})"
        case Cember(Nokta(x, y), r):
            return f"Çember: merkez({x}, {y}), yarıçap={r}"

nokta = Nokta(10, 20)
cember = Cember(Nokta(0, 0), 5.0)

print(sekil_analiz(nokta))   # Nokta: (10, 20)
print(sekil_analiz(cember))  # Çember: merkez(0, 0), yarıçap=5.0
```

## 46. Dataclass Fields

**Ne İşe Yarar:** Dataclass'larda alan özelliklerini özelleştirme yöntemini öğretir. Field dekoratörünün farklı parametrelerini kapsar.

**Ne Yapar:** Dataclass'ların davranışını özelleştirir, alan özelliklerini kontrol eder ve daha esnek veri sınıfları oluşturur.

### Field Özellikleri
```python
from dataclasses import dataclass, field

@dataclass
class Kisi:
    isim: str
    yas: int = field(default=18, compare=False)
    id: int = field(init=False, default_factory=lambda: hash(str(id)))
    notlar: list = field(default_factory=list, repr=False)

kisi = Kisi("Ali")
print(kisi)  # Kisi(isim='Ali', yas=18)
```

## 47. Post Init Processing

**Ne İşe Yarar:** Dataclass'larda __init__ sonrası işlemler yapma yöntemini öğretir. __post_init__ metodunun kullanımını kapsar.

**Ne Yapar:** Nesne oluşturulduktan sonra ek işlemler yapar, hesaplanmış alanları otomatik oluşturur ve veri doğrulama işlemlerini gerçekleştirir.

### Post Init
```python
from dataclasses import dataclass

@dataclass
class Dikdortgen:
    genislik: float
    yukseklik: float
    alan: float = None
    
    def __post_init__(self):
        if self.alan is None:
            self.alan = self.genislik * self.yukseklik

dikdortgen = Dikdortgen(5.0, 3.0)
print(dikdortgen.alan)  # 15.0
```

## 48. Dataclass Inheritance

**Ne İşe Yarar:** Dataclass'larda kalıtım kullanma yöntemini öğretir. Dataclass'ların nasıl miras alınacağını ve genişletileceğini kapsar.

**Ne Yapar:** Dataclass'ları genişletir, kod tekrarını önler ve hiyerarşik veri yapıları oluşturur.

### Kalıtım
```python
from dataclasses import dataclass

@dataclass
class Hayvan:
    isim: str
    yas: int

@dataclass
class Kopek(Hayvan):
    cins: str
    havlar: bool = True

kopek = Kopek("Karabaş", 5, "Golden")
print(kopek)  # Kopek(isim='Karabaş', yas=5, cins='Golden', havlar=True)
```

## 49. Frozen Dataclasses

**Ne İşe Yarar:** Değişmez (immutable) dataclass'lar oluşturma yöntemini öğretir. Frozen dataclass'ların özelliklerini ve kullanımını kapsar.

**Ne Yapar:** Veri bütünlüğünü korur, thread-safe kod yazmayı sağlar ve yanlışlıkla veri değişikliklerini önler.

### Frozen Özelliği
```python
from dataclasses import dataclass

@dataclass(frozen=True)
class Ayarlar:
    tema: str
    dil: str
    ses_seviyesi: int

ayarlar = Ayarlar("koyu", "tr", 50)
# ayarlar.tema = "açık"  # FrozenInstanceError
```

## 50. Slots

**Ne İşe Yarar:** Sınıf nesnelerinin bellek kullanımını optimize etme yöntemini öğretir. __slots__ özelliğinin kullanımını ve faydalarını kapsar.

**Ne Yapar:** Bellek kullanımını azaltır, nesne erişim hızını artırır ve dinamik özellik eklemeyi sınırlar.

### __slots__ Kullanımı
```python
class Kisi:
    __slots__ = ['isim', 'yas', 'sehir']
    
    def __init__(self, isim, yas, sehir):
        self.isim = isim
        self.yas = yas
        self.sehir = sehir

kisi = Kisi("Ali", 25, "İstanbul")
# kisi.yeni_ozellik = "değer"  # AttributeError
```

## 51. Property Decorators

**Ne İşe Yarar:** Sınıf özelliklerini kontrollü erişim ile yönetme yöntemini öğretir. @property, @setter ve @deleter dekoratörlerini kapsar.

**Ne Yapar:** Veri doğrulama sağlar, hesaplanmış özellikler oluşturur ve encapsulation prensibini uygular.

### Property Kullanımı
```python
class Daire:
    def __init__(self, yaricap):
        self._yaricap = yaricap
    
    @property
    def yaricap(self):
        return self._yaricap
    
    @yaricap.setter
    def yaricap(self, deger):
        if deger < 0:
            raise ValueError("Yarıçap negatif olamaz")
        self._yaricap = deger
    
    @property
    def alan(self):
        import math
        return math.pi * self._yaricap ** 2

daire = Daire(5)
print(daire.alan)  # 78.54...
daire.yaricap = 10
# daire.yaricap = -5  # ValueError
```

## 52. Class Methods

**Ne İşe Yarar:** Sınıf seviyesinde çalışan metodlar oluşturma yöntemini öğretir. @classmethod dekoratörünün kullanımını kapsar.

**Ne Yapar:** Sınıf üzerinden çağrılabilen metodlar oluşturur, factory pattern uygular ve sınıf durumunu yönetir.

### Class Method
```python
class Tarih:
    def __init__(self, gun, ay, yil):
        self.gun = gun
        self.ay = ay
        self.yil = yil
    
    @classmethod
    def bugun(cls):
        from datetime import date
        bugun = date.today()
        return cls(bugun.day, bugun.month, bugun.year)
    
    def __str__(self):
        return f"{self.gun}/{self.ay}/{self.yil}"

bugun_tarih = Tarih.bugun()
print(bugun_tarih)
```

## 53. Static Methods

**Ne İşe Yarar:** Sınıf veya nesne durumundan bağımsız metodlar oluşturma yöntemini öğretir. @staticmethod dekoratörünün kullanımını kapsar.

**Ne Yapar:** Yardımcı fonksiyonlar oluşturur, sınıf organizasyonunu iyileştirir ve utility fonksiyonları gruplar.

### Static Method
```python
class Matematik:
    @staticmethod
    def topla(a, b):
        return a + b
    
    @staticmethod
    def carp(a, b):
        return a * b
    
    @staticmethod
    def us_al(taban, us):
        return taban ** us

print(Matematik.topla(5, 3))    # 8
print(Matematik.carp(4, 6))     # 24
print(Matematik.us_al(2, 8))    # 256
```

## 54. Abstract Base Classes

**Ne İşe Yarar:** Soyut sınıflar oluşturma yöntemini öğretir. ABC modülünün kullanımını ve abstract metodları kapsar.

**Ne Yapar:** Interface tanımlar, zorunlu metodları belirler ve sınıf hiyerarşilerini standartlaştırır.

### ABC Kullanımı
```python
from abc import ABC, abstractmethod

class Sekil(ABC):
    @abstractmethod
    def alan_hesapla(self):
        pass
    
    @abstractmethod
    def cevre_hesapla(self):
        pass

class Dikdortgen(Sekil):
    def __init__(self, genislik, yukseklik):
        self.genislik = genislik
        self.yukseklik = yukseklik
    
    def alan_hesapla(self):
        return self.genislik * self.yukseklik
    
    def cevre_hesapla(self):
        return 2 * (self.genislik + self.yukseklik)

# sekil = Sekil()  # TypeError
dikdortgen = Dikdortgen(5, 3)
print(dikdortgen.alan_hesapla())  # 15
```

## 55. Protocols

**Ne İşe Yarar:** Structural typing (yapısal tip sistemi) kullanma yöntemini öğretir. Protocol sınıflarının kullanımını kapsar.

**Ne Yapar:** Duck typing'i type system ile birleştirir, interface'leri daha esnek tanımlar ve tip güvenliğini artırır.

### Protocol Kullanımı
```python
from typing import Protocol

class Cizilebilir(Protocol):
    def ciz(self) -> str:
        ...

class Daire:
    def __init__(self, yaricap):
        self.yaricap = yaricap
    
    def ciz(self) -> str:
        return f"Daire çizildi (yarıçap: {self.yaricap})"

class Kare:
    def __init__(self, kenar):
        self.kenar = kenar
    
    def ciz(self) -> str:
        return f"Kare çizildi (kenar: {self.kenar})"

def ciz_nesne(nesne: Cizilebilir):
    print(nesne.ciz())

ciz_nesne(Daire(5))  # Daire çizildi (yarıçap: 5)
ciz_nesne(Kare(4))   # Kare çizildi (kenar: 4)
```

## 56. TypeVar ve Generic Types

**Ne İşe Yarar:** Generic (jenerik) tip tanımlama yöntemini öğretir. TypeVar kullanımını ve generic fonksiyon/sınıf oluşturmayı kapsar.

**Ne Yapar:** Tip güvenliğini korur, kod tekrarını önler ve farklı tiplerle çalışan genel kod yazar.

### TypeVar Kullanımı
```python
from typing import TypeVar, List

T = TypeVar('T')
U = TypeVar('U')

def ilk_eleman(liste: List[T]) -> T:
    return liste[0]

def esle(liste1: List[T], liste2: List[U]) -> List[tuple[T, U]]:
    return list(zip(liste1, liste2))

sayilar = [1, 2, 3, 4]
isimler = ["Ali", "Ayşe", "Mehmet"]

print(ilk_eleman(sayilar))  # 1
print(esle(sayilar, isimler))  # [(1, 'Ali'), (2, 'Ayşe'), (3, 'Mehmet')]
```

## 57. Union Types

**Ne İşe Yarar:** Birden fazla tip kabul eden parametreler tanımlama yöntemini öğretir. Union tipinin kullanımını kapsar.

**Ne Yapar:** Esnek tip tanımları oluşturur, farklı tiplerle çalışan fonksiyonlar yazar ve tip güvenliğini korur.

### Union Kullanımı
```python
from typing import Union

def islem_yap(deger: Union[int, float, str]) -> str:
    if isinstance(deger, (int, float)):
        return f"Sayı: {deger}"
    elif isinstance(deger, str):
        return f"String: {deger}"
    else:
        return "Bilinmeyen tip"

# Python 3.10+ için | operatörü
def islem_yap_v2(deger: int | float | str) -> str:
    return str(deger)

print(islem_yap(42))      # Sayı: 42
print(islem_yap("test"))  # String: test
```

## 58. Optional Types

**Ne İşe Yarar:** None değeri kabul eden tipler tanımlama yöntemini öğretir. Optional tipinin kullanımını kapsar.

**Ne Yapar:** Null safety sağlar, None değerlerini açıkça belirtir ve tip güvenliğini artırır.

### Optional Kullanımı
```python
from typing import Optional

def kisi_bul(id: int) -> Optional[str]:
    kullanicilar = {1: "Ali", 2: "Ayşe", 3: "Mehmet"}
    return kullanicilar.get(id)

def guvenli_bol(a: float, b: Optional[float]) -> Optional[float]:
    if b is None or b == 0:
        return None
    return a / b

print(kisi_bul(1))    # Ali
print(kisi_bul(99))   # None
print(guvenli_bol(10, 2))   # 5.0
print(guvenli_bol(10, 0))   # None
```

## 59. Literal Types

**Ne İşe Yarar:** Belirli değerleri kabul eden tipler tanımlama yöntemini öğretir. Literal tipinin kullanımını kapsar.

**Ne Yapar:** Enum benzeri davranış sağlar, sabit değerleri tip güvenliği ile kullanır ve API tasarımını iyileştirir.

### Literal Kullanımı
```python
from typing import Literal

def renk_analiz(renk: Literal["kırmızı", "yeşil", "mavi"]) -> str:
    match renk:
        case "kırmızı":
            return "Sıcak renk"
        case "yeşil":
            return "Doğal renk"
        case "mavi":
            return "Soğuk renk"

print(renk_analiz("kırmızı"))  # Sıcak renk
# print(renk_analiz("sarı"))   # Type error
```

## 60. TypedDict

**Ne İşe Yarar:** Sözlük yapılarında tip güvenliği sağlama yöntemini öğretir. TypedDict kullanımını kapsar.

**Ne Yapar:** Sözlük anahtarlarının tiplerini belirtir, JSON benzeri veri yapılarında tip güvenliği sağlar ve API tasarımını iyileştirir.

### TypedDict Kullanımı
```python
from typing import TypedDict

class KisiBilgi(TypedDict):
    isim: str
    yas: int
    sehir: str

def kisi_olustur(isim: str, yas: int, sehir: str) -> KisiBilgi:
    return {"isim": isim, "yas": yas, "sehir": sehir}

kisi = kisi_olustur("Ali", 25, "İstanbul")
print(kisi["isim"])  # Ali

## 61. NewType

**Ne İşe Yarar:** Mevcut tiplerden yeni tip tanımları oluşturma yöntemini öğretir. Type safety için özel tip tanımlarını kapsar.

**Ne Yapar:** Tip güvenliğini artırır, aynı temel tipten farklı anlamlı tipler oluşturur ve kod okunabilirliğini iyileştirir.

### NewType Kullanımı
```python
from typing import NewType

KullaniciId = NewType('KullaniciId', int)
SiparisId = NewType('SiparisId', int)

def kullanici_bul(id: KullaniciId) -> str:
    return f"Kullanıcı {id} bulundu"

def siparis_bul(id: SiparisId) -> str:
    return f"Sipariş {id} bulundu"

kullanici_id = KullaniciId(123)
siparis_id = SiparisId(456)

print(kullanici_bul(kullanici_id))  # Kullanıcı 123 bulundu
# print(kullanici_bul(siparis_id))  # Type error
```

## 62. Final

**Ne İşe Yarar:** Değişmez (immutable) değişkenler ve sabitler tanımlama yöntemini öğretir. Final dekoratörünün kullanımını kapsar.

**Ne Yapar:** Sabit değerleri korur, yanlışlıkla değişiklikleri önler ve kod güvenliğini artırır.

### Final Kullanımı
```python
from typing import Final

PI: Final = 3.14159
MAX_KULLANICI: Final[int] = 1000

class Ayarlar:
    VARSayILAN_TEMA: Final[str] = "açık"
    VARSayILAN_DIL: Final[str] = "tr"

# PI = 3.14  # Type error
print(PI)  # 3.14159
```

## 63. Annotated

**Ne İşe Yarar:** Tip tanımlarına ek metadata ekleme yöntemini öğretir. Tip açıklamaları ve ek bilgiler eklemeyi kapsar.

**Ne Yapar:** Tip tanımlarını zenginleştirir, dokümantasyon sağlar ve tip sistemini genişletir.

### Annotated Kullanımı
```python
from typing import Annotated

def kullanici_ekle(
    isim: Annotated[str, "Kullanıcı adı"],
    yas: Annotated[int, "Yaş (18-100)"]
) -> str:
    return f"Kullanıcı {isim} eklendi"

# Metadata ile birlikte type hints
PozitifSayi = Annotated[int, "Pozitif sayı olmalı"]
Email = Annotated[str, "Geçerli email formatı"]

def dogrula_email(email: Email) -> bool:
    return "@" in email
```

## 64. Self Type

**Ne İşe Yarar:** Sınıf metodlarında kendi tipini referans alma yöntemini öğretir. Self tipinin kullanımını kapsar.

**Ne Yapar:** Method chaining sağlar, tip güvenliğini artırır ve fluent interface tasarımını destekler.

### Self Type Kullanımı
```python
from typing import Self

class Zincir:
    def __init__(self, deger: str):
        self.deger = deger
    
    def ekle(self, yeni: str) -> Self:
        self.deger += yeni
        return self
    
    def buyuk_harf(self) -> Self:
        self.deger = self.deger.upper()
        return self

zincir = Zincir("merhaba")
zincir.ekle(" dünya").buyuk_harf()
print(zincir.deger)  # MERHABA DÜNYA
```

## 65. Callable Types

**Ne İşe Yarar:** Fonksiyon tiplerini tanımlama yöntemini öğretir. Callable tipinin kullanımını kapsar.

**Ne Yapar:** Fonksiyon parametrelerinin tiplerini belirtir, callback fonksiyonları tip güvenliği ile kullanır ve higher-order fonksiyonları destekler.

### Callable Kullanımı
```python
from typing import Callable

def uygula(fonksiyon: Callable[[int], int], deger: int) -> int:
    return fonksiyon(deger)

def kare(x: int) -> int:
    return x ** 2

def iki_kat(x: int) -> int:
    return x * 2

print(uygula(kare, 5))      # 25
print(uygula(iki_kat, 5))   # 10

# Lambda ile
print(uygula(lambda x: x + 1, 5))  # 6
```

## 66. Iterator Types

**Ne İşe Yarar:** Iterator tiplerini tanımlama yöntemini öğretir. Iterator ve Generator tiplerinin kullanımını kapsar.

**Ne Yapar:** Veri akışlarını tip güvenliği ile tanımlar, lazy evaluation sağlar ve bellek verimliliğini artırır.

### Iterator Kullanımı
```python
from typing import Iterator

def sayi_uret(baslangic: int, bitis: int) -> Iterator[int]:
    for i in range(baslangic, bitis):
        yield i

def liste_uret(liste: list) -> Iterator[str]:
    for item in liste:
        yield str(item)

# Kullanım
for sayi in sayi_uret(1, 6):
    print(sayi)  # 1, 2, 3, 4, 5

isimler = ["Ali", "Ayşe", "Mehmet"]
for isim in liste_uret(isimler):
    print(isim.upper())  # ALI, AYŞE, MEHMET
```

## 67. Async Types

**Ne İşe Yarar:** Asenkron fonksiyon tiplerini tanımlama yöntemini öğretir. Async/await tiplerinin kullanımını kapsar.

**Ne Yapar:** Asenkron kodda tip güvenliği sağlar, async fonksiyonları doğru şekilde tanımlar ve asenkron programlama hatalarını önler.

### Async Type Hints
```python
from typing import AsyncIterator, Awaitable
import asyncio

async def sayi_uret_async(baslangic: int, bitis: int) -> AsyncIterator[int]:
    for i in range(baslangic, bitis):
        await asyncio.sleep(0.1)
        yield i

async def islem_yap(deger: int) -> Awaitable[str]:
    await asyncio.sleep(1)
    return f"İşlem tamamlandı: {deger}"

async def main():
    async for sayi in sayi_uret_async(1, 4):
        sonuc = await islem_yap(sayi)
        print(sonuc)

# asyncio.run(main())
```

## 68. Context Manager Types

**Ne İşe Yarar:** Context manager tiplerini tanımlama yöntemini öğretir. ContextManager tipinin kullanımını kapsar.

**Ne Yapar:** Resource management tiplerini belirtir, with statement'ları tip güvenliği ile kullanır ve kaynak yönetimini iyileştirir.

### Context Manager Type Hints
```python
from typing import ContextManager
from contextlib import contextmanager

@contextmanager
def dosya_yoneticisi(dosya_adi: str) -> ContextManager[str]:
    dosya = open(dosya_adi, 'w')
    try:
        yield dosya_adi
    finally:
        dosya.close()

# Kullanım
with dosya_yoneticisi("test.txt") as dosya:
    print(f"Dosya açıldı: {dosya}")
```

## 69. Protocol Types

**Ne İşe Yarar:** Gelişmiş protocol tiplerini öğretir. Runtime checkable protocol'ların kullanımını kapsar.

**Ne Yapar:** Structural typing'i runtime'da kontrol eder, interface'leri daha esnek tanımlar ve tip güvenliğini artırır.

### Protocol Detaylı
```python
from typing import Protocol, runtime_checkable

@runtime_checkable
class Yazilabilir(Protocol):
    def yaz(self, mesaj: str) -> None:
        ...

class Dosya:
    def __init__(self, dosya_adi: str):
        self.dosya_adi = dosya_adi
    
    def yaz(self, mesaj: str) -> None:
        print(f"Dosyaya yazılıyor: {mesaj}")

class Konsol:
    def yaz(self, mesaj: str) -> None:
        print(f"Konsola yazılıyor: {mesaj}")

def yazdir(cihaz: Yazilabilir, mesaj: str) -> None:
    cihaz.yaz(mesaj)

yazdir(Dosya("test.txt"), "Merhaba")
yazdir(Konsol(), "Merhaba")
```

## 70. Generic Protocols

**Ne İşe Yarar:** Generic protocol tiplerini öğretir. TypeVar ile birlikte protocol kullanımını kapsar.

**Ne Yapar:** Generic interface'ler oluşturur, tip parametreleri ile protocol'ları genişletir ve daha esnek tip sistemleri kurar.

### Generic Protocol
```python
from typing import Protocol, TypeVar

T = TypeVar('T')

class Karsilastirilabilir(Protocol[T]):
    def __lt__(self, other: T) -> bool:
        ...

class Sayi:
    def __init__(self, deger: int):
        self.deger = deger
    
    def __lt__(self, other: 'Sayi') -> bool:
        return self.deger < other.deger

def sirala(liste: list[Karsilastirilabilir[T]]) -> list[T]:
    return sorted(liste)

sayilar = [Sayi(3), Sayi(1), Sayi(2)]
sirali = sirala(sayilar)
print([s.deger for s in sirali])  # [1, 2, 3]
```

## 71. Covariant ve Contravariant

**Ne İşe Yarar:** Generic tip sisteminde variance (değişkenlik) kavramlarını öğretir. Covariant ve contravariant tiplerin kullanımını kapsar.

**Ne Yapar:** Tip uyumluluğunu doğru şekilde yönetir, generic tip sistemini güvenli hale getirir ve tip hiyerarşilerini korur.

### Variance Kullanımı
```python
from typing import TypeVar, List

# Covariant (çıktı tipi)
T_co = TypeVar('T_co', covariant=True)

class ListeOkuyucu(List[T_co]):
    def oku(self) -> T_co:
        return self[0]

# Contravariant (giriş tipi)
T_contra = TypeVar('T_contra', contravariant=True)

class Yazici:
    def yaz(self, veri: T_contra) -> None:
        print(f"Yazılıyor: {veri}")

# Kullanım
sayi_listesi = ListeOkuyucu([1, 2, 3])
sayi = sayi_listesi.oku()  # int

yazici = Yazici()
yazici.yaz("test")  # str
```

## 72. Bounded TypeVar

**Ne İşe Yarar:** TypeVar'lara sınırlama ekleme yöntemini öğretir. Bounded type variable'ların kullanımını kapsar.

**Ne Yapar:** Tip parametrelerini sınırlar, tip güvenliğini artırır ve daha spesifik generic tipler oluşturur.

### Bounded TypeVar
```python
from typing import TypeVar, Union

# Sayısal tipler için
SayiTipi = TypeVar('SayiTipi', bound=Union[int, float])

def topla(a: SayiTipi, b: SayiTipi) -> SayiTipi:
    return a + b

print(topla(5, 3))      # 8 (int)
print(topla(3.14, 2.86))  # 6.0 (float)
# print(topla("a", "b"))  # Type error
```

## 73. Multiple TypeVar

**Ne İşe Yarar:** Birden fazla TypeVar kullanma yöntemini öğretir. Çoklu tip parametrelerinin kullanımını kapsar.

**Ne Yapar:** Karmaşık generic tipler oluşturur, farklı tip parametrelerini yönetir ve esnek tip sistemleri kurar.

### Çoklu TypeVar
```python
from typing import TypeVar, Tuple

T = TypeVar('T')
U = TypeVar('U')
V = TypeVar('V')

def uc_esle(a: T, b: U, c: V) -> Tuple[T, U, V]:
    return (a, b, c)

def degistir(a: T, b: U) -> Tuple[U, T]:
    return (b, a)

sonuc1 = uc_esle(1, "test", 3.14)
sonuc2 = degistir(42, "merhaba")
print(sonuc1)  # (1, 'test', 3.14)
print(sonuc2)  # ('merhaba', 42)
```

## 74. TypeVar with Default

**Ne İşe Yarar:** TypeVar'lara varsayılan değer atama yöntemini öğretir. Default type variable'ların kullanımını kapsar.

**Ne Yapar:** Generic tipleri daha kullanışlı hale getirir, tip çıkarımını iyileştirir ve kod yazımını kolaylaştırır.

### TypeVar Default
```python
from typing import TypeVar, List

T = TypeVar('T', default=str)

def liste_olustur(*args: T) -> List[T]:
    return list(args)

# Varsayılan tip (str)
liste1 = liste_olustur("a", "b", "c")
print(liste1)  # ['a', 'b', 'c']

# Belirtilen tip
liste2: List[int] = liste_olustur(1, 2, 3)
print(liste2)  # [1, 2, 3]
```

## 75. TypeVar with Constraints

**Ne İşe Yarar:** TypeVar'lara kısıtlama ekleme yöntemini öğretir. Constrained type variable'ların kullanımını kapsar.

**Ne Yapar:** Tip parametrelerini belirli tiplerle sınırlar, tip güvenliğini artırır ve daha spesifik generic tipler oluşturur.

### TypeVar Constraints
```python
from typing import TypeVar, Union

# Sadece belirli tipler
SayiTipi = TypeVar('SayiTipi', int, float)

def ortalama(liste: list[SayiTipi]) -> float:
    return sum(liste) / len(liste)

print(ortalama([1, 2, 3, 4, 5]))      # 3.0
print(ortalama([1.5, 2.5, 3.5]))      # 2.5
# print(ortalama(["a", "b", "c"]))    # Type error
```

## 76. Generic Functions

**Ne İşe Yarar:** Generic fonksiyonlar oluşturma yöntemini öğretir. TypeVar ile fonksiyon tanımlamayı kapsar.

**Ne Yapar:** Farklı tiplerle çalışan genel fonksiyonlar oluşturur, kod tekrarını önler ve tip güvenliğini korur.

### Generic Fonksiyon
```python
from typing import TypeVar, List

T = TypeVar('T')

def ilk_eleman(liste: List[T]) -> T:
    return liste[0]

def son_eleman(liste: List[T]) -> T:
    return liste[-1]

def ters_cevir(liste: List[T]) -> List[T]:
    return liste[::-1]

# Kullanım
sayilar = [1, 2, 3, 4, 5]
isimler = ["Ali", "Ayşe", "Mehmet"]

print(ilk_eleman(sayilar))    # 1
print(son_eleman(isimler))    # Mehmet
print(ters_cevir(sayilar))    # [5, 4, 3, 2, 1]
```

## 77. Generic Classes

**Ne İşe Yarar:** Generic sınıflar oluşturma yöntemini öğretir. TypeVar ile sınıf tanımlamayı kapsar.

**Ne Yapar:** Farklı tiplerle çalışan genel sınıflar oluşturur, container sınıfları tip güvenliği ile yazar ve kod tekrarını önler.

### Generic Sınıf
```python
from typing import TypeVar, Generic, List

T = TypeVar('T')

class Stack(Generic[T]):
    def __init__(self):
        self.items: List[T] = []
    
    def push(self, item: T) -> None:
        self.items.append(item)
    
    def pop(self) -> T:
        return self.items.pop()
    
    def peek(self) -> T:
        return self.items[-1]
    
    def is_empty(self) -> bool:
        return len(self.items) == 0

# Kullanım
int_stack: Stack[int] = Stack()
int_stack.push(1)
int_stack.push(2)
print(int_stack.pop())  # 2

str_stack: Stack[str] = Stack()
str_stack.push("merhaba")
str_stack.push("dünya")
print(str_stack.peek())  # dünya
```

## 78. Generic Methods

**Ne İşe Yarar:** Generic metodlar oluşturma yöntemini öğretir. Sınıf metodlarında TypeVar kullanımını kapsar.

**Ne Yapar:** Sınıf metodlarını farklı tiplerle çalışacak şekilde genelleştirir, tip güvenliğini korur ve metod esnekliğini artırır.

### Generic Metod
```python
from typing import TypeVar, List

T = TypeVar('T')
U = TypeVar('U')

class ListeIsleyici:
    def __init__(self, liste: List[T]):
        self.liste = liste
    
    def donustur(self, fonksiyon) -> List[U]:
        return [fonksiyon(item) for item in self.liste]
    
    def filtrele(self, kosul) -> List[T]:
        return [item for item in self.liste if kosul(item)]
    
    def birlesim(self, other: List[T]) -> List[T]:
        return self.liste + other

# Kullanım
sayilar = ListeIsleyici([1, 2, 3, 4, 5])
kareler = sayilar.donustur(lambda x: x ** 2)
cift_sayilar = sayilar.filtrele(lambda x: x % 2 == 0)
print(kareler)      # [1, 4, 9, 16, 25]
print(cift_sayilar) # [2, 4]
```

## 79. Generic Inheritance

**Ne İşe Yarar:** Generic sınıflarda kalıtım kullanma yöntemini öğretir. Generic sınıf hiyerarşilerini kapsar.

**Ne Yapar:** Generic sınıfları genişletir, tip parametrelerini miras alır ve hiyerarşik generic yapılar oluşturur.

### Generic Kalıtım
```python
from typing import TypeVar, Generic, List

T = TypeVar('T')

class Koleksiyon(Generic[T]):
    def __init__(self):
        self.items: List[T] = []
    
    def ekle(self, item: T) -> None:
        self.items.append(item)
    
    def boyut(self) -> int:
        return len(self.items)

class SiralanabilirKoleksiyon(Koleksiyon[T]):
    def sirala(self) -> List[T]:
        return sorted(self.items)
    
    def ters_sirala(self) -> List[T]:
        return sorted(self.items, reverse=True)

# Kullanım
koleksiyon = SiralanabilirKoleksiyon[int]()
koleksiyon.ekle(3)
koleksiyon.ekle(1)
koleksiyon.ekle(2)
print(koleksiyon.sirala())      # [1, 2, 3]
print(koleksiyon.ters_sirala()) # [3, 2, 1]
```

## 80. Generic Protocols

**Ne İşe Yarar:** Generic protocol'ların detaylı kullanımını öğretir. Karmaşık generic interface'leri kapsar.

**Ne Yapar:** Generic interface'ler oluşturur, tip parametreleri ile protocol'ları genişletir ve esnek tip sistemleri kurar.

### Generic Protocol Detaylı
```python
from typing import Protocol, TypeVar, runtime_checkable

T = TypeVar('T')

@runtime_checkable
class Karsilastirilabilir(Protocol[T]):
    def __lt__(self, other: T) -> bool:
        ...
    
    def __eq__(self, other: T) -> bool:
        ...

class Sayi:
    def __init__(self, deger: int):
        self.deger = deger
    
    def __lt__(self, other: 'Sayi') -> bool:
        return self.deger < other.deger
    
    def __eq__(self, other: 'Sayi') -> bool:
        return self.deger == other.deger

def min_bul(a: Karsilastirilabilir[T], b: Karsilastirilabilir[T]) -> Karsilastirilabilir[T]:
    return a if a < b else b

sayi1 = Sayi(5)
sayi2 = Sayi(3)
kucuk = min_bul(sayi1, sayi2)
print(kucuk.deger)  # 3

## 81. Type Aliases

**Ne İşe Yarar:** Karmaşık tip tanımlarını basitleştirme yöntemini öğretir. Tip alias'larının kullanımını kapsar.

**Ne Yapar:** Karmaşık tipleri basitleştirir, kod okunabilirliğini artırır ve tip tanımlarını yeniden kullanılabilir hale getirir.

### Type Alias Kullanımı
```python
from typing import TypeAlias, List, Dict

# Basit alias
KullaniciListesi = List[str]
Ayarlar = Dict[str, str]

# Karmaşık alias
KullaniciBilgi = Dict[str, str | int]
Koordinat = tuple[int, int]

# Kullanım
kullanicilar: KullaniciListesi = ["Ali", "Ayşe", "Mehmet"]
ayarlar: Ayarlar = {"tema": "koyu", "dil": "tr"}
kisi: KullaniciBilgi = {"isim": "Ali", "yas": 25}
nokta: Koordinat = (10, 20)
```

## 82. Type Guards

**Ne İşe Yarar:** Tip kontrolü yapan fonksiyonlar oluşturma yöntemini öğretir. TypeGuard dekoratörünün kullanımını kapsar.

**Ne Yapar:** Tip kontrolü yapar, type narrowing sağlar ve tip güvenliğini artırır.

### Type Guard Kullanımı
```python
from typing import TypeGuard, Union

def is_string(obj: object) -> TypeGuard[str]:
    return isinstance(obj, str)

def is_number(obj: object) -> TypeGuard[Union[int, float]]:
    return isinstance(obj, (int, float))

def islem_yap(veri: object) -> str:
    if is_string(veri):
        return f"String: {veri.upper()}"  # Type guard sayesinde str olarak tanınır
    elif is_number(veri):
        return f"Sayı: {veri * 2}"
    else:
        return f"Bilinmeyen: {veri}"

print(islem_yap("merhaba"))  # String: MERHABA
print(islem_yap(42))         # Sayı: 84
```

## 83. Type Narrowing

**Ne İşe Yarar:** Tip kontrolü sonrası tip bilgisini daraltma yöntemini öğretir. Type narrowing kavramını kapsar.

**Ne Yapar:** Tip güvenliğini artırır, tip kontrolü sonrası daha spesifik tipler kullanır ve hataları önler.

### Type Narrowing
```python
from typing import Union

def analiz_et(veri: Union[str, int, list]) -> str:
    if isinstance(veri, str):
        return f"String uzunluğu: {len(veri)}"
    elif isinstance(veri, int):
        return f"Sayı karesi: {veri ** 2}"
    elif isinstance(veri, list):
        return f"Liste eleman sayısı: {len(veri)}"
    else:
        return "Bilinmeyen tip"

print(analiz_et("test"))     # String uzunluğu: 4
print(analiz_et(5))          # Sayı karesi: 25
print(analiz_et([1, 2, 3]))  # Liste eleman sayısı: 3
```

## 84. Type Assertions

**Ne İşe Yarar:** Tip kontrolü yapma ve tip dönüşümü zorlama yöntemini öğretir. Type assertion kavramını kapsar.

**Ne Yapar:** Tip kontrolü yapar, tip dönüşümü zorlar ve tip güvenliğini sağlar.

### Type Assertion
```python
from typing import Any

def guvenli_cast(veri: Any, tip: type) -> Any:
    assert isinstance(veri, tip), f"Veri {tip} tipinde değil"
    return veri

def string_isle(veri: Any) -> str:
    veri = guvenli_cast(veri, str)
    return veri.upper()

print(string_isle("merhaba"))  # MERHABA
# print(string_isle(42))       # AssertionError
```

## 85. Type Casting

**Ne İşe Yarar:** Tip dönüşümü yapma yöntemini öğretir. Cast fonksiyonunun kullanımını kapsar.

**Ne Yapar:** Tip dönüşümü yapar, type checker'ı bilgilendirir ve tip güvenliğini sağlar.

### Type Casting
```python
from typing import cast, Any

def guvenli_cast(veri: Any, tip: type) -> Any:
    return cast(tip, veri)

def sayi_isle(veri: Any) -> int:
    return cast(int, veri)

# Dikkat: cast sadece type checker için, runtime'da kontrol etmez
sonuc = sayi_isle("42")  # Type checker kabul eder ama runtime'da hata olabilir
```

## 86. Type Checking

**Ne İşe Yarar:** Tip kontrolü sırasında çalışan kod yazma yöntemini öğretir. TYPE_CHECKING sabitinin kullanımını kapsar.

**Ne Yapar:** Tip kontrolü sırasında çalışan kod yazar, runtime'da çalışmayan kod oluşturur ve performansı artırır.

### Type Checking
```python
from typing import TYPE_CHECKING

if TYPE_CHECKING:
    from expensive_module import ExpensiveType

def islem_yap(veri: 'ExpensiveType') -> str:
    return str(veri)

# TYPE_CHECKING sadece type checking sırasında True'dur
# Runtime'da import edilmez
```

## 87. Type Inference

**Ne İşe Yarar:** Python'un otomatik tip çıkarımı yapma özelliğini öğretir. Type inference kavramını kapsar.

**Ne Yapar:** Otomatik tip çıkarımı yapar, kod yazımını kolaylaştırır ve tip belirtme ihtiyacını azaltır.

### Type Inference
```python
# Python otomatik tip çıkarımı yapar
sayi = 42          # int
metin = "merhaba"  # str
liste = [1, 2, 3]  # list[int]
sozluk = {"a": 1}  # dict[str, int]

# Type hints ile daha net
from typing import List, Dict

sayilar: List[int] = [1, 2, 3]
kullanicilar: Dict[str, int] = {"Ali": 25, "Ayşe": 30}
```

## 88. Type Erasure

**Ne İşe Yarar:** Runtime'da tip bilgilerinin kaybolması kavramını öğretir. Type erasure kavramını kapsar.

**Ne Yapar:** Runtime'da tip bilgilerini kaybeder, performansı artırır ve bellek kullanımını azaltır.

### Type Erasure
```python
from typing import List, TypeVar

T = TypeVar('T')

def liste_olustur() -> List[T]:
    return []

# Runtime'da type information kaybolur
liste = liste_olustur()
print(type(liste))  # <class 'list'>
# T tipi runtime'da mevcut değil
```

## 89. Type Preservation

**Ne İşe Yarar:** Tip bilgilerinin korunması kavramını öğretir. Type preservation kavramını kapsar.

**Ne Yapar:** Tip bilgilerini korur, tip güvenliğini artırır ve runtime'da tip kontrolü sağlar.

### Type Preservation
```python
from typing import TypeVar, Generic

T = TypeVar('T')

class Kutu(Generic[T]):
    def __init__(self, icerik: T):
        self.icerik = icerik
    
    def al(self) -> T:
        return self.icerik

# Tip bilgisi korunur
sayi_kutusu: Kutu[int] = Kutu(42)
metin_kutusu: Kutu[str] = Kutu("merhaba")

sayi = sayi_kutusu.al()  # int olarak tanınır
metin = metin_kutusu.al()  # str olarak tanınır
```

## 90. Type Safety

**Ne İşe Yarar:** Tip güvenliği sağlama yöntemlerini öğretir. Type safety kavramını kapsar.

**Ne Yapar:** Tip hatalarını önler, kod güvenliğini artırır ve hataları erken tespit eder.

### Type Safety
```python
from typing import List, Dict

def guvenli_topla(sayilar: List[int]) -> int:
    return sum(sayilar)

def guvenli_sozluk_isle(sozluk: Dict[str, int]) -> int:
    return sum(sozluk.values())

# Type checker hataları yakalar
# guvenli_topla(["a", "b"])  # Type error
# guvenli_sozluk_isle({"a": "b"})  # Type error

print(guvenli_topla([1, 2, 3]))  # 6
print(guvenli_sozluk_isle({"a": 1, "b": 2}))  # 3
```

## 91. Type Compatibility

**Ne İşe Yarar:** Tip uyumluluğu kavramlarını öğretir. Covariant ve contravariant tip uyumluluğunu kapsar.

**Ne Yapar:** Tip uyumluluğunu doğru şekilde yönetir, generic tip sistemini güvenli hale getirir ve tip hiyerarşilerini korur.

### Type Compatibility
```python
from typing import List, Union

# Covariant
def liste_oku(liste: List[object]) -> None:
    for item in liste:
        print(item)

sayilar: List[int] = [1, 2, 3]
liste_oku(sayilar)  # int -> object uyumlu

# Contravariant
def sayi_yazici(fonksiyon) -> None:
    print(fonksiyon(42))

def object_yazdir(obj: object) -> str:
    return str(obj)

sayi_yazici(object_yazdir)  # object -> int uyumlu
```

## 92. Type Coercion

**Ne İşe Yarar:** Otomatik tip dönüşümü kavramını öğretir. Type coercion kavramını kapsar.

**Ne Yapar:** Otomatik tip dönüşümü yapar, kod yazımını kolaylaştırır ve tip uyumluluğunu sağlar.

### Type Coercion
```python
def sayi_isle(a: int, b: int) -> int:
    return a + b

# Python otomatik coercion yapar
sonuc1 = sayi_isle(5, 3.0)  # float -> int coercion
sonuc2 = sayi_isle(True, False)  # bool -> int coercion

print(sonuc1)  # 8
print(sonuc2)  # 1
```

## 93. Type Conversion

**Ne İşe Yarar:** Manuel tip dönüşümü yapma yöntemini öğretir. Type conversion kavramını kapsar.

**Ne Yapar:** Manuel tip dönüşümü yapar, tip güvenliğini sağlar ve hataları kontrol eder.

### Type Conversion
```python
def guvenli_cevir(veri: str, hedef_tip: type) -> Any:
    try:
        if hedef_tip == int:
            return int(veri)
        elif hedef_tip == float:
            return float(veri)
        elif hedef_tip == bool:
            return veri.lower() in ('true', '1', 'yes')
        else:
            return hedef_tip(veri)
    except (ValueError, TypeError):
        return None

print(guvenli_cevir("42", int))      # 42
print(guvenli_cevir("3.14", float))  # 3.14
print(guvenli_cevir("true", bool))   # True
print(guvenli_cevir("abc", int))     # None
```

## 94. Type Validation

**Ne İşe Yarar:** Tip doğrulama yapma yöntemini öğretir. Type validation kavramını kapsar.

**Ne Yapar:** Tip doğrulama yapar, hataları erken tespit eder ve tip güvenliğini artırır.

### Type Validation
```python
from typing import Any, TypeVar

T = TypeVar('T')

def dogrula_tip(veri: Any, beklenen_tip: type[T]) -> T:
    if not isinstance(veri, beklenen_tip):
        raise TypeError(f"Beklenen tip: {beklenen_tip}, alınan: {type(veri)}")
    return veri

def guvenli_islem(veri: Any) -> str:
    try:
        sayi = dogrula_tip(veri, int)
        return f"Sayı: {sayi * 2}"
    except TypeError as e:
        return f"Hata: {e}"

print(guvenli_islem(5))      # Sayı: 10
print(guvenli_islem("5"))    # Hata: Beklenen tip: <class 'int'>, alınan: <class 'str'>
```

## 95. Type Serialization

**Ne İşe Yarar:** Tip bilgilerini serileştirme yöntemini öğretir. Type serialization kavramını kapsar.

**Ne Yapar:** Tip bilgilerini serileştirir, veri transferini kolaylaştırır ve tip bilgilerini saklar.

### Type Serialization
```python
import json
from typing import Any, Dict

def serialize_typed_dict(data: Dict[str, Any]) -> str:
    return json.dumps(data, ensure_ascii=False, indent=2)

def deserialize_typed_dict(json_str: str) -> Dict[str, Any]:
    return json.loads(json_str)

kisi = {"isim": "Ali", "yas": 25, "aktif": True}
json_str = serialize_typed_dict(kisi)
print(json_str)

geri_yuklenen = deserialize_typed_dict(json_str)
print(geri_yuklenen["isim"])  # Ali
```

## 96. Type Deserialization

**Ne İşe Yarar:** Serileştirilmiş tip bilgilerini geri yükleme yöntemini öğretir. Type deserialization kavramını kapsar.

**Ne Yapar:** Serileştirilmiş tip bilgilerini geri yükler, veri transferini tamamlar ve tip bilgilerini restore eder.

### Type Deserialization
```python
from typing import TypeVar, Type, Any

T = TypeVar('T')

def deserialize_with_type(data: Any, target_type: Type[T]) -> T:
    if target_type == int:
        return int(data)
    elif target_type == float:
        return float(data)
    elif target_type == str:
        return str(data)
    elif target_type == bool:
        return bool(data)
    else:
        return target_type(data)

# Kullanım
sayi = deserialize_with_type("42", int)
metin = deserialize_with_type(123, str)
print(sayi)   # 42
print(metin)  # "123"
```

## 97. Type Marshalling

**Ne İşe Yarar:** Tip bilgilerini marshalling yapma yöntemini öğretir. Type marshalling kavramını kapsar.

**Ne Yapar:** Tip bilgilerini marshalling yapar, veri transferini kolaylaştırır ve tip bilgilerini korur.

### Type Marshalling
```python
import pickle
from typing import Any

def marshal_data(data: Any) -> bytes:
    return pickle.dumps(data)

def unmarshal_data(data_bytes: bytes) -> Any:
    return pickle.loads(data_bytes)

# Kullanım
orijinal = {"isim": "Ali", "yas": 25, "liste": [1, 2, 3]}
marshalled = marshal_data(orijinal)
unmarshalled = unmarshal_data(marshalled)

print(unmarshalled == orijinal)  # True
```

## 98. Type Unmarshalling

**Ne İşe Yarar:** Marshalled tip bilgilerini geri yükleme yöntemini öğretir. Type unmarshalling kavramını kapsar.

**Ne Yapar:** Marshalled tip bilgilerini geri yükler, veri transferini tamamlar ve tip bilgilerini restore eder.

### Type Unmarshalling
```python
from typing import Any, Dict, List

def unmarshal_dict(data: Any) -> Dict[str, Any]:
    if not isinstance(data, dict):
        raise TypeError("Dict bekleniyor")
    return data

def unmarshal_list(data: Any) -> List[Any]:
    if not isinstance(data, list):
        raise TypeError("List bekleniyor")
    return data

# Kullanım
dict_data = unmarshal_dict({"a": 1, "b": 2})
list_data = unmarshal_list([1, 2, 3])

print(dict_data)  # {'a': 1, 'b': 2}
print(list_data)  # [1, 2, 3]
```

## 99. Type Reflection

**Ne İşe Yarar:** Runtime'da tip bilgilerini inceleme yöntemini öğretir. Type reflection kavramını kapsar.

**Ne Yapar:** Runtime'da tip bilgilerini inceler, dinamik tip analizi yapar ve tip bilgilerini keşfeder.

### Type Reflection
```python
import inspect
from typing import Any, Type

def get_type_info(obj: Any) -> Dict[str, Any]:
    obj_type = type(obj)
    return {
        "type_name": obj_type.__name__,
        "module": obj_type.__module__,
        "bases": [base.__name__ for base in obj_type.__bases__],
        "attributes": dir(obj),
        "annotations": getattr(obj_type, '__annotations__', {})
    }

class TestClass:
    def __init__(self, value: int):
        self.value = value

test_obj = TestClass(42)
info = get_type_info(test_obj)
print(info["type_name"])  # TestClass
print(info["annotations"])  # {'value': <class 'int'>}
```

## 100. Type Introspection

**Ne İşe Yarar:** Tip bilgilerini detaylı inceleme yöntemini öğretir. Type introspection kavramını kapsar.

**Ne Yapar:** Tip bilgilerini detaylı inceler, tip yapısını analiz eder ve tip bilgilerini keşfeder.

### Type Introspection
```python
from typing import Any, get_type_hints, get_args, get_origin

def introspect_type(obj: Any) -> Dict[str, Any]:
    obj_type = type(obj)
    hints = get_type_hints(obj_type)
    
    return {
        "type": obj_type,
        "type_hints": hints,
        "is_generic": hasattr(obj_type, '__origin__'),
        "origin": get_origin(obj_type),
        "args": get_args(obj_type) if hasattr(obj_type, '__origin__') else None
    }

from typing import List, Dict

class TestClass:
    def __init__(self, items: List[int], config: Dict[str, str]):
        self.items = items
        self.config = config

info = introspect_type(TestClass([1, 2], {"a": "b"}))
print(info["type_hints"])  # {'items': typing.List[int], 'config': typing.Dict[str, str]}

## 101. Type Metaprogramming

**Ne İşe Yarar:** Tip sistemini programatik olarak manipüle etme yöntemini öğretir. Type metaprogramming kavramını kapsar.

**Ne Yapar:** Tip sistemini programatik olarak manipüle eder, dinamik tip oluşturma sağlar ve tip sistemini genişletir.

### Type Metaprogramming
```python
from typing import Type, TypeVar, Generic

T = TypeVar('T')

class TypeFactory:
    @staticmethod
    def create_type(name: str, bases: tuple = (), attrs: dict = None) -> Type:
        if attrs is None:
            attrs = {}
        return type(name, bases, attrs)

# Dinamik sınıf oluşturma
DynamicClass = TypeFactory.create_type(
    "DynamicClass",
    (object,),
    {"value": 42, "method": lambda self: f"Value: {self.value}"}
)

obj = DynamicClass()
print(obj.method())  # Value: 42
```

## 102. Type Code Generation

**Ne İşe Yarar:** Tip tabanlı kod üretimi yapma yöntemini öğretir. Type code generation kavramını kapsar.

**Ne Yapar:** Tip tabanlı kod üretimi yapar, otomatik kod oluşturma sağlar ve kod yazımını kolaylaştırır.

### Type Code Generation
```python
def generate_class_code(class_name: str, fields: list[str]) -> str:
    field_definitions = "\n    ".join([f"{field}: str" for field in fields])
    init_params = ", ".join([f"{field}: str" for field in fields])
    init_body = "\n        ".join([f"self.{field} = {field}" for field in fields])
    
    return f"""
class {class_name}:
    {field_definitions}
    
    def __init__(self, {init_params}):
        {init_body}
"""

# Kullanım
code = generate_class_code("Kisi", ["isim", "yas", "sehir"])
print(code)
# exec(code)  # Dikkatli kullanın!
```

## 103. Type Templates

**Ne İşe Yarar:** Tip tabanlı şablonlar oluşturma yöntemini öğretir. Type templates kavramını kapsar.

**Ne Yapar:** Tip tabanlı şablonlar oluşturur, kod tekrarını önler ve tip güvenliği sağlar.

### Type Templates
```python
from typing import TypeVar, Generic, List

T = TypeVar('T')

class Template(Generic[T]):
    def __init__(self, template_type: Type[T]):
        self.template_type = template_type
    
    def create_instance(self, *args, **kwargs) -> T:
        return self.template_type(*args, **kwargs)

class Kisi:
    def __init__(self, isim: str, yas: int):
        self.isim = isim
        self.yas = yas

# Template kullanımı
kisi_template = Template(Kisi)
kisi = kisi_template.create_instance("Ali", 25)
print(f"{kisi.isim}, {kisi.yas}")  # Ali, 25
```

## 104. Type Macros

**Ne İşe Yarar:** Tip tabanlı makrolar oluşturma yöntemini öğretir. Type macros kavramını kapsar.

**Ne Yapar:** Tip tabanlı makrolar oluşturur, kod üretimini otomatikleştirir ve tip sistemini genişletir.

### Type Macros
```python
from typing import TypeVar, Callable, Any

T = TypeVar('T')

def type_macro(func: Callable) -> Callable:
    """Basit bir type macro decorator"""
    def wrapper(*args, **kwargs) -> Any:
        print(f"Macro çalıştırılıyor: {func.__name__}")
        return func(*args, **kwargs)
    return wrapper

@type_macro
def test_function(x: int) -> int:
    return x * 2

print(test_function(5))  # Macro çalıştırılıyor: test_function\n10
```

## 105. Type Compilers

**Ne İşe Yarar:** Tip tabanlı derleyiciler oluşturma yöntemini öğretir. Type compiler kavramını kapsar.

**Ne Yapar:** Tip tabanlı derleyiciler oluşturur, tip kontrolü yapar ve tip güvenliği sağlar.

### Type Compiler Simulation
```python
from typing import Dict, Any, Type

class TypeCompiler:
    def __init__(self):
        self.type_registry: Dict[str, Type] = {}
    
    def register_type(self, name: str, type_class: Type) -> None:
        self.type_registry[name] = type_class
    
    def compile_type(self, type_name: str) -> Type:
        if type_name not in self.type_registry:
            raise ValueError(f"Tip bulunamadı: {type_name}")
        return self.type_registry[type_name]

# Kullanım
compiler = TypeCompiler()
compiler.register_type("int", int)
compiler.register_type("str", str)

compiled_type = compiler.compile_type("int")
print(compiled_type(42))  # 42
```

## 106. Type Interpreters

**Ne İşe Yarar:** Tip tabanlı yorumlayıcılar oluşturma yöntemini öğretir. Type interpreter kavramını kapsar.

**Ne Yapar:** Tip tabanlı yorumlayıcılar oluşturur, tip kontrolü yapar ve tip güvenliği sağlar.

### Type Interpreter
```python
from typing import Any, Dict, List

class TypeInterpreter:
    def __init__(self):
        self.variables: Dict[str, Any] = {}
    
    def interpret_type_declaration(self, name: str, value: Any, type_hint: str) -> None:
        """Tip bildirimini yorumla"""
        if type_hint == "int":
            self.variables[name] = int(value)
        elif type_hint == "str":
            self.variables[name] = str(value)
        elif type_hint == "list":
            self.variables[name] = list(value)
        else:
            self.variables[name] = value
    
    def get_variable(self, name: str) -> Any:
        return self.variables.get(name)

# Kullanım
interpreter = TypeInterpreter()
interpreter.interpret_type_declaration("sayi", "42", "int")
interpreter.interpret_type_declaration("metin", 123, "str")

print(interpreter.get_variable("sayi"))   # 42
print(interpreter.get_variable("metin"))  # "123"
```

## 107. Type Virtual Machines

**Ne İşe Yarar:** Tip tabanlı sanal makineler oluşturma yöntemini öğretir. Type virtual machine kavramını kapsar.

**Ne Yapar:** Tip tabanlı sanal makineler oluşturur, tip kontrolü yapar ve tip güvenliği sağlar.

### Type VM Simulation
```python
from typing import List, Any, Dict

class TypeVM:
    def __init__(self):
        self.stack: List[Any] = []
        self.variables: Dict[str, Any] = {}
        self.instructions: List[str] = []
    
    def push(self, value: Any) -> None:
        self.stack.append(value)
    
    def pop(self) -> Any:
        return self.stack.pop()
    
    def store(self, name: str) -> None:
        self.variables[name] = self.pop()
    
    def load(self, name: str) -> None:
        self.push(self.variables[name])
    
    def execute(self, instruction: str) -> None:
        if instruction.startswith("PUSH"):
            value = instruction.split()[1]
            self.push(eval(value))
        elif instruction.startswith("STORE"):
            name = instruction.split()[1]
            self.store(name)
        elif instruction.startswith("LOAD"):
            name = instruction.split()[1]
            self.load(name)

# Kullanım
vm = TypeVM()
vm.execute("PUSH 42")
vm.execute("STORE x")
vm.execute("LOAD x")
print(vm.pop())  # 42
```

## 108. Type Runtime

**Ne İşe Yarar:** Runtime'da tip kontrolü yapma yöntemini öğretir. Type runtime kavramını kapsar.

**Ne Yapar:** Runtime'da tip kontrolü yapar, tip güvenliği sağlar ve tip hatalarını önler.

### Type Runtime
```python
import time
from typing import Any, Callable

class TypeRuntime:
    def __init__(self):
        self.start_time = time.time()
        self.type_checks = 0
    
    def type_check(self, value: Any, expected_type: type) -> bool:
        self.type_checks += 1
        return isinstance(value, expected_type)
    
    def get_stats(self) -> Dict[str, Any]:
        return {
            "runtime": time.time() - self.start_time,
            "type_checks": self.type_checks
        }

# Kullanım
runtime = TypeRuntime()
print(runtime.type_check(42, int))      # True
print(runtime.type_check("test", str))  # True
print(runtime.type_check(42, str))      # False
print(runtime.get_stats())              # {'runtime': ..., 'type_checks': 3}
```

## 109. Type Compile Time

**Ne İşe Yarar:** Compile time'da tip kontrolü yapma yöntemini öğretir. Compile time type checking kavramını kapsar.

**Ne Yapar:** Compile time'da tip kontrolü yapar, tip hatalarını erken tespit eder ve tip güvenliği sağlar.

### Compile Time Type Checking
```python
from typing import TYPE_CHECKING, TypeVar, Type

if TYPE_CHECKING:
    # Sadece type checking sırasında çalışır
    from typing import List, Dict
    
    T = TypeVar('T')
    
    def compile_time_check(data: List[T]) -> bool:
        return len(data) > 0

# Runtime'da bu kod çalışmaz
def runtime_function(data: list) -> bool:
    return len(data) > 0

# TYPE_CHECKING compile time'da True, runtime'da False
print(TYPE_CHECKING)  # False (runtime'da)
```

## 110. Type Link Time

**Ne İşe Yarar:** Link time'da tip kontrolü yapma yöntemini öğretir. Type link time kavramını kapsar.

**Ne Yapar:** Link time'da tip kontrolü yapar, tip uyumluluğunu kontrol eder ve tip güvenliği sağlar.

### Type Link Time
```python
from typing import Dict, Type, Any

class TypeLinker:
    def __init__(self):
        self.type_table: Dict[str, Type] = {}
        self.linked_types: Dict[str, Type] = {}
    
    def register_type(self, name: str, type_class: Type) -> None:
        self.type_table[name] = type_class
    
    def link_type(self, name: str) -> Type:
        if name in self.linked_types:
            return self.linked_types[name]
        
        if name not in self.type_table:
            raise ValueError(f"Tip bulunamadı: {name}")
        
        linked_type = self.type_table[name]
        self.linked_types[name] = linked_type
        return linked_type

# Kullanım
linker = TypeLinker()
linker.register_type("int", int)
linker.register_type("str", str)

linked_int = linker.link_type("int")
linked_str = linker.link_type("str")

print(linked_int(42))    # 42
print(linked_str("test"))  # test
```

## 111. Type Load Time

**Ne İşe Yarar:** Load time'da tip kontrolü yapma yöntemini öğretir. Type load time kavramını kapsar.

**Ne Yapar:** Load time'da tip kontrolü yapar, tip bilgilerini yükler ve tip güvenliği sağlar.

### Type Load Time
```python
import importlib
from typing import Type, Any

class TypeLoader:
    def __init__(self):
        self.loaded_types: Dict[str, Type] = {}
    
    def load_type(self, module_name: str, type_name: str) -> Type:
        key = f"{module_name}.{type_name}"
        
        if key in self.loaded_types:
            return self.loaded_types[key]
        
        try:
            module = importlib.import_module(module_name)
            type_class = getattr(module, type_name)
            self.loaded_types[key] = type_class
            return type_class
        except (ImportError, AttributeError) as e:
            raise ValueError(f"Tip yüklenemedi: {e}")
    
    def get_loaded_types(self) -> Dict[str, Type]:
        return self.loaded_types.copy()

# Kullanım
loader = TypeLoader()
# int_type = loader.load_type("builtins", "int")
# print(int_type(42))  # 42
```

## 112. Type Execution Time

**Ne İşe Yarar:** Execution time'da tip kontrolü yapma yöntemini öğretir. Type execution time kavramını kapsar.

**Ne Yapar:** Execution time'da tip kontrolü yapar, runtime tip güvenliği sağlar ve tip hatalarını önler.

### Type Execution Time
```python
import time
from typing import Any, Callable

class TypeExecutionTimer:
    def __init__(self):
        self.execution_times: Dict[str, float] = {}
    
    def time_type_operation(self, operation_name: str, operation: Callable) -> Any:
        start_time = time.time()
        result = operation()
        end_time = time.time()
        
        self.execution_times[operation_name] = end_time - start_time
        return result
    
    def get_execution_stats(self) -> Dict[str, float]:
        return self.execution_times.copy()

# Kullanım
timer = TypeExecutionTimer()

def type_check_operation():
    return isinstance(42, int)

result = timer.time_type_operation("type_check", type_check_operation)
print(result)  # True
print(timer.get_execution_stats())  # {'type_check': ...}
```

## 113. Type Static Analysis

**Ne İşe Yarar:** Statik tip analizi yapma yöntemini öğretir. Type static analysis kavramını kapsar.

**Ne Yapar:** Statik tip analizi yapar, tip hatalarını erken tespit eder ve kod kalitesini artırır.

### Type Static Analysis
```python
from typing import Dict, List, Any, Type

class TypeStaticAnalyzer:
    def __init__(self):
        self.type_usage: Dict[str, int] = {}
        self.type_dependencies: Dict[str, List[str]] = {}
    
    def analyze_type_usage(self, type_name: str) -> None:
        self.type_usage[type_name] = self.type_usage.get(type_name, 0) + 1
    
    def add_type_dependency(self, type_name: str, dependency: str) -> None:
        if type_name not in self.type_dependencies:
            self.type_dependencies[type_name] = []
        self.type_dependencies[type_name].append(dependency)
    
    def get_analysis_report(self) -> Dict[str, Any]:
        return {
            "usage_count": self.type_usage,
            "dependencies": self.type_dependencies
        }

# Kullanım
analyzer = TypeStaticAnalyzer()
analyzer.analyze_type_usage("int")
analyzer.analyze_type_usage("str")
analyzer.analyze_type_usage("int")
analyzer.add_type_dependency("List", "T")

print(analyzer.get_analysis_report())
```

## 114. Type Dynamic Analysis

**Ne İşe Yarar:** Dinamik tip analizi yapma yöntemini öğretir. Type dynamic analysis kavramını kapsar.

**Ne Yapar:** Dinamik tip analizi yapar, runtime tip bilgilerini inceler ve tip davranışlarını analiz eder.

### Type Dynamic Analysis
```python
import sys
from typing import Dict, Any, Type

class TypeDynamicAnalyzer:
    def __init__(self):
        self.runtime_types: Dict[str, Type] = {}
        self.type_instances: Dict[str, int] = {}
    
    def track_type_creation(self, type_class: Type) -> None:
        type_name = type_class.__name__
        self.runtime_types[type_name] = type_class
        self.type_instances[type_name] = self.type_instances.get(type_name, 0) + 1
    
    def get_memory_usage(self) -> Dict[str, int]:
        return {name: sys.getsizeof(cls) for name, cls in self.runtime_types.items()}
    
    def get_instance_count(self) -> Dict[str, int]:
        return self.type_instances.copy()

# Kullanım
analyzer = TypeDynamicAnalyzer()
analyzer.track_type_creation(int)
analyzer.track_type_creation(str)
analyzer.track_type_creation(list)

print(analyzer.get_instance_count())  # {'int': 1, 'str': 1, 'list': 1}
```

## 115. Type Profiling

**Ne İşe Yarar:** Tip performansını ölçme yöntemini öğretir. Type profiling kavramını kapsar.

**Ne Yapar:** Tip performansını ölçer, tip işlemlerini analiz eder ve performans optimizasyonu sağlar.

### Type Profiling
```python
import cProfile
import pstats
from typing import Callable, Any

class TypeProfiler:
    def __init__(self):
        self.profiler = cProfile.Profile()
        self.stats = None
    
    def profile_type_operation(self, operation: Callable, *args, **kwargs) -> Any:
        self.profiler.enable()
        result = operation(*args, **kwargs)
        self.profiler.disable()
        
        self.stats = pstats.Stats(self.profiler)
        return result
    
    def get_profile_stats(self, limit: int = 10) -> str:
        if self.stats is None:
            return "Profil verisi yok"
        
        import io
        output = io.StringIO()
        self.stats.sort_stats('cumulative')
        self.stats.print_stats(limit, stream=output)
        return output.getvalue()

# Kullanım
profiler = TypeProfiler()

def type_intensive_operation():
    return [isinstance(i, int) for i in range(10000)]

result = profiler.profile_type_operation(type_intensive_operation)
print(profiler.get_profile_stats(5))
```

## 116. Type Debugging

**Ne İşe Yarar:** Tip hatalarını ayıklama yöntemini öğretir. Type debugging kavramını kapsar.

**Ne Yapar:** Tip hatalarını ayıklar, tip sorunlarını çözer ve tip güvenliği sağlar.

### Type Debugging
```python
import traceback
from typing import Any, Dict, List

class TypeDebugger:
    def __init__(self):
        self.debug_log: List[Dict[str, Any]] = []
        self.enabled = True
    
    def log_type_check(self, value: Any, expected_type: type, success: bool) -> None:
        if not self.enabled:
            return
        
        self.debug_log.append({
            "value": value,
            "expected_type": expected_type.__name__,
            "actual_type": type(value).__name__,
            "success": success,
            "traceback": traceback.format_stack()
        })
    
    def get_debug_report(self) -> List[Dict[str, Any]]:
        return self.debug_log.copy()
    
    def clear_log(self) -> None:
        self.debug_log.clear()

# Kullanım
debugger = TypeDebugger()
debugger.log_type_check(42, int, True)
debugger.log_type_check("test", int, False)

for entry in debugger.get_debug_report():
    print(f"{entry['value']} -> {entry['expected_type']}: {entry['success']}")
```

## 117. Type Tracing

**Ne İşe Yarar:** Tip işlemlerini izleme yöntemini öğretir. Type tracing kavramını kapsar.

**Ne Yapar:** Tip işlemlerini izler, tip akışını takip eder ve tip davranışlarını analiz eder.

### Type Tracing
```python
from typing import Any, List, Dict
import sys

class TypeTracer:
    def __init__(self):
        self.trace_log: List[Dict[str, Any]] = []
        self.original_trace = sys.gettrace()
    
    def start_tracing(self) -> None:
        sys.settrace(self.trace_callback)
    
    def stop_tracing(self) -> None:
        sys.settrace(self.original_trace)
    
    def trace_callback(self, frame, event, arg):
        if event == 'call':
            self.trace_log.append({
                "function": frame.f_code.co_name,
                "filename": frame.f_code.co_filename,
                "line": frame.f_lineno,
                "locals": frame.f_locals.copy()
            })
        return self.trace_callback
    
    def get_trace_log(self) -> List[Dict[str, Any]]:
        return self.trace_log.copy()

# Kullanım
tracer = TypeTracer()
tracer.start_tracing()

def test_function(x: int) -> int:
    return x * 2

result = test_function(5)
tracer.stop_tracing()

print(f"Trace log entries: {len(tracer.get_trace_log())}")
```

## 118. Type Logging

**Ne İşe Yarar:** Tip işlemlerini loglama yöntemini öğretir. Type logging kavramını kapsar.

**Ne Yapar:** Tip işlemlerini loglar, tip bilgilerini kaydeder ve tip analizi sağlar.

### Type Logging
```python
import logging
from typing import Any, Dict

class TypeLogger:
    def __init__(self, log_level: int = logging.INFO):
        self.logger = logging.getLogger("TypeLogger")
        self.logger.setLevel(log_level)
        
        if not self.logger.handlers:
            handler = logging.StreamHandler()
            formatter = logging.Formatter('%(asctime)s - %(name)s - %(levelname)s - %(message)s')
            handler.setFormatter(formatter)
            self.logger.addHandler(handler)
    
    def log_type_check(self, value: Any, expected_type: type, result: bool) -> None:
        self.logger.info(f"Type check: {value} ({type(value).__name__}) -> {expected_type.__name__}: {result}")
    
    def log_type_error(self, error: Exception) -> None:
        self.logger.error(f"Type error: {error}")
    
    def log_type_warning(self, message: str) -> None:
        self.logger.warning(f"Type warning: {message}")

# Kullanım
type_logger = TypeLogger()
type_logger.log_type_check(42, int, True)
type_logger.log_type_check("test", int, False)
type_logger.log_type_warning("Potansiyel tip uyumsuzluğu")
```

## 119. Type Monitoring

**Ne İşe Yarar:** Tip sistemini izleme yöntemini öğretir. Type monitoring kavramını kapsar.

**Ne Yapar:** Tip sistemini izler, tip durumunu takip eder ve tip sorunlarını tespit eder.

### Type Monitoring
```python
import time
from typing import Dict, List, Any
from collections import defaultdict

class TypeMonitor:
    def __init__(self):
        self.type_usage: Dict[str, int] = defaultdict(int)
        self.type_errors: List[Dict[str, Any]] = []
        self.start_time = time.time()
    
    def record_type_usage(self, type_name: str) -> None:
        self.type_usage[type_name] += 1
    
    def record_type_error(self, error: Exception, context: str) -> None:
        self.type_errors.append({
            "error": str(error),
            "context": context,
            "timestamp": time.time()
        })
    
    def get_monitoring_stats(self) -> Dict[str, Any]:
        return {
            "uptime": time.time() - self.start_time,
            "type_usage": dict(self.type_usage),
            "error_count": len(self.type_errors),
            "most_used_type": max(self.type_usage.items(), key=lambda x: x[1])[0] if self.type_usage else None
        }

# Kullanım
monitor = TypeMonitor()
monitor.record_type_usage("int")
monitor.record_type_usage("str")
monitor.record_type_usage("int")
monitor.record_type_error(ValueError("Invalid type"), "function_call")

print(monitor.get_monitoring_stats())
```

## 120. Type Metrics

**Ne İşe Yarar:** Tip sistemi metriklerini ölçme yöntemini öğretir. Type metrics kavramını kapsar.

**Ne Yapar:** Tip sistemi metriklerini ölçer, tip kalitesini değerlendirir ve tip performansını analiz eder.

### Type Metrics
```python
from typing import Dict, List, Any
from statistics import mean, median

class TypeMetrics:
    def __init__(self):
        self.type_check_times: Dict[str, List[float]] = defaultdict(list)
        self.type_success_rates: Dict[str, List[bool]] = defaultdict(list)
    
    def record_type_check(self, type_name: str, check_time: float, success: bool) -> None:
        self.type_check_times[type_name].append(check_time)
        self.type_success_rates[type_name].append(success)
    
    def get_type_metrics(self, type_name: str) -> Dict[str, Any]:
        if type_name not in self.type_check_times:
            return {}
        
        times = self.type_check_times[type_name]
        successes = self.type_success_rates[type_name]
        
        return {
            "avg_check_time": mean(times),
            "median_check_time": median(times),
            "success_rate": sum(successes) / len(successes),
            "total_checks": len(times)
        }
    
    def get_overall_metrics(self) -> Dict[str, Any]:
        all_times = [t for times in self.type_check_times.values() for t in times]
        all_successes = [s for successes in self.type_success_rates.values() for s in successes]
        
        return {
            "total_type_checks": len(all_times),
            "overall_success_rate": sum(all_successes) / len(all_successes) if all_successes else 0,
            "avg_check_time": mean(all_times) if all_times else 0
        }

# Kullanım
metrics = TypeMetrics()
metrics.record_type_check("int", 0.001, True)
metrics.record_type_check("int", 0.002, True)
metrics.record_type_check("str", 0.001, False)

print(metrics.get_type_metrics("int"))
print(metrics.get_overall_metrics())
```

## 121. Type Benchmarks

**Ne İşe Yarar:** Tip sistemi performansını karşılaştırma yöntemini öğretir. Type benchmarks kavramını kapsar.

**Ne Yapar:** Tip sistemi performansını karşılaştırır, tip işlemlerini ölçer ve performans optimizasyonu sağlar.

### Type Benchmarks
```python
import time
from typing import Callable, Dict, Any

class TypeBenchmark:
    def __init__(self):
        self.benchmark_results: Dict[str, float] = {}
    
    def benchmark_type_operation(self, name: str, operation: Callable, iterations: int = 1000) -> float:
        start_time = time.time()
        
        for _ in range(iterations):
            operation()
        
        end_time = time.time()
        total_time = end_time - start_time
        avg_time = total_time / iterations
        
        self.benchmark_results[name] = avg_time
        return avg_time
    
    def compare_benchmarks(self, operation1: str, operation2: str) -> Dict[str, Any]:
        if operation1 not in self.benchmark_results or operation2 not in self.benchmark_results:
            return {"error": "Benchmark bulunamadı"}
        
        time1 = self.benchmark_results[operation1]
        time2 = self.benchmark_results[operation2]
        
        return {
            "operation1": {"name": operation1, "time": time1},
            "operation2": {"name": operation2, "time": time2},
            "difference": abs(time1 - time2),
            "faster": operation1 if time1 < time2 else operation2
        }

# Kullanım
benchmark = TypeBenchmark()

def isinstance_check():
    return isinstance(42, int)

def type_check():
    return type(42) == int

benchmark.benchmark_type_operation("isinstance", isinstance_check)
benchmark.benchmark_type_operation("type_check", type_check)

print(benchmark.compare_benchmarks("isinstance", "type_check"))
```

## 122. Type Performance

**Ne İşe Yarar:** Tip sistemi performansını ölçme yöntemini öğretir. Type performance kavramını kapsar.

**Ne Yapar:** Tip sistemi performansını ölçer, tip işlemlerini analiz eder ve performans optimizasyonu sağlar.

### Type Performance
```python
import time
from typing import Dict, Any, Callable

class TypePerformance:
    def __init__(self):
        self.performance_data: Dict[str, Dict[str, Any]] = {}
    
    def measure_performance(self, operation_name: str, operation: Callable, *args, **kwargs) -> Dict[str, Any]:
        # Memory usage (basit yaklaşım)
        import sys
        
        start_time = time.time()
        start_memory = sys.getsizeof(operation)
        
        result = operation(*args, **kwargs)
        
        end_time = time.time()
        end_memory = sys.getsizeof(result)
        
        performance_data = {
            "execution_time": end_time - start_time,
            "memory_delta": end_memory - start_memory,
            "result_size": sys.getsizeof(result)
        }
        
        self.performance_data[operation_name] = performance_data
        return performance_data
    
    def get_performance_report(self) -> Dict[str, Dict[str, Any]]:
        return self.performance_data.copy()

# Kullanım
perf = TypePerformance()

def list_operation():
    return [i for i in range(1000)]

def set_operation():
    return {i for i in range(1000)}

perf.measure_performance("list_creation", list_operation)
perf.measure_performance("set_creation", set_operation)

print(perf.get_performance_report())
```

## 123. Type Optimization

**Ne İşe Yarar:** Tip sistemi optimizasyonu yapma yöntemini öğretir. Type optimization kavramını kapsar.

**Ne Yapar:** Tip sistemi optimizasyonu yapar, tip performansını artırır ve tip verimliliğini sağlar.

### Type Optimization
```python
from typing import Dict, Any, Type, Callable

class TypeOptimizer:
    def __init__(self):
        self.optimizations: Dict[str, Callable] = {}
        self.optimization_stats: Dict[str, int] = {}
    
    def register_optimization(self, name: str, optimizer: Callable) -> None:
        self.optimizations[name] = optimizer
    
    def optimize_type_operation(self, operation_name: str, operation: Callable, *args, **kwargs) -> Any:
        if operation_name in self.optimizations:
            self.optimization_stats[operation_name] = self.optimization_stats.get(operation_name, 0) + 1
            return self.optimizations[operation_name](*args, **kwargs)
        else:
            return operation(*args, **kwargs)
    
    def get_optimization_stats(self) -> Dict[str, int]:
        return self.optimization_stats.copy()

# Kullanım
optimizer = TypeOptimizer()

def slow_type_check(value, target_type):
    return isinstance(value, target_type)

def fast_type_check(value, target_type):
    return type(value) == target_type

optimizer.register_optimization("type_check", fast_type_check)

result = optimizer.optimize_type_operation("type_check", slow_type_check, 42, int)
print(result)  # True
print(optimizer.get_optimization_stats())  # {'type_check': 1}
```

## 124. Type Caching

**Ne İşe Yarar:** Tip bilgilerini önbellekleme yöntemini öğretir. Type caching kavramını kapsar.

**Ne Yapar:** Tip bilgilerini önbellekler, tip işlemlerini hızlandırır ve tip performansını artırır.

### Type Caching
```python
from typing import Dict, Any, Type, Callable
from functools import lru_cache

class TypeCache:
    def __init__(self):
        self.cache: Dict[str, Any] = {}
        self.hit_count = 0
        self.miss_count = 0
    
    def get_cached_type(self, key: str) -> Any:
        if key in self.cache:
            self.hit_count += 1
            return self.cache[key]
        else:
            self.miss_count += 1
            return None
    
    def cache_type(self, key: str, value: Any) -> None:
        self.cache[key] = value
    
    def get_cache_stats(self) -> Dict[str, Any]:
        total_requests = self.hit_count + self.miss_count
        hit_rate = self.hit_count / total_requests if total_requests > 0 else 0
        
        return {
            "cache_size": len(self.cache),
            "hit_count": self.hit_count,
            "miss_count": self.miss_count,
            "hit_rate": hit_rate
        }

# LRU Cache ile type caching
@lru_cache(maxsize=128)
def cached_type_check(value: Any, target_type: Type) -> bool:
    return isinstance(value, target_type)

# Kullanım
type_cache = TypeCache()
type_cache.cache_type("int_check", int)
type_cache.cache_type("str_check", str)

cached_int = type_cache.get_cached_type("int_check")
print(cached_int)  # <class 'int'>
print(type_cache.get_cache_stats())
```

## 125. Type Memoization

**Ne İşe Yarar:** Tip işlemlerini memoization ile optimize etme yöntemini öğretir. Type memoization kavramını kapsar.

**Ne Yapar:** Tip işlemlerini memoization ile optimize eder, tip hesaplamalarını hızlandırır ve tip performansını artırır.

### Type Memoization
```python
from typing import Dict, Any, Callable
from functools import wraps

def type_memoize(func: Callable) -> Callable:
    cache: Dict[str, Any] = {}
    
    @wraps(func)
    def wrapper(*args, **kwargs):
        # Cache key oluştur
        key = str(args) + str(sorted(kwargs.items()))
        
        if key not in cache:
            cache[key] = func(*args, **kwargs)
        
        return cache[key]
    
    return wrapper

@type_memoize
def expensive_type_operation(value: Any, target_type: type) -> bool:
    # Pahalı tip kontrolü simülasyonu
    import time
    time.sleep(0.001)  # Simüle edilmiş gecikme
    return isinstance(value, target_type)

# Kullanım
print(expensive_type_operation(42, int))  # İlk çağrı - yavaş
print(expensive_type_operation(42, int))  # İkinci çağrı - hızlı (cache'den)
```

## 126. Type Lazy Loading

**Ne İşe Yarar:** Tip bilgilerini lazy loading ile yükleme yöntemini öğretir. Type lazy loading kavramını kapsar.

**Ne Yapar:** Tip bilgilerini lazy loading ile yükler, bellek kullanımını optimize eder ve tip performansını artırır.

### Type Lazy Loading
```python
from typing import Any, Type, Callable

class LazyType:
    def __init__(self, loader: Callable[[], Type]):
        self._loader = loader
        self._type = None
        self._loaded = False
    
    def __call__(self, *args, **kwargs) -> Any:
        if not self._loaded:
            self._type = self._loader()
            self._loaded = True
        
        return self._type(*args, **kwargs)
    
    @property
    def type(self) -> Type:
        if not self._loaded:
            self._type = self._loader()
            self._loaded = True
        return self._type

# Kullanım
def load_expensive_type():
    # Pahalı tip yükleme simülasyonu
    import time
    time.sleep(0.1)
    return int

lazy_int = LazyType(load_expensive_type)
# Tip henüz yüklenmedi

value = lazy_int("42")  # Şimdi yüklendi
print(value)  # 42
```

## 127. Type Eager Loading

**Ne İşe Yarar:** Tip bilgilerini eager loading ile yükleme yöntemini öğretir. Type eager loading kavramını kapsar.

**Ne Yapar:** Tip bilgilerini eager loading ile yükler, tip erişimini hızlandırır ve tip performansını artırır.

### Type Eager Loading
```python
from typing import Dict, Type, Any

class EagerTypeLoader:
    def __init__(self):
        self.loaded_types: Dict[str, Type] = {}
        self.load_on_init = True
    
    def preload_types(self, type_names: list[str]) -> None:
        """Tipleri önceden yükle"""
        for name in type_names:
            if name not in self.loaded_types:
                try:
                    # Built-in tipleri yükle
                    if name == "int":
                        self.loaded_types[name] = int
                    elif name == "str":
                        self.loaded_types[name] = str
                    elif name == "list":
                        self.loaded_types[name] = list
                    elif name == "dict":
                        self.loaded_types[name] = dict
                    # Diğer tipler için genişletilebilir
                except Exception as e:
                    print(f"Tip yüklenemedi {name}: {e}")
    
    def get_type(self, name: str) -> Type:
        if name not in self.loaded_types:
            raise ValueError(f"Tip yüklenmemiş: {name}")
        return self.loaded_types[name]

# Kullanım
loader = EagerTypeLoader()
loader.preload_types(["int", "str", "list"])

int_type = loader.get_type("int")
str_type = loader.get_type("str")

print(int_type(42))    # 42
print(str_type("test"))  # test
```

## 128. Type Preloading

**Ne İşe Yarar:** Tip bilgilerini önceden yükleme yöntemini öğretir. Type preloading kavramını kapsar.

**Ne Yapar:** Tip bilgilerini önceden yükler, tip erişimini hızlandırır ve tip performansını artırır.

### Type Preloading
```python
from typing import Dict, Type, Any
import importlib

class TypePreloader:
    def __init__(self):
        self.preloaded_types: Dict[str, Type] = {}
        self.preload_queue: list[str] = []
    
    def add_to_preload_queue(self, type_name: str) -> None:
        """Yükleme kuyruğuna ekle"""
        if type_name not in self.preload_queue:
            self.preload_queue.append(type_name)
    
    def preload_all(self) -> None:
        """Kuyruktaki tüm tipleri yükle"""
        for type_name in self.preload_queue:
            self.preload_type(type_name)
        self.preload_queue.clear()
    
    def preload_type(self, type_name: str) -> None:
        """Belirli bir tipi yükle"""
        try:
            if type_name in ["int", "str", "list", "dict", "tuple", "set"]:
                self.preloaded_types[type_name] = globals()[type_name]
            else:
                # Modül tipi varsayımı
                module_name, class_name = type_name.rsplit(".", 1)
                module = importlib.import_module(module_name)
                self.preloaded_types[type_name] = getattr(module, class_name)
        except Exception as e:
            print(f"Preload hatası {type_name}: {e}")
    
    def get_preloaded_type(self, type_name: str) -> Type:
        return self.preloaded_types.get(type_name)

# Kullanım
preloader = TypePreloader()
preloader.add_to_preload_queue("int")
preloader.add_to_preload_queue("str")
preloader.preload_all()

int_type = preloader.get_preloaded_type("int")
print(int_type(42))  # 42
```

## 129. Type Postloading

**Ne İşe Yarar:** Tip bilgilerini sonradan yükleme yöntemini öğretir. Type postloading kavramını kapsar.

**Ne Yapar:** Tip bilgilerini sonradan yükler, bellek kullanımını optimize eder ve tip performansını artırır.

### Type Postloading
```python
from typing import Dict, Type, Any, Callable

class TypePostloader:
    def __init__(self):
        self.postload_hooks: Dict[str, Callable] = {}
        self.loaded_types: Dict[str, Type] = {}
    
    def register_postload_hook(self, type_name: str, hook: Callable[[Type], None]) -> None:
        """Tip yüklendikten sonra çalışacak hook kaydet"""
        self.postload_hooks[type_name] = hook
    
    def load_type_with_postload(self, type_name: str, type_class: Type) -> Type:
        """Tipi yükle ve postload hook'u çalıştır"""
        self.loaded_types[type_name] = type_class
        
        if type_name in self.postload_hooks:
            self.postload_hooks[type_name](type_class)
        
        return type_class
    
    def get_loaded_type(self, type_name: str) -> Type:
        return self.loaded_types.get(type_name)

# Kullanım
postloader = TypePostloader()

def int_postload_hook(int_type: Type) -> None:
    print(f"Int tipi yüklendi: {int_type}")

postloader.register_postload_hook("int", int_postload_hook)
loaded_int = postloader.load_type_with_postload("int", int)
# Çıktı: Int tipi yüklendi: <class 'int'>

print(loaded_int(42))  # 42
```

## 130. Type Hot Reloading

**Ne İşe Yarar:** Tip bilgilerini hot reloading ile güncelleme yöntemini öğretir. Type hot reloading kavramını kapsar.

**Ne Yapar:** Tip bilgilerini hot reloading ile günceller, geliştirme sürecini hızlandırır ve tip değişikliklerini anında uygular.

### Type Hot Reloading
```python
import importlib
from typing import Dict, Type, Any, Callable

class TypeHotReloader:
    def __init__(self):
        self.reloadable_types: Dict[str, Type] = {}
        self.reload_callbacks: Dict[str, Callable] = {}
        self.module_versions: Dict[str, int] = {}
    
    def register_reloadable_type(self, type_name: str, type_class: Type) -> None:
        """Yeniden yüklenebilir tip kaydet"""
        self.reloadable_types[type_name] = type_class
        module_name = type_class.__module__
        self.module_versions[module_name] = 0
    
    def register_reload_callback(self, type_name: str, callback: Callable[[Type], None]) -> None:
        """Yeniden yükleme callback'i kaydet"""
        self.reload_callbacks[type_name] = callback
    
    def hot_reload_type(self, type_name: str) -> bool:
        """Tipi sıcak yeniden yükle"""
        if type_name not in self.reloadable_types:
            return False
        
        old_type = self.reloadable_types[type_name]
        module_name = old_type.__module__
        
        try:
            # Modülü yeniden yükle
            module = importlib.reload(importlib.import_module(module_name))
            new_type = getattr(module, type_name)
            
            # Tipi güncelle
            self.reloadable_types[type_name] = new_type
            self.module_versions[module_name] += 1
            
            # Callback'i çalıştır
            if type_name in self.reload_callbacks:
                self.reload_callbacks[type_name](new_type)
            
            return True
        except Exception as e:
            print(f"Hot reload hatası: {e}")
            return False
    
    def get_type_version(self, module_name: str) -> int:
        return self.module_versions.get(module_name, 0)

# Kullanım
hot_reloader = TypeHotReloader()

def reload_callback(new_type: Type) -> None:
    print(f"Tip yeniden yüklendi: {new_type}")

hot_reloader.register_reloadable_type("int", int)
hot_reloader.register_reload_callback("int", reload_callback)

# Hot reload simülasyonu
success = hot_reloader.hot_reload_type("int")
print(f"Hot reload başarılı: {success}")

---

## 131. Regular Expressions (Regex)

**Ne İşe Yarar:** Metin arama, değiştirme ve doğrulama işlemlerini öğretir. Regex pattern'ları ile karmaşık metin işlemleri yapmayı kapsar.

**Ne Yapar:** Metinlerde belirli pattern'ları arar, değiştirir ve doğrular. Email, telefon numarası gibi formatları kontrol eder.

### Temel Regex İşlemleri
```python
import re

# Metin arama
text = "Telefon: 0555-123-4567, Email: test@example.com"
phone_pattern = r'\d{4}-\d{3}-\d{4}'
email_pattern = r'[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}'

# Telefon numarası bul
phone_match = re.search(phone_pattern, text)
if phone_match:
    print(f"Telefon: {phone_match.group()}")  # 0555-123-4567

# Email bul
email_match = re.search(email_pattern, text)
if email_match:
    print(f"Email: {email_match.group()}")  # test@example.com

# Tüm eşleşmeleri bul
all_phones = re.findall(phone_pattern, text)
print(all_phones)  # ['0555-123-4567']

# Metin değiştirme
new_text = re.sub(phone_pattern, '***-***-****', text)
print(new_text)  # Telefon: ***-***-****, Email: test@example.com
```

## 132. JSON İşlemleri

**Ne İşe Yarar:** JSON formatındaki verileri okuma, yazma ve işleme yöntemlerini öğretir. API'ler ve veri değişimi için kullanılır.

**Ne Yapar:** JSON verilerini Python objelerine dönüştürür, Python objelerini JSON formatına çevirir ve dosyalarda saklar.

### JSON Temel İşlemleri
```python
import json

# Python objesini JSON'a çevir
data = {
    "isim": "Ahmet",
    "yas": 25,
    "sehirler": ["İstanbul", "Ankara"],
    "aktif": True
}

# JSON string'e çevir
json_string = json.dumps(data, ensure_ascii=False, indent=2)
print(json_string)

# JSON dosyasına yaz
with open('veri.json', 'w', encoding='utf-8') as f:
    json.dump(data, f, ensure_ascii=False, indent=2)

# JSON dosyasından oku
with open('veri.json', 'r', encoding='utf-8') as f:
    loaded_data = json.load(f)
print(loaded_data["isim"])  # Ahmet

# JSON string'den Python objesine çevir
json_text = '{"isim": "Mehmet", "yas": 30}'
parsed_data = json.loads(json_text)
print(parsed_data["isim"])  # Mehmet
```

## 133. XML İşlemleri

**Ne İşe Yarar:** XML formatındaki verileri okuma, yazma ve işleme yöntemlerini öğretir. Web servisleri ve veri değişimi için kullanılır.

**Ne Yapar:** XML dosyalarını parse eder, XML elementlerini işler ve yeni XML dosyaları oluşturur.

### XML Temel İşlemleri
```python
import xml.etree.ElementTree as ET

# XML string'den parse et
xml_string = '''
<kisiler>
    <kisi>
        <isim>Ahmet</isim>
        <yas>25</yas>
    </kisi>
    <kisi>
        <isim>Mehmet</isim>
        <yas>30</yas>
    </kisi>
</kisiler>
'''

root = ET.fromstring(xml_string)

# XML elementlerini işle
for kisi in root.findall('kisi'):
    isim = kisi.find('isim').text
    yas = kisi.find('yas').text
    print(f"{isim}: {yas} yaşında")

# Yeni XML oluştur
root = ET.Element("kisiler")
kisi1 = ET.SubElement(root, "kisi")
isim1 = ET.SubElement(kisi1, "isim")
isim1.text = "Ali"
yas1 = ET.SubElement(kisi1, "yas")
yas1.text = "28"

# XML'i string'e çevir
xml_str = ET.tostring(root, encoding='unicode')
print(xml_str)
```

## 134. CSV İşlemleri

**Ne İşe Yarar:** CSV (Comma Separated Values) dosyalarını okuma ve yazma yöntemlerini öğretir. Veri analizi ve tablo verileri için kullanılır.

**Ne Yapar:** CSV dosyalarını satır satır okur, verileri işler ve yeni CSV dosyaları oluşturur.

### CSV Temel İşlemleri
```python
import csv

# CSV dosyasına yaz
veriler = [
    ['isim', 'yas', 'sehir'],
    ['Ahmet', '25', 'İstanbul'],
    ['Mehmet', '30', 'Ankara'],
    ['Ayşe', '28', 'İzmir']
]

with open('kisiler.csv', 'w', newline='', encoding='utf-8') as f:
    writer = csv.writer(f)
    writer.writerows(veriler)

# CSV dosyasından oku
with open('kisiler.csv', 'r', encoding='utf-8') as f:
    reader = csv.reader(f)
    for row in reader:
        print(row)  # ['isim', 'yas', 'sehir'], ['Ahmet', '25', 'İstanbul'], ...

# Dictionary olarak oku
with open('kisiler.csv', 'r', encoding='utf-8') as f:
    reader = csv.DictReader(f)
    for row in reader:
        print(f"{row['isim']}: {row['yas']} yaşında, {row['sehir']}")
```

## 135. Environment Variables

**Ne İşe Yarar:** Sistem ortam değişkenlerini okuma ve ayarlama yöntemlerini öğretir. Konfigürasyon ve güvenlik için kullanılır.

**Ne Yapar:** Sistem ortam değişkenlerini okur, yeni değişkenler ayarlar ve uygulama konfigürasyonunu yönetir.

### Environment Variables İşlemleri
```python
import os

# Ortam değişkeni oku
python_path = os.environ.get('PYTHONPATH')
print(f"Python Path: {python_path}")

# Ortam değişkeni ayarla (sadece bu process için)
os.environ['CUSTOM_VAR'] = 'test_value'

# Ortam değişkeni kontrol et
if 'CUSTOM_VAR' in os.environ:
    print(f"Custom Var: {os.environ['CUSTOM_VAR']}")

# Tüm ortam değişkenlerini listele
for key, value in os.environ.items():
    if key.startswith('PYTHON'):
        print(f"{key}: {value}")

# .env dosyasından yükle (python-dotenv gerekli)
# from dotenv import load_dotenv
# load_dotenv()
# api_key = os.getenv('API_KEY')
```

## 136. Command Line Arguments

**Ne İşe Yarar:** Komut satırından argüman alma ve işleme yöntemlerini öğretir. CLI uygulamaları geliştirmek için kullanılır.

**Ne Yapar:** Komut satırı argümanlarını parse eder, kullanıcı girdilerini işler ve uygulama davranışını kontrol eder.

### Command Line Arguments İşlemleri
```python
import argparse
import sys

# Basit argüman okuma
if len(sys.argv) > 1:
    dosya_adi = sys.argv[1]
    print(f"Dosya: {dosya_adi}")

# Argparse ile gelişmiş argüman işleme
parser = argparse.ArgumentParser(description='Dosya işleme uygulaması')
parser.add_argument('dosya', help='İşlenecek dosya')
parser.add_argument('-o', '--output', help='Çıktı dosyası')
parser.add_argument('-v', '--verbose', action='store_true', help='Detaylı çıktı')
parser.add_argument('--limit', type=int, default=100, help='Satır limiti')

args = parser.parse_args()

print(f"İşlenecek dosya: {args.dosya}")
if args.output:
    print(f"Çıktı dosyası: {args.output}")
if args.verbose:
    print("Detaylı mod aktif")
print(f"Limit: {args.limit}")

# Kullanım: python script.py input.txt -o output.txt -v --limit 50
```

## 137. Logging Module

**Ne İşe Yarar:** Uygulama loglarını yönetme ve kaydetme yöntemlerini öğretir. Hata ayıklama ve izleme için kullanılır.

**Ne Yapar:** Farklı seviyelerde log mesajları oluşturur, logları dosyaya kaydeder ve uygulama davranışını izler.

### Logging Temel İşlemleri
```python
import logging

# Logging konfigürasyonu
logging.basicConfig(
    level=logging.INFO,
    format='%(asctime)s - %(name)s - %(levelname)s - %(message)s',
    handlers=[
        logging.FileHandler('app.log'),
        logging.StreamHandler()
    ]
)

logger = logging.getLogger(__name__)

# Farklı log seviyeleri
logger.debug("Bu debug mesajı")
logger.info("Bu info mesajı")
logger.warning("Bu uyarı mesajı")
logger.error("Bu hata mesajı")
logger.critical("Bu kritik hata mesajı")

# Özel logger oluştur
custom_logger = logging.getLogger('custom')
custom_logger.setLevel(logging.DEBUG)

# Log mesajı formatla
logger.info("Kullanıcı %s giriş yaptı", "ahmet")
```

## 138. Config Files

**Ne İşe Yarar:** Konfigürasyon dosyalarını okuma ve yazma yöntemlerini öğretir. Uygulama ayarlarını yönetmek için kullanılır.

**Ne Yapar:** INI formatındaki konfigürasyon dosyalarını okur, yazar ve uygulama ayarlarını yönetir.

### Config Files İşlemleri
```python
import configparser

# ConfigParser oluştur
config = configparser.ConfigParser()

# Konfigürasyon oluştur
config['DATABASE'] = {
    'host': 'localhost',
    'port': '5432',
    'name': 'mydb',
    'user': 'admin'
}

config['API'] = {
    'url': 'https://api.example.com',
    'timeout': '30',
    'retries': '3'
}

# Konfigürasyonu dosyaya yaz
with open('config.ini', 'w') as f:
    config.write(f)

# Konfigürasyonu dosyadan oku
config.read('config.ini')

# Değerleri oku
db_host = config.get('DATABASE', 'host')
db_port = config.getint('DATABASE', 'port')
api_timeout = config.getint('API', 'timeout')

print(f"DB Host: {db_host}")
print(f"DB Port: {db_port}")
print(f"API Timeout: {api_timeout}")

# Tüm bölümleri listele
for section in config.sections():
    print(f"Bölüm: {section}")
    for key, value in config.items(section):
        print(f"  {key}: {value}")
```

## 139. Date/Time İşlemleri

**Ne İşe Yarar:** Tarih ve saat işlemlerini yapma yöntemlerini öğretir. Zaman hesaplamaları ve formatlamaları için kullanılır.

**Ne Yapar:** Tarih ve saat objelerini oluşturur, zaman hesaplamaları yapar ve farklı formatlarda tarih gösterir.

### Date/Time Temel İşlemleri
```python
from datetime import datetime, date, timedelta

# Şu anki zaman
now = datetime.now()
print(f"Şu an: {now}")

# Belirli tarih oluştur
birth_date = datetime(1990, 5, 15, 14, 30, 0)
print(f"Doğum tarihi: {birth_date}")

# Tarih formatla
formatted_date = now.strftime("%d/%m/%Y %H:%M:%S")
print(f"Formatlanmış: {formatted_date}")

# String'den tarih parse et
date_string = "2023-12-25 10:30:00"
parsed_date = datetime.strptime(date_string, "%Y-%m-%d %H:%M:%S")
print(f"Parse edilen: {parsed_date}")

# Zaman hesaplamaları
future_date = now + timedelta(days=7)
print(f"1 hafta sonra: {future_date}")

# Tarih farkı hesapla
age = now - birth_date
print(f"Yaş: {age.days} gün")

# Sadece tarih
today = date.today()
print(f"Bugün: {today}")
```

## 140. Math ve Statistics

**Ne İşe Yarar:** Matematiksel işlemler ve istatistiksel hesaplamalar yapma yöntemlerini öğretir. Veri analizi ve bilimsel hesaplamalar için kullanılır.

**Ne Yapar:** Matematiksel fonksiyonları kullanır, istatistiksel hesaplamalar yapar ve rastgele sayılar üretir.

### Math ve Statistics İşlemleri
```python
import math
import statistics
import random

# Matematiksel işlemler
print(f"Pi: {math.pi}")
print(f"E: {math.e}")
print(f"Karekök 16: {math.sqrt(16)}")
print(f"2^10: {math.pow(2, 10)}")
print(f"Sin 90: {math.sin(math.radians(90))}")

# İstatistiksel hesaplamalar
sayilar = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
print(f"Ortalama: {statistics.mean(sayilar)}")
print(f"Medyan: {statistics.median(sayilar)}")
print(f"Standart sapma: {statistics.stdev(sayilar)}")
print(f"Varyans: {statistics.variance(sayilar)}")

# Rastgele sayılar
print(f"0-100 arası: {random.randint(0, 100)}")
print(f"0-1 arası: {random.random()}")
print(f"Normal dağılım: {random.gauss(0, 1)}")

# Liste karıştırma
kartlar = ['As', 'Kupa', 'Maça', 'Karo']
random.shuffle(kartlar)
print(f"Karıştırılmış kartlar: {kartlar}")

# Seçim yapma
secim = random.choice(kartlar)
print(f"Seçilen kart: {secim}")

## 141. Collections Module

**Ne İşe Yarar:** Gelişmiş veri yapılarını kullanma yöntemlerini öğretir. Namedtuple, defaultdict, Counter gibi özel koleksiyonları kapsar.

**Ne Yapar:** Standart veri yapılarının gelişmiş versiyonlarını sağlar, veri işleme işlemlerini kolaylaştırır ve performansı artırır.

### Collections Module İşlemleri
```python
from collections import namedtuple, defaultdict, Counter, deque

# Namedtuple - alan adları olan tuple
Person = namedtuple('Person', ['name', 'age', 'city'])
person1 = Person('Ahmet', 25, 'İstanbul')
print(f"{person1.name} {person1.age} yaşında, {person1.city}'de")

# Defaultdict - varsayılan değerli sözlük
word_count = defaultdict(int)
words = ['python', 'java', 'python', 'javascript', 'python']
for word in words:
    word_count[word] += 1
print(dict(word_count))  # {'python': 3, 'java': 1, 'javascript': 1}

# Counter - sayım yapan sözlük
counter = Counter(words)
print(counter)  # Counter({'python': 3, 'java': 1, 'javascript': 1})
print(counter.most_common(2))  # [('python', 3), ('java', 1)]

# Deque - çift yönlü kuyruk
queue = deque([1, 2, 3])
queue.append(4)  # Sağa ekle
queue.appendleft(0)  # Sola ekle
print(queue)  # deque([0, 1, 2, 3, 4])
print(queue.popleft())  # 0
print(queue.pop())  # 4
```

## 142. Itertools Module

**Ne İşe Yarar:** Iterator'lar üzerinde işlem yapma yöntemlerini öğretir. Kombinasyon, permütasyon ve diğer iterator işlemlerini kapsar.

**Ne Yapar:** Iterator'ları birleştirir, filtreler ve dönüştürür. Bellek verimli işlemler sağlar ve performansı artırır.

### Itertools Module İşlemleri
```python
import itertools

# Sonsuz iterator'lar
counter = itertools.count(1, 2)  # 1'den başla, 2'şer art
print(next(counter))  # 1
print(next(counter))  # 3

cycle = itertools.cycle(['A', 'B', 'C'])
print(next(cycle))  # A
print(next(cycle))  # B

repeat = itertools.repeat(10, 3)  # 10'u 3 kez tekrarla
print(list(repeat))  # [10, 10, 10]

# Kombinasyonlar ve permütasyonlar
letters = ['A', 'B', 'C']
combinations = list(itertools.combinations(letters, 2))
print(combinations)  # [('A', 'B'), ('A', 'C'), ('B', 'C')]

permutations = list(itertools.permutations(letters, 2))
print(permutations)  # [('A', 'B'), ('A', 'C'), ('B', 'A'), ('B', 'C'), ('C', 'A'), ('C', 'B')]

# Iterator'ları birleştir
chain = itertools.chain([1, 2], [3, 4], [5, 6])
print(list(chain))  # [1, 2, 3, 4, 5, 6]

# Grup yapma
grouped = itertools.groupby([1, 1, 2, 2, 3, 3])
for key, group in grouped:
    print(f"{key}: {list(group)}")
```

## 143. Functools Module

**Ne İşe Yarar:** Fonksiyonlar üzerinde işlem yapma yöntemlerini öğretir. Decorator'lar, partial fonksiyonlar ve cache işlemlerini kapsar.

**Ne Yapar:** Fonksiyonları değiştirir, optimize eder ve yeni fonksiyonlar oluşturur. Kod tekrarını azaltır ve performansı artırır.

### Functools Module İşlemleri
```python
from functools import partial, reduce, lru_cache, wraps

# Partial fonksiyon - parametreleri önceden doldur
def greet(name, greeting="Merhaba"):
    return f"{greeting}, {name}!"

say_hello = partial(greet, greeting="Selam")
print(say_hello("Ahmet"))  # Selam, Ahmet!

# Reduce - liste elemanlarını birleştir
numbers = [1, 2, 3, 4, 5]
sum_result = reduce(lambda x, y: x + y, numbers)
print(sum_result)  # 15

# LRU Cache - sonuçları önbellekle
@lru_cache(maxsize=128)
def fibonacci(n):
    if n < 2:
        return n
    return fibonacci(n-1) + fibonacci(n-2)

print(fibonacci(10))  # 55 (önbellekten gelir)

# Wraps - decorator metadata'sını koru
def my_decorator(func):
    @wraps(func)
    def wrapper(*args, **kwargs):
        print(f"Fonksiyon çağrılıyor: {func.__name__}")
        return func(*args, **kwargs)
    return wrapper

@my_decorator
def test_function():
    """Test fonksiyonu"""
    pass

print(test_function.__name__)  # test_function (wraps olmadan wrapper olurdu)
```

## 144. Pathlib

**Ne İşe Yarar:** Modern dosya yolu işlemlerini yapma yöntemlerini öğretir. Dosya ve dizin işlemlerini nesne yönelimli yaklaşımla kapsar.

**Ne Yapar:** Dosya yollarını nesne olarak yönetir, platform bağımsız işlemler sağlar ve dosya işlemlerini kolaylaştırır.

### Pathlib İşlemleri
```python
from pathlib import Path

# Path objesi oluştur
current_dir = Path.cwd()
print(f"Mevcut dizin: {current_dir}")

# Dosya yolu oluştur
file_path = Path("dosyalar") / "test.txt"
print(f"Dosya yolu: {file_path}")

# Dosya işlemleri
if file_path.exists():
    print(f"Dosya boyutu: {file_path.stat().st_size} bytes")
    print(f"Son değişiklik: {file_path.stat().st_mtime}")

# Dizin oluştur
new_dir = Path("yeni_klasor")
new_dir.mkdir(exist_ok=True)

# Dosya oluştur ve yaz
file_path = new_dir / "test.txt"
file_path.write_text("Merhaba Dünya!")

# Dosya oku
content = file_path.read_text()
print(content)  # Merhaba Dünya!

# Dizin içeriğini listele
for item in current_dir.iterdir():
    if item.is_file():
        print(f"Dosya: {item.name}")
    elif item.is_dir():
        print(f"Dizin: {item.name}")

# Pattern ile dosya ara
python_files = list(current_dir.glob("*.py"))
print(f"Python dosyaları: {[f.name for f in python_files]}")
```

## 145. Subprocess Module

**Ne İşe Yarar:** Sistem komutlarını çalıştırma ve alt süreçleri yönetme yöntemlerini öğretir. Shell komutları ve harici programları çalıştırmayı kapsar.

**Ne Yapar:** Sistem komutlarını Python'dan çalıştırır, komut çıktılarını yakalar ve alt süreçleri kontrol eder.

### Subprocess Module İşlemleri
```python
import subprocess
import sys

# Basit komut çalıştırma
result = subprocess.run(['ls', '-la'], capture_output=True, text=True)
print(f"Çıktı: {result.stdout}")
print(f"Hata: {result.stderr}")
print(f"Kod: {result.returncode}")

# Shell komutu çalıştırma
result = subprocess.run('echo "Merhaba Dünya"', shell=True, capture_output=True, text=True)
print(result.stdout)  # Merhaba Dünya

# Komut çıktısını yakala
try:
    result = subprocess.run(['python', '--version'], 
                          capture_output=True, text=True, check=True)
    print(f"Python versiyonu: {result.stdout.strip()}")
except subprocess.CalledProcessError as e:
    print(f"Hata: {e}")

# Popen ile sürekli çıktı
process = subprocess.Popen(['ping', '-c', '3', 'google.com'], 
                          stdout=subprocess.PIPE, text=True)
for line in process.stdout:
    print(line.strip())

# Komut zinciri
cmd1 = subprocess.run(['echo', 'hello world'], capture_output=True, text=True)
cmd2 = subprocess.run(['grep', 'hello'], input=cmd1.stdout, capture_output=True, text=True)
print(cmd2.stdout)  # hello world
```

## 146. Pickle/Serialization

**Ne İşe Yarar:** Python objelerini serileştirme ve deserileştirme yöntemlerini öğretir. Objeleri dosyaya kaydetme ve geri yükleme işlemlerini kapsar.

**Ne Yapar:** Python objelerini binary format'a çevirir, dosyaya kaydeder ve gerektiğinde geri yükler. Veri kalıcılığı sağlar.

### Pickle/Serialization İşlemleri
```python
import pickle

# Basit obje serileştirme
data = {
    'name': 'Ahmet',
    'age': 25,
    'cities': ['İstanbul', 'Ankara']
}

# Objeyi dosyaya kaydet
with open('data.pkl', 'wb') as f:
    pickle.dump(data, f)

# Objeyi dosyadan yükle
with open('data.pkl', 'rb') as f:
    loaded_data = pickle.load(f)
print(loaded_data)  # {'name': 'Ahmet', 'age': 25, 'cities': ['İstanbul', 'Ankara']}

# String olarak serileştir
serialized = pickle.dumps(data)
print(f"Serileştirilmiş boyut: {len(serialized)} bytes")

# String'den deserileştir
deserialized = pickle.loads(serialized)
print(deserialized)

# Özel sınıf serileştirme
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age
    
    def __repr__(self):
        return f"Person({self.name}, {self.age})"

person = Person("Mehmet", 30)

# Sınıfı serileştir
with open('person.pkl', 'wb') as f:
    pickle.dump(person, f)

# Sınıfı yükle
with open('person.pkl', 'rb') as f:
    loaded_person = pickle.load(f)
print(loaded_person)  # Person(Mehmet, 30)
```

## 147. Virtual Environments

**Ne İşe Yarar:** Python sanal ortamları oluşturma ve yönetme yöntemlerini öğretir. Proje bağımlılıklarını izole etmeyi kapsar.

**Ne Yapar:** Projeler için izole Python ortamları oluşturur, paket çakışmalarını önler ve proje bağımlılıklarını yönetir.

### Virtual Environments İşlemleri
```python
import sys
import subprocess
import venv
from pathlib import Path

# Sanal ortam oluşturma (komut satırı)
# python -m venv myenv

# Sanal ortam oluşturma (programatik)
venv_path = Path("myenv")
venv.create(venv_path, with_pip=True)

# Sanal ortam aktivasyonu (Windows)
# myenv\Scripts\activate

# Sanal ortam aktivasyonu (Unix/Mac)
# source myenv/bin/activate

# Sanal ortamda Python yolu
venv_python = venv_path / "bin" / "python"  # Unix/Mac
# venv_python = venv_path / "Scripts" / "python.exe"  # Windows

# Sanal ortamda paket yükleme
def install_package(package_name):
    subprocess.run([str(venv_python), "-m", "pip", "install", package_name])

# Paket listesi oluştur
def create_requirements():
    result = subprocess.run([str(venv_python), "-m", "pip", "freeze"], 
                          capture_output=True, text=True)
    with open("requirements.txt", "w") as f:
        f.write(result.stdout)

# Paketleri requirements.txt'den yükle
def install_from_requirements():
    subprocess.run([str(venv_python), "-m", "pip", "install", "-r", "requirements.txt"])

# Sanal ortam bilgileri
print(f"Python yolu: {sys.executable}")
print(f"Python versiyonu: {sys.version}")
print(f"Paket yolu: {sys.path}")

# Sanal ortam kontrolü
def is_venv():
    return hasattr(sys, 'real_prefix') or (hasattr(sys, 'base_prefix') and sys.base_prefix != sys.prefix)

print(f"Sanal ortamda mı: {is_venv()}")

---

## Ek Kaynaklar

### Python Standartları ve Versiyonları
- **Python 2.7**: Eski versiyon (2020'de sonlandı)
- **Python 3.8**: Pattern matching, assignment expressions
- **Python 3.9**: Dictionary union operators, type hints improvements
- **Python 3.10**: Structural pattern matching, better error messages
- **Python 3.11**: Performance improvements, better error traces
- **Python 3.12**: Sub-interpreter support, f-string improvements
- **Python 3.13**: Performance optimizations, new features

### Python Framework'leri ve Kütüphaneleri
- **Web Development**: Django, Flask, FastAPI, Pyramid, Bottle
- **Data Science**: Pandas, NumPy, SciPy, Matplotlib, Seaborn
- **Machine Learning**: Scikit-learn, TensorFlow, PyTorch, Keras
- **Deep Learning**: TensorFlow, PyTorch, JAX, MXNet
- **GUI Development**: Tkinter, PyQt5, Kivy, wxPython, PySide
- **Game Development**: Pygame, Arcade, Panda3D, Kivy
- **Network Programming**: Requests, urllib, asyncio, aiohttp
- **Database**: SQLAlchemy, Django ORM, Peewee, Tortoise ORM
- **Testing**: unittest, pytest, nose, doctest, coverage
- **Documentation**: Sphinx, pdoc, mkdocs, readthedocs
- **Package Management**: pip, conda, poetry, pipenv, pip-tools
- **Code Quality**: flake8, black, isort, mypy, pylint

### Veri Bilimi ve Analiz Araçları
- **Jupyter Notebook**: Interactive computing
- **Google Colab**: Cloud-based notebooks
- **Anaconda**: Data science platform
- **Spyder**: Scientific Python IDE
- **VS Code**: Modern code editor with Python support
- **PyCharm**: Professional Python IDE
- **RStudio**: R and Python integration
- **Zeppelin**: Multi-language notebook
- **Databricks**: Cloud data platform
- **Kaggle**: Data science competitions

### Web Framework'leri Detayları
- **Django**: Full-stack web framework
- **Flask**: Micro web framework
- **FastAPI**: Modern API framework
- **Pyramid**: Flexible web framework
- **Bottle**: Minimal web framework
- **Tornado**: Asynchronous web framework
- **Sanic**: Async web framework
- **Starlette**: ASGI framework
- **aiohttp**: Async HTTP client/server
- **Dash**: Data visualization web apps

### Veri Tabanı ve ORM'ler
- **SQLAlchemy**: SQL toolkit and ORM
- **Django ORM**: Django's object-relational mapper
- **Peewee**: Lightweight ORM
- **Tortoise ORM**: Async ORM
- **SQLModel**: SQL databases in Python
- **Pony ORM**: Advanced ORM
- **MongoDB**: Document database with PyMongo
- **Redis**: In-memory data store
- **PostgreSQL**: Advanced open source database
- **MySQL**: Popular open source database
- **SQLite**: Lightweight database
- **Cassandra**: Distributed NoSQL database

### DevOps ve Deployment Araçları
- **Docker**: Containerization
- **Kubernetes**: Container orchestration
- **GitLab CI/CD**: Continuous integration
- **GitHub Actions**: Automated workflows
- **Jenkins**: Automation server
- **Ansible**: Configuration management
- **Terraform**: Infrastructure as code
- **AWS Lambda**: Serverless computing
- **Google Cloud Functions**: Serverless
- **Azure Functions**: Microsoft serverless
- **Heroku**: Platform as a service
- **DigitalOcean**: Cloud platform
- **Vercel**: Frontend deployment
- **Netlify**: Static site hosting

### Güvenlik ve Penetration Testing
- **OWASP ZAP**: Security testing
- **Burp Suite**: Web application security
- **Metasploit**: Penetration testing
- **Nmap**: Network scanning
- **Scapy**: Packet manipulation
- **Cryptography**: Encryption library
- **PyJWT**: JSON Web Tokens
- **Passlib**: Password hashing
- **Bandit**: Security linter
- **Safety**: Dependency vulnerability checker

### Öğrenme Kaynakları
- **Official Python Documentation**: python.org
- **Real Python**: Tutorials and articles
- **Python.org Tutorial**: Official tutorial
- **W3Schools Python**: Online tutorials
- **GeeksforGeeks**: Programming tutorials
- **LeetCode**: Coding problems
- **HackerRank**: Programming challenges
- **Codewars**: Coding katas
- **Exercism**: Programming exercises
- **Python Challenge**: Programming puzzles
- **Automate the Boring Stuff**: Practical Python
- **Fluent Python**: Advanced concepts
- **Effective Python**: Best practices
- **Python Cookbook**: Recipes and solutions

### Sertifikalar
- **PCAP (Python Institute)**: Certified Associate
- **PCPP (Python Institute)**: Certified Professional
- **PCEP (Python Institute)**: Certified Entry-Level
- **Microsoft Certified: Azure Developer**
- **AWS Certified Developer**
- **Google Cloud Professional Developer**
- **Django Certified Developer**
- **Flask Certified Developer**
- **DataCamp Python Certificates**
- **Coursera Python Specializations**

### Modern Python Araçları
- **Poetry**: Dependency management
- **Pipenv**: Virtual environment management
- **Black**: Code formatter
- **isort**: Import sorter
- **flake8**: Linter
- **mypy**: Type checker
- **pre-commit**: Git hooks
- **tox**: Testing automation
- **coverage**: Code coverage
- **pytest**: Testing framework
- **hypothesis**: Property-based testing
- **factory-boy**: Test data generation
- **faker**: Fake data generation

### Python Toplulukları ve Konferanslar
- **PyCon**: Annual Python conference
- **EuroPython**: European Python conference
- **DjangoCon**: Django conference
- **PyData**: Data science conference
- **Python Discord**: Community server
- **Reddit r/Python**: Python subreddit
- **Stack Overflow**: Q&A platform
- **GitHub**: Open source projects
- **PyPI**: Package index
- **Python Package Index**: Official repository

### Python Best Practices
- **PEP 8**: Style guide
- **PEP 20**: Zen of Python
- **PEP 257**: Docstring conventions
- **PEP 484**: Type hints
- **PEP 585**: Type hints in standard collections
- **PEP 604**: Union types
- **PEP 695**: Type parameter syntax
- **Clean Code**: Robert C. Martin
- **Refactoring**: Martin Fowler
- **Design Patterns**: Gang of Four

### Python Performance ve Optimizasyon
- **cProfile**: Performance profiler
- **line_profiler**: Line-by-line profiling
- **memory_profiler**: Memory usage profiling
- **py-spy**: Sampling profiler
- **Cython**: C extensions for Python
- **Numba**: JIT compiler
- **PyPy**: Alternative Python implementation
- **mypyc**: Static type compiler
- **Pyston**: Performance-optimized Python
- **GraalPython**: GraalVM Python implementation

---

## Sonuç

Bu kapsamlı Python cheatsheet, Python'un tüm temel ve ileri seviye konularını ele almaktadır. Her konunun Türkçe açıklaması ile birlikte pratik örnekler verilmiştir. Bu rehberi referans olarak kullanarak Python kodlarınızı daha etkili bir şekilde yazabilir ve Python programlama konusunda uzmanlaşabilirsiniz.

**Not:** Bu rehber Python 3.x standartlarını takip etmekle birlikte, bazı özellikler belirli Python versiyonlarına özgü olabilir. Kullandığınız Python versiyonunun dokümantasyonunu kontrol etmeyi unutmayın.

---

**Python Cheatsheet** - Python'un tüm özelliklerini kapsayan eksiksiz referans rehberi! 🐍🚀 