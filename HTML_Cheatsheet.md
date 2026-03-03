# HTML Cheatsheet - Kapsamlı HTML Referans Rehberi

Bu rehber HTML5'in temel yapısından formlara, medyaya, API'lere kadar tüm önemli konuları Türkçe açıklamalar ve pratik örneklerle kapsar. Web sayfası oluştururken hızlı referans olarak kullanabilirsiniz.

### Bu Cheatsheet Ne İşe Yarar?
- HTML belge yapısı ve temel etiketler
- Metin biçimlendirme, stiller, renkler ve CSS kullanımı
- Bağlantılar, görseller, tablolar ve listeler
- Formlar, input türleri ve form nitelikleri (form attribute dahil)
- Canvas, SVG, video, audio ve YouTube gömme
- Web API'leri: Geolocation, Drag & Drop, Web Storage, Workers, SSE
- Karakter setleri, entity'ler, erişilebilirlik ve etiket referansı

## İçindekiler

1. [HTML'e Giriş ve Temel Yapı](#1-htmle-giriş-ve-temel-yapı)
2. [HTML Öğeleri ve Nitelikler](#2-html-öğeleri-ve-nitelikler)
3. [Başlıklar, Paragraflar ve Metin Biçimlendirme](#3-başlıklar-paragraflar-ve-metin-biçimlendirme)
4. [Stiller, Renkler ve CSS](#4-stiller-renkler-ve-css)
5. [Bağlantılar, Görseller ve Favicon](#5-bağlantılar-görseller-ve-favicon)
6. [Sayfa Başlığı, Head ve Layout](#6-sayfa-başlığı-head-ve-layout)
7. [Tablolar ve Listeler](#7-tablolar-ve-listeler)
8. [Blok / Inline, Div, Class ve Id](#8-blok--inline-div-class-ve-id)
9. [Butonlar, Iframe ve JavaScript](#9-butonlar-iframe-ve-javascript)
10. [Dosya Yolları](#10-dosya-yolları)
11. [Responsive ve Semantik HTML](#11-responsive-ve-semantik-html)
12. [Entity'ler, Semboller, Emoji ve Karakter Setleri](#12-entityler-semboller-emoji-ve-karakter-setleri)
13. [URL Encode ve HTML vs XHTML](#13-url-encode-ve-html-vs-xhtml)
14. [HTML Formlar](#14-html-formlar)
15. [Form Nitelikleri ve Form Öğeleri](#15-form-nitelikleri-ve-form-öğeleri)
16. [Input Türleri ve Input Nitelikleri](#16-input-türleri-ve-input-nitelikleri)
17. [Input Form Nitelikleri (form Attribute)](#17-input-form-nitelikleri-form-attribute)
18. [Canvas ve SVG](#18-canvas-ve-svg)
19. [Medya: Video, Audio, Plug-in ve YouTube](#19-medya-video-audio-plug-in-ve-youtube)
20. [Web API'leri](#20-web-apileri)
21. [Erişilebilirlik](#21-erişilebilirlik)
22. [Etiket Listesi ve Global Nitelikler](#22-etiket-listesi-ve-global-nitelikler)
23. [Olaylar (Events) ve Tarayıcı Desteği](#23-olaylar-events-ve-tarayıcı-desteği)

---

## 1. HTML'e Giriş ve Temel Yapı

**Ne İşe Yarar:** Bir HTML belgesinin zorunlu iskeletini ve DOCTYPE kavramını anlamanızı sağlar.  
**Ne Yapar:** Tarayıcıya belgenin HTML5 olduğunu söyler; `<html>`, `<head>` ve `<body>` ile içeriği yapılandırır.

### DOCTYPE ve Temel İskelet
```html
<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Sayfa Başlığı</title>
</head>
<body>
  <!-- İçerik buraya -->
</body>
</html>
```

| Bölüm | Açıklama |
|-------|----------|
| `<!DOCTYPE html>` | Belgenin HTML5 olduğunu bildirir; "quirks mode"u önler. |
| `<html lang="tr">` | Tüm sayfanın kök öğesi; `lang` erişilebilirlik ve SEO için önemlidir. |
| `<head>` | Sayfa hakkında bilgi (meta, başlık, stil/script referansları). |
| `<body>` | Sayfada görünen tüm içerik. |

### HTML Basic Örnek
```html
<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8">
  <title>İlk Sayfam</title>
</head>
<body>
  <h1>Merhaba Dünya</h1>
  <p>Bu bir paragraf.</p>
</body>
</html>
```

---

## 2. HTML Öğeleri ve Nitelikler

**Ne İşe Yarar:** Etiket (tag), öğe (element) ve nitelik (attribute) kavramlarını netleştirir.  
**Ne Yapar:** Öğelerin açılış/kapanış kullanımını ve niteliklerin nasıl eklendiğini gösterir.

### Öğe Yapısı
- **Etiket:** `<p>`, `</p>` gibi işaretleyiciler.
- **Öğe:** Açılış etiketinden kapanış etiketine kadar tüm blok (içerik dahil).
- **Nitelik:** Etiketin içinde, `isim="değer"` formatında ek bilgi.

### Nitelik Örneği
```html
<!-- class ve id nitelikleri -->
<p class="vurgu" id="ilk-paragraf">Bu paragrafa stil veya script ile erişilir.</p>

<!-- href ve target (bağlantı) -->
<a href="https://example.com" target="_blank">Dış bağlantı</a>

<!-- src ve alt (görsel) -->
<img src="resim.jpg" alt="Açıklama metni">
```

**Not:** Nitelik değerleri çift tırnak (`"`) veya tek tırnak (`'`) içinde yazılır. HTML5'te tırnaksız da kabul edilir ancak tırnak kullanmak önerilir.

---

## 3. Başlıklar, Paragraflar ve Metin Biçimlendirme

**Ne İşe Yarar:** Sayfadaki metin hiyerarşisini ve vurgulama (kalın, italik, alıntı) kurallarını verir.  
**Ne Yapar:** `<h1>`–`<h6>`, `<p>`, `<strong>`, `<em>`, `<blockquote>` ve yorum satırlarını kullanmayı gösterir.

### Başlıklar (Headings)
```html
<h1>En üst düzey başlık (sayfada genelde bir tane)</h1>
<h2>Alt bölüm</h2>
<h3>Alt alt bölüm</h3>
<h4>h4</h4>
<h5>h5</h5>
<h6>h6</h6>
```

### Paragraflar ve Satır Sonu
```html
<p>Bu bir paragraf. Uzun metinler paragraf etiketleri içinde yazılır.</p>
<p>İkinci paragraf.</p>
<p>Satır sonu için<br>br etiketi kullanılır.</p>
```

### Metin Biçimlendirme (Formatting)
```html
<p><b>Kalın (bold)</b> ve <strong>önemli metin (strong)</strong>.</p>
<p><i>İtalik (italic)</i> ve <em>vurgu (em)</em>.</p>
<p><mark>İşaretli</mark>, <small>küçük</small>, <del>silinmiş</del>, <ins>eklenmiş</ins>.</p>
<p>Alt simge: H<sub>2</sub>O. Üst simge: x<sup>2</sup>.</p>
```

### Alıntılar (Quotations)
```html
<blockquote cite="https://example.com">
  Uzun alıntılar blockquote içinde gösterilir.
</blockquote>
<p>Kısa alıntı: <q>tırnak içi</q>.</p>
<p><abbr title="HyperText Markup Language">HTML</abbr> kısaltması.</p>
<address>İletişim adresi bu etiketle yazılır.</address>
```

### Yorumlar (Comments)
```html
<!-- Bu satır tarayıcıda görünmez, sadece kaynak kodda görülür -->
<!--
  Çok satırlı
  yorum
-->
```

---

## 4. Stiller, Renkler ve CSS

**Ne İşe Yarar:** Sayfaya görsel stil vermek için inline stil, renk ve CSS kullanımını açıklar.  
**Ne Yapar:** `style` niteliği ve renk değerleri (isim, HEX, RGB, HSL) ile temel CSS kurallarını gösterir.

### Inline Stil (style Attribute)
```html
<p style="color: blue; font-size: 18px;">Mavi ve büyük metin.</p>
<div style="background-color: #f0f0f0; padding: 20px;">Arka plan ve padding.</div>
```

### Renk Verilmesi
```html
<!-- Renk adı -->
<p style="color: tomato;">tomato</p>

<!-- HEX -->
<p style="color: #ff6347;">#ff6347</p>

<!-- RGB / RGBA -->
<p style="color: rgb(255, 99, 71);">rgb</p>
<p style="color: rgba(255, 99, 71, 0.7);">rgba (şeffaflık)</p>

<!-- HSL / HSLA -->
<p style="color: hsl(9, 100%, 64%);">hsl</p>
```

### CSS Dosyası Bağlama (Head İçinde)
```html
<head>
  <link rel="stylesheet" href="stil.css">
  <!-- veya sayfa içi stil -->
  <style>
    body { font-family: sans-serif; }
    .kutu { border: 1px solid #ccc; }
  </style>
</head>
```

---

## 5. Bağlantılar, Görseller ve Favicon

**Ne İşe Yarar:** Tıklanabilir linkler, resimler ve sekme ikonu (favicon) eklemeyi gösterir.  
**Ne Yapar:** `<a>`, `<img>` ve `<link rel="icon">` kullanımını açıklar.

### Bağlantılar (Links)
```html
<!-- Dış link, yeni sekmede açılır -->
<a href="https://example.com" target="_blank" rel="noopener">Example</a>

<!-- Sayfa içi çapa -->
<a href="#bolum1">Bölüm 1'e git</a>
<section id="bolum1">...</section>

<!-- E-posta ve telefon -->
<a href="mailto:info@example.com">E-posta</a>
<a href="tel:+901234567890">Telefon</a>

<!-- title ile ipucu -->
<a href="/doc.pdf" title="PDF indir">İndir</a>
```

### Görseller (Images)
```html
<img src="resim.jpg" alt="Görselin açıklaması" width="400" height="300">

<!-- responsive: tarayıcı genişliğine göre ölçeklenir -->
<img src="resim.jpg" alt="Açıklama" style="max-width: 100%; height: auto;">
```

**Ne İşe Yarar (alt):** Erişilebilirlik ve SEO için her görselde anlamlı `alt` metni kullanın.

### Favicon
```html
<head>
  <link rel="icon" type="image/x-icon" href="favicon.ico">
  <!-- PNG için -->
  <link rel="icon" type="image/png" sizes="32x32" href="favicon-32x32.png">
</head>
```

---

## 6. Sayfa Başlığı, Head ve Layout

**Ne İşe Yarar:** Sekme başlığı, meta bilgileri ve sayfa düzeni (header, main, footer) yapısını verir.  
**Ne Yapar:** `<title>`, `<meta>`, `<head>` içeriği ve semantik layout etiketlerini kullanmayı gösterir.

### Page Title ve Temel Meta
```html
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="Sayfa kısa açıklaması (SEO)">
  <meta name="keywords" content="anahtar, kelimeler">
  <title>Sayfa Başlığı - Sekmede Görünen</title>
</head>
```

### Basit Layout (Semantik)
```html
<body>
  <header>
    <nav>
      <a href="/">Ana Sayfa</a>
      <a href="/hakkimda">Hakkımda</a>
    </nav>
  </header>
  <main>
    <article>
      <h1>Başlık</h1>
      <p>İçerik...</p>
    </article>
  </main>
  <footer>
    <p>© 2025 Site Adı</p>
  </footer>
</body>
```

---

## 7. Tablolar ve Listeler

**Ne İşe Yarar:** Veriyi satır/sütun halinde göstermek ve maddeli/sıralı listeler oluşturmak için kullanılır.  
**Ne Yapar:** `<table>`, `<tr>`, `<td>`, `<th>`, `<ul>`, `<ol>`, `<li>` ve `<dl>` kullanımını gösterir.

### Tablolar
```html
<table>
  <thead>
    <tr>
      <th>Ad</th>
      <th>Soyad</th>
      <th>Yaş</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Ali</td>
      <td>Yılmaz</td>
      <td>25</td>
    </tr>
    <tr>
      <td>Ayşe</td>
      <td>Kaya</td>
      <td>30</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td colspan="2">Toplam</td>
      <td>2 kişi</td>
    </tr>
  </tfoot>
</table>
```

### Listeler
```html
<!-- Sırasız liste -->
<ul>
  <li>Madde 1</li>
  <li>Madde 2</li>
</ul>

<!-- Sıralı liste (numaralı) -->
<ol>
  <li>İlk adım</li>
  <li>İkinci adım</li>
</ol>

<!-- Tanım listesi -->
<dl>
  <dt>HTML</dt>
  <dd>HyperText Markup Language</dd>
  <dt>CSS</dt>
  <dd>Cascading Style Sheets</dd>
</dl>
```

---

## 8. Blok / Inline, Div, Class ve Id

**Ne İşe Yarar:** Blok ve inline öğe farkını, gruplama için `<div>`/`<span>` ve seçici olarak `class`/`id` kullanımını açıklar.  
**Ne Yapar:** Yerleşim ve stiller için hangi etiketin ne zaman kullanılacağını netleştirir.

### Blok vs Inline
- **Blok:** Kendi satırını kaplar; altına başka içerik geçer. Örnek: `<div>`, `<p>`, `<h1>`, `<section>`.
- **Inline:** Satır içinde kalır. Örnek: `<span>`, `<a>`, `<strong>`, `<img>`.

### Div ve Span
```html
<div class="kutu">
  Blok düzeyinde gruplama; sayfa bölümleri için.
</div>
<p>Bu cümlede <span class="vurgu">sadece bu kısım</span> vurgulanıyor.</p>
```

### Class ve Id
```html
<div id="benzersiz-bolum" class="kutu kenar">
  id: Sayfada tek olmalı (çapa ve JS için).
  class: Birden fazla öğede aynı olabilir; stil ve JS seçicisi.
</div>
```

```css
/* CSS'te kullanım */
#benzersiz-bolum { margin-top: 20px; }
.kutu { padding: 10px; }
.kenar { border: 1px solid #ccc; }
```

---

## 9. Butonlar, Iframe ve JavaScript

**Ne İşe Yarar:** Tıklanabilir butonlar, başka sayfa/servis gömme ve sayfaya script eklemeyi gösterir.  
**Ne Yapar:** `<button>`, `<iframe>` ve `<script>` kullanımını açıklar.

### Butonlar
```html
<button type="button">Tıkla</button>
<button type="submit">Gönder</button>
<button type="reset">Sıfırla</button>

<!-- Görsel olarak buton gibi link -->
<a href="/devam" class="btn">Devam Et</a>
```

### Iframe
```html
<iframe src="https://example.com" title="Açıklama" width="600" height="400"></iframe>

<!-- YouTube gömme (videonun paylaş kodundan) -->
<iframe width="560" height="315" src="https://www.youtube.com/embed/VIDEO_ID" title="YouTube video" allowfullscreen></iframe>
```

### JavaScript Ekleme
```html
<!-- Sayfa sonunda, body kapanmadan önce -->
<script src="script.js"></script>

<!-- Satır içi -->
<script>
  document.querySelector('button').addEventListener('click', function() {
    alert('Tıklandı!');
  });
</script>
```

---

## 10. Dosya Yolları

**Ne İşe Yarar:** Resim, CSS, JS ve linklerde kullanılan göreli ve mutlak yolları açıklar.  
**Ne Yapar:** Aynı klasör, alt klasör ve üst klasör referanslarını gösterir.

| Yol | Örnek | Açıklama |
|-----|--------|----------|
| Aynı klasör | `resim.jpg` veya `./resim.jpg` | HTML dosyasıyla aynı dizin. |
| Alt klasör | `img/resim.jpg` veya `css/stil.css` | Belirtilen alt klasör. |
| Üst klasör | `../resim.jpg` | Bir üst dizin. |
| İki üst | `../../assets/logo.png` | İki üst dizin, sonra `assets`. |
| Mutlak (site kökü) | `/img/resim.jpg` | Sunucu kökünden (genelde site kökü). |
| Mutlak URL | `https://example.com/dosya.pdf` | Tam adres. |

```html
<!-- Örnek yapı: proje/index.html, proje/css/stil.css, proje/img/logo.png -->
<link rel="stylesheet" href="css/stil.css">
<img src="img/logo.png" alt="Logo">
<a href="../ust-klasor/sayfa.html">Üst klasördeki sayfa</a>
```

---

## 11. Responsive ve Semantik HTML

**Ne İşe Yarar:** Farklı ekran boyutlarına uyum ve anlamlı (semantik) etiket kullanımını destekler.  
**Ne Yapar:** Viewport meta etiketi, semantik etiketler ve basit responsive örnekleri verir.

### Viewport (Mobil Uyum)
```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```
- `width=device-width`: Genişliği cihaz genişliğine eşitler.  
- `initial-scale=1.0`: Yakınlaştırma oranı.

### Semantik Öğeler
```html
<header>Üst bilgi, logo, menü</header>
<nav>Navigasyon linkleri</nav>
<main>Ana içerik (sayfada bir tane)</main>
<article>Bağımsız içerik (yazı, kart)</article>
<section>Konuya göre bölüm</section>
<aside>Yan içerik, sidebar</aside>
<footer>Alt bilgi, telif</footer>
<figure>
  <img src="grafik.png" alt="Grafik">
  <figcaption>Grafik açıklaması</figcaption>
</figure>
```

### Bilgisayar Kodu (Computercode)
```html
<code>değişkenAdi</code>
<pre><code>function merhaba() {
  console.log("Merhaba");
}</code></pre>
<kbd>Ctrl</kbd> + <kbd>C</kbd>
<samp>Örnek çıktı</samp>
<var>x</var>
```

### Style Guide Özeti
- Tutarlı girintileme (2 veya 4 boşluk).
- Küçük harf etiket ve nitelik: `<div class="kutu">`.
- Nitelik değerlerinde tırnak kullanın.
- Kapanış etiketlerini atlamayın (HTML5’te bazıları opsiyonel olsa da yazmak iyidir).

---

## 12. Entity'ler, Semboller, Emoji ve Karakter Setleri

**Ne İşe Yarar:** Özel karakterleri güvenli yazmak, sembol ve emoji göstermek ve karakter kodlamasını ayarlamak için kullanılır.  
**Ne Yapar:** HTML entity, Unicode ve `charset` kullanımını gösterir.

### HTML Entity'ler
```html
&lt;    <!-- < -->
&gt;    <!-- > -->
&amp;   <!-- & -->
&quot;  <!-- " -->
&apos; <!-- ' -->
&nbsp; <!-- Bölünmeyen boşluk -->
&copy;  <!-- © -->
&reg;   <!-- ® -->
&euro;  <!-- € -->
```

### Semboller ve Emoji
```html
<!-- Unicode karakter (sayısal) -->
&#9733;  <!-- ★ -->
&#128512; <!-- 😀 -->

<!-- Doğrudan UTF-8 ile emoji -->
<p>Emoji: 🎉 ✅ 🔒</p>
```

### Charset (Karakter Seti)
```html
<head>
  <meta charset="UTF-8">
</head>
```
**Ne İşe Yarar:** UTF-8, Türkçe karakterler ve emojilerin doğru görünmesi için neredeyse her sayfada kullanılmalıdır.

---

## 13. URL Encode ve HTML vs XHTML

**Ne İşe Yarar:** URL’de özel karakterlerin kodlanması ve HTML ile XHTML farkını kavramanızı sağlar.  
**Ne Yapar:** Yüzde kodlama (percent-encoding) ve kısa karşılaştırma tablosu verir.

### URL Encode (Yüzde Kodlama)
URL’de boşluk, `&`, `=`, `?`, `#`, Türkçe karakterler vb. kodlanır:

| Karakter | Kodlanmış |
|----------|-----------|
| Boşluk | `%20` veya `+` |
| & | `%26` |
| = | `%3D` |
| ? | `%3F` |
| # | `%23` |
| ğ | `%C4%9F` (UTF-8) |

JavaScript: `encodeURIComponent("değer")`  
HTML linkte sorun çıkarsa query parametrelerini encode edin.

### HTML vs XHTML (Kısa)
| Özellik | HTML5 | XHTML |
|---------|--------|--------|
| Etiketler | Küçük/büyük harf serbest | Küçük harf zorunlu |
| Kapanış | Bazı etiketler opsiyonel | Tüm etiketler kapanmalı |
| Nitelikler | Tırnaksız değer mümkün | Tırnak zorunlu |
| MIME | `text/html` | `application/xhtml+xml` |

Pratikte HTML5 ve `text/html` kullanımı yaygındır; XHTML gerektiren özel senaryolar dışında HTML5 yeterlidir.

---

## 14. HTML Formlar

**Ne İşe Yarar:** Kullanıcıdan veri toplamak için form oluşturmayı ve sunucuya göndermeyi sağlar.  
**Ne Yapar:** `<form>`, `action`, `method` ve temel form öğelerini açıklar.

### Temel Form Yapısı
```html
<form action="/api/kayit" method="post">
  <label for="kullanici">Kullanıcı adı:</label>
  <input type="text" id="kullanici" name="kullanici" required>
  <br><br>
  <label for="sifre">Şifre:</label>
  <input type="password" id="sifre" name="sifre" required>
  <br><br>
  <button type="submit">Gönder</button>
  <button type="reset">Temizle</button>
</form>
```

| Nitelik | Açıklama |
|---------|----------|
| `action` | Formun gönderileceği URL. |
| `method` | `get` (varsayılan) veya `post`. GET parametreleri URL’de, POST gövdede gider. |

---

## 15. Form Nitelikleri ve Form Öğeleri

**Ne İşe Yarar:** Formun davranışını (autocomplete, novalidate vb.) ve farklı form öğelerini (label, input, select, textarea) tanıtır.  
**Ne Yapar:** Form nitelikleri ve her öğenin kullanımını örneklerle gösterir.

### Form Nitelikleri
```html
<form action="/gonder" method="post"
      autocomplete="on"
      novalidate
      target="_blank">
  <!-- autocomplete: tarayıcı otomatik doldurma -->
  <!-- novalidate: HTML5 validasyonunu kapatır -->
  <!-- target: yanıtın nerede açılacağı -->
</form>
```

### Form Öğeleri Özeti
```html
<form action="/arama" method="get">
  <label for="ad">Ad:</label>
  <input type="text" id="ad" name="ad">

  <label for="mesaj">Mesaj:</label>
  <textarea id="mesaj" name="mesaj" rows="4" cols="50"></textarea>

  <label for="ulke">Ülke:</label>
  <select id="ulke" name="ulke">
    <option value="tr">Türkiye</option>
    <option value="de">Almanya</option>
  </select>

  <label>
    <input type="checkbox" name="onay" value="1"> Koşulları kabul ediyorum
  </label>

  <p>Cinsiyet:</p>
  <label><input type="radio" name="cinsiyet" value="E"> Erkek</label>
  <label><input type="radio" name="cinsiyet" value="K"> Kadın</label>

  <button type="submit">Gönder</button>
</form>
```

---

## 16. Input Türleri ve Input Nitelikleri

**Ne İşe Yarar:** Metin, sayı, tarih, dosya yükleme vb. için `<input type="...">` ve yaygın input niteliklerini listeler.  
**Ne Yapar:** Her input türünün ne işe yaradığını ve hangi niteliklerle kullanıldığını gösterir.

### Input Türleri
```html
<input type="text" name="metin" placeholder="Metin">
<input type="password" name="sifre">
<input type="email" name="eposta">
<input type="number" name="sayi" min="0" max="100" step="1">
<input type="range" name="aralik" min="0" max="100" value="50">
<input type="date" name="tarih">
<input type="time" name="saat">
<input type="datetime-local" name="yerel_tarih_saat">
<input type="month" name="ay">
<input type="week" name="hafta">
<input type="color" name="renk" value="#ff0000">
<input type="file" name="dosya" accept=".pdf,.jpg">
<input type="checkbox" name="onay" value="1">
<input type="radio" name="secim" value="A">
<input type="hidden" name="token" value="abc123">
<input type="submit" value="Gönder">
<input type="reset" value="Sıfırla">
<input type="button" value="Tıkla">
<input type="search" name="arama" placeholder="Ara...">
<input type="url" name="url">
<input type="tel" name="telefon">
```

### Yaygın Input Nitelikleri
```html
<input type="text"
       name="alan"
       value="Varsayılan değer"
       placeholder="İpucu metni"
       required
       readonly
       disabled
       maxlength="100"
       minlength="2"
       pattern="[A-Za-z]+"
       autofocus
       size="30"
       autocomplete="off">
```

| Nitelik | Açıklama |
|---------|----------|
| `required` | Alan boş bırakılamaz. |
| `readonly` | Değer değiştirilemez, formla gönderilir. |
| `disabled` | Değer değiştirilemez ve formla gönderilmez. |
| `pattern` | Regex ile format kısıtı. |
| `autocomplete` | Tarayıcı otomatik doldurma. |

---

## 17. Input Form Nitelikleri (form Attribute)

**Ne İşe Yarar:** `<input>` (veya diğer form kontrolleri) fiziksel olarak `<form>` içinde olmasa bile hangi forma ait olduğunu belirtmenizi sağlar.  
**Ne Yapar:** `form` niteliğinin değerinin, hedef formun `id` değeriyle eşleşmesi gerektiğini gösterir; böylece form dışındaki alanlar da o formla birlikte gönderilir.

### form Niteliği Kullanımı
`form` niteliğinin değeri, bağlanmak istediğiniz `<form>` öğesinin `id` değeriyle **aynı** olmalıdır.

**Örnek:** Form dışında yer alan bir input alanının aynı formla gönderilmesi:

```html
<form action="/action_page.php" id="form1" method="post">
  <label for="fname">Ad:</label>
  <input type="text" id="fname" name="fname"><br><br>
  <input type="submit" value="Gönder">
</form>

<label for="lname">Soyad:</label>
<input type="text" id="lname" name="lname" form="form1">
```

Burada:
- `id="form1"` formu benzersiz tanımlar.
- Dışarıdaki `<input id="lname" name="lname" form="form1">` bu formla ilişkilendirilir.
- Gönder’e basıldığında hem `fname` hem `lname` aynı formla `/action_page.php` adresine gider.

### Birden Fazla Alan Form Dışında
```html
<form id="kayit_formu" action="/kayit" method="post">
  <input type="text" name="email" required>
  <button type="submit">Kayıt</button>
</form>

<input type="text" name="telefon" form="kayit_formu" placeholder="Telefon">
<input type="checkbox" name="kvkk" value="1" form="kayit_formu"> KVKK metnini okudum.
```
`telefon` ve `kvkk` alanları form etiketinin dışında olsa da `form="kayit_formu"` ile aynı formla gönderilir.

**Özet:** `form` niteliği, form kontrolünün hangi forma ait olduğunu `id` ile eşleştirerek belirler; layout veya erişilebilirlik gereği alanları form dışında tutarken kullanışlıdır.

---

## 18. Canvas ve SVG

**Ne İşe Yarar:** Sayfada çizim ve grafik oluşturmak için Canvas (piksel tabanlı) ve SVG (vektör tabanlı) kullanımını özetler.  
**Ne Yapar:** Temel `<canvas>` ve `<svg>` örnekleri verir; detaylı çizim JavaScript veya SVG elementleriyle yapılır.

### Canvas
```html
<canvas id="cizim" width="400" height="200"></canvas>
<script>
  const canvas = document.getElementById('cizim');
  const ctx = canvas.getContext('2d');
  ctx.fillStyle = 'blue';
  ctx.fillRect(50, 50, 100, 80);
  ctx.beginPath();
  ctx.arc(200, 100, 40, 0, Math.PI * 2);
  ctx.stroke();
</script>
```

### SVG (Basit Örnek)
```html
<svg width="200" height="200" xmlns="http://www.w3.org/2000/svg">
  <rect x="10" y="10" width="80" height="60" fill="green"/>
  <circle cx="120" cy="80" r="40" fill="red"/>
  <text x="100" y="180" text-anchor="middle">Metin</text>
</svg>
```

---

## 19. Medya: Video, Audio, Plug-in ve YouTube

**Ne İşe Yarar:** Sayfaya video, ses ve YouTube embed eklemeyi sağlar.  
**Ne Yapar:** `<video>`, `<audio>`, `<source>` ve `<iframe>` ile YouTube kullanımını gösterir.

### Video
```html
<video controls width="640" height="360" poster="onizleme.jpg">
  <source src="film.mp4" type="video/mp4">
  <source src="film.webm" type="video/webm">
  Tarayıcınız video etiketini desteklemiyor.
</video>
```
- `controls`: Oynat, duraklat, ses.  
- `autoplay`, `muted`, `loop` de kullanılabilir.

### Audio
```html
<audio controls>
  <source src="ses.mp3" type="audio/mpeg">
  <source src="ses.ogg" type="audio/ogg">
</audio>
```

### YouTube (iframe)
```html
<iframe width="560" height="315"
        src="https://www.youtube.com/embed/VIDEO_ID"
        title="Video başlığı"
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
        allowfullscreen>
</iframe>
```
`VIDEO_ID` yerine videonun paylaş linkindeki ID yazılır (örn. `dQw4w9WgXcQ`).

---

## 20. Web API'leri

**Ne İşe Yarar:** Tarayıcıda konum, sürükle-bırak, depolama, arka plan işi ve sunucu olayları gibi özellikleri kullanmayı özetler.  
**Ne Yapar:** Her API için kısa açıklama ve temel kod örneği verir; tam kullanım JavaScript ile yapılır.

### Geolocation
```javascript
if (navigator.geolocation) {
  navigator.geolocation.getCurrentPosition(
    (pos) => console.log(pos.coords.latitude, pos.coords.longitude),
    (err) => console.error(err)
  );
}
```

### Drag and Drop
HTML’de sürüklenebilir öğeye `draggable="true"`, bırakma alanına `ondragover` ve `ondrop` (veya JS ile `addEventListener`) eklenir; detaylar JavaScript API’sinde.

### Web Storage
```javascript
localStorage.setItem('anahtar', 'değer');
const deger = localStorage.getItem('anahtar');
sessionStorage.setItem('oturum', 'veri');
```

### Web Workers
Ana sayfadan ağır işi ayrı thread’de çalıştırma:
```javascript
const worker = new Worker('worker.js');
worker.postMessage({ data: 42 });
worker.onmessage = (e) => console.log(e.data);
```

### Server-Sent Events (SSE)
Sunucudan gelen olayları dinleme:
```javascript
const evtSource = new EventSource('/akış');
evtSource.onmessage = (e) => console.log(e.data);
```

---

## 21. Erişilebilirlik

**Ne İşe Yarar:** Klavye ve ekran okuyucu kullanıcıları için anlamlı yapı, etiketler ve nitelikler kullanmanızı sağlar.  
**Ne Yapar:** Yaygın erişilebilirlik uygulamalarını listeler.

- **Dil:** `<html lang="tr">`.
- **Başlık:** Her sayfada anlamlı `<title>`.
- **Görseller:** Anlamlı `alt` metni; dekoratif görsellerde `alt=""`.
- **Formlar:** Her input için `<label for="id">` veya sarılı label.
- **Başlık hiyerarşisi:** `<h1>`–`<h6>` sırasıyla, atlama yapmadan.
- **Kontrast:** Metin ve arka plan yeterli kontrast.
- **Klavye:** Tüm işlevler klavye ile erişilebilir; `tabindex` gerekirse anlamlı kullanın.
- **Semantik:** `<header>`, `<nav>`, `<main>`, `<article>`, `<footer>` gibi etiketler.
- **ARIA:** Gerekirse `aria-label`, `aria-describedby`, `role` ile ek bilgi verin.

---

## 22. Etiket Listesi ve Global Nitelikler

**Ne İşe Yarar:** Hızlı bakış için yaygın HTML etiketleri ve tüm öğelerde kullanılabilen global nitelikleri listeler.

### Yaygın Etiketler (Özet)
| Etiket | Açıklama |
|--------|----------|
| `<!DOCTYPE html>` | Belge tipi |
| `<html>`, `<head>`, `<body>` | Belge iskeleti |
| `<meta>`, `<title>`, `<link>` | Head bilgisi |
| `<h1>`–`<h6>`, `<p>`, `<br>` | Metin |
| `<a>`, `<img>` | Bağlantı, görsel |
| `<ul>`, `<ol>`, `<li>` | Listeler |
| `<table>`, `<tr>`, `<td>`, `<th>` | Tablo |
| `<div>`, `<span>` | Gruplama |
| `<form>`, `<input>`, `<button>`, `<select>`, `<textarea>`, `<label>` | Form |
| `<header>`, `<nav>`, `<main>`, `<article>`, `<section>`, `<aside>`, `<footer>` | Semantik |
| `<video>`, `<audio>`, `<canvas>`, `<svg>` | Medya ve grafik |
| `<script>`, `<style>` | Script ve stil |

### Global Nitelikler
Tüm HTML öğelerinde (bazı istisnalar dışında) kullanılabilir:

| Nitelik | Açıklama |
|---------|----------|
| `id` | Benzersiz tanımlayıcı |
| `class` | Stil/JS sınıfı |
| `style` | Satır içi CSS |
| `title` | İpucu metni |
| `lang` | Dil kodu |
| `dir` | `ltr` / `rtl` |
| `tabindex` | Sekme sırası |
| `contenteditable` | Düzenlenebilir içerik |
| `data-*` | Özel veri (data-id, data-action vb.) |
| `hidden` | Gizleme |
| `aria-*` | Erişilebilirlik (ARIA) |

---

## 23. Olaylar (Events) ve Tarayıcı Desteği

**Ne İşe Yarar:** Tarayıcı veya kullanıcı eylemine göre tetiklenen olayları ve tarayıcı uyumluluğunu özetler.  
**Ne Yapar:** Yaygın HTML olay nitelikleri ve destek notunu listeler.

### Yaygın Olay Nitelikleri (Inline)
```html
<button onclick="alert('Tıklandı')">Tıkla</button>
<input onfocus="this.style.background='yellow'" onblur="this.style.background=''">
<form onsubmit="return confirm('Gönderilsin mi?')">...</form>
<div onmouseover="this.style.color='red'" onmouseout="this.style.color=''">Üzerime gel</div>
```
Pratikte olayları JavaScript’te `addEventListener` ile bağlamak daha temiz ve bakımı kolaydır.

### Tarayıcı Desteği
HTML5 özellikleri modern tarayıcılarda (Chrome, Firefox, Safari, Edge) yaygın desteklenir. Eski tarayıcılar için:
- [Can I use](https://caniuse.com) ile özellik bazlı kontrol edin.
- Polyfill veya fallback içerik (örn. `<video>` içinde metin) kullanabilirsiniz.

---

*Bu cheatsheet, HTML5 standartları ve yaygın kullanıma göre hazırlanmıştır; güncel spesifikasyonlar için [MDN Web Docs](https://developer.mozilla.org/tr/docs/Web/HTML) veya [W3C](https://www.w3.org/TR/html52/) kaynaklarına bakınız.*
