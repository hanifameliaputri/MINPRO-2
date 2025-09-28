# MINI PROJECT 2
NAMA: Hanif Amelia Putri

KELAS: B

NIM: 2509116075


                                                  SISTEM CATATAN PENGGUNAAN LABORATORIUM KOMPUTER

# DESKRIPSI SINGKAT
Sistem ini adalah Sistem Catatan Penggunaan Lab Komputer yang memungkinkan pengguna untuk melihat, menambah, mengubah, dan menghapus jadwal penggunaan ruangan lab. Terdapat dua jenis pengguna yaitu Admin yang memiliki akses penuh, dan Mahasiswa yang hanya dapat melihat dan menambah jadwal. Sistem dilengkapi dengan login, pengecekan input, dan tampilan jadwal terstruktur untuk memudahkan pengelolaan penggunaan lab.

# FLOWCHART
<img width="2060" height="1733" alt="image" src="https://github.com/user-attachments/assets/cb109f8b-22f4-4a08-ba12-f13cc9549fd2" />


PENJELASAN:

1. Start: Program dimulai.

Menu Login: Sistem menampilkan menu login dan meminta pengguna untuk menginput username dan password.

2. Proses Login:
Sistem memeriksa apakah login sebagai Mahasiswa atau Admin.
Jika login gagal, sistem mengurangi kesempatan login dan menanyakan lagi.
Jika kesempatan habis, program akan berhenti.

3. Menu Utama Mahasiswa / Admin (1,2,3 untuk mahasiswa, 1,2,3,4,5 untuk admin)

4. Menu 1 (Lihat Catatan/Jadwal)

Jika user admin ingin mengecek ruangan, sistem akan menampilkan seluruh daftar penggunaan ruangan laboratorium komputer.

Jika user mahasiswa ingin mengecek ruangan tertentu, sistem meminta input nama ruangan dan menampilkan daftar ruangan yang dicari. Jika tidak, sistem menampilkan seluruh daftar catatan/jadwal.

5. Menu 2 (Tambah Catatan/Jadwal)- Admin dan Mahasiswa

Pengguna menginput ruangan, kelas, tanggal, jam, dan nama kegiatan. 
Data akan disimpan oleh sistem dan catatan berhasil ditambahkan. 
Sistem akan menampilkan daftar catatan.

6. Menu 3 (Ubah Catatan/Jadwal) – hanya admin:

Sistem menampilkan seluruh catatan. 
Admin memilih ruangan yang ingin diubah dan menginput data baru (ruangan, kelas, tanggal, jam, nama kegiatan). 
Data berhasil diubah oleh sistem.

7. Menu 4 (Hapus Catatan/Jadwal) – hanya admin:

Sistem menampilkan seluruh catatan. 
Admin memilih catatan yang ingin dihapus. 
Catatan berhasil dihapus oleh sistem.

8. Menu Keluar- Admin dan Mahasiswa

program berhenti.

End: Program selesai dijalankan.


# PROGRAM PYTHON

