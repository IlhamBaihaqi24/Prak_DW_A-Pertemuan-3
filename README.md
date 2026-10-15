# LAPORAN PRAKTIKUM DESAIN WEB A
## Pertemuan 3: Dasar-Dasar CSS (Inline dan External Stylesheet)

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)
![Status](https://img.shields.io/badge/Status-Selesai-success)

---

## 📋 Identitas Praktikan

| | |
|---|---|
| **Nama** | Ilham Baihaqi |
| **NIM** | 4525210029 |
| **Program Studi** | Teknik Informatika |
| **Fakultas** | Teknik |
| **Universitas** | Universitas Pancasila |
| **Mata Kuliah** | Praktikum Desain Web A |
| **Pertemuan** | 3 |

---
## 1. Tujuan Praktikum

1. Memahami fungsi CSS dalam mengatur tampilan halaman web.
2. Menerapkan CSS dengan metode **inline** (atribut `style`).
3. Menerapkan CSS dengan metode **external** (file `.css` terpisah yang dihubungkan dengan `<link>`).
4. Menggunakan berbagai format warna: nama warna, hexadecimal, `rgb()`, `rgba()`, dan `linear-gradient()`.
5. Mengatur tipografi: `font-family`, `font-size`, `font-weight`, `line-height`, dan `text-align`.
6. Memahami dasar *box model*: `width`, `padding`, `margin`, dan `border`.
7. Menggunakan selector elemen, selector class, dan pseudo-class `:hover`.
8. Menyusun halaman dengan elemen semantik: `<header>`, `<main>`, `<section>`, dan `<footer>`.

---

## 2. Dasar Teori

### 2.1 CSS
**CSS (Cascading Style Sheets)** adalah bahasa yang digunakan untuk mengatur tampilan elemen HTML seperti warna, ukuran, jarak, dan tata letak. HTML menentukan *struktur*, sedangkan CSS menentukan *tampilan*.

### 2.2 Tiga Cara Menerapkan CSS

| Metode | Cara Penulisan | Contoh |
|---|---|---|
| **Inline** | Atribut `style` langsung pada tag | `<p style="color: red;">` |
| **Internal** | Tag `<style>` di dalam `<head>` | `<style> p { color: red; } </style>` |
| **External** | File `.css` terpisah, dihubungkan dengan `<link>` | `<link rel="stylesheet" href="css/style.css">` |

Praktikum ini memakai metode **inline** (Contoh 1) dan **external** (Contoh 2).

### 2.3 Sintaks CSS
```css
selector {
  properti: nilai;
}
```
- **Selector**: menentukan elemen yang ditarget (`h1`, `.profesi`, `a:hover`).
- **Properti**: aspek tampilan yang diatur (`color`, `font-size`).
- **Nilai**: pengaturan untuk properti tersebut.

### 2.4 Jenis Selector yang Dipakai

| Selector | Contoh | Keterangan |
|---|---|---|
| Elemen | `body`, `header`, `h2`, `p` | Menarget semua elemen dengan nama tag tersebut |
| Class | `.foto-profil`, `.profesi` | Menarget elemen dengan atribut `class` tertentu |
| Turunan | `header h1`, `footer p` | Menarget elemen di dalam elemen lain |
| Pseudo-class | `a:hover` | Menarget elemen dalam kondisi tertentu (saat kursor di atas link) |

### 2.5 Format Warna

| Format | Contoh | Keterangan |
|---|---|---|
| Hexadecimal | `#003366` | Kode warna 6 digit heksadesimal (RGB) |
| RGB | `rgb(0, 102, 153)` | Nilai merah, hijau, biru (0-255) |
| RGBA | `rgba(0, 102, 153, 0.15)` | RGB ditambah transparansi (0 = transparan, 1 = solid) |
| Gradient | `linear-gradient(135deg, #180db4, #c471ed)` | Perpaduan dua warna atau lebih dengan arah tertentu |

### 2.6 Box Model
Setiap elemen HTML dianggap sebagai kotak yang terdiri dari lapisan berikut (dari dalam ke luar): **content → padding → border → margin**.

---

## 3. Alat dan Bahan

| Kategori | Keterangan |
|---|---|
| **Bahasa** | HTML5 dan CSS3 |
| **Text Editor** | Visual Studio Code _(sesuaikan)_ |
| **Browser** | Google Chrome / Microsoft Edge _(sesuaikan)_ |
| **Version Control** | Git dan GitHub |
| **Aset Gambar** | `saipul.jpg` (foto profil) |

---

## 4. Struktur Proyek

```
Pertemuan 3/
├── Contoh1/
│   ├── index.html        # Profil mahasiswa (inline CSS)
│   └── img/
│       └── saipul.jpg
├── Contoh2/
│   ├── index.html        # Curriculum Vitae (external CSS)
│   ├── CSS/
│   │   └── style.css
│   └── img/
│       └── saipul.jpg
└── README.md             # Laporan praktikum
```

---

## 5. Pembahasan dan Hasil

### 5.1 Contoh 1: Profil Mahasiswa dengan Inline CSS

**Deskripsi:** Halaman profil mahasiswa yang seluruh gayanya ditulis langsung pada atribut `style` di setiap elemen. Halaman memuat foto profil, data pribadi, deskripsi diri, dan daftar keahlian.

#### a. Pengaturan Halaman pada `<body>`
```html
<body style="
  font-family: Arial, sans-serif;
  background-color: #f4f4f4;
  margin: 30px;
  line-height: 1.6;
">
```
| Properti | Fungsi |
|---|---|
| `font-family` | Jenis huruf; `sans-serif` sebagai cadangan bila Arial tidak tersedia |
| `background-color` | Warna latar halaman (abu-abu muda) |
| `margin` | Jarak antara isi halaman dan tepi jendela browser |
| `line-height` | Jarak antar baris teks agar nyaman dibaca |

#### b. Judul Utama
```html
<h1 style="color: #003366; font-size: 32px; font-weight: bold; text-align: center;">
  Profil Mahasiswa
</h1>
```
Judul diberi warna biru tua (hex), ukuran 32px, tebal, dan rata tengah.

#### c. Foto Profil
```html
<div style="text-align: center;">
  <img src="img/saipul.jpg" alt="Foto Profil Mahasiswa" width="180"
       style="border-radius: 10px; border: 3px solid #003366;">
</div>
```
- `text-align: center` pada `<div>` memusatkan gambar.
- `border-radius` membuat sudut gambar membulat.
- `border` memberi bingkai 3px berwarna biru tua.

#### d. Subjudul dengan Format Warna `rgb()`
```html
<h2 style="color: rgb(0, 102, 153); font-size: 24px;">Data Pribadi</h2>
```

#### e. Paragraf dan List
```html
<p style="color: #444444; font-size: 17px; line-height: 1.8; text-align: justify;">
  ...
</p>

<ul style="color: #333333; font-size: 16px; line-height: 2;">
  <li>...</li>
</ul>
```
`text-align: justify` meratakan teks di kiri dan kanan, sedangkan `line-height: 2` memberi jarak antar item list yang lebih lega.

#### f. Transparansi dengan `rgba()`
```html
<p style="background-color: rgba(0, 102, 153, 0.15); padding: 15px; font-size: 16px;">
  Saya tertarik mempelajari pengembangan antarmuka website ...
</p>
```
Nilai alpha `0.15` membuat latar biru terlihat sangat tipis (transparan), dan `padding: 15px` memberi ruang di dalam kotak.

**Hasil tampilan:**

![Hasil Contoh 1](screenshots/contoh1.png)

---

### 5.2 Contoh 2: Curriculum Vitae dengan External CSS

**Deskripsi:** Halaman Curriculum Vitae yang struktur HTML-nya dipisah dari gayanya. Seluruh aturan tampilan berada di `CSS/style.css`, lalu dihubungkan ke HTML dengan tag `<link>`.

#### a. Menghubungkan HTML dengan CSS
```html
<head>
  <link rel="stylesheet" href="css/style.css">
</head>
```

#### b. Struktur HTML Semantik
```html
<header>   <!-- foto, nama, NPM, profesi -->
<main>
  <section> <!-- Profil -->
  <section> <!-- Pendidikan -->
  <section> <!-- Keahlian -->
  <section> <!-- Kontak -->
</main>
<footer>   <!-- hak cipta -->
```

| Tag | Fungsi |
|---|---|
| `<header>` | Bagian kepala: foto profil, nama, dan identitas singkat |
| `<main>` | Konten utama halaman |
| `<section>` | Pengelompokan isi berdasarkan topik |
| `<footer>` | Bagian kaki halaman |

#### c. Latar Halaman dengan Gradient
```css
body {
  font-family: Arial, Helvetica, sans-serif;
  font-size: 16px;
  line-height: 1.7;
  background: linear-gradient(135deg, #e788d0, #8ec5fc);
  color: #333333;
  margin: 0;
}
```
`margin: 0` menghilangkan jarak bawaan browser, dan `linear-gradient` membuat latar berpadu dua warna dengan sudut 135°.

#### d. Header dan Selector Class
```css
header {
  background: linear-gradient(135deg, #180db4, #c471ed);
  color: white;
  text-align: center;
  padding: 30px;
}

.profesi {
  font-size: 18px;
  font-weight: normal;
  color: rgba(245, 245, 245, 0.85);
}

.foto-profil {
  width: 250px;
  height: 250px;
  border-radius: 10%;
  border: 4px solid white;
}
```
`.profesi` dan `.foto-profil` adalah **selector class** yang dipanggil lewat atribut `class="..."` di HTML, sehingga gaya hanya berlaku pada elemen yang ditandai.

#### e. Konten Utama (Box Model)
```css
main {
  width: 80%;
  margin: 30px auto;
  padding: 30px;
}

section {
  margin-bottom: 30px;
}

h2 {
  font-size: 25px;
  border-bottom: 2px solid #ecdd53;
  padding-bottom: 5px;
}
```
`margin: 30px auto` membuat blok `main` berada di tengah halaman (nilai `auto` membagi sisa ruang kiri-kanan secara sama), sedangkan `border-bottom` menghasilkan garis pemisah di bawah tiap subjudul.

#### f. Hyperlink dan Efek `:hover`
```css
a {
  color: #006699;
  text-decoration: none;
}

a:hover {
  text-decoration: underline;
}
```
Link tampil tanpa garis bawah, dan garis bawah baru muncul saat kursor diarahkan ke link.

#### g. Footer
```css
footer {
  color: white;
  text-align: center;
  padding: 15px;
}

footer p {
  text-align: center;
  font-size: 14px;
}
```
Selector `footer p` hanya memengaruhi paragraf di dalam footer.

**Hasil tampilan:**

![Hasil Contoh 2](screenshots/contoh2.png)

---

## 6. Perbandingan Inline CSS dan External CSS

| Aspek | Inline CSS (Contoh 1) | External CSS (Contoh 2) |
|---|---|---|
| **Lokasi gaya** | Di dalam atribut `style` tiap elemen | Di file `.css` terpisah |
| **Pengulangan kode** | Tinggi (gaya yang sama ditulis berulang) | Rendah (satu aturan berlaku untuk banyak elemen) |
| **Kemudahan perawatan** | Sulit, harus mengubah elemen satu per satu | Mudah, cukup ubah satu tempat |
| **Keterbacaan HTML** | Kurang rapi karena bercampur dengan gaya | Lebih rapi, HTML fokus pada struktur |
| **Penggunaan ulang** | Tidak bisa dipakai di halaman lain | Satu file bisa dipakai banyak halaman |
| **Cocok untuk** | Perubahan cepat pada satu elemen | Proyek web yang sebenarnya |

**Contoh perbedaannya:** pada Contoh 1, gaya `color: rgb(0, 102, 153); font-size: 24px;` ditulis berulang pada tiga elemen `<h2>`. Pada Contoh 2, cukup satu aturan `h2 { ... }` untuk semua subjudul.

---

## 7. Rekap Properti CSS yang Digunakan

| Kategori | Properti |
|---|---|
| **Teks** | `color`, `font-family`, `font-size`, `font-weight`, `line-height`, `text-align`, `text-decoration` |
| **Latar** | `background-color`, `background` (gradient) |
| **Box model** | `width`, `height`, `margin`, `padding`, `padding-bottom`, `margin-bottom` |
| **Border** | `border`, `border-bottom`, `border-radius` |
| **Format warna** | nama warna, hex (`#003366`), `rgb()`, `rgba()`, `linear-gradient()` |
| **Selector** | elemen, class (`.`), turunan (`header h1`), pseudo-class (`:hover`) |

---

## 8. Cara Menjalankan

1. **Clone repositori**
```bash
   git clone https://github.com/IlhamBaihaqi24/Prak_DW_A-Pertemuan-3.git
```
2. **Masuk ke folder proyek**
```bash
   cd Prak_DW_A-Pertemuan-3
```
3. **Buka file HTML di browser**: `Contoh1/index.html` dan `Contoh2/index.html`, dengan klik dua kali atau memakai ekstensi *Live Server* di VS Code.

> ⚠️ Pada Contoh 2, folder CSS dan `img/` harus berada satu level dengan `index.html`, dan penulisan path harus persis sama (perhatikan huruf besar/kecil).

---

## 9. Kendala dan Evaluasi

| No | Kendala | Solusi |
|---|---|---|
| 1 | Pada Contoh 2, file CSS tidak terbaca bila dibuka lewat GitHub Pages atau server Linux, karena `href="css/style.css"` sedangkan nama foldernya `CSS` (huruf besar). Di Windows tetap jalan karena tidak membedakan huruf besar/kecil. | Samakan penulisan: ubah nama folder menjadi `css` atau ubah `href` menjadi `CSS/style.css` |
| 2 | Pada Contoh 2, tulisan link email tidak sama dengan alamat tujuannya (`href` memakai `ilhambhq378@gmail.com`, teks yang tampil `ilhambhq@gmail.com`) | Samakan teks link dengan alamat pada `href` |
| 3 | Kombinasi warna Contoh 2 (latar konten merah, judul hijau, link biru) membuat sebagian teks sulit dibaca | Pilih warna dengan kontras yang cukup, misalnya latar terang dengan teks gelap |
| 4 | Properti `text-align` pada selector `p` ditulis dua kali (`justify` lalu `center`); yang berlaku hanya yang terakhir | Tulis satu nilai saja agar kode bersih |
| 5 | Pada Contoh 1, gaya yang sama ditulis berulang di banyak elemen sehingga kode panjang | Pindahkan ke external CSS seperti pada Contoh 2 |
| 6 | Path gambar tidak terbaca bila folder `img/` tidak sejajar dengan HTML | Gunakan path relatif yang benar dan pastikan struktur folder sesuai |

---

## 10. Kesimpulan

Dari praktikum Pertemuan 3 ini dapat disimpulkan bahwa:

1. **CSS** berfungsi memisahkan urusan *tampilan* dari *struktur* HTML.
2. **Inline CSS** mudah dipakai untuk perubahan cepat, tetapi membuat kode panjang, berulang, dan sulit dirawat.
3. **External CSS** lebih rapi, efisien, dan mudah dikelola karena satu file dapat mengatur banyak elemen, bahkan banyak halaman.
4. Warna dapat ditulis dalam beberapa format (hex, `rgb()`, `rgba()`, dan `linear-gradient()`), dan `rgba()` memungkinkan pengaturan transparansi.
5. Pemahaman *box model* (`width`, `padding`, `border`, `margin`) dan selector (elemen, class, `:hover`) menjadi dasar untuk mengatur tata letak dan tampilan halaman.
6. Elemen semantik (`header`, `main`, `section`, `footer`) membuat struktur halaman lebih jelas dan mudah diberi gaya.

Materi ini menjadi dasar sebelum melanjutkan ke tata letak yang lebih kompleks (misalnya Flexbox dan responsive design) pada pertemuan berikutnya.

---

<p align="center">
  <sub>© 2026 Ilham Baihaqi (4525210029) · Teknik Informatika · Universitas Pancasila</sub>
</p>
