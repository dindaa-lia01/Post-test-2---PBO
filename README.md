Nama: Dinda Aulia Rizky   NIM: 2409116076   Kelas: B

# ***`Manajemen Daftar Obat di Apotek`***

   Program manajemen obat di apotek ini dibuat dengan menggunakan bahasa pemrograman Java yang memiliki tujuan untuk membantu pengelolaan data obat secara sederhana. Program ini merupakan lanjutan dari program sebelumnya dengan konsep CRUD (Create, Read, Update, Delete). Dalam perancangannya, program dibagi menjadi beberapa class yang masing-masing memiliki minimal tiga properties, serta menerapkan constructor untuk mempermudah inisialisasi objek. 
   
   Selain itu, penggunaan access modifier dilakukan untuk menjaga keamanan dan keteraturan data. Struktur program disusun dengan memanfaatkan packages agar lebih terorganisir, yaitu: package main yang berisi kode untuk menampilkan menu interaksi dengan pengguna, package service yang menyimpan logika utama CRUD, dan package model yang mendefinisikan struktur data termasuk atribut dan constructor dari objek obat. 
   
   Dengan pembagian ini, program menjadi lebih rapi, mudah dipahami, serta memisahkan tanggung jawab tiap bagian sesuai fungsinya. Program ini juga memiliki fitur search untuk mencari obat yang diperlukan, sehingga dapat memudahkan penggunanya dalam melakukan manajemen obat di apotek.

# A. Penjelasan Baris Kode

## 1. Package Main

- Package dan Import 

    Pada bagian ini, package main; menunjukkan bahwa kelas utama dari program ini berada dalam package bernama main. Kemudian terdapat perintah import service.obatService; yang berfungsi untuk memanggil kelas atau service dari package lain bernama service, di mana di dalamnya terdapat method untuk mengelola data obat. Selanjutnya, import java.util.Scanner; digunakan agar program bisa memakai kelas Scanner untuk membaca input dari pengguna.

  <img width="251" height="96" alt="Screenshot 2025-09-15 035709" src="https://github.com/user-attachments/assets/b286eb5b-3575-4e78-91b3-1e113b43e9a5" />

- Class apotek

  Program dimulai dengan mendefinisikan kelas utama bernama Apotek yang menjadi wadah eksekusi program. Di dalamnya terdapat method main yang berfungsi sebagai entry point, yaitu titik awal ketika program dijalankan. Pada method ini dibuat sebuah objek Scanner dengan perintah Scanner scanner = new Scanner(System.in); yang memungkinkan program untuk membaca input dari pengguna melalui keyboard. Selanjutnya, dibuat pula sebuah objek dari kelas obatService dengan sintaks obatService obatService = new obatService();. Objek ini digunakan untuk memanggil method-method yang telah didefinisikan di dalam kelas obatService, sehingga memudahkan pengelolaan data obat dalam program.

  <img width="480" height="135" alt="Screenshot 2025-09-15 034533" src="https://github.com/user-attachments/assets/03f1ae2b-1d3e-41e3-86ea-aa3ebfbfe2a0" />

- Menu Pilihan Program

  Pada bagian ini, kode mendefinisikan sebuah variabel int pilihan; untuk menyimpan input menu dari pengguna. Kemudian terdapat struktur do { ... } while yang digunakan untuk membuat perulangan menu agar selalu tampil sampai pengguna memilih keluar. Di dalamnya, terdapat beberapa baris System.out.println() yang berfungsi untuk menampilkan teks ke layar berupa daftar menu, mulai dari menampilkan daftar obat hingga keluar dari program. Setelah itu, input pilihan diambil menggunakan scanner.nextInt(); yang berfungsi membaca angka yang dimasukkan oleh pengguna. Baris scanner.nextLine(); digunakan untuk membersihkan buffer input agar tidak terjadi error saat membaca input selanjutnya.

  <img width="762" height="403" alt="Screenshot 2025-09-15 034548" src="https://github.com/user-attachments/assets/d21b0793-c3bc-4181-be0d-b50a18924609" />

