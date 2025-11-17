# 🍽️ Aplikasi Pemesanan Menu Sederhana (C++)

Aplikasi konsol sederhana ini ditulis dalam C++ untuk mensimulasikan proses pemesanan menu makanan, menghitung total harga, dan menerapkan diskon 10% jika total pembelian melebihi Rp. 100.000.

---

## 🚀 Cara Menjalankan Program

1.  **Kompilasi**: Gunakan kompiler C++ (seperti G++).
    ```bash
    g++ nama_file_anda.cpp -o menu_pesanan
    ```
2.  **Jalankan**: Eksekusi program yang telah dikompilasi.
    ```bash
    ./menu_pesanan
    ```
3.  **Interaksi**: Ikuti petunjuk di konsol untuk memilih menu dan jumlah pesanan. Anda dapat memesan item berulang kali hingga memilih 'n' (tidak).

---

## 💻 Penjelasan Fungsi dan Struktur Kode

Program ini dibangun di atas sebuah `struct` dan beberapa fungsi penting untuk menangani proses pemesanan dan perhitungan.

### 1. `struct Barang`

Ini adalah **struktur data** dasar yang digunakan untuk mendefinisikan item-item menu. Setiap item memiliki dua properti:

| Properti | Tipe Data | Deskripsi |
| :------- | :-------- | :-------- |
| `nama`   | `string`  | Nama makanan atau minuman. |
| `harga`  | `int`     | Harga satuan dari item tersebut. |

---

### 2. Fungsi Perhitungan

#### `int hitungTotal(int harga, int jumlah)`
* **Tujuan**: Menghitung **subtotal** untuk satu item menu tertentu.
* **Mekanisme**: Mengembalikan hasil perkalian `harga` satuan dengan `jumlah` yang dipesan.
    *Contoh: Jika harga 8000 dan jumlah 2, hasilnya adalah 16000.*

#### `int hargaSetelahDiskon(int total)`
* **Tujuan**: Menghitung **jumlah diskon** yang akan diberikan.
* **Mekanisme**:
    * Mengecek apakah `total` keseluruhan belanja lebih dari **Rp. 100.000**.
    * Jika **YA**, mengembalikan nilai diskon sebesar **10%** (`total * 0.10`).
    * Jika **TIDAK**, mengembalikan **0** (tidak ada diskon).

---

### 3. `int main()`

Ini adalah **fungsi utama** tempat semua logika program berjalan:

1.  **Inisialisasi**: Mendefinisikan menu makanan dalam array `Barang daftar[6]` dan variabel awal seperti `totalKeseluruhan`, `diskon`, dan `totalSebelumDiskon`.
2.  **Loop Pemesanan (`do-while`)**:
    * Menampilkan menu yang tersedia.
    * Menerima input `pilih` (pilihan menu) dan `jumlah` dari pengguna.
    * Menghitung total subpesanan dan menambahkannya ke `totalKeseluruhan`.
    * Perulangan berlanjut hingga pengguna memasukkan 'n' atau 'N'.
3.  **Perhitungan Diskon**:
    * Nilai `totalKeseluruhan` sebelum diproses disimpan ke `totalSebelumDiskon`.
    * Fungsi `hargaSetelahDiskon` dipanggil untuk mendapatkan nilai `diskon`.
    * `totalKeseluruhan` diperbarui dengan mengurangi nilai `diskon`.
4.  **Output**: Mencetak hasil akhir transaksi:
    * **Total sebelum diskon**.
    * Nilai **Diskon** yang diterapkan (jika ada).
    * **Total keseluruhan setelah diskon** yang harus dibayar.
