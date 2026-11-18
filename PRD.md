# Product Requirement Document (PRD)
## Proyek: Platform Web Pemasaran & Pemesanan Kos ("Buat Web Kos")

**Disusun oleh:** Arka, Principal Product Architect – ReyDev Web Studio  
**Status Dokumen:** *Draft / Siap untuk Pengembangan*  
**Versi:** 1.0  

---

## 1. Ringkasan Eksekutif & Sasaran

### 1.1 Ringkasan Eksekutif
Proyek "Buat Web Kos" adalah inisiatif pengembangan solusi *landing page* dan katalog digital yang dirancang khusus untuk pemilik properti kos (pemilik usaha mikro hingga menengah). Tujuannya adalah mendigitalisasi proses pemasaran kamar kos, mempermudah calon penyewa melihat fasilitas secara transparan, dan mempercepat proses konversi melalui integrasi langsung ke WhatsApp (*Chat-to-Order*).

### 1.2 Sasaran Proyek (Goals)
* **Meningkatkan Okupansi:** Membantu pemilik kos mengurangi kamar kosong melalui visibilitas online yang profesional.
* **Efisiensi Komunikasi:** Menjembatani calon penyewa dan pengelola kos secara instan tanpa perantara sistem chat pihak ketiga yang rumit.
* **Kecepatan & Kemudahan Setup:** Menyediakan platform web yang ringan, cepat dimuat, dan mudah diakses dari berbagai perangkat (*mobile-first*).

---

## 2. Target Audiens & Persona

### 2.1 Persona 1: Pemilik Kos / Pengelola (B2B / Klien ReyDev)
* **Nama:** Pak Budi (50 tahun)
* **Karakteristik:** Pemilik kos dengan 15 pintu. Kurang paham teknis koding, tetapi ingin propertinya cepat laku dan terlihat profesional.
* **Kebutuhan:** Ingin web yang informatif, mudah dikelola (atau dibantu kelola oleh ReyDev), dan langsung mendatangkan calon penyewa serius via WhatsApp.

### 2.2 Persona 2: Pencari Kos (B2C / Pengguna Akhir)
* **Nama:** Siska (21 tahun, Mahasiswi/Karyawan baru)
* **Karakteristik:** Sangat bergantung pada *smartphone*, mengutamakan kecepatan informasi (harga, lokasi, fasilitas), dan menyukai komunikasi yang cepat (*chat-based*).
* **Kebutuhan:** Mencari kos yang bersih, strategis, harga transparan, dan bisa langsung bertanya atau *booking* jadwal survey ke pemilik via WhatsApp.

---

## 3. Fitur Utama & Spesifikasi Fungsional

Arsitektur produk ini dibagi menjadi 4 komponen utama sesuai dengan struktur *landing page* berkonversi tinggi:

### 3.1 Komponen 1: Hero Section (Bagian Atas / *First Impression*)
* **Fungsi:** Menangkap perhatian pengguna dalam 3 detik pertama dan menyampaikan nilai utama kos.
* **Spesifikasi Fungsional:**
  * **Judul Utama (H1):** Headline yang menarik (Contoh: *"Hunian Nyaman, Strategis, & Fasilitas Lengkap di Pusat Kota"*).
  * **Sub-headline:** Penjelasan singkat mengenai keunggulan utama (misal: *Free Wi-Fi, AC, Kamar Mandi Dalam*).
  * **Call to Action (CTA) Utama:** Tombol *"Cek Ketersediaan Kamar"* atau *"Hubungi via WhatsApp"* yang mengarahkan langsung ke bagian katalog atau chat.
  * **Visual/Banner:** Gambar latar (*background*) berkualitas tinggi atau *slider* foto kondisi fisik kos yang estetik.

### 3.2 Komponen 2: Showcase / Katalog Kamar
* **Fungsi:** Menampilkan tipe kamar, fasilitas, dan harga secara transparan kepada calon penyewa.
* **Spesifikasi Fungsional:**
  * **Grid/Card Layout:** Menampilkan daftar tipe kamar (contoh: Tipe Standar, Tipe Deluxe).
  * **Detail per Card:**
    * Foto thumbnail kamar (bisa diperbesar via *lightbox*).
    * Nama tipe kamar.
    * Harga sewa (per bulan / per tahun).
    * Daftar fasilitas (ikon + teks: AC, Kasur, Lemari, Wi-Fi, KM Dalam).
    * Status ketersediaan (*Tersedia* / *Penuh*).
  * **Filter Sederhana (Opsional):** Berdasarkan kisaran harga atau ketersediaan kamar.