- Switch Case Menu

  Pada bagian ini, kode menggunakan struktur switch (pilihan) untuk menentukan aksi berdasarkan input pengguna. Jika pengguna memilih angka 1, maka program akan memanggil obatService.tampilkanObat();, begitu juga untuk pilihan lain seperti tambahObat(), updateObat(), hapusObat(), dan cariObat(). Jika pengguna memilih 6, maka program akan mencetak pesan "Terima kasih, program selesai." melalui System.out.println. Sementara itu, jika pengguna memasukkan angka yang tidak sesuai dengan menu, maka blok default akan dijalankan dan menampilkan pesan "Pilihan tidak valid!". Perulangan } while (pilihan != 6); memastikan bahwa menu akan terus berulang kecuali pengguna memilih keluar.

  <img width="610" height="339" alt="Screenshot 2025-09-15 034559" src="https://github.com/user-attachments/assets/82280696-9a55-4e22-8510-1eb6f9811c59" />

## 2. Package Service

- Package dan Import 
        
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

## 3. Package Models

   - Package dan Import

     Kode ini menunjukkan bahwa kelas Obat berada dalam package bernama models, yang biasanya digunakan untuk menyimpan struktur data atau entitas. Selain itu, terdapat import java.time.LocalDate; yang digunakan untuk mengimpor class LocalDate dari library Java. LocalDate dipakai untuk menyimpan informasi tanggal kedaluwarsa obat, sehingga lebih akurat dibandingkan hanya menggunakan String.

     <img width="295" height="84" alt="Screenshot 2025-09-15 040306" src="https://github.com/user-attachments/assets/e224cf49-5a98-4453-a41c-c6b01c97900e" />

   - Deklarasi Kelas dan Konstruktor

     Kode ini mendefinisikan sebuah kelas bernama Obat yang berada dalam konsep Object-Oriented Programming (OOP). Di dalamnya terdapat atribut privat yaitu namaObat, kategori, expiredDate, stok, dan harga. Atribut-atribut ini diset sebagai private agar hanya bisa diakses melalui method khusus (getter dan setter), sehingga mendukung prinsip enkapsulasi. Pada bagian konstruktor public Obat(...), terdapat parameter untuk mengisi data awal dari atribut kelas. Keyword this digunakan untuk membedakan antara variabel lokal dengan atribut kelas, contohnya this.namaObat = namaObat;.

     <img width="835" height="419" alt="Screenshot 2025-09-15 040104" src="https://github.com/user-attachments/assets/19c038e3-8fe5-4b28-8737-c1ffb928b7d1" />

   - Getter dan Setter

     Bagian ini berisi kumpulan getter dan setter untuk setiap atribut. Getter seperti getNamaObat() berfungsi mengembalikan nilai dari atribut tertentu, sedangkan setter seperti setNamaObat(String namaObat) berfungsi mengubah nilai atribut tersebut. Pola ini berlaku untuk semua atribut: namaObat, kategori, expiredDate, stok, dan harga. Dengan adanya getter dan setter, akses data menjadi lebih aman dan fleksibel, karena program tidak langsung memanipulasi atribut, tetapi melalui method yang sudah disediakan.

     <img width="592" height="844" alt="Screenshot 2025-09-15 040229" src="https://github.com/user-attachments/assets/a3eda214-8a8b-4531-b640-b79bd4e64594" />

     <img width="415" height="362" alt="Screenshot 2025-09-15 040251" src="https://github.com/user-attachments/assets/16a4b4fd-3c4d-4eb6-b3b0-0639b12edb2e" />

   - Method tampilkanObat()

     Pada bagian ini terdapat method tampilkanObat() yang bertugas untuk menampilkan informasi detail dari objek obat yang dibuat. Data yang ditampilkan mencakup nama obat, kategori, tanggal kedaluwarsa, stok, dan harga. Setiap informasi dicetak ke layar dengan System.out.println(). Method ini berguna agar data objek bisa dilihat dengan mudah oleh pengguna dalam format yang rapi.

     
     <img width="523" height="254" alt="Screenshot 2025-09-15 040259" src="https://github.com/user-attachments/assets/6573571a-5f80-410d-b577-fd6944d4c21d" />

