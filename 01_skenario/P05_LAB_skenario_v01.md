# Jobsheet Praktikum Pertemuan 5 - Skenario Use Case

# Sistem Informasi Peminjaman dan Pengembalian Peralatan Laboratorium

---

## Tabel 5.1 Skenario Use Case LAB-UC03 Ajukan Peminjaman

| Field             | Value                                                                                     |
| ----------------- | ----------------------------------------------------------------------------------------- |
| **Nama use case** | LAB-UC03 Ajukan Peminjaman                                                                |
| **Aktor**         | Peminjam (berlaku untuk Mahasiswa dan Dosen)                                              |
| **Tujuan**        | Pengajuan peminjaman tercatat dan dapat diproses oleh petugas                             |
| **Deskripsi**     | Peminjam memilih peralatan yang tersedia, mengisi data peminjaman, dan mengirim pengajuan |

| Kegiatan                                                                                                                                                                                         | Respon sistem                                                                                                                                                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Skenario Normal**                                                                                                                                                                              |                                                                                                                                                                                                                               |
| 1. Peminjam memilih peralatan yang akan dipinjam                                                                                                                                                 | 2. Sistem menjalankan Periksa Ketersediaan (lihat Tabel skenario LAB-UC04)                                                                                                                                                    |
| 3. Peminjam mengisi tanggal pinjam, tanggal rencana kembali, dan keperluan peminjaman                                                                                                            | 4. Sistem memeriksa kelengkapan isian dan menampilkan ringkasan pengajuan                                                                                                                                                     |
| 5. Peminjam mengirim pengajuan                                                                                                                                                                   | 6. Sistem menyimpan pengajuan dengan status Menunggu Keputusan dan menampilkan nomor pengajuan                                                                                                                                |
| **Skenario Alternative**                                                                                                                                                                         |                                                                                                                                                                                                                               |
| 7. Peralatan yang dipilih tidak tersedia (cabang dari langkah 2)                                                                                                                                 | 8. Sistem menampilkan pesan peralatan tidak tersedia dan pengajuan tidak dilanjutkan                                                                                                                                          |
| 9. Isian pengajuan tidak lengkap (cabang dari langkah 4)                                                                                                                                         | 10. Sistem menampilkan pesan isian belum lengkap dan meminta peminjam melengkapi isian                                                                                                                                        |
| 11. Peminjam memilih cetak bukti, dengan condition [mahasiswa memilih cetak] dan extension point Bukti pengajuan tersedia (extend LAB-UC05 Cetak Bukti Pengajuan; lihat Tabel skenario LAB-UC05) | 12. Sistem menampilkan bukti pengajuan dengan nomor pengajuan sesuai Tabel skenario LAB-UC05                                                                                                                                  |
| **Skenario Akhir**                                                                                                                                                                               | Use case selesai jika pengajuan tersimpan dengan status Menunggu Keputusan; jika peralatan tidak tersedia atau isian tidak lengkap, pengajuan tidak tersimpan dan peminjam kembali ke daftar peralatan atau melengkapi isian. |

Keterangan: use case ini direalisasikan oleh collaboration LAB-CO01 Ajukan Peminjaman.

---

## Tabel 5.2 Skenario Use Case LAB-UC01 Lihat Ketersediaan Peralatan

| Field             | Value                                                                                            |
| ----------------- | ------------------------------------------------------------------------------------------------ |
| **Nama use case** | LAB-UC01 Lihat Ketersediaan Peralatan                                                            |
| **Aktor**         | Peminjam (berlaku untuk Mahasiswa dan Dosen)                                                     |
| **Tujuan**        | Peminjam dapat mengetahui peralatan yang tersedia sebelum mengajukan peminjaman                  |
| **Deskripsi**     | Peminjam membuka fungsi ketersediaan dan melihat daftar peralatan beserta status ketersediaannya |

| Kegiatan                                                                 | Respon sistem                                                                                                                                                      |
| ------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Skenario Normal**                                                      |                                                                                                                                                                    |
| 1. Peminjam membuka fungsi Lihat Ketersediaan Peralatan                  | 2. Sistem menampilkan daftar peralatan beserta status ketersediaannya                                                                                              |
| **Skenario Alternative**                                                 |                                                                                                                                                                    |
| 3. Tidak ada peralatan yang tersedia pada daftar (cabang dari langkah 2) | 4. Sistem menampilkan pesan tidak ada peralatan yang tersedia                                                                                                      |
| **Skenario Akhir**                                                       | Use case selesai jika daftar peralatan beserta status ketersediaannya ditampilkan; jika tidak ada peralatan yang tersedia, use case selesai dengan pesan tersebut. |

---

## Tabel 5.3 Skenario Use Case LAB-UC04 Periksa Ketersediaan

