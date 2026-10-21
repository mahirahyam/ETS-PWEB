# Dokumentasi Perancangan dan Publikasi LibraryReg

**Sistem Pendaftaran Anggota Perpustakaan Perguruan Tinggi**

## 1. Deskripsi dan Ruang Lingkup Pekerjaan

### A. Deskripsi Sistem

**LibraryReg** (*Library Registration System*) adalah aplikasi berbasis web *front-end* yang dirancang untuk merelokasi proses pendaftaran anggota perpustakaan perguruan tinggi dari sistem manual (formulir kertas) menjadi sistem digital yang efisien, cepat, dan terintegrasi.

Sistem ini memfasilitasi mahasiswa, dosen, dan tenaga kependidikan untuk melakukan pendaftaran secara mandiri (*self-service*), sekaligus menyediakan antarmuka pengelolaan data (*dashboard*) bagi petugas perpustakaan tanpa memerlukan konfigurasi database server pada tahap awal *development*.

### B. Ruang Lingkup Pekerjaan (*Scope of Work*)

1. **Front-End User Interface (UI)**
   - *Landing page* interaktif berisi informasi fasilitas, statistik koleksi, dan keunggulan perpustakaan.
   - Navigasi responsif berbasis *Single Page Application* (SPA) yang ramah pengguna, baik di perangkat desktop maupun *mobile*.

2. **Formulir Pendaftaran Digital dan Validasi Client-Side**
   - Penginputan data: Nama Lengkap, NIM/NIP, Program Studi, Alamat, Nomor Telepon, Email, dan Jenis Keanggotaan.
   - Validasi otomatis: kolom wajib diisi, validasi format email, dan pengecekan keunikan NIM/NIP untuk mencegah duplikasi pendaftaran.

3. **Sistem Pengelolaan Data Anggota (Petugas)**
   - Tabel responsif untuk menampilkan seluruh data anggota terdaftar.
   - Fitur *Live Search* (pencarian instan berdasarkan nama atau NIM/NIP) serta filter jenis keanggotaan.
   - Operasi CRUD dasar pada *front-end*, meliputi:
     - **Create:** Menambah data melalui formulir.
     - **Read:** Melihat detail data dan kartu anggota.
     - **Update:** Mengedit data anggota.
     - **Delete:** Menghapus data anggota dengan konfirmasi.

4. **Penyimpanan Data Sementara (*Persistence*)**
   - Menggunakan HTML5 `localStorage` untuk menyimpan data anggota secara lokal di browser, sehingga data tetap tersimpan saat halaman dimuat ulang (*page refresh*).

5. **Fitur Tambahan (*Digital Card & QR Code*)**
   - Generasi otomatis **Kartu Anggota Digital** lengkap dengan QR Code unik berdasarkan NIM/NIP yang siap dicetak atau diunduh.

## 2. Rancangan Halaman dan Struktur Menu

### A. Sitemap / Struktur Navigasi

```text
LibraryReg (App)
├── 1. Dokumentasi Proyek (Laporan Soal 1 & 2)
├── 2. Beranda (Landing Page)
│   ├── Hero Section (Slogan & Tombol CTA)
│   ├── Statistik Koleksi & Anggota
│   ├── Keunggulan & Fasilitas
│   ├── Layanan Utama Perpustakaan
│   └── Footer (Kontak & Jam Operasional)
├── 3. Pendaftaran Anggota (Formulir Online)
│   └── Form Input + Validasi + Kirim Data
├── 4. Kelola Data Anggota (Petugas Dashboard)
│   ├── Ringkasan Statistik Anggota
│   ├── Bar Pencarian & Filter
│   ├── Tabel Data Anggota
│   ├── Modal Edit Data
│   └── Modal Kartu Anggota Digital (+ QR Code)
└── 5. Panduan Publish (Langkah Deployment)
```

### B. User Flow (Alur Pengguna)

#### 1. Calon Anggota (Mahasiswa/Dosen/Tendik)

1. Mengunjungi *landing page*.
2. Mengeklik tombol **Daftar Anggota**.
3. Mengisi formulir pendaftaran.
4. Sistem memvalidasi input.
5. Jika valid, data tersimpan ke `localStorage`.
6. Sistem menampilkan **Kartu Anggota Digital** beserta QR Code.

#### 2. Petugas Perpustakaan

1. Membuka menu **Kelola Data**.
2. Melihat daftar anggota.
3. Menggunakan fitur pencarian dan filter.
4. Melakukan *edit* atau *hapus* data anggota.
5. Melihat atau mencetak kartu anggota dari tabel.

## 3. Desain UI Landing Page dan Aplikasi Web

Aplikasi dibangun menggunakan kombinasi teknologi berikut:

- **HTML5 dan CSS3 Custom Variables**
- **Bootstrap 5 dan Font Awesome 6**
- **Vanilla JavaScript ES6**, meliputi:
  - `localStorage`
  - DOM Manipulation
  - SPA Routing

Semua komponen UI *landing page*, formulir pendaftaran, tabel pengelolaan data, dan modal kartu digital terintegrasi dalam satu file executable bernama `index.html`.

Link Website: https://mahirahyam.github.io/ETS-PWEB/

Link Demo Youtube: https://youtu.be/GYT3NiwS1l0
