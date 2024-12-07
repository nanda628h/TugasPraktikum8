# Tugas Praktikum 8 
Buat program sederhana dengan mengaplikasikan penggunaan class. Buatlah class untuk menampilkan daftar nilai mahasiswa, dengan ketentuan:

* Method tambah() untuk menambah data

* Method tampilkan() untuk menampilkan data

* Method hapus(nama) untuk menghapus data berdasarkan nama

* Method ubah(nama) untuk mengubah data berdasarkan nama

## kode program 
```python
class DaftarNilaiMahasiswa:
    def __init__(self):
        self.data_mahasiswa = []

    def tambah(self, nama, nilai):
        """Menambahkan data mahasiswa."""
        self.data_mahasiswa.append({'nama': nama, 'nilai': nilai})
        print(f"Data {nama} berhasil ditambahkan.")

    def tampilkan(self):
        """Menampilkan daftar nilai mahasiswa."""
        if not self.data_mahasiswa:
            print("Daftar mahasiswa kosong.")
        else:
            print("Daftar Nilai Mahasiswa:")
            for i, mahasiswa in enumerate(self.data_mahasiswa, start=1):
                print(f"{i}. Nama: {mahasiswa['nama']}, Nilai: {mahasiswa['nilai']}")

    def hapus(self, nama):
        """Menghapus data mahasiswa berdasarkan nama."""
        for mahasiswa in self.data_mahasiswa:
            if mahasiswa['nama'] == nama:
                self.data_mahasiswa.remove(mahasiswa)
                print(f"Data {nama} berhasil dihapus.")
                return
        print(f"Data dengan nama {nama} tidak ditemukan.")

    def ubah(self, nama, nilai_baru):
        """Mengubah nilai mahasiswa berdasarkan nama."""
        for mahasiswa in self.data_mahasiswa:
            if mahasiswa['nama'] == nama:
                mahasiswa['nilai'] = nilai_baru
                print(f"Nilai {nama} berhasil diubah menjadi {nilai_baru}.")
                return
        print(f"Data dengan nama {nama} tidak ditemukan.")


# Contoh penggunaan program
if __name__ == "__main__":
    daftar_nilai = DaftarNilaiMahasiswa()
    
    while True:
        print("\nMenu:")
        print("1. Tambah Data")
        print("2. Tampilkan Data")
        print("3. Hapus Data")
        print("4. Ubah Data")
        print("5. Keluar")
        
        pilihan = input("Pilih menu (1-5): ")
        
        if pilihan == '1':
            nama = input("Masukkan nama mahasiswa: ")
            nilai = input("Masukkan nilai mahasiswa: ")
            daftar_nilai.tambah(nama, nilai)
        elif pilihan == '2':
            daftar_nilai.tampilkan()
        elif pilihan == '3':
            nama = input("Masukkan nama mahasiswa yang ingin dihapus: ")
            daftar_nilai.hapus(nama)
        elif pilihan == '4':
            nama = input("Masukkan nama mahasiswa yang ingin diubah: ")
            nilai_baru = input("Masukkan nilai baru: ")
            daftar_nilai.ubah(nama, nilai_baru)
        elif pilihan == '5':
            print("Program selesai. Terima kasih!")
            break
        else:
            print("Pilihan tidak valid. Silakan pilih menu 1-5.")
```
## penjelasan kode

1. Class DaftarNilaiMahasiswa
Class ini merupakan inti dari program yang berfungsi sebagai pengelola data mahasiswa. Semua data mahasiswa akan disimpan dalam atribut self.data_mahasiswa, yang berupa list.