| Field             | Value                                                                                                                                                                                                       |
| ----------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Nama use case** | LAB-UC04 Periksa Ketersediaan                                                                                                                                                                               |
| **Aktor**         | Peminjam (berjalan di dalam LAB-UC03 Ajukan Peminjaman)                                                                                                                                                     |
| **Tujuan**        | Ketersediaan peralatan yang dipilih terperiksa sebelum pengajuan disimpan                                                                                                                                   |
| **Deskripsi**     | Sistem memeriksa jumlah dan status peralatan yang dipilih peminjam dan menyampaikan hasilnya kepada alur pengajuan. Use case ini berjalan di dalam UC03 dan tidak mempunyai interaksi langsung dengan aktor |

| Kegiatan                                                                        | Respon sistem                                                                                                                                                 |
| ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Skenario Normal**                                                             |                                                                                                                                                               |
| 1. Alur pengajuan memanggil Periksa Ketersediaan dengan peralatan yang dipilih  | 2. Sistem memeriksa jumlah dan status peralatan tersebut                                                                                                      |
| 3. Sistem menyatakan peralatan tersedia                                         | 4. Alur pengajuan melanjutkan penyimpanan pengajuan                                                                                                           |
| **Skenario Alternative**                                                        |                                                                                                                                                               |
| 5. Peralatan tidak tersedia atau jumlah tidak mencukupi (cabang dari langkah 2) | 6. Sistem menyampaikan hasil tidak tersedia sehingga alur pengajuan berhenti                                                                                  |
| **Skenario Akhir**                                                              | Use case selesai jika hasil pemeriksaan disampaikan kepada alur pengajuan; hasil tersedia melanjutkan pengajuan, hasil tidak tersedia menghentikan pengajuan. |

---

## Tabel 5.4 Skenario Use Case LAB-UC05 Cetak Bukti Pengajuan

| Field             | Value                                                                                                                                                                                                                            |
| ----------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Nama use case** | LAB-UC05 Cetak Bukti Pengajuan                                                                                                                                                                                                   |
| **Aktor**         | Mahasiswa (asosiasi khusus)                                                                                                                                                                                                      |
| **Tujuan**        | Bukti pengajuan tercetak sebagai tambahan bersyarat pada pengajuan                                                                                                                                                               |
| **Deskripsi**     | Mahasiswa yang memilih cetak pada konfirmasi pengajuan menerima bukti pengajuan dengan nomor pengajuan. Cabang ini berlaku dengan condition [mahasiswa memilih cetak] dan extension point Bukti pengajuan tersedia pada LAB-UC03 |

| Kegiatan                                                   | Respon sistem                                                                                                                  |
| ---------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| **Skenario Normal**                                        |                                                                                                                                |
| 1. Mahasiswa memilih cetak bukti pada konfirmasi pengajuan | 2. Sistem menampilkan bukti pengajuan dengan nomor pengajuan dan status Menunggu Keputusan                                     |
| 3. Mahasiswa mengonfirmasi pencetakan                      | 4. Sistem mencetak bukti pengajuan                                                                                             |
| **Skenario Alternative**                                   |                                                                                                                                |
| 5. Mahasiswa tidak memilih cetak (cabang dari langkah 1)   | 6. Sistem menutup konfirmasi tanpa mencetak bukti dan pengajuan tetap tersimpan                                                |
| **Skenario Akhir**                                         | Use case selesai jika bukti pengajuan tercetak; jika mahasiswa tidak memilih cetak, pengajuan tetap selesai tanpa bukti cetak. |

---

## Tabel 5.5 Skenario Use Case LAB-UC02 Kelola Data Peralatan

| Field             | Value                                                                                                                                                                                |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Nama use case** | LAB-UC02 Kelola Data Peralatan                                                                                                                                                       |
| **Aktor**         | Petugas Laboratorium                                                                                                                                                                 |
| **Tujuan**        | Data peralatan terkelola melalui satu fungsi pengelolaan bersama                                                                                                                     |
| **Deskripsi**     | Petugas membuka fungsi pengelolaan data peralatan, memilih bentuk pengelolaan, dan menyimpan perubahan. Bentuk tambah, ubah, dan hapus dijabarkan pada tabel khususnya masing-masing |

| Kegiatan                                                              | Respon sistem                                                                                                                |
| --------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| **Skenario Normal**                                                   |                                                                                                                              |
| 1. Petugas membuka fungsi Kelola Data Peralatan                       | 2. Sistem menampilkan daftar data peralatan                                                                                  |
| 3. Petugas memilih bentuk pengelolaan, yaitu tambah, ubah, atau hapus | 4. Sistem menampilkan formulir sesuai bentuk pengelolaan yang dipilih                                                        |
| 5. Petugas mengisi atau mengonfirmasi data                            | 6. Sistem memeriksa kelengkapan dan keabsahan data                                                                           |
| 7. Petugas menyimpan perubahan                                        | 8. Sistem menyimpan perubahan dan menampilkan konfirmasi                                                                     |
| **Skenario Alternative**                                              |                                                                                                                              |
| 9. Data tidak lengkap atau tidak sah (cabang dari langkah 6)          | 10. Sistem menolak penyimpanan dan menampilkan pesan kesalahan data                                                          |
| **Skenario Akhir**                                                    | Use case selesai jika perubahan data peralatan tersimpan; jika data tidak lengkap atau tidak sah, perubahan tidak tersimpan. |

