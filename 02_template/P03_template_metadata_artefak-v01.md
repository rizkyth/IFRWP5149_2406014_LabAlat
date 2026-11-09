# Identitas Artefak P03 — Use Case Diagram Sistem Informasi Akademik

| Atribut                       | Keterangan                                                                                                      |
| ----------------------------- | --------------------------------------------------------------------------------------------------------------- |
| ID artefak                    | P03                                                                                                             |
| Judul                         | Use Case Diagram Sistem Informasi Akademik: Pengajuan KRS                                                       |
| Pertemuan                     | 03                                                                                                              |
| Kebutuhan yang menjadi sumber | SIA-R01, SIA-R03, SIA-R04, SIA-R05, SIA-R06; SIA-R02 tidak direalisasikan pada skenario ini                    |
| Jenis/status                  | Use case diagram                                                                                               |
| Kakas                         | draw.io                                                                                                        |
| Penyusun                      | Rizky Taupik Hidayat 2406014                                                                                    |
| Versi dan tanggal             | v01 / 09-11-2026                                                                                                |
| Asumsi                        | Pengguna telah terautentikasi; data mata kuliah, prasyarat, dan jadwal tersedia                                 |
| Pemeriksaan                   | Perlu revisi: selaraskan ID use case dengan ID kebutuhan, sumber kebutuhan Ajukan KRS, dan penjelasan SIA-R02 |
| Riwayat revisi                | v01: metadata artefak P03 dibuat                                                                               |

## Cakupan dan catatan

Diagram memodelkan Mahasiswa yang melihat jadwal, mengajukan KRS, dan secara opsional melihat bukti pengajuan; Validasi KRS merupakan perilaku internal yang selalu disertakan dalam Ajukan KRS; serta Dosen Wali yang memproses persetujuan atau penolakan. SIA-R02 tentang pengelolaan jadwal oleh Admin akademik tidak dimodelkan karena berada di luar alur pengajuan KRS.

Gunakan ID SIA-R01 dan SIA-R03 sampai SIA-R06 secara konsisten pada diagram dan deskripsi. Ajukan KRS bersumber dari SIA-R03 saja; Validasi KRS tetap dicatat sebagai use case include yang bersumber dari SIA-R04.
