Daftar use case
| ID | Nama | Aktor |
| SIA-R01 | Lihat jadwal kuliah | Mahasiswa ||
| SIA-R03 | Ajukan KRS | Mahasiswa
| SIA-R04 | Validasi KRS | (internal sistem, dipanggil oleh R03) |
| SIA-R05 | Lihat bukti pengajuan KRS | Mahasiswa |
| SIA-R06 | Konfirmasi pengajuan KRS | Dosen Wali |

Alur utama:

| Langkah | Tindakan mahasiswa | Respons sistem |
| 1 | Membuka pengajuan KRS | Menampilkan formulir KRS dan daftar mata kuliah yang ditawarkan |
| 2 | Memilih mata kuliah yang akan diambil | Menampung isian dan menghitung total SKS |
| 3 | Mengirim pengajuan KRS | Memeriksa kelengkapan data |
| 4 | — | Menjalankan SIA-R04 (validasi KRS) |
| 5 | — | Jika valid, menyimpan pengajuan KRS dan meneruskannya ke Dosen Wali |
| 6 | Melihat konfirmasi | Menampilkan status pengajuan; mencapai extension point |
| 7 | Mengakhiri pengajuan | Menutup proses pengajuan |

A . SIA-R03 — Ajukan KRS

| Elemen | Uraian |
| Tujuan | Menghasilkan pengajuan KRS yang tersimpan |
| Aktor utama | Mahasiswa |
| Aktor pendukung | Dosen Wali (menerima pengajuan untuk dikonfirmasi pada SIA-R06) |
| Sumber kebutuhan | SIA-R03 dan SIA-R04 |
| Pemicu | Mahasiswa memilih fungsi pengajuan KRS |
| Prasyarat | Mahasiswa telah terautentikasi; periode pengisian KRS dibuka; data mata kuliah dan jadwal tersedia |
| Pascakondisi Berhasil | Pengajuan KRS tersimpan dengan status Menunggu konfirmasi Dosen Wali |
| Pascakondisi gagal | Tidak ada pengajuan KRS baru yang berhasil tersimpan |
| Include | SIA-R04 — Validasi KRS |
| Extension point | Bukti pengajuan tersedia, pada langkah 6 |
| Extend | SIA-R05 jika [mahasiswa memilih lihat bukti pengajuan] |

| Langkah | Tindakan mahasiswa | Respons sistem |
| 1 | Membuka pengajuan KRS | Menampilkan formulir KRS dan daftar mata kuliah yang ditawarkan |
| 2 | Memilih mata kuliah yang akan diambil | Menampung isian dan menghitung total SKS |
| 3 | Mengirim pengajuan KRS | Memeriksa kelengkapan data |
| 4 | — | Menjalankan SIA-R04 (validasi KRS) |
| 5 | — | Jika valid, menyimpan pengajuan KRS dan meneruskannya ke Dosen Wali |
| 6 | Melihat konfirmasi | Menampilkan status pengajuan; mencapai extension point |
| 7 | Mengakhiri pengajuan | Menutup proses pengajuan |

B . SIA-R04 — Validasi KRS
| Elemen | Uraian |
| Tujuan | Memastikan pengajuan KRS memenuhi aturan akademik |
| Aktor utama | Tidak ada (dijalankan sistem) |
| Pemicu | Dipanggil oleh SIA-R03 pada langkah 4 |
| Prasyarat | Data pengajuan KRS telah diterima sistem |
| Pascakondisi berhasil | Pengajuan dinyatakan valid |
| Pascakondisi gagal | Pengajuan dinyatakan tidak valid beserta alasannya |
| Included by | SIA-R03 |

| Langkah | Tindakan aktor | Respons sistem |
| 1 | — | Memeriksa batas SKS berdasarkan IPS semester sebelumnya |
| 2 | — | Memeriksa bentrok jadwal antar mata kuliah |
| 3 | — | Memeriksa prasyarat mata kuliah |
| 4 | — | Mengembalikan hasil validasi ke SIA-R03 |

C. SIA-R05 — Lihat bukti pengajuan KRS
| Elemen | Uraian |
| Tujuan | Menampilkan bukti bahwa pengajuan KRS telah tersimpan |
| Aktor utama | Mahasiswa |
| Pemicu | Mahasiswa memilih lihat bukti pada extension point SIA-R03 |
| Prasyarat | Pengajuan KRS telah tersimpan |
| Pascakondisi berhasil | Bukti pengajuan KRS ditampilkan |
| Pascakondisi gagal | Bukti tidak ditampilkan |
| Extend | Memperluas SIA-R03 di extension point “Bukti pengajuan tersedia” |

| Langkah | Tindakan mahasiswa | Respons sistem |
| 1 | Memilih lihat bukti pengajuan | Mengambil data pengajuan KRS |
| 2 | — | Menampilkan bukti (daftar mata kuliah, total SKS, status, waktu pengajuan) |
| 3 | Menutup bukti | Kembali ke SIA-R03 |

D. SIA-R06 — Konfirmasi pengajuan KRS
| Elemen | Uraian |
| Tujuan | Menetapkan keputusan Dosen Wali atas pengajuan KRS |
| Aktor utama | Dosen Wali |
| Prasyarat | Dosen Wali terautentikasi; ada pengajuan KRS berstatus Menunggu konfirmasi |
| Pascakondisi berhasil | Status pengajuan menjadi Disetujui atau Ditolak |
| Pascakondisi gagal | Status pengajuan tetap Menunggu konfirmasi |

| Langkah | Tindakan Dosen Wali | Respons sistem |
| 1 | Membuka daftar pengajuan KRS mahasiswa bimbingan | Menampilkan daftar pengajuan |
| 2 | Memilih satu pengajuan | Menampilkan rincian KRS |
| 3 | Menyetujui atau menolak (dengan catatan) | Menyimpan keputusan dan memperbarui status |
| 4 | — | Menampilkan konfirmasi |
