# Laporan Praktikum Pertemuan 6

## Activity Diagram: Dari Skenario ke Alur Aktivitas

### Identitas

| Elemen | Keterangan |
|---|---|
| Nama | Rizky Taupik Hidayat |
| NIM | 2406014 |
| Kelas | Informatika A |
| Kakas | draw.io |
| Praktikum | Analisis dan Desain Berorientasi Objek |
| Artefak | Activity Diagram Sistem Informasi Laboratorium |
| Versi | v01 |

## 1. Tujuan

Menyusun dan menilai seluruh activity diagram hasil transformasi dari skenario use case pada Pertemuan 4 dan 5 ke bentuk alur aktivitas. Tujuan utamanya adalah memastikan setiap diagram memiliki struktur activity yang benar, konsisten dengan skenario LAB, serta mematuhi aturan notasi UML yang berlaku.

## 2. Kegiatan

Pada P06, kegiatan yang dilakukan meliputi:

1. Menurunkan activity diagram dari skenario use case LAB yang sudah disusun sebelumnya.
2. Membuat diagram untuk alur utama dan cabang keputusan yang sesuai dengan fungsi laboratorium.
3. Menetapkan penggunaan `include` dan `extend` secara tepat dalam alur aktivitas.
4. Memastikan action, actor, guard, fork/join, serta final state mengikuti kaidah aturan praktek diagram activity.
5. Menguji kelengkapan diagram terhadap checklist QA yang ditetapkan di logbook.

## 3. Hasil Artefak P06

Setiap activity diagram yang dihasilkan sudah disusun dalam bentuk file yang lengkap beserta ekspor PNG pada folder model analisis. Berkas utama yang tersedia meliputi:

- `04_model_analisi/P06/LAB/P06_2406014_LAB_activity_lihat_ketersediaan_v01.png`
- `04_model_analisi/P06/LAB/P06_2406014_LAB_activity_kelola_data_v01.png`
- `04_model_analisi/P06/LAB/P06_2406014_LAB_activity_peminjaman_v01.png`
- `04_model_analisi/P06/LAB/P06_2406014_LAB_activity_cetak_bukti_v01.png`
- `04_model_analisi/P06/LAB/P06_2406014_LAB_activity_keputusan_v01.png`
- `04_model_analisi/P06/LAB/P06_2406014_LAB_activity_pengembalian_v01.png`
- `04_model_analisi/P06/LAB/P06_2406014_LAB_activity_laporan_v01.png`

### 3.1 Activity Lihat Ketersediaan (LAB-UC01)

Diagram ini merepresentasikan alur ketika pengguna memeriksa ketersediaan peralatan sebelum melakukan peminjaman. Aktivitas utama terdiri dari menentukan kebutuhan, memeriksa data peralatan, menampilkan status ketersediaan, dan menghasilkan keputusan apakah proses dapat dilanjutkan atau harus diulang. Diagram ini menegaskan bahwa pemeriksaan ketersediaan merupakan tahapan wajib pada alur peminjaman.

### 3.2 Activity Kelola Data Peralatan (LAB-UC02)

Diagram ini memuat varian operasi pengelolaan data peralatan: tambah, ubah, dan hapus. Ketiga cabang tersebut dijadikan sebagai variasi fungsi pada satu activity diagram yang sama. Struktur ini konsisten dengan skenario karena fungsi-fungsi tersebut merupakan bagian dari pengelolaan data peralatan, sekaligus mencerminkan keputusan operasional yang berbeda untuk tiap kasus.

### 3.3 Activity Peminjaman (LAB-UC03)

Diagram ini menjelaskan alur peminjaman peralatan mulai dari pengajuan, pengecekan ketersediaan, validasi kelengkapan data, penyimpanan status pengajuan, hingga pembuatan bukti pengajuan. Periksa Ketersediaan digambarkan sebagai action `include`, bukan sebagai aktivitas mandiri di luar alur utama. Jika pengguna memilih mencetak bukti, maka diagram menggunakan cabang bersyarat `extend` dengan kondisi `[ya, memilih cetak]`.

### 3.4 Activity Cetak Bukti (LAB-UC05)

Diagram ini memuat aktivitas opsional yang terjadi setelah peminjaman diajukan. Cabang ini muncul hanya ketika pengguna memilih untuk mencetak bukti pengajuan. Dengan demikian, cetak bukti bukan proses inti dari peminjaman, melainkan aktivitas tambahan yang bersifat kondisional.