```python
print("=======================================================")
print("|       SISTEM CATATAN PENGGUNAAN LAB KOMPUTER        |")
print("|                  LOGIN AKUN SEBAGAI                 |")
print("=======================================================")

# USER DAN ROLE
users = [
    {"username": "admin", "password": "123", "role": "Admin"},
    {"username": "mahasiswa", "password": "111", "role": "Mahasiswa"}
]

# DATA JADWAL RUANGAN
jadwal_ruangan = [
    {"ruangan": "D404", "kelas": "Kelas A", "tanggal": "10/09/2025", "jam": "08:00-09:00", "kegiatan": "Praktikum DDP"},
    {"ruangan": "D402", "kelas": "Kelas B", "tanggal": "10/09/2025", "jam": "11:00-12:00", "kegiatan": "Praktikum PTI"},
    {"ruangan": "D308", "kelas": "Kelas C", "tanggal": "10/09/2025", "jam": "07:00-08:00", "kegiatan": "Praktikum PTI"}
]

# LOGIN
def login():
    kesempatan = 3
    while kesempatan > 0:
        try:
            username = input("Masukkan username: ")
            password = input("Masukkan password: ")
            for user in users:
                if username == user["username"] and password == user["password"]:
                    print("Login berhasil sebagai", user["role"])
                    return user
            else:
                kesempatan -= 1
                print("Login gagal. Sisa kesempatan:", kesempatan)
                if kesempatan == 0:
                    return None
        except ValueError:
            print("Tolong masukkan angka.")
        except KeyboardInterrupt:
            print("\nJangan tekan CTRL + C ya!")
        except EOFError:
            print("\nJangan tekan CTRL + Z ya!")

# LIHAT JADWAL MAHASISWA (cek ruangan atau semua)
def lihat_jadwal_mahasiswa():
    try:
        cek = input("Apakah ingin cek ruangan tertentu? (iya/tidak): ")
        if cek == "iya":
            cari_ruangan = input("Masukkan ID Ruangan: ")
            nomor = 1
            ditemukan = False
            print("\n===== HASIL PENCARIAN RUANGAN =====")
            print("No | Ruangan | Kelas | Tanggal | Jam | Kegiatan")
            print("-----------------------------------------------")
            for jadwal in jadwal_ruangan:
                if jadwal['ruangan'] == cari_ruangan:
                    print(nomor, "|", jadwal['ruangan'], "|", jadwal['kelas'], "|", jadwal['tanggal'], "|", jadwal['jam'], "|", jadwal['kegiatan'])
                    nomor += 1
                    ditemukan = True
            if not ditemukan:
                print("Ruangan", cari_ruangan, "tidak ditemukan atau masih kosong.")
        else:
            lihat_semua_jadwal()
    except ValueError:
        print("Tolong masukkan angka.")
    except KeyboardInterrupt:
        print("\nJangan tekan CTRL + C ya!")
    except EOFError:
        print("\nJangan tekan CTRL + Z ya!")

# LIHAT SELURUH JADWAL
def lihat_semua_jadwal():
    print("===============================================")
    print("|             DAFTAR JADWAL RUANGAN           |")
    print("===============================================")
    print("No | Ruangan | Kelas | Tanggal | Jam | Kegiatan")
    print("-----------------------------------------------")
    nomor = 1
    for jadwal in jadwal_ruangan:
        print(nomor, "|", jadwal['ruangan'], "|", jadwal['kelas'], "|", jadwal['tanggal'], "|", jadwal['jam'], "|", jadwal['kegiatan'])
        nomor += 1

# TAMBAH JADWAL
def tambah_jadwal():
    try:
        ruangan = input("ID Ruangan: ")
        kelas = input("Kelas: ")
        tanggal = (input("Tanggal (DD/MM/YYYY): "))
        jam = (input("Jam (HH:MM-HH:MM): "))
        kegiatan = input("Nama Kegiatan: ")

        jadwal_baru = {"ruangan": ruangan, "kelas": kelas, "tanggal": tanggal, "jam": jam, "kegiatan": kegiatan}
        jadwal_ruangan.append(jadwal_baru)
        print("Data berhasil ditambahkan!")
        lihat_semua_jadwal()
    except ValueError:
        print("Tolong masukkan angka.")
    except KeyboardInterrupt:
        print("\nJangan tekan CTRL + C ya!")
    except EOFError:
        print("\nJangan tekan CTRL + Z ya!")

# UBAH JADWAL (Admin)
def ubah_jadwal():
    try:
        lihat_semua_jadwal()
        pilih = int(input("Nomor jadwal yang mau diubah (misal 1,2,3 dst.): "))
        if pilih == 1:
            jadwal = jadwal_ruangan[0]
        elif pilih == 2:
            jadwal = jadwal_ruangan[1]
        elif pilih == 3:
            jadwal = jadwal_ruangan[2]
        elif pilih == 4:
            jadwal = jadwal_ruangan[3]
        elif pilih == 5:
            jadwal = jadwal_ruangan[4]
        else:
            print("Nomor tidak valid atau belum ditambahkan.")
            return

        jadwal["ruangan"] = input("ID Ruangan Baru: ")
        jadwal["kelas"] = input("Kelas Baru: ")
        jadwal["tanggal"] = input("Tanggal Baru (DD/MM/YYYY): ")
        jadwal["jam"] = input("Jam Baru (HH:MM-HH:MM): ")
        jadwal["kegiatan"] = input("Nama Kegiatan Baru: ")

        print("Data berhasil diubah!")
        lihat_semua_jadwal()
    except ValueError:
        print("Tolong masukkan angka.")
    except KeyboardInterrupt:
        print("\nJangan tekan CTRL + C ya!")
    except EOFError:
        print("\nJangan tekan CTRL + Z ya!")

# HAPUS JADWAL (Admin)
def hapus_jadwal():
    try:
        lihat_semua_jadwal()
        pilih = int(input("Nomor jadwal yang mau dihapus (misal 1,2,3 dst.): "))
        if pilih == 1:
            jadwal_ruangan.pop(0)
        elif pilih == 2:
            jadwal_ruangan.pop(1)
        elif pilih == 3:
            jadwal_ruangan.pop(2)
        elif pilih == 4:
            jadwal_ruangan.pop(3)
        elif pilih == 5:
            jadwal_ruangan.pop(4)
        else:
            print("Nomor tidak valid atau belum ditambahkan.")
            return

        print("Data berhasil dihapus!")
        lihat_semua_jadwal()
    except ValueError:
        print("Tolong masukkan angka.")
    except KeyboardInterrupt:
        print("\nJangan tekan CTRL + C ya!")
    except EOFError:
        print("\nJangan tekan CTRL + Z ya!")

# MENU UTAMA
def menu(user):
    while True:
        print("\n===== MENU UTAMA =====")
        print("1. Lihat Jadwal")
        print("2. Tambah Jadwal")
        if user["role"] == "Admin":
            print("3. Ubah Jadwal")
            print("4. Hapus Jadwal")
            print("5. Keluar")
        else:
            print("3. Keluar")

        try:
            pilihan = input("Pilih menu: ")
            if pilihan == "1":
                if user["role"] == "Mahasiswa":
                    lihat_jadwal_mahasiswa()
                else:
                    lihat_semua_jadwal()
            elif pilihan == "2":
                tambah_jadwal()
            elif pilihan == "3" and user["role"] == "Admin":
                ubah_jadwal()
            elif pilihan == "4" and user["role"] == "Admin":
                hapus_jadwal()
            elif (pilihan == "3" and user["role"] == "Mahasiswa") or (pilihan == "5" and user["role"] == "Admin"):
                print("Keluar dari sistem. Sampai jumpa", user["username"])
                break
            else:
                print("Pilihan tidak valid.")
        except ValueError:
            print("Tolong masukkan angka.")
        except KeyboardInterrupt:
            print("\nJangan tekan CTRL + C ya!")
        except EOFError:
            print("\nJangan tekan CTRL + Z ya!")


user_login = login()
if user_login:
    menu(user_login)
```


