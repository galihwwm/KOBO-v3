# 🌾🐃 KOBO v3 — Belajar Koperasi Bersama Bao

Aplikasi gamifikasi literasi koperasi yang dikembangkan untuk
**Hackathon Digital Cooperatives Expo 2026 — Pilar 4: Literasi Gen-Z & Gen-Alpha dalam Berkoperasi**.

KOBO v3 hadir dengan pembaruan besar yang berfokus pada pemberian materi dasar-dasar koperasi melalui fitur *materi*, game pembelajaran melalui fitur *belajar*, dan daftar koperasi melalui fitur *katalog* dari shared database Kemenkop. Kami memperbaiki kekurangan dan menambahkan fitur baru dari versi prototipe sebelumnya menjadi fitur yang lebih matang dan interaktif.

> **Status: Minimum Viable Product (MVP) Version 3.0**

🔗 **Coba langsung:** https://galihwwm.github.io/KOBO-v3/

---

## 👥 Tim

| Peran | Nama |
|-------|------|
| Nama Tim | _(CIA-14)_ |
| Project Lead | _(Galih Wening Werdi Mukti)_ |
| Developer | _(Asriza Yolanda)_ |
| UI/UX & Creative Designer | _(Monike Febrianti)_ |

---

## 🎯 Relevansi dengan Tema Pilar 4 (Apa yang baru di v3?)

Jika pada versi sebelumnya Kobo berfokus pada simulasi kuis, KOBO v3 merealisasikan komitmen Pilar 4 secara penuh dengan mengusung alur "Belajar $\rightarrow$ Paham $\rightarrow$ Bergabung":
1. Belajar: pengguna kini dibekali materi yang dapat dipelajari sebelum bermain game pembelajaran.
2. Paham: pengguna menguji dan memahami materi melalui game interaktif.
3. Bergabung: menghubungkan minat generasi muda untuk bergabung langsung ke koperasi di sekitar mereka.

---


## ✨ Fitur Utama & Pembaruan

- **Maskot "Bao" 🐃** — Bao si kerbau memandu dan memberi umpan balik tiap soal. Kerbau dipilih sebagai simbol kerja keras dan gotong royong yang identik dengan pertanian Indonesia — sekaligus pembeda dari aplikasi belajar lain.

- **📖 Menu Materi (Pembaruan v2)**: Pengguna tidak lagi langsung dihadapkan pada kuis. Kini tersedia menu materi khusus agar pengguna bisa membaca dan mempelajari konsep perkoperasian terlebih dahulu. Seluruh materi diambil dari sumber resmi terpercaya.

- **🗺️ Menu Mandiri Katalog Koperasi (Pembaruan v2)**: Menu katalog koperasi kini dipisahkan menjadi halaman/menu tersendiri agar pengguna dapat mengeksplorasi, mencari, dan menyaring daftar koperasi di lingkungan sekitarnya dengan jauh lebih mudah dan fokus untuk bergabung pada keanggotaan koperasi.

- **📍 Deteksi & Sinkronisasi Lokasi (Pembaruan v3)**: Jika pada versi 1 data katalog masih bersifat dummy (contoh), KOBO v3 kini dilengkapi fitur deteksi lokasi. Aplikasi melakukan pencocokan (match) data koperasi berdasarkan titik koordinat lintang dan bujur (Latitude & Longitude) perangkat pengguna untuk menampilkan koperasi terdekat secara presisi. Data katalog koperasi pada KOBO v3 berdasarkan shared database Kemenkop untuk kegiatan Hackathon Digital Cooperatives Expo 2026. 

- **🎮 Sistem Gamifikasi yang Matang**: Mempertahankan elemen interaktif yang disukai Gen-Z dan Gen-Alpha seperti perolehan poin XP, daily streak, nyawa (hearts), lencana kelulusan, dan bimbingan dari maskot Bao 🐃.

- **Pembelajaran bertingkat** : 4 unit pembelajaran dengan mode terkunci/terbuka antar tingkat.

- **3 Tipe soal interaktif**: pilihan ganda, benar/salah, dan mencocokkan pasangan.