---

## Tabel 5.6 Skenario Use Case LAB-UC08 Tambah Data Peralatan

| Field             | Value                                                                                                              |
| ----------------- | ------------------------------------------------------------------------------------------------------------------ |
| **Nama use case** | LAB-UC08 Tambah Data Peralatan                                                                                     |
| **Aktor**         | Petugas Laboratorium                                                                                               |
| **Tujuan**        | Data peralatan baru tersimpan sebagai bentuk khusus dari pengelolaan data peralatan                                |
| **Deskripsi**     | Petugas mengisi data peralatan baru dan menyimpan data tersebut; langkah bersama mengikuti Tabel skenario LAB-UC02 |

| Kegiatan                                        | Respon sistem                                                                                       |
| ----------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| **Skenario Normal**                             |                                                                                                     |
| 1. Petugas membuka fungsi Tambah Data Peralatan | 2. Sistem menampilkan formulir data peralatan baru                                                  |
| 3. Petugas mengisi data peralatan baru          | 4. Sistem memeriksa kelengkapan data                                                                |
| 5. Petugas menyimpan data                       | 6. Sistem menyimpan data peralatan baru dan menampilkan konfirmasi                                  |
| **Skenario Alternative**                        |                                                                                                     |
| 7. Data tidak lengkap (cabang dari langkah 4)   | 8. Sistem menolak penyimpanan dan meminta petugas melengkapi data                                   |
| **Skenario Akhir**                              | Use case selesai jika data peralatan baru tersimpan; jika data tidak lengkap, data tidak tersimpan. |

Keterangan: use case khusus dari LAB-UC02 Kelola Data Peralatan. Perilaku pembeda: data baru tersimpan. Langkah bersama mengikuti Tabel skenario LAB-UC02.

---

## Tabel 5.7 Skenario Use Case LAB-UC09 Ubah Data Peralatan

| Field             | Value                                                                                                                        |
| ----------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| **Nama use case** | LAB-UC09 Ubah Data Peralatan                                                                                                 |
| **Aktor**         | Petugas Laboratorium                                                                                                         |
| **Tujuan**        | Data peralatan berubah sebagai bentuk khusus dari pengelolaan data peralatan                                                 |
| **Deskripsi**     | Petugas memilih data peralatan, mengubah datanya, dan menyimpan perubahan; langkah bersama mengikuti Tabel skenario LAB-UC02 |

| Kegiatan                                                  | Respon sistem                                                                                                   |
| --------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| **Skenario Normal**                                       |                                                                                                                 |
| 1. Petugas memilih data peralatan yang akan diubah        | 2. Sistem menampilkan data peralatan saat ini                                                                   |
| 3. Petugas mengubah data peralatan                        | 4. Sistem memeriksa perubahan data                                                                              |
| 5. Petugas menyimpan perubahan                            | 6. Sistem menyimpan data yang diubah dan menampilkan konfirmasi                                                 |
| **Skenario Alternative**                                  |                                                                                                                 |
| 7. Data peralatan tidak ditemukan (cabang dari langkah 2) | 8. Sistem menampilkan pesan data peralatan tidak ditemukan                                                      |
| **Skenario Akhir**                                        | Use case selesai jika perubahan data peralatan tersimpan; jika data tidak ditemukan, perubahan tidak tersimpan. |

Keterangan: use case khusus dari LAB-UC02 Kelola Data Peralatan. Perilaku pembeda: data peralatan berubah. Langkah bersama mengikuti Tabel skenario LAB-UC02.

---

## Tabel 5.8 Skenario Use Case LAB-UC10 Hapus Data Peralatan

| Field             | Value                                                                                                                                            |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Nama use case** | LAB-UC10 Hapus Data Peralatan                                                                                                                    |
| **Aktor**         | Petugas Laboratorium                                                                                                                             |
| **Tujuan**        | Data peralatan terhapus sebagai bentuk khusus dari pengelolaan data peralatan                                                                    |
| **Deskripsi**     | Petugas memilih data peralatan, mengonfirmasi penghapusan, dan sistem menghapus data tersebut; langkah bersama mengikuti Tabel skenario LAB-UC02 |