# TAMPILAN AWAL
<img width="1648" height="332" alt="Screenshot_20250928_093527" src="https://github.com/user-attachments/assets/07f5406d-98fa-400a-8422-3442c61e2405" />
PENJELASAN: Tampilan awal pengguna akan diarahkan untuk login agar bisa masuk ke sistem. Pada menu login diberi 2 jenis username dan password yang berbeda. user dan password pertama adalah khusus admin yang bertugas untuk melihat, menambahkah, menghapus, dan update. User yang kedua adalah mahasiswa yang hanya bisa melihat dan menambah catatan penggunaan lab komputer.

# USER ADMIN (1. LIHAT JADWAL)
<img width="1626" height="807" alt="image" src="https://github.com/user-attachments/assets/50f1efb3-9ca3-4225-b83c-e5820cb3e9f5" />
PENJELASAN: Ketika admin memilih menu 1. Lihat Jadwal sistem akan langsung menampilkan seluruh catatan jadwal pengguna laboratorium komputer. Ketika admin sudah selesai melihat, admin bisa memilih menu "5. keluar", dan sistem berhenti.

# USER ADMIN (2. TAMBAH JADWAL)
<img width="1479" height="906" alt="image" src="https://github.com/user-attachments/assets/f2535736-1c1a-4485-8c4f-862eff67bcd6" />
PENJELASAN: Ketika admin memilih menu 2. Tambah jadwal admin akan diarahkan untuk menginput nama/id ruangan, kelas, tanggal, jam, dan kegiatan. setelah itu sistem akan menambahkan dan menampilkan daftar catatan baru.