### 3.3 Komponen 3: Form Pemesanan & *Booking* WhatsApp
* **Fungsi:** Mengubah pengunjung web menjadi *lead* atau calon penyewa melalui integrasi WhatsApp API.
* **Spesifikasi Fungsional:**
  * Formulir interaktif ringan di dalam web yang berisi field:
    * Nama Lengkap
    * Nomor WhatsApp / Kontak
    * Tipe Kamar yang Dipilih (Dropdown dari Katalog)
    * Rencana Tanggal Masuk (*Check-in*)
    * Catatan Tambahan (Opsional)
  * **Tombol "Kirim Pesanan / Tanya Kos":** Ketika diklik, sistem secara otomatis merangkum data input ke dalam format pesan WhatsApp yang rapi dan langsung membuka aplikasi WhatsApp (web/mobile) menuju nomor admin/pemilik kos.
  * *Contoh Format Pesan WhatsApp Otomatis:*
    > "Halo Admin, saya ingin memesan/survei kos. 
    > Nama: [Nama]
    > Tipe Kamar: [Tipe]
    > Rencana Masuk: [Tanggal]
    > Catatan: [Catatan]"

### 3.4 Komponen 4: Footer
* **Fungsi:** Menyediakan informasi pendukung, legitimasi, dan navigasi tambahan di bagian bawah halaman.
* **Spesifikasi Fungsional:**
  * **Informasi Kontak & Lokasi:** Alamat lengkap kos, Google Maps *embed*, nomor telepon/WhatsApp, dan email pengelola.
  * **Jam Operasional:** Jam operasional layanan atau jadwal survey.
  * **Tautan Cepat (*Quick Links*):** Navigasi internal ke *Hero*, *Katalog*, *Fasilitas*, dan *Kontak*.
  * **Media Sosial & Legalitas:** Ikon tautan ke Instagram/Facebook kos (jika ada) dan *Copyright* (Powered by ReyDev Web Studio).

---

## 4. Non-Functional Requirements (NFR)

Sebagai Principal Product Architect di ReyDev, standar teknis yang diterapkan pada proyek ini adalah sebagai berikut:

* **4.1 Mobile-First & Responsif:**
  * Desain harus dioptimalkan untuk layar *smartphone* (karena >85% pencari kos menggunakan *mobile*), namun tetap tampil sempurna di *tablet* dan *desktop*.
* **4.2 Aksesibilitas (Accessibility):**
  * Kontras warna teks dan latar belakang memenuhi standar WCAG AA agar mudah dibaca oleh semua kalangan.
  * Ukuran tombol CTA ramah sentuhan (*touch-friendly*, minimum 48x48 px).
* **4.3 Keamanan & Performa (Security & Performance):**
  * Menggunakan protokol HTTPS terenkripsi.
  * Optimasi aset gambar (kompresi otomatis format WebP) agar kecepatan muat halaman (*Page Load Time*) di bawah 3 detik pada jaringan standar.
  * Validasi *input* pada form untuk mencegah *spam* atau *script injection*.

---

## 5. KPI (Key Performance Indicators) Keberhasilan

Untuk mengukur kesuksesan produk "Buat Web Kos" setelah diluncurkan, indikator kinerja utama (KPI) yang akan dipantau meliputi:

1. **Conversion Rate (CR):** Persentase pengunjung web yang mengklik tombol CTA WhatsApp atau mengisi form pemesanan (Target minimal: 5-8% dari total *unique visitors*).
2. **Page Load Speed:** Waktu muat halaman di bawah 3 detik berdasarkan *Google PageSpeed Insights*.
3. **Bounce Rate:** Persentase pengguna yang langsung keluar dari web di bawah 50%, menandakan bahwa *Hero Section* dan informasi awal cukup menarik.
4. **Kepuasan Klien (Pemilik Kos):** Umpan balik positif dari pemilik kos terkait kemudahan calon penyewa dalam menghubungi mereka.

---
*Dokumen ini bersifat dinamis dan dapat diperbarui sesuai dengan kebutuhan spesifik penyesuaian fitur lanjutan (seperti integrasi payment gateway atau sistem manajemen properti penuh) pada fase berikutnya.*

---

Halo! Sebagai Lead Product Architect di DeepMind, saya akan langsung mengeksekusi penambahan revisi ini ke dalam dokumen PRD Anda dengan standar arsitektur sistem yang jelas, terstruktur, dan berorientasi pada pengalaman pengguna.

Berikut adalah tambahan bab baru yang harus disematkan pada bagian akhir dokumen PRD "Buat Web Kos":

---

## Changelog & Spesifikasi Fitur Baru (Iterasi Pengembangan)

**ID Revisi:** `REV-2023-01`  
**Fitur yang Ditambahkan:** Galeri Foto Properti (*Dynamic Photo Gallery*)  
**Status:** *Approved for Development*  

### 1. Deskripsi Fitur Baru
Fitur **Galeri Foto Properti** ditambahkan untuk merespons kebutuhan visual calon penyewa (Persona 2: Siska) yang sangat bergantung pada kejelasan visual sebelum memutuskan untuk *booking* atau survei. Fitur ini menampilkan kumpulan dokumentasi visual resolusi tinggi dari berbagai sudut properti—termasuk area komunal (dapur, ruang tamu, parkiran), fasilitas sekitar, dan detail kamar—dalam format *grid* interaktif yang mendukung fitur *lightbox* (zoom gambar).

