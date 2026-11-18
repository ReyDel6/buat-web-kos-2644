# Technical Specification (TECH_SPEC.md)
**Proyek:** Buat Web Kos  
**Lead System Architect:** Arka (ReyDev Web Studio)  
**Status:** Draft / Approved  
**Tanggal:** 24 Mei 2024  

---

## 1. Tech Stack
Mengingat kebutuhan proyek "Buat Web Kos" yang menuntut kecepatan *development*, performa tinggi, dan kemudahan *deployment* tanpa kompleksitas *build tool* yang berlebihan (seperti Webpack/Vite untuk MVP), kita akan menggunakan *stack* modern berbasis *vanilla* yang dioptimasi.

*   **Markup (Struktur):** HTML5 Semantik (`<header>`, `<main>`, `<section>`, `<article>`, `<aside>`, `<footer>`) untuk memastikan aksesibilitas (a11y) dan *SEO-friendly*.
*   **Styling:** Tailwind CSS (via CDN - Play CDN untuk efisiensi pengembangan tahap awal, dengan konfigurasi *custom theme* via script tag).
*   **Logika & Interaksi:** Vanilla ES6+ Modular (menggunakan ES Modules `import`/`export`) tanpa *framework* berat untuk menjaga *bundle size* mendekati 0 KB dan eksekusi browser yang instan.

---

## 2. Arsitektur Komponen UI
Kita mengadopsi pola **Component-Based Architecture** menggunakan *Web Components* (Vanilla Custom Elements) atau *Modular Function Render* yang dikelola oleh *DOM Renderer* sederhana. Struktur direktori dan komponen dibagi sebagai berikut:

```text
/
├── index.html
├── src/
│   ├── css/
│   │   └── custom.css          # Custom utility tambahan jika diperlukan
│   ├── js/
│   │   ├── app.js              # Entry point
│   │   ├── components/
│   │   │   ├── Navbar.js       # Navigasi & Auth state
│   │   │   ├── Hero.js         # Banner & Search bar utama
│   │   │   ├── FilterBar.js    # Filter harga, lokasi, fasilitas
│   │   │   ├── KosCard.js      # Kartu item kos (Grid/List)
│   │   │   ├── KosDetail.js    # Modal/Halaman detail kos
│   │   │   └── Footer.js       # Footer standar
│   │   ├── services/
│   │   │   ├── api.js          # Mock API / Fetch handler
│   │   │   └── storage.js      # LocalStorage wrapper
│   │   └── utils/
│   │       └── formatters.js   # Format Rupiah, tanggal, dll.
```

### Pola Render Komponen:
Setiap komponen adalah sebuah fungsi murni yang mengembalikan string HTML atau *DOM Node*, yang kemudian disuntikkan ke dalam *DOM root* oleh router/state manager sederhana.

---

## 3. State & Event Handling
Manajemen state dirancang dengan pola **Pub/Sub (Publish/Subscriber)** atau *Centralized Store* sederhana menggunakan Javascript `Proxy` untuk reaktivitas UI secara *real-time*.

### A. Centralized State (`store.js`)
```javascript
// Contoh konsep State Management
export const state = new Proxy({
    user: null,
    filters: {
        location: '',
        priceMax: 5000000,
        facilities: []
    },
    favorites: JSON.parse(localStorage.getItem('favorites')) || []
}, {
    set(target, property, value) {
        target[property] = value;
        // Trigger render ulang komponen yang mendengarkan perubahan ini
        window.dispatchEvent(new CustomEvent('stateChange', { detail: { property, value } }));
        return true;
    }
});
```

### B. Event Handling
*   **DOM Events:** Menggunakan *Event Delegation* pada *parent container* untuk meminimalkan *memory footprint* (terutama pada daftar kartu kos yang dinamis).
*   **Custom Events:** Komunikasi antar-komponen (misal: dari `FilterBar` ke `KosCard`) dilakukan via `CustomEvent` yang di-dispatch ke `window` atau *Event Bus* lokal.

---

## 4. SEO & Performance Target
Sebagai web properti (kos-kosan), visibilitas di mesin pencari (SEO) dan kecepatan muat (Performance) adalah prioritas utama untuk konversi pengguna.

### A. SEO Strategy
*   **Meta Tags Dinamis:** Setiap kali detail kos dibuka, JavaScript akan memperbarui `<title>`, meta `description`, dan Open Graph (OG) tags secara dinamis untuk keperluan *social sharing* (WhatsApp, Telegram).
*   **Structured Data (Schema.org):** Menggunakan format JSON-LD untuk tipe `LodgingBusiness` atau `Accommodation` agar Google dapat menampilkan informasi harga dan lokasi langsung di hasil pencarian (Rich Snippets).
*   **Semantic HTML:** Penggunaan hierarki heading yang benar (`H1` untuk judul halaman/hero, `H2` untuk kategori/filter, `H3` untuk nama kos).

### B. Performance Targets (Core Web Vitals)
*   **LCP (Largest Contentful Paint):** < 2.0 detik. Gambar utama (Hero/Thumbnail kos pertama) wajib menggunakan atribut `loading="lazy"` untuk *below-the-fold*, dan `fetchpriority="high"` untuk *above-the-fold*.
*   **INP (Interaction to Next Paint):** < 200 ms. Memastikan *event listener* pada filter dan pencarian tidak memblokir *main thread* (menggunakan *debouncing* pada input pencarian).
*   **CLS (Cumulative Layout Shift):** 0 (Nol). Semua elemen kontainer gambar dan kartu kos harus memiliki dimensi tetap (`aspect-ratio` atau ukuran eksplisit via Tailwind) sebelum data dimuat untuk mencegah pergeseran layout.
*   **Asset Optimization:** Gambar properti dikirim dalam format modern (`WebP`) dengan kompresi otomatis melalui CDN pihak ketiga (misal: Cloudinary atau ImageKit).

---
*Dokumen ini bersifat hidup (living document) dan akan diperbarui seiring dengan perkembangan fase implementasi oleh tim ReyDev Web Studio.*