| Kegiatan                                                                           | Respon sistem                                                                                                                     |
| ---------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| **Skenario Normal**                                                                |                                                                                                                                   |
| 1. Petugas memilih data peralatan yang akan dihapus                                | 2. Sistem memeriksa peralatan tidak sedang dipinjam dan tidak memiliki pengajuan aktif                                            |
| 3. Petugas mengonfirmasi penghapusan                                               | 4. Sistem menghapus data peralatan dan menampilkan konfirmasi penghapusan                                                         |
| **Skenario Alternative**                                                           |                                                                                                                                   |
| 5. Peralatan sedang dipinjam atau memiliki pengajuan aktif (cabang dari langkah 2) | 6. Sistem menolak penghapusan dan menampilkan pesan peralatan masih terpakai                                                      |
| **Skenario Akhir**                                                                 | Use case selesai jika data peralatan terhapus; jika peralatan sedang dipinjam atau memiliki pengajuan aktif, data tidak terhapus. |

Keterangan: use case khusus dari LAB-UC02 Kelola Data Peralatan. Perilaku pembeda: data peralatan terhapus, dengan syarat peralatan tidak sedang dipinjam dan tidak memiliki pengajuan aktif. Langkah bersama mengikuti Tabel skenario LAB-UC02.

---

## Tabel 5.9 Skenario Use Case LAB-UC06 Proses Keputusan Peminjaman

| Field             | Value                                                                                                                                   |
| ----------------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| **Nama use case** | LAB-UC06 Proses Keputusan Peminjaman                                                                                                    |
| **Aktor**         | Petugas Laboratorium                                                                                                                    |
| **Tujuan**        | Pengajuan peminjaman mendapat keputusan setuju atau tolak                                                                               |
| **Deskripsi**     | Petugas memeriksa pengajuan yang berstatus Menunggu Keputusan, menetapkan persetujuan atau penolakan, dan sistem menyampaikan keputusan |

| Kegiatan                                                                          | Respon sistem                                                                                                                |
| --------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| **Skenario Normal**                                                               |                                                                                                                              |
| 1. Petugas membuka daftar pengajuan yang berstatus Menunggu Keputusan             | 2. Sistem menampilkan daftar pengajuan tersebut                                                                              |
| 3. Petugas memilih pengajuan dan menetapkan persetujuan                           | 4. Sistem mengubah status pengajuan menjadi Disetujui dan menampilkan konfirmasi                                             |
| **Skenario Alternative**                                                          |                                                                                                                              |
| 5. Petugas menetapkan penolakan (cabang dari langkah 4)                           | 6. Sistem mengubah status pengajuan menjadi Ditolak dan menampilkan konfirmasi penolakan                                     |
| 7. Pengajuan tidak ditemukan atau statusnya sudah berubah (cabang dari langkah 2) | 8. Sistem menampilkan pesan pengajuan tidak dapat diproses                                                                   |
| **Skenario Akhir**                                                                | Use case selesai jika pengajuan berstatus Disetujui atau Ditolak; jika pengajuan tidak dapat diproses, status tidak berubah. |

---

## Tabel 5.10 Skenario Use Case LAB-UC07 Lihat Laporan Peminjaman

| Field             | Value                                                                                               |
| ----------------- | --------------------------------------------------------------------------------------------------- |
| **Nama use case** | LAB-UC07 Lihat Laporan Peminjaman                                                                   |
| **Aktor**         | Kepala Laboratorium                                                                                 |
| **Tujuan**        | Laporan peminjaman dapat dilihat oleh kepala laboratorium                                           |
| **Deskripsi**     | Kepala Laboratorium membuka fungsi laporan dan melihat laporan peminjaman pada periode yang dipilih |

| Kegiatan                                                                       | Respon sistem                                                                                                                |
| ------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------- |
| **Skenario Normal**                                                            |                                                                                                                              |
| 1. Kepala Laboratorium membuka fungsi Lihat Laporan Peminjaman                 | 2. Sistem menampilkan daftar periode laporan                                                                                 |
| 3. Kepala Laboratorium memilih periode                                         | 4. Sistem menampilkan laporan peminjaman periode tersebut                                                                    |
| **Skenario Alternative**                                                       |                                                                                                                              |
| 5. Tidak ada data peminjaman pada periode yang dipilih (cabang dari langkah 4) | 6. Sistem menampilkan pesan tidak ada data peminjaman pada periode tersebut                                                  |
| **Skenario Akhir**                                                             | Use case selesai jika laporan periode yang dipilih ditampilkan; jika tidak ada data, use case selesai dengan pesan tersebut. |

Keterangan: satu-satunya use case Kepala Laboratorium. Tabel ini berdiri sendiri dan tidak memuat langkah include, extend, generalization, atau realization.

---

## Tabel 5.11 Skenario Use Case LAB-UC11 Catat Pengembalian Peralatan