### 2. Alur Pengguna (*User Flow*)
1. **Eksplorasi Beranda:** Pengguna melakukan *scrolling* melewati *Hero Section* dan *Showcase* katalog.
2. **Akses Galeri:** Pengguna menemukan bagian "Galeri Fasilitas & Lingkungan Kos" yang terletak sebelum bagian *Footer* atau *Call to Action* akhir.
3. **Interaksi Visual:** 
   * Pengguna melihat foto-foto dalam tampilan *grid* yang rapi.
   * Pengguna dapat mengklik salah satu foto untuk memperbesar gambar (*Lightbox View*).
   * Pengguna dapat menggeser (*swipe/next*) foto satu per satu tanpa harus menutup mode *lightbox*.
4. **Konversi:** Setelah melihat transparansi kondisi kos, pengguna terdorong untuk menekan tombol CTA WhatsApp yang tersedia di dekat galeri.

### 3. Komponen Teknis yang Ditambahkan/Diubah
* **Frontend (UI/UX Component):**
  * Membuat komponen modular `GalleryGrid.jsx` menggunakan pendekatan *mobile-first* (layout 2 kolom di HP, 3-4 kolom di Desktop).
  * Mengintegrasikan *LightBox Library* ringan (contoh: `Yet Another React Lightbox` atau implementasi *custom modal* CSS murni) untuk memastikan performa web tetap cepat (*load time* < 2 detik).
  * Menambahkan sistem *Lazy Loading* pada aset gambar untuk optimalisasi *Core Web Vitals* (LCP & CLS).
* **Backend / CMS (Bagi Pemilik Kos / Pak Budi):**
  * Menambahkan *Endpoint* API baru atau memperbarui struktur JSON lokal (`property.json`) untuk mengakomodasi *array* URL gambar galeri.
  * Memastikan *dashboard* sederhana (jika ada) mendukung *multi-image upload* dengan kompresi otomatis di sisi klien sebelum diunggah ke *cloud storage* (misal: Cloudinary/Supabase Storage).

---

Halo! Sebagai Arka, Lead Product Architect di Google DeepMind, saya menyambut baik penambahan fitur inter

---

Halo tim, Arka di sini. 

Saya telah meninjau permintaan penambahan fitur dari stakeholder terkait integrasi lokasi strategis dan peta interaktif pada platform "Buat Web Kos". Mengingat fitur ini krusial untuk meningkatkan *conversion rate* bagi Persona 2 (Siska - Pencari Kos) yang sangat mengandalkan aksesibilitas lokasi, mari kita masukkan pembaruan ini ke dalam dokumen resmi.

Berikut adalah tambahan bab baru yang harus diintegrasikan ke bagian akhir dokumen PRD:

---

## Changelog & Spesifikasi Fitur Baru (Iterasi Pengembangan)

**Tanggal Pembaruan:** *Current Date*  
**Ditinjau oleh:** Arka (Lead Product Architect, Google DeepMind / Principal Product Architect ReyDev)  
**Status Iterasi:** *Approved for Sprint Backlog*

---

### 1. Deskripsi Fitur Baru
Penambahan **Seksi Lokasi Strategis & Peta Interaktif** bertujuan untuk memberikan transparansi penuh kepada calon penyewa mengenai letak geografis properti kos. Fitur ini tidak hanya menampilkan alamat teks, tetapi juga menyertakan *embedded map* (peta interaktif) serta estimasi jarak tempuh dan waktu perjalanan (menggunakan kendaraan atau jalan kaki) ke titik-titik penting di sekitar kos, seperti:
* Kampus / Universitas terdekat
* Stasiun Kereta, Halte Bus, atau akses Tol
* Fasilitas publik (Rumah sakit, pusat perbelanjaan, minimarket)

### 2. Alur Pengguna (*User Flow*)
1. **Eksplorasi Halaman:** Setelah melihat *Hero Section* dan *Showcase* kamar, pengguna (*Siska*) melakukan *scroll* ke bawah untuk meninjau aksesibilitas lokasi kos.
2. **Melihat Peta Interaktif:** Pengguna melihat peta mini (*embedded map*) yang menempatkan pin lokasi kos secara akurat. Pengguna dapat melakukan *zoom-in/out* untuk melihat lingkungan sekitar.
3. **Membaca Estimasi Jarak:** Di samping atau di bawah peta, terdapat *badge* informasi jarak ringkas (Contoh: *"5 Menit ke Kampus X"* atau *"350 meter ke Stasiun Y"*).
4. **Navigasi Langsung (Opsional):** Pengguna dapat mengeklik tombol *"Buka di Google Maps"* untuk membuka aplikasi navigasi eksternal di *smartphone* mereka guna merencanakan rute survei lokasi secara *real-time*.

### 3. Komponen Teknis yang Ditambahkan/Diubah
* **Frontend Component (`LocationSection.jsx` / `Location.astro`):**
  * Membuat komponen UI baru yang responsif (*mobile-first*) dengan tata letak dua kolom (kolom kiri untuk daftar poin jarak tempuh/landmark, kolom kanan untuk peta).
* **Integrasi Peta (Map Integration):**
  * Menggunakan *iframe* Google Maps Embed API yang ringan, atau Mapbox GL JS jika membutuhkan kustomisasi pin yang lebih estetik sesuai *branding* kos.