# B. Penjelasan Alur Output

1. Menu Tampilkan Daftar Obat

   Ketika pengguna memilih menu 1, program akan menjalankan fungsi untuk menampilkan daftar obat yang tersedia di dalam sistem. Output yang ditampilkan berupa informasi detail dari setiap obat, seperti nama obat, kategori, tanggal kedaluwarsa (Expired Date), jumlah stok, dan harga. Setiap obat dipisahkan dengan garis pemisah agar lebih rapi. Contohnya, program menampilkan data Amoxicillin, Paracetamol, Ibuprofen, dan Vitamin C beserta atributnya masing-masing. Hal ini menunjukkan bahwa data obat sudah tersimpan dalam sistem dan bisa dilihat kembali kapan saja oleh pengguna.

   <img width="665" height="813" alt="Screenshot 2025-09-15 041009" src="https://github.com/user-attachments/assets/89563fe2-f27a-475b-b55e-02d7447b3df5" />

3. Menu Tambah Obat

   Pada gambar kedua, pengguna memilih menu 2, yaitu Tambah Obat. Program kemudian meminta input dari pengguna berupa nama obat, kategori, tanggal kedaluwarsa, stok, dan harga. Setelah semua data dimasukkan, sistem akan menyimpannya ke dalam daftar obat. Sebagai contoh, pengguna menambahkan obat baru dengan nama Antasida Tablet, kategori Obat lambung, expired date 01-05-2027, stok 60, dan harga 3000. Setelah data dimasukkan, program menampilkan pesan konfirmasi “Obat berhasil ditambahkan!” yang berarti data obat baru sudah masuk ke dalam sistem.
   
   <img width="508" height="301" alt="Screenshot 2025-09-15 041312" src="https://github.com/user-attachments/assets/57640cff-2028-408b-bf49-e3532c0b2e6e" />

    Pengecekan:

   <img width="384" height="170" alt="image" src="https://github.com/user-attachments/assets/6260e20f-4d77-4067-93d3-b96de824b7ae" />
   

4. Menu Update Stok

   Pengguna memilih menu nomor 3 (Update Stok). Program menanyakan nomor obat yang ingin diupdate, lalu pengguna memasukkan nomor 5. Setelah itu, pengguna mengisi ulang data obat dengan nama Antasida Tablet, kategori Obat lambung, stok 0, dan harga 3000.0. Program kemudian mengonfirmasi bahwa “Obat berhasil diupdate!”. Proses ini menunjukkan bahwa data lama obat nomor 5 telah diganti dengan data baru.
   
   <img width="524" height="177" alt="image" src="https://github.com/user-attachments/assets/60d08c0a-8d11-4a8a-836a-217a2e837078" />

   <img width="405" height="148" alt="image" src="https://github.com/user-attachments/assets/31a37010-2f3b-4784-82ac-4b7125cd960c" />


   Pengecekan:

   <img width="364" height="165" alt="image" src="https://github.com/user-attachments/assets/ac1b72d5-2a28-41de-bdea-0b40dd782320" />
   
6. Menu Hapus Daftar

   Pengguna memilih menu nomor 4 (Hapus Daftar). Setelah itu, program meminta input nomor obat yang ingin dihapus. Pengguna memasukkan nomor 5, lalu sistem menghapus obat tersebut dari daftar dan menampilkan pesan “Obat berhasil dihapus!”. Ini menandakan proses penghapusan data obat berjalan sukses.

   <img width="517" height="178" alt="image" src="https://github.com/user-attachments/assets/3d4fc980-2856-4255-b9e3-d0460175e96c" />

   <img width="405" height="75" alt="image" src="https://github.com/user-attachments/assets/9f1c793b-c23d-44ef-992c-0707d14ea5c7" />

   Pengecekan:

   <img width="570" height="774" alt="image" src="https://github.com/user-attachments/assets/a7f259df-d288-4b53-90e8-72e23fb4186a" />