| Field             | Value                                                                                                                                                  |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Nama use case** | LAB-UC11 Catat Pengembalian Peralatan                                                                                                                  |
| **Aktor**         | Petugas Laboratorium                                                                                                                                   |
| **Tujuan**        | Pengembalian tercatat dan status peminjaman serta kondisi peralatan terbarui                                                                           |
| **Deskripsi**     | Petugas memilih peminjaman yang akan dikembalikan, mengonfirmasi alat yang kembali, dan menyimpan pencatatan. Prasyarat: peminjaman berstatus Dipinjam |

| Kegiatan                                                                                 | Respon sistem                                                                                                                                                                                                                                |
| ---------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Skenario Normal**                                                                      |                                                                                                                                                                                                                                              |
| 1. Petugas memilih peminjaman yang akan dikembalikan                                     | 2. Sistem menampilkan data peminjaman terpilih dan statusnya                                                                                                                                                                                 |
| 3. Petugas mengonfirmasi alat yang kembali dan jumlahnya                                 | 4. Sistem menampung konfirmasi petugas                                                                                                                                                                                                       |
| 5. Sistem memeriksa status peminjaman harus Dipinjam                                     | 6. Sistem menjalankan Periksa Kondisi Peralatan (lihat Tabel skenario LAB-UC12)                                                                                                                                                              |
| 7. Petugas menyimpan pencatatan                                                          | 8. Sistem menyimpan tanggal kembali dan kondisi serta mengubah status peminjaman menjadi Selesai                                                                                                                                             |
| 9. Petugas melihat konfirmasi pengembalian                                               | 10. Sistem menampilkan ringkasan                                                                                                                                                                                                             |
| **Skenario Alternative**                                                                 |                                                                                                                                                                                                                                              |
| 11. Status bukan Dipinjam (cabang dari langkah 5)                                        | 12. Sistem menolak pencatatan dan menampilkan status peminjaman saat ini                                                                                                                                                                     |
| 13. Kondisi Rusak Ringan atau Rusak Berat dicatat pada langkah 6 (cabang dari langkah 6) | 14. Sistem tetap menyimpan pencatatan, menandai kondisi tersebut pada data peralatan, dan pengembalian tetap tercatat tanpa denda                                                                                                            |
| 15. Jumlah alat yang kembali tidak sesuai (cabang dari langkah 3)                        | 16. Sistem meminta petugas memeriksa kembali isian sebelum penyimpanan                                                                                                                                                                       |
| **Skenario Akhir**                                                                       | Use case selesai jika pengembalian tercatat dengan tanggal kembali dan kondisi peralatan serta status peminjaman menjadi Selesai; jika status bukan Dipinjam, tidak ada pengembalian baru yang tercatat dan status peminjaman tidak berubah. |

Keterangan: use case ini direalisasikan oleh collaboration LAB-CO02 Catat Pengembalian Peralatan, tanpa langkah kegiatan sendiri.

---

## Tabel 5.12 Skenario Use Case LAB-UC12 Periksa Kondisi Peralatan

| Field             | Value                                                                                                                                                                                                           |
| ----------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Nama use case** | LAB-UC12 Periksa Kondisi Peralatan                                                                                                                                                                              |
| **Aktor**         | Petugas Laboratorium (berjalan di dalam LAB-UC11 Catat Pengembalian Peralatan)                                                                                                                                  |
| **Tujuan**        | Kondisi peralatan yang dikembalikan terperiksa dan tercatat                                                                                                                                                     |
| **Deskripsi**     | Sistem memeriksa kondisi peralatan yang dikembalikan dan mencatat nilainya sebagai bagian dari pencatatan pengembalian. Use case ini berjalan di dalam UC11 dan tidak mempunyai interaksi langsung dengan aktor |

| Kegiatan                                                                                    | Respon sistem                                                                                                                                            |
| ------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Skenario Normal**                                                                         |                                                                                                                                                          |
| 1. Alur pengembalian memanggil Periksa Kondisi Peralatan dengan peralatan yang dikembalikan | 2. Sistem menampilkan pilihan kondisi, yaitu Baik, Rusak Ringan, atau Rusak Berat                                                                        |
| 3. Petugas memilih nilai kondisi                                                            | 4. Sistem mencatat nilai kondisi pada data pengembalian                                                                                                  |
| **Skenario Alternative**                                                                    |                                                                                                                                                          |
| 5. Petugas belum memilih nilai kondisi (cabang dari langkah 4)                              | 6. Sistem meminta petugas memilih nilai kondisi sebelum pencatatan disimpan                                                                              |
| **Skenario Akhir**                                                                          | Use case selesai jika nilai kondisi peralatan tercatat pada data pengembalian; jika nilai belum dipilih, pencatatan tidak disimpan sampai nilai dipilih. |

---

# SISTEM INFORMASI AKADEMIK (SIA)

---

## Tabel 5.13 Skenario Use Case SIA-UC07 Lihat Kalender Akademik