* **Struktur Data (CMS / JSON Schema):**
  * Menambahkan *fields* baru pada database/config properti:
    ```json
    {
      "location": {
        "address": "Jl. Merdeka No. 45, Bandung",
        "google_maps_embed_url": "https://www.google.com/maps/embed?...",
        "google_maps_direct_link": "https://maps.app.goo.gl/...",
        "landmarks": [
          { "name": "Universitas Padjadjaran (Unpad)", "distance": "1.2 km", "time": "5 menit (Motor)" },
          { "name": "Stasiun Kereta", "distance": "800 m", "time": "10 menit (Jalan Kaki)" }
        ]
      }
    }
    ```
* **Optimasi Performa:**
  * Memastikan *iframe* peta menggunakan atribut `loading="lazy"` agar tidak memperlambat waktu muat awal (*Initial Page Load*) dari *landing page* kos.

---

Halo! Sebagai Lead Product Architect di Google DeepMind, saya menyambut baik usulan penambahan fitur interaktif ini. Fitur Kalkulator Estimasi Biaya Sewa & Deposit akan sangat meningkatkan *user experience* (UX) bagi calon penyewa (Siska) serta memberikan transparansi finansial di awal sebelum mereka menghubungi pemilik kos via WhatsApp.

Berikut adalah tambahan bab untuk dokumen PRD sesuai dengan permintaan Anda:

---

## Changelog & Spesifikasi Fitur Baru (Iterasi Pengembangan)

**ID Fitur:** `FEAT-2023-REV01`  
**Nama Fitur:** Kalkulator Estimasi Biaya Sewa & Deposit Interaktif  
**Status:** *Approved for Development*  
**Diusulkan Oleh:** Product Management & Engineering Team  

---

### 1. Deskripsi Fitur Baru
Kalkulator interaktif yang ditempatkan pada halaman detail kamar atau bagian bawah katalog. Fitur ini memungkinkan calon penyewa untuk menghitung total biaya awal yang harus dibayarkan (sewa bulan pertama + deposit + *add-ons* opsional seperti parkir kendaraan, penambahan perangkat elektronik, atau laundry) secara real-time sebelum mereka melakukan *Chat-to-Order* ke WhatsApp.

**Nilai Bisnis (Business Value):**
* **Transparansi:** Mengurangi *friction* dan pertanyaan berulang di WhatsApp terkait rincian harga.
* **Kualifikasi Lead:** Calon penyewa yang mengklik tombol WhatsApp setelah menggunakan kalkulator sudah memiliki ekspektasi budget yang jelas (leads berkualitas tinggi).

---

### 2. Alur Pengguna (User Flow)
1. **Akses:** Pengguna menggulir (scroll) ke bagian Katalog Kamar atau spesifikasi tipe kamar tertentu.
2. **Interaksi Kalkulator:** 
   * Pengguna memilih **Durasi Sewa** (Bulanan: 1, 3, 6, atau 12 bulan).
   * Pengguna mencentang **Layanan Tambahan / *Add-ons*** (misal: Bawa Kulkas/TV +Rp50.000/bln, Tambah Penghuni +Rp100.000/bln, Parkir Mobil +Rp150.000/bln).
   * Sistem otomatis menghitung: `(Harga Kamar x Durasi) + Biaya Add-ons + Deposit Keamanan` = **Total Estimasi Pembayaran**.
3. **Konversi (CTA):** Pengguna menekan tombol *"Pesan Kamar Ini via WhatsApp"*.
4. **Handoff ke WhatsApp:** Sistem merangkum hasil kalkulasi ke dalam format teks otomatis yang langsung terkirim ke nomor WhatsApp pengelola kos. 
   *(Contoh Format Pesan: "Halo Kak, saya ingin memesan Tipe Kamar A untuk durasi 3 bulan dengan tambahan Parkir Mobil. Berdasarkan kalkulator di web, total estimasi biaya awal adalah Rp X. Apakah kamar masih tersedia?")*

---

### 3. Komponen Teknis yang Ditambahkan/Diubah
* **Frontend Component (React / Vanilla JS):**
  * Membuat komponen UI baru: `<RentCalculator />` yang berisi *dropdown* durasi, *checkbox group* untuk *add-ons*, dan *live display card* untuk *Total Cost Summary*.
  * State management lokal untuk merekam perubahan input pengguna secara *real-time* tanpa memuat ulang halaman (*page reload*).
* **WhatsApp API Generator:**
  * Fungsi utilitas (*helper function*) untuk mengubah objek data hasil kalkulasi menjadi string URL-encoded yang dikirimkan sebagai parameter teks ke `api.whatsapp.com`.
* **Mobile Responsiveness:**
  * Memastikan komponen kalkulator mudah digunakan dengan satu tangan (*thumb-friendly zone*) pada perangkat *mobile*, mengingat mayoritas Persona Siska mengakses melalui *smartphone*.

---

Halo! Saya Arka, Lead Product Architect di tim engineering AI Google DeepMind. Berdasarkan permintaan penambahan fitur filter pada katalog kos, berikut adalah bab tambahan yang siap diintegrasikan ke dalam dokumen PRD "Griya Kost Harmoni":

