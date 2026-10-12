Perbaikan Notasi - P03 Sistem Informasi Akademik (KRS)

1. ID use case menggunakan format SIA-UC di file deskripsi (03_latihan_tools/P03/SIA/P03_2406014_SIA_deskripsi_v01.md). 
   Alasan: ID kebutuhan sudah menggunakan format SIA-R01 sampai SIA-R06, tetapi ID use case masih menggunakan SIA-UC01, SIA-UC03, SIA-UC04, SIA-UC05, SIA-UC06. Ini menyebabkan inkonsistensi antara tabel kebutuhan dan katalog fungsi. Seharusnya semua ID menggunakan format SIA-R agar konsisten dengan tabel kebutuhan tugas.

2. Sumber kebutuhan di bagian A (SIA-UC03) masih mencantumkan "SIA-R03 dan SIA-R04".
   Alasan: Berdasarkan prinsip pemisahan tanggung jawab, SIA-R03 adalah use case utama "Ajukan KRS", sedangkan SIA-R04 "Validasi KRS" adalah fungsi include yang dipanggil dari R03. Sumber kebutuhan untuk use case Ajukan KRS seharusnya hanya SIA-R03, karena validasi sudah menjadi bagian internal (include) dari proses pengajuan, bukan kebutuhan terpisah yang harus dicantumkan sebagai sumber ganda.

3. ID use case tidak berurutan (SIA-UC01, lompat ke SIA-UC03, SIA-UC04, SIA-UC05, SIA-UC06).
   Alasan: Tidak ada SIA-UC02 dalam daftar, padahal SIA-R02 ada di tabel kebutuhan (Admin akademik dapat mengelola jadwal kuliah). Meskipun fungsi ini tidak direalisasikan dalam skenario pengajuan KRS (karena Admin akademik tidak berinteraksi dengan alur KRS), penomoran yang melompat dapat membingungkan. Seharusnya dijelaskan secara eksplisit bahwa SIA-R02 tidak direalisasikan sebagai use case dalam diagram karena di luar cakupan skenario ini.

4. Referensi ID di seluruh dokumen perlu konsistensi.
   Alasan: Jika keputusan akhir adalah menggunakan SIA-R untuk semua ID (kebutuhan dan use case), maka file deskripsi di folder 03_latihan_tools dan 04_model_analisi perlu diperbarui agar selaras dengan file skenario utama (01_skenario/P03_SIA_skenario_v01.md) yang sudah menggunakan format SIA-R secara konsisten.
