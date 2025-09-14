Nama: Dinda Aulia Rizky   NIM: 2409116076   Kelas: B

# ***`Manajemen Daftar Obat di Apotek`***

   Program manajemen obat di apotek ini dibuat dengan menggunakan bahasa pemrograman Java yang memiliki tujuan untuk membantu pengelolaan data obat secara sederhana. Program ini merupakan lanjutan dari program sebelumnya dengan konsep CRUD (Create, Read, Update, Delete). Dalam perancangannya, program dibagi menjadi beberapa class yang masing-masing memiliki minimal tiga properties, serta menerapkan constructor untuk mempermudah inisialisasi objek. Selain itu, penggunaan access modifier dilakukan untuk menjaga keamanan dan keteraturan data. Struktur program disusun dengan memanfaatkan packages agar lebih terorganisir, yaitu: package main yang berisi kode untuk menampilkan menu interaksi dengan pengguna, package service yang menyimpan logika utama CRUD, dan package model yang mendefinisikan struktur data termasuk atribut dan constructor dari objek obat. Dengan pembagian ini, program menjadi lebih rapi, mudah dipahami, serta memisahkan tanggung jawab tiap bagian sesuai fungsinya. Program ini juga memiliki fitur search untuk mencari obat yang diperlukan, sehingga dapat memudahkan penggunanya dalam melakukan manajemen obat di apotek.

# A. Penjelasan Baris Kode

## 1. Package Main

- Import dan Package

    c

- Class apotek

  Program dimulai dengan mendefinisikan kelas utama bernama Apotek yang menjadi wadah eksekusi program. Di dalamnya terdapat method main yang berfungsi sebagai entry point, yaitu titik awal ketika program dijalankan. Pada method ini dibuat sebuah objek Scanner dengan perintah Scanner scanner = new Scanner(System.in); yang memungkinkan program untuk membaca input dari pengguna melalui keyboard. Selanjutnya, dibuat pula sebuah objek dari kelas obatService dengan sintaks obatService obatService = new obatService();. Objek ini digunakan untuk memanggil method-method yang telah didefinisikan di dalam kelas obatService, sehingga memudahkan pengelolaan data obat dalam program.

  <img width="480" height="135" alt="Screenshot 2025-09-15 034533" src="https://github.com/user-attachments/assets/03f1ae2b-1d3e-41e3-86ea-aa3ebfbfe2a0" />

  

## 2. Package Service

- Import dan Package
        
    Pada bagian ini dilakukan import beberapa library yang dibutuhkan dalam program. models.Obat digunakan untuk memanggil class Obat yang berisi atribut dan method terkait data obat. LocalDate serta DateTimeFormatter dipakai untuk mengelola dan memformat tanggal kadaluarsa obat. ArrayList berfungsi sebagai struktur data dinamis untuk menyimpan kumpulan objek Obat, sedangkan Scanner memungkinkan program membaca input dari pengguna melalui console. Dengan adanya import ini, program dapat menjalankan operasi dasar seperti pengolahan tanggal, penyimpanan data obat, serta interaksi dengan pengguna.
       
   <img width="427" height="207" alt="Screenshot 2025-09-15 030959" src="https://github.com/user-attachments/assets/f684a1dd-62e1-4dad-af0a-efd8f8b36ea5" />

- Constructor
  
    Constructor obatService() digunakan untuk menginisialisasi data awal obat yang langsung dimasukkan ke dalam list daftarObat. Kode daftarObat.add(new Obat(...)) menambahkan objek baru Obat lengkap dengan parameter nama, kategori, tanggal kadaluarsa, stok, dan harga. Pada bagian tanggal, digunakan LocalDate.parse("01-12-2027", formatter) untuk mengubah input string tanggal menjadi objek LocalDate. Dengan cara ini, ketika program dijalankan, sudah ada beberapa data dummy obat yang bisa ditampilkan atau diolah tanpa perlu menambahkannya secara manual dari pengguna.

   <img width="894" height="166" alt="Screenshot 2025-09-15 031033" src="https://github.com/user-attachments/assets/b4b6fb09-8797-4613-9e15-951f734960d2" />