---

## Changelog & Spesifikasi Fitur Baru (Iterasi Pengembangan)

### 1. Deskripsi Fitur Baru
Untuk meningkatkan pengalaman pengguna (terutama bagi persona Siska sebagai pencari kos) dalam menemukan kamar yang paling sesuai dengan kebutuhan dan budget mereka secara cepat, kami menambahkan **Fitur Filter Katalog Kos**. 

Fitur ini memungkinkan calon penyewa menyaring daftar kamar berdasarkan beberapa parameter utama secara *real-time* tanpa perlu memuat ulang halaman (*client-side filtering*):
* **Rentang Harga (Price Range):** Filter berdasarkan minimum dan maksimum harga sewa per bulan.
* **Tipe/Kategori Kamar:** Berdasarkan fasilitas kamar mandi (Dalam / Luar).
* **Fasilitas Unggulan (Amenities):** Pilihan *checkbox* untuk fasilitas spesifik (AC, Wi-Fi, Water Heater, Kasur, Lemari).
* **Ketersediaan (Availability):** Status kamar (Kamar Tersedia vs. Penuh).

---

### 2. Alur Pengguna (User Flow)
1. **Akses Katalog:** Pengguna melakukan *scrolling* dari *Hero Section* atau mengklik navigasi menuju bagian **Showcase / Katalog Kamar**.
2. **Interaksi Panel Filter:** 
   * Pengguna melihat bilah filter (*filter bar/drawer*) yang terletak di bagian atas atau sisi kiri grid katalog (dioptimalkan untuk *mobile* menggunakan sistem *collapsible filter drawer*).
   * Pengguna memasukkan atau memilih kriteria yang diinginkan (contoh: memilih filter "AC" dan menetapkan batas maksimal harga Rp 1.500.000).
3. **Pembaruan Data Instan:** 
   * Sistem secara otomatis memproses parameter dan memperbarui tampilan grid kamar (*live filtering*) dalam waktu $< 100\text{ms}$.
   * Jika tidak ada kamar yang cocok, sistem menampilkan komponen *Empty State* (contoh: *"Maaf, tidak ada kamar yang sesuai dengan filter Anda"* beserta tombol *Reset Filter*).
4. **Konversi (CTA):** Pengguna melihat kamar yang telah difilter, mengklik detail kamar, atau langsung menekan tombol *"Tanya via WhatsApp"* untuk memesan atau survey.

---

### 3. Komponen Teknis yang Ditambahkan/Diubah
* **Frontend Component (`/components/RoomFilter.tsx`):**
  * Membuat komponen UI baru berupa *stateful form* yang mencakup *range slider* untuk harga, *checkbox group* untuk fasilitas, dan tombol *Reset*.
  * Menggunakan *React Hook* (`useState`, `useMemo`) untuk menangani logika penyaringan data array kamar secara efisien di sisi *client* demi menjaga performa *mobile-first*.
* **UI/UX Adaptation (`/components/CatalogGrid.tsx`):**
  * Menyesuaikan *layout grid* agar responsif terhadap perubahan jumlah item yang ditampilkan setelah difilter.
  * Menambahkan animasi transisi halus (*CSS transitions/Framer Motion*) saat kartu kamar dimuat ulang atau disembunyikan.
* **Data Structure / Mock Data:**
  * Memperbarui skema objek data kamar (`RoomType`) untuk menyertakan *boolean flags* pada properti fasilitas (`hasAC`, `hasWiFi`, dll) dan *integer value* untuk `price`, guna mendukung logika *filtering*.

---

Halo! Sebagai Arka, Lead Product Architect di tim engineering AI Google DeepMind, saya akan langsung merumuskan penambahan fitur baru untuk iterasi selanjutnya pada PRD "Griya Kost Harmoni" ini. 

Berikut adalah tambahan bab baru yang harus diintegrasikan ke bagian akhir dokumen PRD:

---

## Changelog & Spesifikasi Fitur Baru (Iterasi Pengembangan)

Dalam rangka meningkatkan *conversion rate* (tingkat konversi) serta memberikan pengalaman pengguna (*user experience*) yang lebih seamless bagi pencari kos (Siska) dan efisiensi manajemen bagi pengelola (Pak Budi), kami menambahkan dua modul strategis pada iterasi V1.1 ini: **Modul Sistem Booking Jadwal Survey (Appointment Scheduler)** dan **Modul Peta Lokasi Interaktif & Panduan Rute (Interactive Map & Directions)**.

---

### 1. Modul Sistem Booking Jadwal Survey (Appointment Scheduler)

#### A. Deskripsi Fitur Baru
Fitur ini memungkinkan calon penyewa untuk menjadwalkan kunjungan/survei kamar kos secara langsung melalui web tanpa harus bolak-balik menebak ketersediaan waktu pengelola. Sistem akan merangkum detail jadwal dan otomatis memformat pesan WhatsApp konfirmasi ke admin kos.

