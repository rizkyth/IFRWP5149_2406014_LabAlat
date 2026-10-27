# Skenario Use Case - Sistem Informasi Akademik (SIA)

# Praktikum Analisis dan Desain Berorientasi Objek - Pertemuan 5

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

| No  | Aspek yang Diperiksa                                                                | SIA |
| --- | ----------------------------------------------------------------------------------- | --- |
| 1   | Seluruh field tabel terisi lengkap                                                  | ☐   |
| 2   | Langkah ditulis berurutan, satu aksi per langkah, penomoran berlanjut               | ☐   |
| 3   | Kolom Kegiatan hanya berisi aksi aktor                                              | ☐   |
| 4   | Kolom Respon sistem hanya berisi tanggapan sistem                                   | ☐   |
| 5   | Data yang dimasukkan dan ditampilkan disebut secara eksplisit                       | ☐   |
| 6   | Relasi include ditulis sebagai langkah rujukan pada Skenario Normal                 | ☐   |
| 7   | Relasi extend ditulis sebagai cabang bersyarat dengan condition dan extension point | ☐   |
| 8   | Generalization actor diterapkan (Civitas Akademika untuk Mahasiswa & Dosen)         | ☐   |
| 9   | Generalization use case diterapkan (UC10 umum, UC11/UC12/UC13 khusus)               | ☐   |
| 10  | Collaboration disebut pada keterangan tabel tanpa langkah kegiatan sendiri          | ☐   |
| 11  | Setiap tabel mempunyai Skenario Alternative dan Skenario Akhir                      | ☐   |
| 12  | Nama, ID, aktor, condition, dan extension point sama persis dengan diagram          | ☐   |

---

# KETERANGAN WARNA DIAGRAM

| Warna  | Makna                                     |
| ------ | ----------------------------------------- |
| Biru   | Use Case utama / peminjaman               |
| Hijau  | Use Case include (di dalam use case lain) |
| Kuning | Use case dengan collaboration             |
| Ungu   | Use case umum (generalization)            |
| Merah  | Use case khusus (generalization)          |

---

# CATATAN PENTING

1. **Generalization Actor**: UC07 ditulis satu kali atas nama Civitas Akademika, berlaku untuk Mahasiswa dan Dosen
2. **Generalization Use Case**: UC10 adalah skenario umum, UC11/UC12/UC13 adalah skenario khusus yang hanya memuat perilaku pembeda
3. **Collaboration**: SIA-CO01 (untuk UC08) dan SIA-CO02 (untuk UC09) disebutkan pada keterangan tanpa langkah kegiatan sendiri
4. **Prasyarat UC08**: Dosen harus merupakan pengampu mata kuliah tersebut
5. **Condition UC09**: Hanya nilai yang sudah dipublikasikan yang ditampilkan
6. **Syarat UC13**: Hapus hanya untuk mahasiswa yang tidak memiliki data akademik aktif
