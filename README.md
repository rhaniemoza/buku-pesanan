# Buku Pesanan — Syifa Dapur Nusantara

Aplikasi pencatatan pesanan untuk jualan masakan offline Syifa Dapur Nusantara.
Dibangun 25 November 2026.

> Catatan: repo ini berisi **dokumentasi** aplikasinya. Aplikasi webnya
> berjalan di platform Muse (aplikasi full-stack dengan data tersimpan), jadi
> kode sumbernya tidak ada di repo ini.

## Fitur

- Ringkasan: pesanan hari ini / belum selesai / omzet hari ini / belum lunas
  (lunas dipecah per cara bayar: Cash / QRIS / Transfer).
- Daftar pesanan per tanggal: nama, nomor WA + tombol Chat WA, isi pesanan,
  total otomatis, jam ambil/antar dan alamat.
- Status pesanan: Baru → Diproses → Siap → Selesai.
- Pembayaran per pesanan: Belum Bayar / Lunas + cara bayar (Cash/QRIS/Transfer).
- Filter: Semua / Belum bayar / Lunas.
- Tab **Menu & Harga**: isi menu sekali, lalu quick-tap saat input pesanan.

## Menu (per 25 November 2026)

| Menu | Harga |
| --- | --- |
| Ayam suwir kemangi | Rp8.000 |
| Ayam Sambal | Rp8.000 |
| Ayam geprek + (tahu/tempe) sambal, lalapan | Rp10.000 |
| Ayam penyet + (tahu/tempe) sambal, lalapan | Rp10.000 |
| Ayam serundeng + (tahu/tempe) sambal, lalapan | Rp10.000 |
| Soto Ayam | Rp10.000 |
| Nasi + Ayam geprek | Rp12.000 |
| Nasi + Ayam penyet | Rp12.000 |
| Nasi + Ayam sambal (tahu/tempe, sayur) | Rp12.000 |
| Nasi + Ayam serundeng | Rp12.000 |

## Alur pesanan

1. Pembeli chat lewat WhatsApp biasa (pembeli tidak mau isi form).
2. Penjual forward chat ke Muse, atau pelanggan isi Form Pemesanan
   (lihat repo `form-pemesanan`) / Form Pemesanan Google.
3. Pesanan masuk ke Buku Pesanan — data yang kurang dilengkapi dengan
   default (nama dari chat, hari ini, ambil sendiri, Belum Bayar),
   bisa diedit belakangan.
4. Jawaban Form Pemesanan Google tersinkron otomatis ke Buku Pesanan
   tiap 30 menit.

## Skema nomor WhatsApp

- Promo tetap pakai **nomor utama**.
- Pesanan dialihkan ke **nomor baru/bot** — setiap promo mencantumkan nomor
  baru, pelanggan memesan ke nomor baru itu. Bot WA (WAHA) menempel di nomor
  baru dan merekap pesanan otomatis ke Buku Pesanan. Nomor utama tidak
  tersentuh otomatisasi.