#### B. Alur Pengguna (*User Flow*)
1. Pengguna (Siska) mengklik tombol *"Jadwalkan Survey"* pada salah satu kartu kamar di Katalog.
2. Muncul *modal* atau *popup* formulir singkat yang meminta data:
   * Nama Lengkap
   * Nomor WhatsApp
   * Tanggal Survey
   * Pilihan Sesi Waktu (Sesi Pagi: 09.00 - 12.00 / Sesi Sore: 15.00 - 17.00)
3. Pengguna menekan tombol *"Kirim Jadwal via WhatsApp"*.
4. Sistem secara otomatis men-generate pesan *pre-filled* WhatsApp dengan format:
   > *"Halo Admin Griya Kost Harmoni, saya [Nama] ingin mengkonfirmasi jadwal survey untuk tipe kamar [Nama Kamar] pada tanggal [Tanggal] sesi [Waktu]. Mohon konfirmasinya, terima kasih."*
5. Aplikasi mengarahkan pengguna langsung ke aplikasi/web WhatsApp untuk mengirimkan pesan tersebut ke nomor pengelola (Pak Budi).

#### C. Komponen Teknis yang Ditambahkan / Diubah
* **Frontend Component:** Penambahan komponen `SurveyModal.jsx` menggunakan React/Tailwind CSS yang dilengkapi *date-picker* dan pilihan *radio button* untuk sesi waktu.
* **State Management:** Menambah logika *state* lokal untuk menangkap input *form* dan merangkai string URL WhatsApp *API encodeURI*.
* **UI/UX Enhancement:** Penambahan *micro-interaction* (animasi buka-tutup modal yang halus) untuk menjaga kenyamanan *mobile-first experience*.

---

### 2. Modul Peta Lokasi Interaktif & Panduan Rute (Interactive Map & Directions)

#### A. Deskripsi Fitur Baru
Siska dan calon penyewa lainnya sering kali membutuhkan kepastian mengenai aksesibilitas kos terhadap kampus, kantor, atau fasilitas umum (stasiun, minimarket). Modul ini menyematkan peta digital interaktif serta poin-poin akses strategis di sekitar kos.

#### B. Alur Pengguna (*User Flow*)
1. Pengguna melakukan *scrolling* ke bagian bawah *landing page* menuju seksi Lokasi.
2. Pengguna melihat peta interaktif (embed Google Maps) yang menandai titik koordinat "Griya Kost Harmoni".
3. Di bawah peta, terdapat *bullet points* aksesibilitas terdekat (misal: "5 Menit ke Universitas X", "2 Menit ke Stasiun Y").
4. Pengguna dapat mengklik tombol *"Buka di Google Maps"* untuk langsung membuka aplikasi navigasi di *smartphone* mereka guna mendapatkan rute perjalanan secara *real-time*.

#### C. Komponen Teknis yang Ditambahkan / Diubah
* **Frontend Component:** Pembuatan komponen `LocationSection.jsx` yang mengintegrasikan *iframe* responsif Google Maps Embed API.
* **Performance Optimization:** Menerapkan teknik *lazy loading* (`loading="lazy"`) pada *iframe* peta untuk memastikan *Initial Page Load* (skor Lighthouse) tetap optimal dan tidak memperlambat kecepatan muat halaman utama (*mobile-first optimization*).
* **Styling:** Penyesuaian *aspect ratio* kontainer peta agar tampil sempurna dan tidak merusak layout pada perangkat berukuran layar kecil (*mobile viewports*).

---

Baik, terima kasih atas masukan berharga ini. Penambahan fitur filter pada katalog kamar kos adalah langkah yang sangat tepat untuk meningkatkan pengalaman pengguna dan efisiensi pencarian. Ini akan sangat membantu Siska (Persona 2) menemukan kamar yang sesuai dengan kebutuhannya lebih cepat.

Sebagai Arka, Lead Product Architect, saya akan menambahkan bab baru di PRD untuk mendokumentasikan fitur ini.

---

## Changelog & Spesifikasi Fitur Baru (Iterasi Pengembangan)

### 1. Deskripsi Fitur Baru: Filter Katalog Kamar Kos

Fitur "Filter Katalog Kamar Kos" dirancang untuk memungkinkan calon penyewa (Persona 2: Siska) menyaring daftar kamar yang tersedia berdasarkan kriteria tertentu. Tujuannya adalah untuk mempercepat proses pencarian, mengurangi *cognitive load*, dan membantu pengguna menemukan kamar yang paling sesuai dengan preferensi mereka tanpa harus menelusuri seluruh daftar secara manual. Fitur ini akan diimplementasikan pada Komponen 2: Showcase / Katalog Kamar.

### 2. Alur Pengguna (User Flow)

