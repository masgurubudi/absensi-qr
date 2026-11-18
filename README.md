# Aplikasi Absensi Siswa QR — Versi Demo (untuk Sosialisasi)

Salinan aplikasi Absensi Siswa QR "Presensi Siswa" (versi demo untuk sosialisasi ke sekolah lain)
untuk diperkenalkan ke sekolah lain. Tampilannya dan cara kerjanya persis sama
dengan aplikasi sebenarnya, dengan 3 perbedaan:

1. **Data contoh, bukan data asli** — 12 siswa fiktif (VII A, VIII B, IX C;
   NIS 2401–2412). Bukan data siswa asli.
2. **PIN demo (bukan PIN asli)** — Scan Absensi dan Rekap Guru memakai PIN Guru,
   Kartu & QR memakai PIN Super Admin, Orang Tua tanpa PIN — seperti aplikasi
   sebenarnya, supaya terlihat bahwa menu guru/admin dijaga PIN. Bedanya, di
   demo PIN apa saja diterima, yang penting diisi.
3. **Tanpa cloud** — tidak ada Firebase/Firestore. Semua catatan hanya tersimpan
   di perangkat yang membuka halaman ini (IndexedDB) dan tidak pernah dikirim
   ke mana pun. Pengaturan Jadwal hanya berlaku di perangkat ini.

Mulai dari kosong: tidak ada catatan kehadiran awal — semua tercatat dari scan
atau penandaan yang dilakukan di perangkat ini.

## File

| File | Isi |
|---|---|
| `index.html` | Aplikasi (satu halaman: Scan, Rekap Guru, Orang Tua, Kartu & QR) |
| `roster.js` | Daftar 12 siswa contoh (fiktif) |
| `jsQR.min.js` | Pustaka baca QR cadangan (lokal, v1.4.0) |
| `qrcode.min.js` | Pustaka gambar QR kartu (lokal, qrcodejs 1.0.0) |
| `sw.js` | Service worker — menyimpan app shell di HP |
| `manifest.webmanifest` | Manifest PWA (nama, ikon, tampil layar penuh) |

Ikon aplikasi (`icon-192.png`, `icon-512.png`) tidak ikut di-repo ini — ikon
instalasi PWA memakai bawaan saja, sama seperti aplikasi sebenarnya.

## Fitur (sama seperti aplikasi sebenarnya)

- 4 mode scan: Datang, Sholat Dhuhur, Pulang, Scan Berhalangan — dengan aturan
  yang sama (masuk 07.00, terlambat lewat 07.00; pulang Senin 14.40,
  Selasa–Kamis 14.00, Jumat 11.00; Sabtu libur).
- Pemindai kamera + cara cadangan (ketuk kartu nama / ketik NIS atau nama).
- Pencari siswa "Ketik NAMA atau NIS" di semua tempat, otomatis kosong saat
  panel/menu ditinggalkan.
- Rekap Harian, Mingguan, Bulanan, dan Sholat Dhuhur + unduh CSV; form Tandai
  Sakit/Izin oleh wali kelas.
- Halaman Orang Tua untuk memantau kehadiran anak; halaman Kartu & QR untuk
  mengunduh/mencetak kartu siswa.
- Bekerja offline setelah sekali dimuat (service worker + IndexedDB).

Buka: https://masgurubudi.github.io/absensi-qr/