| Field             | Value                                                                                   |
| ----------------- | --------------------------------------------------------------------------------------- |
| **Nama use case** | SIA-UC07 Lihat Kalender Akademik                                                        |
| **Aktor**         | Civitas Akademika (berlaku untuk Mahasiswa dan Dosen)                                   |
| **Tujuan**        | Civitas akademika dapat melihat jadwal akademik                                         |
| **Deskripsi**     | Civitas akademika membuka fungsi kalender akademik dan melihat jadwal kegiatan akademik |

| Kegiatan                                                              | Respon sistem                                                                                                                               |
| --------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| **Skenario Normal**                                                   |                                                                                                                                             |
| 1. Civitas Akademika membuka fungsi Lihat Kalender Akademik           | 2. Sistem menampilkan daftar jadwal akademik                                                                                                |
| 3. Civitas Akademika memilih periode atau jenis kegiatan              | 4. Sistem menampilkan detail jadwal sesuai pilihan                                                                                          |
| **Skenario Alternative**                                              |                                                                                                                                             |
| 5. Tidak ada jadwal pada periode yang dipilih (cabang dari langkah 4) | 6. Sistem menampilkan pesan tidak ada jadwal pada periode tersebut                                                                          |
| **Skenario Akhir**                                                    | Use case selesai jika jadwal akademik ditampilkan; jika tidak ada jadwal pada periode yang dipilih, use case selesai dengan pesan tersebut. |

Keterangan: use case ini berlaku untuk Mahasiswa dan Dosen (generalization actor).

---

## Tabel 5.14 Skenario Use Case SIA-UC08 Input Nilai Mata Kuliah

| Field             | Value                                                                                                                          |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| **Nama use case** | SIA-UC08 Input Nilai Mata Kuliah                                                                                               |
| **Aktor**         | Dosen (prasyarat: dosen pengampu mata kuliah)                                                                                  |
| **Tujuan**        | Nilai mahasiswa dapat diinput ke dalam sistem                                                                                  |
| **Deskripsi**     | Dosen pengampu mata kuliah input nilai mahasiswa yang telah diajarkan. Use case ini direalisasikan oleh collaboration SIA-CO01 |

| Kegiatan                                                     | Respon sistem                                                                                                            |
| ------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------ |
| **Skenario Normal**                                          |                                                                                                                          |
| 1. Dosen membuka fungsi Input Nilai Mata Kuliah              | 2. Sistem menampilkan daftar mahasiswa pada mata kuliah yang diampu                                                      |
| 3. Dosen memilih mahasiswa                                   | 4. Sistem menampilkan data nilai saat ini (jika ada)                                                                     |
| 5. Dosen menginput nilai                                     | 6. Sistem memeriksa keabsahan nilai                                                                                      |
| 7. Dosen mengonfirmasi input nilai                           | 8. Sistem menyimpan nilai dan menampilkan konfirmasi                                                                     |
| **Skenario Alternative**                                     |                                                                                                                          |
| 9. Nilai di luar rentang yang sah (cabang dari langkah 6)    | 10. Sistem menolak penyimpanan dan menampilkan pesan nilai di luar rentang                                               |
| 11. Dosen bukan pengampu mata kuliah (cabang dari langkah 2) | 12. Sistem menampilkan pesan akses ditolak                                                                               |
| **Skenario Akhir**                                           | Use case selesai jika nilai tersimpan; jika nilai tidak sesuai rentang atau dosen bukan pengampu, nilai tidak tersimpan. |

Keterangan: use case ini direalisasikan oleh collaboration SIA-CO01 Input Nilai.

---

## Tabel 5.15 Skenario Use Case SIA-UC09 Lihat KHS

| Field             | Value                                                                                                                                                                                                 |
| ----------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Nama use case** | SIA-UC09 Lihat KHS                                                                                                                                                                                    |
| **Aktor**         | Mahasiswa                                                                                                                                                                                             |
| **Tujuan**        | Mahasiswa dapat melihat hasil studi (KHS) yang sudah dipublikasikan                                                                                                                                   |
| **Deskripsi**     | Mahasiswa membuka fungsi Lihat KHS dan melihat nilai-nilai yang telah dipublikasikan. Hanya nilai yang sudah dipublikasikan yang ditampilkan. Use case ini direalisasikan oleh collaboration SIA-CO02 |

| Kegiatan                                                                              | Respon sistem                                                                                                            |
| ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| **Skenario Normal**                                                                   |                                                                                                                          |
| 1. Mahasiswa membuka fungsi Lihat KHS                                                 | 2. Sistem menampilkan daftar semester yang tersedia                                                                      |
| 3. Mahasiswa memilih semester                                                         | 4. Sistem menampilkan KHS untuk semester tersebut                                                                        |
| **Skenario Alternative**                                                              |                                                                                                                          |
| 5. Belum ada nilai yang dipublikasikan untuk semester dipilih (cabang dari langkah 4) | 6. Sistem menampilkan pesan belum ada nilai yang dipublikasikan                                                          |
| **Skenario Akhir**                                                                    | Use case selesai jika KHS ditampilkan; jika belum ada nilai yang dipublikasikan, use case selesai dengan pesan tersebut. |

