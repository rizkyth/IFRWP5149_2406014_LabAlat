# Laporan Praktikum Pertemuan 4

## Sistem Informasi Peminjaman dan Pengembalian Peralatan Laboratorium

### Identitas

| Elemen | Keterangan |
|---|---|
| Nama | Rizky Taupik Hidayat |
| NIM | 2406014 |
| Kelas | Informatika A |
| Kakas | Draw.io |
| Praktikum | Analisis dan Desain Berorientasi Objek |

## 1. Tujuan

Memperluas model Sistem Informasi Peminjaman dan Pengembalian Peralatan Laboratorium dari Pertemuan 3 dengan fungsi pengelolaan peralatan dan pencatatan pengembalian. Pemodelan menggunakan *generalization* aktor dan use case, serta *collaboration* untuk merealisasikan Ajukan Peminjaman dan Catat Pengembalian Peralatan.

## 2. Kegiatan

1. Mempertahankan fungsi dan kebutuhan LAB-R01 sampai LAB-R06 dari Pertemuan 3.
2. Menambahkan kebutuhan LAB-R07 sampai LAB-R11 untuk peran peminjam, pengelolaan peralatan, pencatatan pengembalian, pemeriksaan kondisi, dan *collaboration*.
3. Menetapkan Peminjam sebagai aktor umum dengan Mahasiswa dan Dosen sebagai aktor khusus.
4. Menetapkan Kelola Data Peralatan sebagai use case umum dengan Tambah, Ubah, dan Hapus Data Peralatan sebagai use case khusus.
5. Menetapkan LAB-CO01 untuk Ajukan Peminjaman dan LAB-CO02 untuk Catat Pengembalian Peralatan.
6. Menguji diagram kumulatif terhadap aturan peminjaman, pengembalian, dan batas sistem.

## 3. Hasil

### Cakupan model

Skenario menetapkan lima aktor: Peminjam, Mahasiswa, Dosen, Petugas Laboratorium, dan Kepala Laboratorium. Use case yang dicakup ialah Lihat Ketersediaan Peralatan, Kelola Data Peralatan, Ajukan Peminjaman, Periksa Ketersediaan, Cetak Bukti Pengajuan, Proses Keputusan Peminjaman, Lihat Laporan Peminjaman, Tambah Data Peralatan, Ubah Data Peralatan, Hapus Data Peralatan, Catat Pengembalian Peralatan, dan Periksa Kondisi Peralatan.

Aturan penting yang harus dipertahankan adalah pengembalian hanya dapat dicatat untuk peminjaman berstatus Dipinjam; kondisi dicatat sebagai Baik, Rusak Ringan, atau Rusak Berat; dan peralatan yang sedang dipinjam atau memiliki pengajuan aktif tidak dapat dihapus. Keterlambatan dan denda dinyatakan di luar cakupan model.

### Artefak dan evaluasi

Artefak diagram LAB yang tersedia adalah berkas PNG [P04_2406014_LAB_notasi_usecase_v01.png](../04_model_analisi/P04/LAB/P04_2406014_LAB_notasi_usecase_v01.png). Berkas editable `.drawio` untuk diagram LAB tidak ditemukan di folder model.

Pemeriksaan terhadap diagram PNG menemukan beberapa hal yang perlu direvisi sebelum model dinyatakan konsisten:

1. Aktor Mahasiswa tampak digambar dua kali, sementara generalization aktor Peminjam kepada Mahasiswa dan Dosen belum tampak dengan jelas. Tampilkan satu aktor untuk tiap peran dan arahkan generalization dari aktor khusus ke Peminjam.
2. Use case Periksa Ketersediaan tampak muncul dua kali. Pertahankan satu use case dan hubungkan sebagai perilaku yang di-include oleh Ajukan Peminjaman.
3. Catat Pengembalian Peralatan tampak terhubung ke Proses Keputusan Peminjaman, sedangkan Periksa Kondisi Peralatan tampak di-include oleh Proses Keputusan. Hubungan ini tidak sesuai skenario; Periksa Kondisi Peralatan merupakan bagian dari Catat Pengembalian Peralatan.
4. Realization untuk LAB-CO01 dan LAB-CO02 belum terlihat jelas pada artefak PNG. Tambahkan dan pastikan masing-masing menunjuk pada use case yang direalisasikannya.
5. Periksa kembali bahwa tiga use case khusus Tambah, Ubah, dan Hapus Data Peralatan memiliki generalization yang benar terhadap Kelola Data Peralatan.

Dengan temuan tersebut, diagram yang tersedia belum memenuhi kriteria penerimaan bahwa seluruh kebutuhan LAB-R01 sampai LAB-R11 terwakili dan hubungan antarunsur konsisten dengan skenario.

## 4. Kesimpulan

Skenario Pertemuan 4 telah menetapkan perluasan kebutuhan dan struktur aktor, use case, serta collaboration untuk sistem laboratorium. Namun, diagram PNG yang tersedia masih memerlukan revisi pada generalization aktor, duplikasi use case, hubungan pencatatan pengembalian dengan pemeriksaan kondisi, dan penandaan realization. Simpan diagram editable yang telah diperbaiki beserta ekspornya agar hasil dapat ditinjau dan diperbarui.

## 5. Referensi Artefak

- Skenario: `01_skenario/P04_LAB_skenario_v01.md`
- Diagram PNG: `04_model_analisi/P04/LAB/P04_2406014_LAB_notasi_usecase_v01.png`