# USER ADMIN (3. UBAH JADWAL)
<img width="1423" height="875" alt="{8CCAB369-9291-483E-A784-265A8E26D23C}" src="https://github.com/user-attachments/assets/bbc7c081-ddc5-4fdd-9cdc-8d518764d279" />
PENJELASAN: Ketika admin memilih menu 3. Ubah jadwal, sistem akan menampilkan daftar catatan penggunaan laboratorium komputer, lalu sistem akan menanyakan nomor catatan ruangan yang ingin diubah dan pengguna akan diarahkan untuk mengisi nama ruangan baru, kelas, tanggal dan jam penggunaan. Setelah itu, sistem akan mengubah daftar catatan sesuai permintaan pengguna. Sistem juga akan menampilkan daftar catatan ruangan terbaru.

# USER ADMIN (4. HAPUS JADWAL)
<img width="1462" height="966" alt="image" src="https://github.com/user-attachments/assets/50117a69-b7bb-4204-83fb-074e93f32176" />
PENJELASAN: Ketika admin memilih menu 4. Hapus catatan, sistem akan menampilkan daftar catatan penggunaan laboratorium komputer, lalu sistem akan menanyakan nomor catatan yang ingin dihapus dan sistem akan menghapus catatan sesuai permintaan pengguna. Sistem juga akan menampilkan daftar catatan terbaru.

# USER ADMIN (5. KELUAR)
<img width="924" height="485" alt="{EE4819CE-3117-42A3-9F89-14CC9489D0C8}" src="https://github.com/user-attachments/assets/b86b2705-94e3-4d3a-89bc-fda9bca8532c" />

PENJELASAN: Ketika admin memilih menu 5. Keluar maka sistem akan selesai dan menampilkan "Keluar dari sistem. Sampai jumpa admin".

# USER MAHASISWA (1. LIHAT JADWAL)
<img width="1422" height="870" alt="image" src="https://github.com/user-attachments/assets/733b0293-9790-4f85-ba25-9c1e7d574599" />
PENJELASAN: Ketika mahasiswa memilih menu 1. Lihat jadwal maka sistem akan menanyakan "Apakah Ingin cek ruangan tertentu?", jika iya maka pengguna diarahkan untuk menginput nama ruangan yang ingin dicek dan sistem akan menampilkan daftar ruangan ketika ruangan yang di input ada di daftar catatan. Jika pengguna memilih tidak sistem akan menampilkan seluruh daftar catatan ruangan.
<img width="1362" height="489" alt="image" src="https://github.com/user-attachments/assets/ddcc3943-d3bb-4d5b-aa7a-7772d944448b" />
PENJELASAN: Ketika mahasiswa mengecek ruangan yang tdiak ada didalam daftar catatan maka sistem akan menampilkan seperti diatas.

# USER MAHASISWA (2. TAMBAH JADWAL)
<img width="1400" height="863" alt="{A8FF2D1A-726B-4506-9153-C8C1D67C6F23}" src="https://github.com/user-attachments/assets/f3f57359-2cce-4928-b5a4-784d4e4ae639" />
Ketika mahasiswa memilih menu 2.Tambah jadwal admin akan diarahkan untuk menginput nama/id ruangan, kelas, tanggal, jam, dan kegiatan. setelah itu sistem akan menambahkan dan menampilkan daftar catatan baru.

# USER MAHASISWA (3. KELUAR)
<img width="1386" height="617" alt="{7F97084A-D854-4284-BB25-BFCD57C4D752}" src="https://github.com/user-attachments/assets/e8a65f3c-77b9-4794-88cc-0dfb3fba3027" />
Ketika mahasiswa memilih menu 3. Keluar maka sistem akan selesai dan menampilkan "Keluar dari sistem. Sampai jumpa mahasiswa".

# OUTPUT ERROR HANDLING
1. ValueError:
   <img width="1016" height="242" alt="{068D2C0B-A23E-4C31-BF3F-669CB6334A0A}" src="https://github.com/user-attachments/assets/1fe2cfce-e8a1-477a-9da4-ae7e478550e2" />
2. Keyboard interupt:
   <img width="1386" height="443" alt="{EE96F4FB-E081-4A60-8127-C602DA98C06B}" src="https://github.com/user-attachments/assets/f171b3a5-c18f-4152-9aa2-18185200111e" />
3. EOFError:
   <img width="1394" height="496" alt="{F4DBBCEA-B4AC-488F-A133-60D1EF1AC9FE}" src="https://github.com/user-attachments/assets/cec2d670-e715-4b57-9544-25b4b398f46d" />














