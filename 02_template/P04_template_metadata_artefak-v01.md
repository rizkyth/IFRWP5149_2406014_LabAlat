# Identitas Artefak P04 — Use Case Diagram Peminjaman dan Pengembalian Peralatan

| Atribut                       | Keterangan                                                                                               |
| ----------------------------- | -------------------------------------------------------------------------------------------------------- |
| ID artefak                    | P04                                                                                                      |
| Judul                         | Use Case Diagram Sistem Informasi Peminjaman dan Pengembalian Peralatan Laboratorium                    |
| Pertemuan                     | 04                                                                                                       |
| Kebutuhan yang menjadi sumber | LAB-R01 sampai LAB-R11                                                                                   |
| Jenis/status                  | Use case diagram kumulatif; perlu revisi berdasarkan pemeriksaan                                         |
| Kakas                         | draw.io                                                                                                |
| Penyusun                      | Rizky Taupik Hidayat 2406014                                                                             |
| Versi dan tanggal             | v01 / 09-11-2026                                                                                         |
| Asumsi                        | Pengguna telah terautentikasi dan memiliki hak akses sesuai peran; perpindahan fisik peralatan di luar sistem |
| Pemeriksaan                   | Diagram PNG belum konsisten: revisi generalization, duplikasi use case, relasi pengembalian, realization, dan generalization use case |
| Riwayat revisi                | v01: metadata artefak P04 dibuat                                                                        |

## Cakupan dan catatan

Model mempertahankan LAB-R01 sampai LAB-R06 dari Pertemuan 3 dan menambahkan LAB-R07 sampai LAB-R11. Cakupan tambahannya meliputi aktor umum Peminjam dengan Mahasiswa dan Dosen sebagai aktor khusus, generalization Kelola Data Peralatan dengan use case Tambah/Ubah/Hapus, Catat Pengembalian Peralatan beserta pemeriksaan kondisi, serta collaboration LAB-CO01 dan LAB-CO02.

Temuan pemeriksaan pada artefak PNG: pastikan generalization aktor mengarah dari Mahasiswa dan Dosen ke Peminjam; tampilkan satu Periksa Ketersediaan yang di-include oleh Ajukan Peminjaman; jadikan Periksa Kondisi Peralatan bagian dari Catat Pengembalian Peralatan; tampilkan realization LAB-CO01 dan LAB-CO02 dengan jelas; dan pastikan Tambah, Ubah, serta Hapus Data Peralatan merupakan spesialisasi Kelola Data Peralatan.

Pengembalian hanya dapat dicatat untuk peminjaman berstatus Dipinjam. Kondisi peralatan dicatat sebagai Baik, Rusak Ringan, atau Rusak Berat. Penghapusan peralatan yang sedang dipinjam atau memiliki pengajuan aktif tidak diperbolehkan. Keterlambatan dan denda berada di luar cakupan.