Keterangan: use case ini direalisasikan oleh collaboration SIA-CO02 Lihat KHS.

---

## Tabel 5.16 Skenario Use Case SIA-UC10 Kelola Data Mahasiswa Akademik

| Field             | Value                                                                                                                                                                                       |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Nama use case** | SIA-UC10 Kelola Data Mahasiswa Akademik                                                                                                                                                     |
| **Aktor**         | Admin Akademik                                                                                                                                                                              |
| **Tujuan**        | Data mahasiswa akademik terkelola melalui satu fungsi pengelolaan bersama                                                                                                                   |
| **Deskripsi**     | Admin Akademik membuka fungsi pengelolaan data mahasiswa, memilih bentuk pengelolaan, dan menyimpan perubahan. Bentuk tambah, ubah, dan hapus dijabarkan pada tabel khususnya masing-masing |

| Kegiatan                                                                     | Respon sistem                                                                                                                |
| ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| **Skenario Normal**                                                          |                                                                                                                              |
| 1. Admin Akademik membuka fungsi Kelola Data Mahasiswa Akademik              | 2. Sistem menampilkan daftar data mahasiswa                                                                                  |
| 3. Admin Akademik memilih bentuk pengelolaan, yaitu tambah, ubah, atau hapus | 4. Sistem menampilkan formulir sesuai bentuk pengelolaan yang dipilih                                                        |
| 5. Admin mengisi atau mengonfirmasi data                                     | 6. Sistem memeriksa kelengkapan dan keabsahan data                                                                           |
| 7. Admin menyimpan perubahan                                                 | 8. Sistem menyimpan perubahan dan menampilkan konfirmasi                                                                     |
| **Skenario Alternative**                                                     |                                                                                                                              |
| 9. Data tidak lengkap atau tidak sah (cabang dari langkah 6)                 | 10. Sistem menolak penyimpanan dan menampilkan pesan kesalahan data                                                          |
| **Skenario Akhir**                                                           | Use case selesai jika perubahan data mahasiswa tersimpan; jika data tidak lengkap atau tidak sah, perubahan tidak tersimpan. |

---

## Tabel 5.17 Skenario Use Case SIA-UC11 Tambah Data Mahasiswa

| Field             | Value                                                                                                              |
| ----------------- | ------------------------------------------------------------------------------------------------------------------ |
| **Nama use case** | SIA-UC11 Tambah Data Mahasiswa                                                                                     |
| **Aktor**         | Admin Akademik                                                                                                     |
| **Tujuan**        | Data mahasiswa baru tersimpan sebagai bentuk khusus dari pengelolaan data mahasiswa                                |
| **Deskripsi**     | Admin menginput data mahasiswa baru dan menyimpan data tersebut; langkah bersama mengikuti Tabel skenario SIA-UC10 |

| Kegiatan                                      | Respon sistem                                                                                       |
| --------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| **Skenario Normal**                           |                                                                                                     |
| 1. Admin membuka fungsi Tambah Data Mahasiswa | 2. Sistem menampilkan formulir data mahasiswa baru                                                  |
| 3. Admin mengisi data mahasiswa baru          | 4. Sistem memeriksa kelengkapan data                                                                |
| 5. Admin menyimpan data                       | 6. Sistem menyimpan data mahasiswa baru dan menampilkan konfirmasi                                  |
| **Skenario Alternative**                      |                                                                                                     |
| 7. Data tidak lengkap (cabang dari langkah 4) | 8. Sistem menolak penyimpanan dan meminta admin melengkapi data                                     |
| **Skenario Akhir**                            | Use case selesai jika data mahasiswa baru tersimpan; jika data tidak lengkap, data tidak tersimpan. |

Keterangan: use case khusus dari SIA-UC10 Kelola Data Mahasiswa Akademik. Perilaku pembeda: data mahasiswa baru tersimpan. Langkah bersama mengikuti Tabel skenario SIA-UC10.

---

## Tabel 5.18 Skenario Use Case SIA-UC12 Ubah Data Mahasiswa

| Field             | Value                                                                                                                      |
| ----------------- | -------------------------------------------------------------------------------------------------------------------------- |
| **Nama use case** | SIA-UC12 Ubah Data Mahasiswa                                                                                               |
| **Aktor**         | Admin Akademik                                                                                                             |
| **Tujuan**        | Data mahasiswa berubah sebagai bentuk khusus dari pengelolaan data mahasiswa                                               |
| **Deskripsi**     | Admin memilih data mahasiswa, mengubah datanya, dan menyimpan perubahan; langkah bersama mengikuti Tabel skenario SIA-UC10 |