- Method tambahObat()
  
    Method tambahObat() berfungsi menambahkan obat baru berdasarkan input pengguna. Program menggunakan scanner.nextLine() untuk membaca string dari console, Integer.parseInt(scanner.nextLine()) untuk mengubah input string menjadi bilangan bulat sebagai stok, dan Double.parseDouble(scanner.nextLine()) untuk mengubah string menjadi angka desimal sebagai harga. Input tanggal juga diproses dengan LocalDate.parse() agar lebih terstruktur. Seluruh proses ini ditempatkan di dalam blok try-catch sehingga jika pengguna salah menginput (misalnya format tanggal salah), maka error bisa ditangani dan program akan menampilkan pesan peringatan. Setelah input valid, objek Obat baru dibuat lalu ditambahkan ke daftarObat menggunakan add().

   <img width="646" height="338" alt="Screenshot 2025-09-15 031055" src="https://github.com/user-attachments/assets/a76c5a22-ec3a-4ff5-b160-69a8394f1f42" />

- Method tampilkanObat()

    Method ini digunakan untuk menampilkan daftar obat yang tersimpan di daftarObat. Pertama, program mengecek apakah daftar kosong dengan if (daftarObat.isEmpty()). Jika kosong, maka muncul pesan bahwa tidak ada data. Jika terdapat data, perulangan for (int i = 0; i < daftarObat.size(); i++) digunakan untuk menampilkan setiap obat satu per satu. Pada setiap iterasi, program memanggil daftarObat.get(i).tampilkanObat(); yang menampilkan detail masing-masing obat sesuai method di class Obat. Dengan begitu, seluruh informasi obat dapat dilihat oleh pengguna.

   <img width="628" height="379" alt="Screenshot 2025-09-15 031240" src="https://github.com/user-attachments/assets/bf58f6cb-9318-4051-9e68-0dbe759fb439" />

- Method updateObat()

   Method updateObat() berfungsi untuk memperbarui data obat yang ada dalam list. Pertama, daftar obat ditampilkan, lalu pengguna diminta memilih nomor obat dengan Integer.parseInt(scanner.nextLine()) - 1 agar sesuai dengan indeks list. Setelah objek Obat dipilih, pengguna bisa memasukkan nama baru, kategori baru, stok baru, atau harga baru. Program menggunakan pengecekan if (!namaBaru.isEmpty()) agar hanya data yang diisi saja yang diperbarui, sedangkan data kosong tetap menggunakan nilai lama. Perubahan dilakukan melalui pemanggilan setter seperti setNamaObat(), setKategori(), setStok(), dan setHarga(). Dengan pendekatan ini, pengguna dapat mengubah sebagian atau seluruh atribut obat sesuai kebutuhan tanpa harus mengisi ulang semuanya.

   <img width="711" height="902" alt="Screenshot 2025-09-15 031349" src="https://github.com/user-attachments/assets/075c35cc-d7dd-4d0c-b6e0-1eb96bb80af7" />

- Method hapusObat()

   Method ini digunakan untuk menghapus obat dari list daftarObat. Program menampilkan daftar obat, lalu meminta pengguna memilih nomor obat yang ingin dihapus. Input yang dimasukkan diubah menjadi indeks list dengan Integer.parseInt(scanner.nextLine()) - 1. Jika indeks valid (dalam rentang ukuran list), maka obat akan dihapus menggunakan daftarObat.remove(index). Jika input tidak sesuai, maka program menampilkan pesan bahwa nomor obat tidak valid. Dengan demikian, pengguna dapat dengan mudah menghapus data yang sudah tidak diperlukan.

   <img width="523" height="417" alt="Screenshot 2025-09-15 031425" src="https://github.com/user-attachments/assets/9903d3b5-873b-4fb6-bfc9-a222a132cc7f" />

- Method cariObat()

   Method cariObat() bertugas mencari obat berdasarkan nama. Pengguna diminta memasukkan kata kunci, lalu input diubah ke huruf kecil dengan toLowerCase() agar pencarian tidak sensitif terhadap kapital. Selanjutnya, program melakukan perulangan pada daftarObat dan memeriksa apakah nama obat (getNamaObat().toLowerCase()) mengandung kata kunci dengan contains(keyword). Jika ditemukan, maka obat ditampilkan dengan memanggil tampilkanObat(). Jika setelah perulangan tidak ada yang cocok, program menampilkan pesan bahwa obat tidak ditemukan. Dengan mekanisme ini, pencarian menjadi lebih fleksibel karena bisa menemukan data berdasarkan sebagian nama obat.

   <img width="760" height="478" alt="Screenshot 2025-09-15 031448" src="https://github.com/user-attachments/assets/c894923f-b3f6-4806-a2dd-96e8f40b8e64" />

   