8. Menu Cari Obat

   Pengguna memilih menu nomor 5 (Cari Obat). Program meminta input nama obat yang ingin dicari, lalu pengguna mengetikkan kata kunci vitamin. Sistem menemukan data yang sesuai, yaitu Vitamin C, dengan kategori Suplemen, tanggal kedaluwarsa 2026-01-01, stok 100, dan harga Rp4000.0. Output ini menampilkan detail lengkap obat yang berhasil ditemukan berdasarkan kata kunci.
   
   <img width="543" height="325" alt="image" src="https://github.com/user-attachments/assets/118471b6-5632-4d48-a391-f5b55b4e5fce" />

   
10. Menu Keluar

    Pengguna memilih menu nomor 6 (Keluar). Program kemudian menampilkan pesan “Terima kasih telah menggunakan program! Program selesai.” yang menandakan aplikasi telah dihentikan secara normal. Dengan begitu, program kembali ke kondisi berhenti tanpa error.    
    <img width="517" height="227" alt="image" src="https://github.com/user-attachments/assets/c60bd6df-ca33-4963-a0f7-fed1a1fe2254" />


# C. Validasi Input

   1. Validasi Menu Utama

      Jika pengguna memilih menu di luar opsi yang tersedia (misalnya memasukkan angka 7 padahal hanya ada 1–6), program menampilkan pesan “Pilihan tidak valid!” lalu kembali ke menu utama. Ini memastikan hanya opsi yang benar yang bisa dijalankan.
      
   <img width="515" height="392" alt="image" src="https://github.com/user-attachments/assets/cc43f9ff-e636-49ca-be8e-acb6f8b1125a" />

   2. Validasi Tambah Obat

      Saat menambahkan obat (menu 2), jika pengguna tidak mengisi nama obat (kosong), program menampilkan pesan “Nama obat tidak boleh kosong!”. Hal ini mencegah data obat tersimpan tanpa informasi penting.

      <img width="525" height="224" alt="Screenshot 2025-09-15 043427" src="https://github.com/user-attachments/assets/3d5f901f-46c3-4ecd-a84d-01b3dfb0828a" />

   3. Validasi Hapus Obat
      
      Jika pengguna ingin menghapus obat dengan nomor yang tidak ada di daftar (misalnya memasukkan 5 sementara hanya ada nomor 3 dan 4), program menampilkan pesan “Nomor obat tidak valid!”. Ini menjaga agar data yang tidak ada tidak bisa dihapus.

      <img width="406" height="365" alt="Screenshot 2025-09-15 043641" src="https://github.com/user-attachments/assets/f898942e-146e-43e0-934e-1f42d3ed8e06" />

   4. Validasi Update Obat

      Sama halnya dengan hapus obat, jika pengguna memilih nomor obat yang tidak tersedia (contohnya nomor 6), program juga memberi pesan “Nomor obat tidak valid!”. Dengan begitu, hanya obat yang ada dalam daftar yang bisa diperbarui.

      <img width="404" height="375" alt="Screenshot 2025-09-15 043601" src="https://github.com/user-attachments/assets/7ea667d1-c63c-4a3c-9fb3-75b2ccf05d4f" />

   5. Validasi Cari Obat

      Jika pengguna memasukkan kata kunci pencarian yang tidak ditemukan dalam daftar (contohnya “siladex”), program menampilkan pesan “Obat dengan kata kunci ‘siladex’ tidak ditemukan.”. Ini memastikan pencarian hanya menampilkan data yang benar-benar ada.

      <img width="524" height="232" alt="Screenshot 2025-09-15 043701" src="https://github.com/user-attachments/assets/e9e2000e-0826-45f6-93fe-b163489e3061" />


      

