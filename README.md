# NAMA: AGUNG HERLAMBANG 
# KELAS: TI.24.A4
# NIM: 312410296
# MATKUL: BAHASA PEMROGRAMAN 

![image 2025-01-07 203043](https://github.com/user-attachments/assets/6371f870-5065-4659-bbae-a627601c2278)
Program ini adalah aplikasi sederhana untuk berjualan bebek rica rica di terminal. Program ini dibuat dengan pendekatan modular dan menggunakan prinsip OOP (Object-Oriented Programming).

## BERIKUT PROGRAM INPUT

```pyhton
class Mattress:
    def __init__(self, quantity):
        self.quantity = quantity
        self.price_per_unit = 20000

    def total_price(self):
        return self.quantity * self.price_per_unit


class View:
    @staticmethod
    def display_table(customer_name, date, quantity, total_price):
        print("\n+~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~+")
        print("|                     Hasil                       |")
        print("+~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~+")
        print(f"| Nama Pelanggan: {customer_name}                  |")
        print(f"| Tanggal: {date}                                 |")
        print(f"| Jumlah mie ayam  : {quantity}                        |")
        print(f"| Total Harga: Rp{total_price}                    |")
        print("+~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~+")


class Process:
    @staticmethod
    def validate_input(input_value):
        try:
            quantity = int(input_value)
            if quantity < 1:
                raise ValueError("Jumlah mie ayam tidak boleh kurang dari 1.")
            return quantity
        except ValueError as e:
            print(e)
            return None

    @staticmethod
    def validate_date(input_date):
        from datetime import datetime
        try:
            date_obj = datetime.strptime(input_date, "%m/%Y")
            return date_obj.strftime("%B %Y")  # Mengembalikan dalam format Bulan Tahun
        except ValueError:
            print("Format tanggal tidak valid. Gunakan MM/YYYY.")
            return None


def main():
    # Input dari pengguna
    customer_name = input("Masukkan nama pelanggan: ")
    user_input = input("Masukkan jumlah mie ayam: ")
    date_input = input("Masukkan tanggal (bulan/tahun - MM/YYYY): ")
    
    # Validasi input
    quantity = Process.validate_input(user_input)
    if quantity is None:
        return  # Menghentikan program jika input tidak valid

    date = Process.validate_date(date_input)
    if date is None:
        return  # Menghentikan program jika input tanggal tidak valid

    # Proses data
    mattress = Mattress(quantity)
    total_price = mattress.total_price()

    # Tampilkan hasil
    View.display_table(customer_name, date, quantity, total_price)


if __name__ == "__main__":
    main()

````
kode di atas merupakan program yang mensimulasikan pemesanan mie ayam, di mana pengguna dapat memasukkan nama pelanggan, jumlah mie ayam yang dipesan, dan tanggal pemesanan. Program ini menghitung total harga dan menampilkan hasilnya dalam format yang terstruktur.

## CLASS VIEW

```pyhton
@staticmethod
    def display_table(customer_name, date, quantity, total_price):
        print("\n+~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~+")
        print("|                     Hasil                       |")
        print("+~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~+")
        print(f"| Nama Pelanggan: {customer_name}                  |")
        print(f"| Tanggal: {date}                                 |")
        print(f"| Jumlah mie ayam  : {quantity}                        |")
        print(f"| Total Harga: Rp{total_price}                    |")
        print("+~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~+")
````

Ini adalah metode statis yang menampilkan hasil pemesanan dalam format tabel. Menampilkan informasi nama pelanggan, tanggal pemesanan, mie ayam yang dipesan, dan total harga. Format output tabel dibuat menggunakan karakter khusus (misalnya +, |, dan spasi) untuk memberikan tampilan yang terstruktur dan mudah dibaca.

## CALSS PROSES

```pyhton
def validate_input(input_value):
        try:
            quantity = int(input_value)
            if quantity < 1:
                raise ValueError("Jumlah mie ayam tidak boleh kurang dari 1.")
            return quantity
        except ValueError as e:
            print(e)
            return None

    @staticmethod
    def validate_date(input_date):
        from datetime import datetime
        try:
            date_obj = datetime.strptime(input_date, "%m/%Y")
            return date_obj.strftime("%B %Y")  # Mengembalikan dalam format Bulan Tahun
        except ValueError:
            print("Format tanggal tidak valid. Gunakan MM/YYYY.")
            return None
````

Metode statis ini memvalidasi input untuk jumlah mie ayam yang dimasukkan oleh pengguna. Pertama, mencoba mengonversi nilai input ke dalam bentuk integer. Jika berhasil, akan memeriksa apakah jumlah mie ayam lebih dari atau sama dengan 1. Jika valid, mengembalikan nilai quantity, jika tidak valid, mencetak pesan error dan mengembalikan None.

## FUNGSI MAIN

```pyhton
# Input dari pengguna
    customer_name = input("Masukkan nama pelanggan: ")
    user_input = input("Masukkan jumlah mie ayam: ")
    date_input = input("Masukkan tanggal (bulan/tahun - MM/YYYY): ")
    
    # Validasi input
    quantity = Process.validate_input(user_input)
    if quantity is None:
        return  # Menghentikan program jika input tidak valid

    date = Process.validate_date(date_input)
    if date is None:
        return  # Menghentikan program jika input tanggal tidak valid

    # Proses data
    mattress = Mattress(quantity)
    total_price = mattress.total_price()

    # Tampilkan hasil
    View.display_table(customer_name, date, quantity, total_price)


if __name__ == "__main__":
    main()
````
Fungsi utama ini berfungsi sebagai penghubung antara input pengguna, pemrosesan data, dan tampilan hasil. Input dari pengguna: Pengguna diminta untuk memasukkan nama pelanggan, jumlah mie ayam, dan tanggal pemesanan.

## BERIKUT CONTOH INPUT 

![image 2025-01-07 210316](https://github.com/user-attachments/assets/a57bb5e1-10d4-4d88-92f1-9c37acddf2b0)