1.  **Pengguna Mengakses Katalog:** Siska membuka halaman "Griya Kost Harmoni" dan *scroll* ke Komponen 2: Showcase / Katalog Kamar.
2.  **Melihat Opsi Filter:** Di bagian atas atau samping daftar kamar, Siska melihat area atau tombol yang menunjukkan opsi untuk "Filter Kamar".
3.  **Membuka Panel Filter:** Siska mengklik atau menyentuh tombol/area filter, yang kemudian menampilkan panel atau *dropdown* berisi pilihan filter.
4.  **Memilih Kriteria Filter:** Siska memilih satu atau lebih kriteria filter yang diinginkan, seperti:
    *   **Rentang Harga:** Slider atau input numerik (misal: "Rp 1.000.000 - Rp 1.500.000").
    *   **Fasilitas Utama:** Checkbox (misal: "AC", "Kamar Mandi Dalam", "Wi-Fi", "Furnished").
    *   **Tipe Kamar:** Radio button/checkbox (misal: "Single", "Double").
    *   *(Opsional)* **Ketersediaan:** Checkbox "Tersedia Saat Ini".
5.  **Menerapkan Filter:** Setelah memilih kriteria, Siska mengklik tombol "Terapkan Filter" atau daftar kamar akan diperbarui secara otomatis (*real-time filtering*).
6.  **Melihat Hasil Terfilter:** Daftar kamar pada Komponen 2 akan diperbarui untuk hanya menampilkan kamar yang memenuhi semua kriteria filter yang dipilih Siska.
7.  **Mengubah/Menghapus Filter:** Siska dapat mengubah pilihan filternya atau menghapus semua filter untuk melihat kembali seluruh daftar kamar.

### 3. Komponen Teknis yang Ditambahkan/Diubah

*   **Antarmuka Pengguna (Frontend):**
    *   **Elemen UI Filter:** Penambahan elemen HTML/CSS/JS untuk kontrol filter (misalnya: `div` untuk panel filter, `input type="range"` untuk harga, `input type="checkbox"` untuk fasilitas, `button` untuk menerapkan/reset filter).
    *   **Logika JavaScript:** Implementasi fungsi JavaScript untuk:
        *   Menangkap input dari kontrol filter.
        *   Memproses data kamar yang sudah dimuat (*client-side filtering*) atau mengirim permintaan filter ke *server* (jika data dimuat secara dinamis).
        *   Secara dinamis memperbarui tampilan daftar kamar berdasarkan hasil filter (menampilkan/menyembunyikan elemen kamar).
    *   **Responsivitas:** Memastikan layout filter tetap optimal dan mudah digunakan di berbagai ukuran layar (*mobile-first*).
*   **Struktur Data Kamar (Data Model):**
    *   Memastikan setiap objek kamar dalam data memiliki properti yang jelas untuk kriteria filter (misalnya: `harga: number`, `fasilitas: string[]`, `tipe_kamar: string`, `is_available: boolean`). Ini penting agar proses filtering dapat berjalan akurat.
*   **Performa:**
    *   Untuk *landing page* yang ringan dan cepat, *client-side filtering* (memuat semua data kamar di awal dan menyaringnya dengan JavaScript) akan menjadi prioritas untuk performa terbaik, terutama jika jumlah kamar tidak terlalu banyak (<50 kamar).
    *   Jika jumlah kamar sangat banyak atau akan ada fitur pencarian yang lebih kompleks di masa depan, pertimbangan untuk integrasi API *endpoint* dengan parameter filter akan diperlukan.
*   **Aksesibilitas:** Memastikan elemen filter dapat diakses dan digunakan oleh pengguna dengan berbagai kebutuhan, termasuk navigasi keyboard dan dukungan *screen reader*.

---

Tentu, sebagai Arka, Lead Product Architect, saya akan menambahkan bab baru untuk mencatat revisi dan penambahan fitur Virtual Tour 360 derajat ke dalam PRD "Griya Kost Harmoni". Ini adalah langkah yang sangat baik untuk meningkatkan transparansi dan pengalaman calon penyewa.

---

Berikut adalah penambahan bab baru dalam format Markdown:

```markdown
---

## Changelog & Spesifikasi Fitur Baru (Iterasi Pengembangan)

### 1. Deskripsi Fitur Baru: Virtual Tour 360 Derajat Kamar

Fitur "Virtual Tour 360 Derajat Kamar" akan memberikan pengalaman imersif bagi calon penyewa untuk menjelajahi interior kamar kos secara virtual. Dengan fitur ini, pengguna dapat melihat setiap sudut kamar, fasilitas, dan tata letak ruangan secara interaktif, seolah-olah mereka berada langsung di dalam kamar tersebut. Tujuan utama fitur ini adalah untuk:

*   **Meningkatkan Transparansi:** Memberikan gambaran yang sangat jelas mengenai kondisi kamar, mengurangi keraguan calon penyewa.
*   **Mengurangi Waktu Survei Fisik:** Calon penyewa dapat melakukan "pra-survei" dari rumah, sehingga hanya yang benar-benar tertarik yang akan menjadwalkan kunjungan fisik.
*   **Meningkatkan Konversi:** Pengalaman yang lebih kaya dan transparan akan membangun kepercayaan dan mempercepat keputusan penyewaan.
*   **Diferensiasi Kompetitif:** Menawarkan keunggulan modern dibandingkan dengan kompetitor yang hanya menyediakan foto statis.

Fitur ini akan diintegrasikan secara mulus ke dalam halaman detail setiap kamar, melengkapi galeri foto dan deskripsi yang sudah ada.

### 2. Alur Pengguna (User Flow)

#### A. Alur Pengguna: Pencari Kos (Siska)

1.  **Akses Website:** Siska membuka website "Griya Kost Harmoni" melalui *smartphone* atau *desktop*.
2.  **Jelajah Katalog:** Siska menelusuri daftar kamar yang tersedia di bagian "Showcase / Katalog Kamar".
3.  **Pilih Kamar:** Siska tertarik pada salah satu kamar dan mengklik untuk melihat detail lebih lanjut.
4.  **Lihat Detail Kamar:** Pada halaman detail kamar, Siska melihat foto-foto, deskripsi, fasilitas, dan harga.
5.  **Akses Virtual Tour:** Siska menemukan tombol atau tautan yang menonjol berlabel **"Lihat Virtual Tour 360°"** atau ikon yang relevan, biasanya ditempatkan di dekat galeri foto atau di bagian atas deskripsi.
6.  **Interaksi Virtual Tour:** Siska mengklik tombol/tautan tersebut. Sebuah *modal* atau bagian baru akan terbuka, menampilkan antarmuka *viewer* 360 derajat. Siska dapat menggeser (pan), memperbesar (zoom), dan menjelajahi seluruh sudut kamar secara interaktif menggunakan *touch gesture* (di *smartphone*) atau *mouse* (di *desktop*).
7.  **Tindakan Lanjut:** Setelah selesai menjelajahi, Siska dapat menutup *modal* virtual tour dan melanjutkan untuk menghubungi pemilik via WhatsApp ("Hubungi via WhatsApp") atau kembali ke daftar kamar.

#### B. Alur Pengelola: Pemilik Kos / ReyDev Admin (Pak Budi)

1.  **Persiapan Konten:** Pak Budi menyediakan file gambar panorama 360 derajat (atau ReyDev membantu dalam proses ini jika layanan *content creation* termasuk).
2.  **Upload & Link:** Melalui panel administrasi yang disediakan oleh ReyDev (atau dibantu oleh tim ReyDev), file gambar 360 derajat diunggah dan ditautkan ke kamar kos yang sesuai.
3.  **Publikasi:** Setelah ditautkan, fitur virtual tour akan otomatis muncul di halaman detail kamar yang relevan di *frontend* website.

### 3. Komponen Teknis yang Ditambahkan/Diubah

Untuk mengimplementasikan fitur Virtual Tour 360 Derajat, beberapa komponen teknis akan ditambahkan atau diubah:

#### 3.1. Front-end (UI/UX)

*   **Tombol/Link Virtual Tour:** Penambahan elemen UI (tombol atau ikon) di halaman detail kamar untuk memicu tampilan virtual tour.
*   **360° Viewer Component:** Integrasi pustaka JavaScript atau komponen UI yang mampu merender dan menginteraksi dengan gambar panorama 360 derajat (misalnya: Three.js, A-Frame, React VR, atau solusi *embed* dari platform 360° tour pihak ketiga).
*   **Modal/Overlay Component:** Untuk menampilkan *viewer* 360 derajat secara *pop-up* tanpa meninggalkan halaman detail kamar.
*   **Optimasi Performa:** Implementasi *lazy loading* untuk aset gambar 360 derajat (yang cenderung berukuran besar) agar tidak membebani waktu *load* halaman utama. Responsi terhadap berbagai ukuran layar (*mobile-first*).

#### 3.2. Back-end & Data Model

*   **Database Schema Update:** Penambahan kolom baru pada entitas `Kamar` (Room) untuk menyimpan URL atau ID unik dari file panorama 360 derajat (misal: `virtual_tour_url` tipe `STRING`).
*   **API Endpoint Modification:** API yang melayani detail kamar akan diperbarui untuk menyertakan `virtual_tour_url` sebagai bagian dari respons data.
*   **Content Management System (CMS) / Admin Interface:**
    *   Penambahan bidang input di panel admin ReyDev untuk memungkinkan pengelola (atau tim ReyDev) mengunggah atau menautkan URL file gambar 360 derajat ke kamar tertentu.
    *   Validasi format file (misal: JPG/PNG equirectangular) dan ukuran file.

#### 3.3. Infrastruktur & Penyimpanan

*   **Penyimpanan Aset Digital (CDN/Cloud Storage):** File gambar panorama 360 derajat akan disimpan di layanan penyimpanan *cloud* yang dioptimalkan untuk pengiriman konten cepat (misal: Google Cloud Storage, AWS S3) dan disajikan melalui CDN (Content Delivery Network) untuk performa global yang optimal.
*   **Bandwidth:** Mempertimbangkan peningkatan kebutuhan *bandwidth* karena ukuran file gambar 360 derajat yang lebih besar.

#### 3.4. Proses Konten

*   **Panduan Pembuatan Konten:** ReyDev perlu menyediakan panduan atau rekomendasi spesifikasi teknis untuk pembuatan gambar panorama 360 derajat yang optimal (resolusi, format, dll.) kepada Pak Budi.
*   **Proses Upload & Review:** Menetapkan proses yang jelas untuk mengunggah, menautkan, dan meninjau konten virtual tour sebelum dipublikasikan.

---
```