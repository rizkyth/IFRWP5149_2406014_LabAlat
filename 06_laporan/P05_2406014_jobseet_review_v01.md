# Laporan Praktikum Pertemuan 5

## Skenario Use Case Sistem Informasi Peminjaman dan Pengembalian Peralatan Laboratorium

### Identitas

| Elemen | Keterangan |
|---|---|
| Nama | Rizky Taupik Hidayat |
| NIM | 2406014 |
| Kelas | Informatika A |
| Kakas | Draw.io |
| Praktikum | Analisis dan Desain Berorientasi Objek |

## 1. Tujuan

Menyusun skenario use case LAB sebagai penjabaran interaksi aktor dan sistem, termasuk alur normal, alternatif, hasil akhir, serta aturan bisnis untuk peminjaman, pengelolaan peralatan, keputusan peminjaman, dan pengembalian.

## 2. Kegiatan

1. Menjabarkan skenario untuk use case LAB-UC01 sampai LAB-UC12.
2. Menuliskan respons sistem untuk alur normal dan kondisi alternatif.
3. Menjelaskan penggunaan `include`, `extend`, generalization, dan realization sesuai hubungan use case.
4. Memastikan aturan pengembalian dan kondisi peralatan tercermin dalam skenario.

## 3. Hasil

Skenario LAB mencakup fungsi berikut:

- Peminjam melihat ketersediaan peralatan dan mengajukan peminjaman. Sistem memeriksa ketersediaan, memeriksa kelengkapan data, menyimpan pengajuan dengan status Menunggu Keputusan, dan memberikan nomor pengajuan.
- Pemeriksaan ketersediaan dijalankan dalam alur Ajukan Peminjaman. Cetak Bukti Pengajuan menjadi cabang opsional untuk mahasiswa yang memilih mencetak bukti.
- Petugas mengelola data peralatan melalui fungsi tambah, ubah, dan hapus. Penghapusan ditolak jika peralatan sedang dipinjam atau memiliki pengajuan aktif.
- Petugas memproses keputusan pengajuan, sementara Kepala Laboratorium melihat laporan peminjaman.
- Petugas mencatat pengembalian hanya untuk peminjaman berstatus Dipinjam. Sistem memeriksa kondisi peralatan dengan pilihan Baik, Rusak Ringan, atau Rusak Berat.
- Ajukan Peminjaman dinyatakan direalisasikan oleh LAB-CO01, sedangkan Catat Pengembalian Peralatan direalisasikan oleh LAB-CO02.

Sumber yang ditinjau:

- Skenario Markdown: [P05_LAB_skenario_v01.md](../01_skenario/P05_LAB_skenario_v01.md)
- Artefak Draw.io yang tersedia: [P05_2406014_LAB_sekenario.drawio](../04_model_analisi/P05/LAB/P05_2406014_LAB_sekenario.drawio)

## 4. Evaluasi dan Tindak Lanjut

1. Periksa konsistensi diagram kumulatif P04 dengan skenario yang dirinci pada P05. Khususnya, hubungkan Periksa Kondisi Peralatan ke Catat Pengembalian Peralatan, bukan ke Proses Keputusan Peminjaman.
2. Pastikan dua realization yang dinyatakan dalam skenario benar-benar tampak pada diagram: LAB-CO01 ke Ajukan Peminjaman dan LAB-CO02 ke Catat Pengembalian Peralatan.
3. Berkas Draw.io P05 yang tersedia bernama `...LAB_sekenario.drawio` dan berisi materi skenario use case. Berkas itu tidak dapat dianggap sebagai diagram kumulatif hasil pemodelan tanpa pemeriksaan atau ekspor diagram yang sesuai.
4. Ada perbedaan rumusan mengenai denda: batasan P04 menyatakan keterlambatan dan denda belum dimodelkan dan harus menjadi pertanyaan terbuka, sedangkan skenario pengembalian P05 menyebut pengembalian tetap tercatat tanpa denda. Konfirmasikan rumusan ini dan jangan menetapkan aturan denda sebagai bagian model sebelum disepakati.
5. Pastikan checklist penilaian pada skenario dilengkapi setelah diagram dan skenario final diperiksa.

## 5. Kesimpulan

Skenario P05 telah menjabarkan alur utama dan alternatif untuk fungsi-fungsi laboratorium serta menetapkan aturan penting peminjaman dan pengembalian. Konsistensi akhir tetap bergantung pada revisi diagram kumulatif, penegasan realization kedua collaboration, penyelesaian perbedaan rumusan denda, dan verifikasi artefak diagram yang diserahkan.

## 6. Referensi Artefak

- Skenario: `01_skenario/P05_LAB_skenario_v01.md`
- Berkas Draw.io: `04_model_analisi/P05/LAB/P05_2406014_LAB_sekenario.drawio`