__init__(self)
Konstruktor ini otomatis dijalankan saat instance dari class dibuat.
Atribut self.data_mahasiswa adalah list kosong yang akan menyimpan data mahasiswa berupa dictionary (contoh: {'nama': 'Ali', 'nilai': 90}).
2. Method Tambah (tambah)
```python
def tambah(self, nama, nilai):
    self.data_mahasiswa.append({'nama': nama, 'nilai': nilai})
    print(f"Data {nama} berhasil ditambahkan.")
Fungsi:
Menambahkan data mahasiswa berupa nama dan nilai.
Data yang ditambahkan berupa dictionary dengan format {'nama': nama, 'nilai': nilai}.
Cara Kerja:
Data baru ditambahkan ke list self.data_mahasiswa menggunakan append().
Setelah data berhasil ditambahkan, pesan konfirmasi akan ditampilkan ke pengguna.
3. Method Tampilkan (tampilkan)
python
Copy code
def tampilkan(self):
    if not self.data_mahasiswa:
        print("Daftar mahasiswa kosong.")
    else:
        print("Daftar Nilai Mahasiswa:")
        for i, mahasiswa in enumerate(self.data_mahasiswa, start=1):
            print(f"{i}. Nama: {mahasiswa['nama']}, Nilai: {mahasiswa['nilai']}")
```
Fungsi:
Menampilkan seluruh data mahasiswa yang ada di self.data_mahasiswa.
Cara Kerja:
Jika self.data_mahasiswa kosong, ditampilkan pesan "Daftar mahasiswa kosong."
Jika ada data, ditampilkan nama dan nilai setiap mahasiswa menggunakan perulangan for. Indeks ditambahkan untuk mempermudah membaca data.
4. Method Hapus (hapus)
```python
def hapus(self, nama):
    for mahasiswa in self.data_mahasiswa:
        if mahasiswa['nama'] == nama:
            self.data_mahasiswa.remove(mahasiswa)
            print(f"Data {nama} berhasil dihapus.")
            return
    print(f"Data dengan nama {nama} tidak ditemukan.")
```
Fungsi:
Menghapus data mahasiswa berdasarkan nama.
Cara Kerja:
Program mencari data mahasiswa yang memiliki nama sesuai dengan input.
Jika ditemukan, data dihapus dari self.data_mahasiswa menggunakan remove().
Jika nama tidak ditemukan, ditampilkan pesan "Data dengan nama {nama} tidak ditemukan."
5. Method Ubah (ubah)
```python
def ubah(self, nama, nilai_baru):
    for mahasiswa in self.data_mahasiswa:
        if mahasiswa['nama'] == nama:
            mahasiswa['nilai'] = nilai_baru
            print(f"Nilai {nama} berhasil diubah menjadi {nilai_baru}.")
            return
    print(f"Data dengan nama {nama} tidak ditemukan.")
```
Fungsi:
Mengubah nilai mahasiswa berdasarkan nama.
Cara Kerja:
Program mencari data mahasiswa berdasarkan nama.
Jika ditemukan, nilai mahasiswa diubah dengan nilai baru yang dimasukkan.
Jika nama tidak ditemukan, ditampilkan pesan "Data dengan nama {nama} tidak ditemukan."
6. Program Utama
```python
if __name__ == "__main__":
    daftar_nilai = DaftarNilaiMahasiswa()
    
    while True:
        print("\nMenu:")
        print("1. Tambah Data")
        print("2. Tampilkan Data")
        print("3. Hapus Data")
        print("4. Ubah Data")
        print("5. Keluar")
        
        pilihan = input("Pilih menu (1-5): ")
        
        if pilihan == '1':
            nama = input("Masukkan nama mahasiswa: ")
            nilai = input("Masukkan nilai mahasiswa: ")
            daftar_nilai.tambah(nama, nilai)
        elif pilihan == '2':
            daftar_nilai.tampilkan()
        elif pilihan == '3':
            nama = input("Masukkan nama mahasiswa yang ingin dihapus: ")
            daftar_nilai.hapus(nama)
        elif pilihan == '4':
            nama = input("Masukkan nama mahasiswa yang ingin diubah: ")
            nilai_baru = input("Masukkan nilai baru: ")
            daftar_nilai.ubah(nama, nilai_baru)
        elif pilihan == '5':
            print("Program selesai. Terima kasih!")
            break
        else:
            print("Pilihan tidak valid. Silakan pilih menu 1-5.")
```
Bagian ini adalah menu interaktif.
Pengguna dapat memilih untuk menambah, menampilkan, menghapus, atau mengubah data, serta keluar dari program.
Input pengguna dikontrol menggunakan perulangan while True, yang terus berjalan sampai pengguna memilih menu keluar (5).
Alur Program:
Pengguna Memilih Menu
```python
Pilihan 1: Menambah data mahasiswa.
Pilihan 2: Menampilkan daftar nilai mahasiswa.
Pilihan 3: Menghapus data berdasarkan nama mahasiswa.
Pilihan 4: Mengubah nilai berdasarkan nama mahasiswa.
Pilihan 5: Keluar dari program.
Pengguna Memberikan Input
```

Nama dan nilai dimasukkan untuk menambah atau mengubah data.
Nama dimasukkan untuk menghapus data.
Proses Data

Program memproses input pengguna sesuai dengan pilihan menu.
Data diolah dalam atribut self.data_mahasiswa.
Menampilkan Hasil

Program menampilkan daftar nilai mahasiswa, konfirmasi perubahan data, atau pesan kesalahan jika ada.
Contoh Penggunaan:
Tambah Data:
```python

Menu:
1. Tambah Data
2. Tampilkan Data
3. Hapus Data
4. Ubah Data
5. Keluar
Pilih menu (1-5): 1
Masukkan nama mahasiswa: Ali
Masukkan nilai mahasiswa: 90
Data Ali berhasil ditambahkan.
Tampilkan Data:
```


```python
Menu:
1. Tambah Data
2. Tampilkan Data
3. Hapus Data
4. Ubah Data
5. Keluar
Pilih menu (1-5): 2
Daftar Nilai Mahasiswa:
1. Nama: Ali, Nilai: 90
```
Ubah Data:

```python
Menu:
1. Tambah Data
2. Tampilkan Data
3. Hapus Data
4. Ubah Data
5. Keluar
Pilih menu (1-5): 4
Masukkan nama mahasiswa yang ingin diubah: Ali
Masukkan nilai baru: 95
Nilai Ali berhasil diubah menjadi 95.
```
