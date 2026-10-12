Mahasiswa mengajukan KRS dengan memilih mata kuliah. Setiap
pengajuan menjalankan validasi KRS yang memeriksa kelengkapan,
prasyarat mata kuliah, dan benturan jadwal. Jika validasi berhasil,
sistem menyimpan pengajuan berstatus menunggu persetujuan dosen
wali. Pada konfirmasi penyimpanan, mahasiswa dapat memilih
mengunduh bukti pengajuan. Dosen wali menyetujui atau menolak KRS
dan memberikan catatan keputusan.

2.  | ID | Kebutuhan tugas |
    | SIA-R01 | Mahasiswa dapat melihat jadwal kuliah |
    | SIA-R02 | Admin akademik dapat mengelola jadwal kuliah |
    | SIA-R03 | Mahasiswa dapat mengajukan KRS |
    | SIA-R04 | Sistem memvalidasi KRS sebagai bagian pengajuan |
    | SIA-R05 | Mahasiswa dapat mengunduh bukti jika memilihnya pada konfirmasi
    pengajuan |
    | SIA-R06 | Dosen wali dapat memproses persetujuan atau penolakan KRS |

Batas dan asumsi:
• Pengguna telah terautentikasi.
• Data mata kuliah, prasyarat, dan jadwal tersedia.
• Validasi gagal menyebabkan pengajuan belum berhasil tersimpan.
• Unduh bukti tidak menjadi syarat keberhasilan pengajuan.
• KRS tersimpan belum berarti disetujui.
• Pembayaran, pengisian nilai, dan implementasi basis data berada di luar
tugas.

| Pihak | Interaksi dalam skenario | Status |
| Mahasiswa | Membuka formulir, memilih mata kuliah, mengirim pengajuan, melihat konfirmasi dan bukti | Aktor|
| Dosen Wali | Menerima pengajuan yang lolos validasi, lalu menyetujui atau menolaknya Aktor
| Sistem (Validasi KRS) | Dijalankan otomatis pada langkah 4 tanpa tindakan manusia | Bukan aktor, fungsi internal (include) |
Admin akademik Tidak berinteraksi dengan satu pun langkah pengajuan KRS Tidak dimasukkan

Katalog fungsi
| ID | Nama fungsi | Aktor terkait | Sumber kebutuhan |
| SIA-R01 | Lihat jadwal kuliah | Mahasiswa | SIA-R01 |
| SIA-R03 | Ajukan KRS | Mahasiswa | SIA-R03 |
| SIA-R04 | Validasi KRS | Tidak ada, dipanggil sistem dari SIA-R03 (include) | SIA-R04 |
| SIA-R05 | Lihat bukti pengajuan KRS | Mahasiswa, extend dari SIA-R03 | SIA-R05 |
| SIA-R06 | Konfirmasi pengajuan KRS | Dosen Wali | SIA-R06 |

SIA-R02, yaitu Admin akademik dapat mengelola jadwal kuliah, tidak direalisasikan
dalam skenario ini karena Admin akademik tidak berinteraksi dengan alur
pengajuan KRS.

3 . Alasan relasi Include
| Aspek | Penjelasan |
| Relasi | SIA-R03 Ajukan KRS include SIA-R04 Validasi KRS |
| Sumber | SIA-R03 (use case dasar), yang memanggil validasi pada langkah 4 |
| Tujuan | Memastikan hanya pengajuan yang memenuhi aturan akademik yang tersimpan |
| Alasan | memakai include Validasi selalu dijalankan pada setiap pengajuan, tanpa kondisi. Bila dilewati, pengajuan tidak boleh disimpan. Itulah ciri include, berbeda dengan extend yang opsional dan bersyarat |
| Alasan dipisah | Alur utama tetap ringkas, dan aturan validasi dapat dipakai ulang, misalnya bila KRS direvisi atau diperiksa lagi saat Dosen Wali mengonfirmasi |
| Arah panah | Dari SIA-R03 ke SIA-R04, karena use case dasar membutuhkan perilaku tersebut |

4. | Elemen | Uraian |
   | Use case dasar | SIA-R03 Ajukan KRS |
   | Use case tambahan | SIA-R05 Lihat bukti pengajuan KRS |
   | Aktor | Mahasiswa |
   | Kondisi | Jika [mahasiswa memilih lihat bukti pengajuan] |
   | Extension point | Bukti pengajuan tersedia, pada langkah 6 |
   | Arah panah| Dari SIA-R05 ke SIA-R03, berlabel <<extend>> |

Penjelasan
Use case dasar tetap lengkap tanpa tambahan. Alur 1 sampai 7 selesai dan pengajuan tersimpan walaupun mahasiswa tidak melihat bukti.
Use case tambahan hanya berjalan bila kondisi terpenuhi. Pemicunya pilihan mahasiswa, bukan keputusan sistem.
Extension point adalah titik pada use case dasar tempat perluasan disisipkan. Pada langkah 6, setelah sistem menampilkan nomor dan status, sistem menyediakan opsi lihat bukti. Bila dipilih, SIA-R05 dijalankan, lalu alur kembali ke langkah 7.
Mengapa bukan include: bila bukti dijadikan include, ia harus selalu tampil pada setiap pengajuan. Karena sifatnya opsional dan bersyarat, ia tepat sebagai extend.

5. Daftar use case
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
| Sumber kebutuhan | SIA-R03 |
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