### 3.5 Activity Keputusan Peminjaman (LAB-UC06)

Diagram ini memaparkan alur keputusan terhadap pengajuan peminjaman yang diajukan oleh peminjam. Proses ini mencakup pemeriksaan terhadap kelayakan, keputusan menerima atau menolak pengajuan, serta penyampaian hasil keputusan kepada peminjam. Decision node pada diagram mempunyai guard yang jelas dan setiap cabang menuju hasil yang telah ditentukan.

### 3.6 Activity Lihat Laporan Peminjaman (LAB-UC07)

Diagram ini menggambarkan fungsi Kepala Laboratorium untuk melihat laporan peminjaman. Aktor yang muncul pada diagram ini adalah Kepala Laboratorium, sesuai dengan fungsi yang memang menjadi tanggung jawabnya. Diagram ini tidak dipadukan dengan alur peminjaman atau pengembalian karena kedua aktivitas tersebut bukan bagian dari peran Kepala Laboratorium.

### 3.7 Activity Pengembalian Peralatan (LAB-UC11)

Diagram ini menggambarkan alur pengembalian peralatan yang mencakup pencatatan status pengembalian dan pengecekan kondisi alat. `Periksa Kondisi Peralatan` diletakkan sebagai action `include` pada alur utama pengembalian, sesuai dengan kebutuhan skenario. Hal ini merupakan konsekuensi dari penggunaan `include` yang valid pada tahapan proses pengembalian.

## 4. Evaluasi Berdasarkan Checklist Logbook

Berdasarkan checklist yang tercantum pada logbook P06, seluruh diagram yang dibuat telah memenuhi prinsip umum activity diagram berikut:

- Terdapat satu initial node dan minimal satu activity final node.
- Setiap decision mempunyai guard yang jelas pada semua cabang keluarnya.
- Cabang keputusan memiliki jalur yang kembali ke merge atau berakhir pada final state yang jelas.
- Fork dan join digunakan secara benar; proses paralel dikumpulkan melalui join.
- Setiap action terdampingi swimlane aktor yang sesuai, dengan respon sistem berada pada swimlane Sistem.
- Nama action konsisten dengan langkah pada skenario Pertemuan 5.
- `Include` diposisikan pada alur utama; `extend` dibuat sebagai cabang bersyarat dengan kondisi `[ya, memilih cetak]`.
- Proses baru Tahap 5, yaitu Periksa Kelengkapan Aksesori Peralatan, dibedakan dan tidak diklaim berasal dari pertemuan sebelumnya.
- Kepala Laboratorium hanya muncul pada activity laporan, bukan pada activity peminjaman atau pengembalian.
- Diagram yang tidak dibuat sebagai activity terpisah tetap tercakup dalam diagram induk sesuai aturan: LAB-UC04 dalam peminjaman, LAB-UC12 dalam pengembalian, serta LAB-UC08, LAB-UC09, dan LAB-UC10 dalam kelola data.
- Nama aktor, action, serta ID konsisten dengan jobsheet P04 dan P05.

## 5. Kesimpulan

Semua artefak P06 telah dibuat sesuai prinsip pemodelan activity diagram dan konsisten dengan skenario use case yang telah disusun sebelumnya. Diagram yang dihasilkan mencakup seluruh fungsi utama laboratorium dan memperlihatkan pemisahan antara alur utama, include, extend, serta cabang keputusan. Dengan demikian, P06 dapat dinyatakan sebagai tahapan yang berhasil mentransformasikan skenario ke bentuk activity diagram yang siap digunakan sebagai artefak analisis dan desain berorientasi objek.

## 6. Referensi Artefak

- Template Metadata: `02_template/P06_template_metadata_artefak-v01.md`
- Logbook: `00_administrasi/P06_2406014_logbook_v01.md`
- Model Analisis P06 LAB: `04_model_analisi/P06/LAB/`
- Berkas PNG utama:
  - `P06_2406014_LAB_activity_lihat_ketersediaan_v01.png`
  - `P06_2406014_LAB_activity_kelola_data_v01.png`
  - `P06_2406014_LAB_activity_peminjaman_v01.png`
  - `P06_2406014_LAB_activity_cetak_bukti_v01.png`
  - `P06_2406014_LAB_activity_keputusan_v01.png`
  - `P06_2406014_LAB_activity_pengembalian_v01.png`
  - `P06_2406014_LAB_activity_laporan_v01.png`
