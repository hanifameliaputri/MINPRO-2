# MINPRO-2
NAMA: Hanif Amelia Putri
KELAS: B
NIM: 2509116075

# FLOWCHART
<img width="2060" height="1732" alt="Untitled Diagram drawio (7)" src="https://github.com/user-attachments/assets/98355890-f200-408a-a700-1124d6cd1b84" />
PENJELASAN:
1. Start: Program dimulai.

Menu Login: Sistem menampilkan menu login dan meminta pengguna untuk menginput username dan password.

2. Proses Login:

Sistem memeriksa apakah login sebagai Mahasiswa atau Admin.

Jika login gagal, sistem mengurangi kesempatan login dan menanyakan lagi.

Jika kesempatan habis, program akan berhenti.

3. Menu Utama Mahasiswa / Admin (1,2,5 untuk mahasiswa, 1–5 untuk admin):

4. Menu 1 (Lihat Catatan/Jadwal):

Jika pengguna ingin mengecek ruangan tertentu, sistem meminta input nama ruangan dan menampilkan status ruangan (dipakai/kosong).

Jika tidak, sistem menampilkan seluruh daftar catatan/jadwal.

5. Menu 2 (Tambah Catatan/Jadwal):

Pengguna menginput ruangan, kelas, tanggal, jam, dan nama kegiatan.

Data akan disimpan oleh sistem dan catatan berhasil ditambahkan.

6. Menu 3 (Ubah Catatan/Jadwal) – hanya admin:

Sistem menampilkan seluruh catatan.

Pengguna memilih ruangan yang ingin diubah dan menginput data baru (ruangan, kelas, tanggal, jam, nama kegiatan).

Data berhasil diubah oleh sistem.

7. Menu 4 (Hapus Catatan/Jadwal) – hanya admin:

Sistem menampilkan seluruh catatan.

Pengguna memilih catatan yang ingin dihapus.

Catatan berhasil dihapus oleh sistem.

8. Menu 5 / Menu Keluar:

program berhenti.

End: Program selesai dijalankan.



# TAMPILAN AWAL
<img width="1648" height="332" alt="Screenshot_20250928_093527" src="https://github.com/user-attachments/assets/07f5406d-98fa-400a-8422-3442c61e2405" />
PENJELASAN: Tampilan awal pengguna akan diarahkan untuk login agar bisa masuk ke sistem. Pada menu login kita diberi 2 jenis username dan password yang berbeda. user dan password pertama adalah khusus admin yang bertugas untuk melihat, menambahkah, menghapus, dan update. User yang kedua adalah mahasiswa yang hanya bisa melihat dan menambah catatan penggunaan lab komputer.

# USER ADMIN (1. LIHAT JADWAL)
<img width="1626" height="807" alt="image" src="https://github.com/user-attachments/assets/50f1efb3-9ca3-4225-b83c-e5820cb3e9f5" />
PENJELASAN: Ketika admin memilih menu "1. Lihat Jadwal" sistem akan langsung menampilkan seluruh catatan jadwal pengguna laboratorium komputer. Ketika admin sudah selesai melihat, admin bisa memilih menu "5. keluar", dan sistem berhenti.

# USER ADMIN (2. TAMBAH JADWAL)
<img width="1479" height="906" alt="image" src="https://github.com/user-attachments/assets/f2535736-1c1a-4485-8c4f-862eff67bcd6" />
PENJELASAN: Ketika admin memilih menu 2.Tambah jadwal admin akan diarahkan untuk menginput nama/id ruangan, kelas, tanggal, jam, dan kegiatan. setelah itu sistem akan menambahkan dan menampilkan daftar catatan baru.

# USER ADMIN (3. UBAH JADWAL)
<img width="1423" height="875" alt="{8CCAB369-9291-483E-A784-265A8E26D23C}" src="https://github.com/user-attachments/assets/bbc7c081-ddc5-4fdd-9cdc-8d518764d279" />
PENJELASAN: Ketika admin memilih menu 3. Ubah jadwal, sistem akan menampilkan daftar catatan penggunaan laboratorium komputer, lalu sistem akan menanyakan nomor catatan ruangan yang ingin diubah dan pengguna akan diarahkan untuk mengisi nama ruangan baru, kelas, tanggal dan jam penggunaan. Setelah itu, sistem akan mengubah daftar catatan sesuai permintaan pengguna. Sistem juga akan menampilkan daftar catatan ruangan terbaru.

# USER ADMIN (4. HAPUS JADWAL)
<img width="1462" height="966" alt="image" src="https://github.com/user-attachments/assets/50117a69-b7bb-4204-83fb-074e93f32176" />
PENJELASAN: Ketika admin memilih menu 4. Hapus catatan, sistem akan menampilkan daftar catatan penggunaan laboratorium komputer, lalu sistem akan menanyakan nomor catatan yang ingin dihapus dan sistem akan menghapus catatan sesuai permintaan pengguna. Sistem juga akan menampilkan daftar catatan terbaru.

# USER ADMIN (5. KELUAR)
PENJELASAN: Ketika admin memilih menu 5. Keluar maka sistem akan selesai dan menampilkan "Keluar dari sistem. Sampai jumpa admin".

# USER MAHASISWA (1. LIHAT JADWAL)
<img width="1422" height="870" alt="image" src="https://github.com/user-attachments/assets/733b0293-9790-4f85-ba25-9c1e7d574599" />
PENJELASAN: Ketika mahasiswa memilih menu 1. Lihat jadwal maka sistem akan menanyakan "Apakah Ingin cek ruangan tertentu?", jika iya maka pengguna diarahkan untuk menginput nama ruangan yang ingin dicek dan sistem akan menampilkan daftar ruangan ketika ruangan yang di input ada di daftar catatan. Jika pengguna memilih tidak sistem akan menampilkan seluruh daftar catatan ruangan.

# USER MAHASISWA (2. TAMBAH JADWAL)
<img width="1400" height="863" alt="{A8FF2D1A-726B-4506-9153-C8C1D67C6F23}" src="https://github.com/user-attachments/assets/f3f57359-2cce-4928-b5a4-784d4e4ae639" />
Ketika mahasiswa memilih menu 2.Tambah jadwal admin akan diarahkan untuk menginput nama/id ruangan, kelas, tanggal, jam, dan kegiatan. setelah itu sistem akan menambahkan dan menampilkan daftar catatan baru.

# USER MAHASISWA (3. KELUAR)
<img width="1386" height="617" alt="{7F97084A-D854-4284-BB25-BFCD57C4D752}" src="https://github.com/user-attachments/assets/e8a65f3c-77b9-4794-88cc-0dfb3fba3027" />
Ketika mahasiswa memilih menu 5. Keluar maka sistem akan selesai dan menampilkan "Keluar dari sistem. Sampai jumpa mahasiswa".