| Kegiatan                                                  | Respon sistem                                                                                                   |
| --------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| **Skenario Normal**                                       |                                                                                                                 |
| 1. Admin memilih data mahasiswa yang akan diubah          | 2. Sistem menampilkan data mahasiswa saat ini                                                                   |
| 3. Admin mengubah data mahasiswa                          | 4. Sistem memeriksa perubahan data                                                                              |
| 5. Admin menyimpan perubahan                              | 6. Sistem menyimpan data yang diubah dan menampilkan konfirmasi                                                 |
| **Skenario Alternative**                                  |                                                                                                                 |
| 7. Data mahasiswa tidak ditemukan (cabang dari langkah 2) | 8. Sistem menampilkan pesan data mahasiswa tidak ditemukan                                                      |
| **Skenario Akhir**                                        | Use case selesai jika perubahan data mahasiswa tersimpan; jika data tidak ditemukan, perubahan tidak tersimpan. |

Keterangan: use case khusus dari SIA-UC10 Kelola Data Mahasiswa Akademik. Perilaku pembeda: data mahasiswa berubah. Langkah bersama mengikuti Tabel skenario SIA-UC10.

---

## Tabel 5.19 Skenario Use Case SIA-UC13 Hapus Data Mahasiswa

| Field             | Value                                                                                                                                          |
| ----------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| **Nama use case** | SIA-UC13 Hapus Data Mahasiswa                                                                                                                  |
| **Aktor**         | Admin Akademik                                                                                                                                 |
| **Tujuan**        | Data mahasiswa terhapus sebagai bentuk khusus dari pengelolaan data mahasiswa                                                                  |
| **Deskripsi**     | Admin memilih data mahasiswa, mengonfirmasi penghapusan, dan sistem menghapus data tersebut; langkah bersama mengikuti Tabel skenario SIA-UC10 |

| Kegiatan                                                 | Respon sistem                                                                                           |
| -------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| **Skenario Normal**                                      |                                                                                                         |
| 1. Admin memilih data mahasiswa yang akan dihapus        | 2. Sistem memeriksa tidak ada data akademik aktif                                                       |
| 3. Admin mengonfirmasi penghapusan                       | 4. Sistem menghapus data mahasiswa dan menampilkan konfirmasi penghapusan                               |
| **Skenario Alternative**                                 |                                                                                                         |
| 5. Masih ada data akademik aktif (cabang dari langkah 2) | 6. Sistem menolak penghapusan dan menampilkan pesan data akademik masih aktif                           |
| **Skenario Akhir**                                       | Use case selesai jika data mahasiswa terhapus; jika masih ada data akademik aktif, data tidak terhapus. |

Keterangan: use case khusus dari SIA-UC10 Kelola Data Mahasiswa Akademik. Perilaku pembeda: data mahasiswa terhapus, dengan syarat tidak ada data akademik aktif. Langkah bersama mengikuti Tabel skenario SIA-UC10.

---

# CHECKLIST PENILAIAN

| No  | Aspek yang Diperiksa                                                                    | LAB | SIA |
| --- | --------------------------------------------------------------------------------------- | --- | --- |
| 1   | Seluruh field tabel terisi lengkap                                                      | ☐   | ☐   |
| 2   | Langkah ditulis berurutan, satu aksi per langkah, penomoran berlanjut                   | ☐   | ☐   |
| 3   | Kolom Kegiatan hanya berisi aksi aktor                                                  | ☐   | ☐   |
| 4   | Kolom Respon sistem hanya berisi tanggapan sistem                                       | ☐   | ☐   |
| 5   | Data yang dimasukkan dan ditampilkan disebut secara eksplisit                           | ☐   | ☐   |
| 6   | Relasi include ditulis sebagai langkah rujukan pada Skenario Normal                     | ☐   | ☐   |
| 7   | Relasi extend ditulis sebagai cabang bersyarat dengan condition dan extension point     | ☐   | ☐   |
| 8   | Generalization actor diterapkan (LAB: Mahasiswa/Dosen; SIA: Civitas Akademika)          | ☐   | ☐   |
| 9   | Generalization use case diterapkan (LAB: UC02/UC08/UC09/UC10; SIA: UC10/UC11/UC12/UC13) | ☐   | ☐   |
| 10  | Collaboration disebut pada keterangan tabel tanpa langkah kegiatan sendiri              | ☐   | ☐   |
| 11  | Setiap tabel mempunyai Skenario Alternative dan Skenario Akhir                          | ☐   | ☐   |
| 12  | Nama, ID, aktor, condition, dan extension point sama persis dengan diagram              | ☐   | ☐   |
