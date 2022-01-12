# UAS
# Membuat package dan modul dengan struktur:
- ✓ daftar_nilai.py berisi modul untuk:
tambah_data, ubah_data, hapus_data, dan
cari_data
- ✓ view_nilai.py berisi modul untuk:
cetak_daftar_nilai, cetak_hasil_pencarian
- ✓ input_nilai.py berisi modul untuk:
input_data yang meminta pengguna
memasukkan data.
- ✓ main.py berisi program utama (menu
pilihan yang memanggil semua menu
yang ada)
## Tampilan package dan modul 
![Screenshot (164)](https://user-images.githubusercontent.com/92356397/149060610-a50930bb-404a-4456-a1cd-b68691f8314d.png)

## Berikut tampilan inputnya:
```python
from view.input_nilai import *

dataMahasiswa = {}


def tambah_data():
    global dataMahasiswa
    nama = input_nama()
    nim = input_nim()
    nilaiTugas = input_nilaiTugas()
    nilaiUts = input_nilaiUts()
    nilaiUas = input_nilaiUas()
    nilaiAkhir = (0.30 * nilaiTugas) + (0.35 * nilaiUts) + (0.35 * nilaiUas)
    dataMahasiswa[nama] = nim, nilaiTugas, nilaiUts, nilaiUas, nilaiAkhir
    print("\nData Berhasil Ditambahkan!")
    return dataMahasiswa

def ubah_data():
    nama = input("Masukkan Nama: ")
    if nama in dataMahasiswa.keys():
        nim = input_nim()
        nilaitugas = input_nilaiTugas()
        nilaiUts = input_nilaiUts()
        nilaiUas = input_nilaiUas()
        nilaiAkhir = (0.30 * nilaiTugas) + (0.35 * nilaiUts) + (0.35 * nilaiUas)
        dataMahasiswa[nama] = nim, nilaiTugas, nilaiUts, nilaiUas, nilaiAkhir
        print("\nData Berhasil Di Update!")
    else:
        print("Data tidak ditemukan!")


def hapus_data():
    nama = input("Masukkan Nama:  ")
    if nama in dataMahasiswa.keys():
        del dataMahasiswa[nama]
        print("Data",nama, "Telah dihapus!")
    else:
        print("Data Mahasiswa Tidak Ada".format(nama))
```
- di atas adalah program pada modul daftar_nilai.py

```python
from model.daftar_nilai import *


def cetak_daftar_nilai():
    if dataMahasiswa.items():
        print("\n                      DAFTAR NILAI MAHASISWA                    ")
        print("==================================================================")
        print("| No |     Nama     |    NIM    | Tugas |  UTS  |  UAS  |  Akhir |")
        print("==================================================================")
        i = 0
        for x in dataMahasiswa.items():
            i += 1
            print("| {6:2} | {0:12s} | {1:9s} | {2:5} | {3:5} | {4:5} | {5:6} |".format(x[0], x[1][0], x[1][1], x[1][2], x[1][3], x[1][4], i))
        print("==================================================================")
    else:
        print("\n                      DAFTAR NILAI MAHASISWA                    ")
        print("==================================================================")
        print("| No |     Nama     |    NIM    | Tugas |  UTS  |  UAS  |  Akhir |")
        print("==================================================================")
        print("|                          TIDAK ADA DATA!                       |")
        print("==================================================================")


def cetak_hasil_pencarian():
    nama = input("Masukkan Nama        : ")
    if nama in dataMahasiswa.keys():
        print("\n                   DAFTAR NILAI MAHASISWA                   ")
        print("==============================================================")
        print("|     Nama     |    NIM    | Tugas |  UTS  |  UAS  |  Akhir  |")
        print("==============================================================")
        print("| {0:12s} | {1:9s} | {2:5} | {3:5} | {4:5} | {5:6}  |".format(nama, dataMahasiswa[nama][0], dataMahasiswa[nama][1], dataMahasiswa[nama][2], dataMahasiswa[nama][3], dataMahasiswa[nama][4]))
        print("==============================================================")
    else:
        print("Datanya {0} Tidak Ada ".format(nama))
```
- diatas adalah program untuk modul cetak_nilai.py

```python
def input_nama():
    global nama
    nama = input("Masukkan Nama        : ")
    return nama


def input_nim():
    global nim
    nim = input("Masukkan NIM         : ")
    return nim


def input_nilaiTugas():
    global nilaiTugas
    nilaiTugas = int(input("Masukkan Nilai Tugas : "))
    return nilaiTugas


def input_nilaiUts():
    global nilaiUts
    nilaiUts = int(input("Masukkan Nilai UTS   : "))
    return nilaiUts


def input_nilaiUas():
    global nilaiUas
    nilaiUas = int(input("Masukkan Nilai UAS   : "))
    return nilaiUas
```
- diatas adalah program untuk modul input_nilai.py

```python
from view.cetak_nilai import *

while True:
    c = input("\nT)ambah, U)bah, C)ari, H)apus, L)ihat, K)eluar: ")

    if c.lower() == 't':
        tambah_data()

    elif c.lower() == 'u':
        ubah_data()

    elif c.lower() == 'c':
        cetak_hasil_pencarian()

    elif c.lower() == 'h':
        hapus_data()

    elif c.lower() == 'l':
        cetak_daftar_nilai()

    elif c.lower() == 'k':
        break

    else:
        print("Menu yang anda maksud tidak tersedia, Silahkan pilih menu yang tersedia")
```
- diatas adalah program untuk modul main.py

# Berikut outpotnya:
![Screenshot (165)](https://user-images.githubusercontent.com/92356397/149060425-0a2c6cbd-8871-4890-addd-c17dc5537716.png)
![Screenshot (166)](https://user-images.githubusercontent.com/92356397/149060446-6c5e2bce-ae78-41c0-b34a-63bd12b2fee7.png)
![Screenshot (167)](https://user-images.githubusercontent.com/92356397/149060481-933851ed-3ea2-4cdb-8834-79b5d9ce6cba.png)
![Screenshot (168)](https://user-images.githubusercontent.com/92356397/149060505-cc022d31-ecdc-46d4-b6f7-08e400ce74cb.png)

- diatas tampilan untuk keluar atau menutup program

# SEKIAN DAN TERIMAKASIH