- **🎓 Sertifikat kelulusan**: setelah semua unit selesai, pengguna membuat sertifikat ber-nama dengan gelar "Sahabat Koperasi" yang bisa diunduh (.png) dan dibagikan ke media sosial.


## 🆚 Yang Membedakan Kobo

Aplikasi belajar gamifikasi pada umumnya berhenti pada penyampaian teori. Kobo melangkah lebih jauh dengan **menghubungkan edukasi ke aksi nyata**. Pengguna disuguhi daftar koperasi beserta jenis, lokasi, layanan, dan syarat keanggotaan yang bisa dicari dan disaring. Inilah inti diferensiasi Kobo — pengetahuan baru langsung dikaitkan dengan peluang konkret untuk menjadi anggota koperasi.

## 🧱 Arsitektur Manajemen Data
Untuk kemudahan pemeliharaan (sustainability), struktur data aplikasi KOBO v3 dirancang secara modular dan terpisah:
- data/materials.json : Menyimpan teks materi, deskripsi, dan tautan referensi eksternal terpercaya yang diakses di Menu Materi.
- data/lessons.json : Menampung bank soal interaktif (pilihan ganda, benar/salah, dan mencocokkan).
- data/coops.json : Database daftar koperasi yang sudah dilengkapi data spasial (lat dan lng) untuk kalkulasi jarak terdekat pengguna.

## 🚀 Cara Menjalankan secara Lokal

**Paling cepat:** buka file `index.html` di browser (double-click).
> Catatan: lewat double-click, aplikasi memakai **data bawaan** dan perubahan pada file JSON tidak akan terlihat. Untuk memuat JSON, jalankan via server (lihat **Catatan Teknis** di bawah).

**Via server lokal (disarankan):**
1. Clone repositori ini ke komputer Anda:
```bash
git clone https://github.com/galihwwm/KOBO-v3.git
```

2. Jalankan server lokal agar fitur pemanggilan data JSON lokal dan deteksi lokasi berjalan lancar:
```bash
python3 -m http.server 8000
```

3. Lalu buka http://localhost:8000 . Pastikan memberikan izin akses lokasi (GPS) saat browser memintanya agar fitur katalog terdekat berfungsi.

## 🧱 Teknologi

HTML, CSS, dan JavaScript.

## 📁 Struktur

```
.
├── index.html      # aplikasi utama (Dashboard, Materi, & Gamifikasi)
├── img             # assets gambar, ikon, dan aset visual
├── lessons.json    # bank soal kuis interaktif — edit di sini untuk menambah/ubah soal
├── coops.json      # database koperasi — edit di sini untuk menambah koperasi
├── materials.json  # materi pembelajaran — edit di sini untuk menambahkan materi
├── README.md
└── LICENSE
```

## 🗺️ Kurikulum Pembelajaran

| Unit | Topik |
|------|-------|
| 1 | Kenalan sama Koperasi (definisi, memahami asas gotong royong) |
| 2 | Simpanan & Modal (pokok, wajib, sukarela) |
| 3 | Rahasia SHU (Sisa Hasil Usaha, RAT) |
| 4 | Koperasi Zaman Now (digitalisasi) |

## ⚠️ Keterbatasan & Catatan

- **Materi & data koperasi bersifat contoh (dummy)** untuk demo.
- **Belum ada autentikasi/akun**, multi-pengguna, atau sinkronisasi cloud.
- **Belum ada fitur sosial** (leaderboard, komunitas) — peluang pengembangan lanjutan.

## 🔭 Ide Pengembangan Lanjutan

- **Integrasi data koperasi resmi** — menggantikan data dummy dengan sumber terverifikasi.
- **Leaderboard & tantangan antar-teman** — memperkuat aspek komunitas digital.
- **Mode kontributor** — antarmuka bagi koperasi/dinas untuk menambah materi tanpa menyentuh kode.
- **Akun pengguna + sinkronisasi** — via backend ringan atau layanan BaaS.
- **Audio & aksesibilitas tambahan** untuk jangkauan lebih luas.

## 📄 Lisensi

MIT — lihat berkas [LICENSE](LICENSE).
