<h1>
IF2150 REKAYASA PERANGKAT LUNAK
<br>
TUGAS 5
<br>
DESKRIPSI PERANCANGAN PERANGKAT LUNAK (DPPL)
</h1>
<br>

## *Food Waste Stop*
<img width="40%" alt="log" src="https://github.com/user-attachments/assets/4444d8f8-8565-4a3e-bc73-00ac09b6d0c9" />

### Untuk: *Aurelia Jennifer Gunawan*

Dipersiapkan oleh:
| Informasi | Keterangan |
| --- | --- |
| Kelas | *K02* |
| Kelompok | *G06*  |

| NIM | Nama |
|---|---|
| *13525122* | *Nadia Aulia Syafarani* |
| *13525041* | *Renata Puspanegara Ninagan* |
| *13525119* | *Ghina Emelia Yantes* |
| *13525017* | *Cendra Asih Chairunnisa* |
| *13525089* | *Sherin Felicia Danessa* |
---

## Daftar Perubahan

| Revisi | Deskripsi |
| :--- | :--- |
| *A* | *Deskripsikan perubahan yang dilakukan dari dokumen sebelumnya pada dokumen ini. Jika tidak terdapat perubahan, harap kosongkan tabel.* |
| *B* |  |
| *C* |  |
| ... |  |

---

<br>

> **Petunjuk pengerjaan:** *[Silahkan hapus bagian ini setelah selesai mengerjakan]*
>
> Dokumen ini melanjutkan **Deskripsi Perancangan Perangkat Lunak**. Gunakan nama, ID, kebutuhan, dan use case yang konsisten dengan kedua dokumen tersebut. Contoh pola ID baru di bawah dapat disesuaikan dengan kesepakatan kelompok, ID yang sudah ada tetap dipertahankan.

<br>

---


# BAB 1: Pendahuluan

## 1.1 Tujuan Penulisan Dokumen
Dokumen Deskripsi Perancangan Perangkat Lunak (DPPL) ini disusun untuk menjelaskan rancangan aplikasi web Food Waste Stop sebagai bagian dari Tugas Besar mata kuliah Rekayasa Perangkat Lunak (RPL). Dokumen ini melanjutkan DPPL sebelumnya yang memuat lingkungan implementasi, arsitektur, realisasi use case, dan diagram kelas keseluruhan, lalu melengkapinya dengan perancangan rinci setiap kelas (operasi, atribut, serta algoritma/*query* untuk operasi penting) serta perancangan antarmuka pengguna. Dengan demikian, kebutuhan pada SKPL dan arsitektur pada APL diterjemahkan menjadi rancangan yang lengkap dan siap diimplementasikan.

Dokumen ini ditujukan bagi asisten dan/atau dosen mata kuliah RPL sebagai bahan evaluasi dan penilaian, serta bagi anggota kelompok sebagai acuan pada tahap implementasi dan pengujian aplikasi.

## 1.2 Lingkup Masalah
Industri makanan sering menghasilkan makanan surplus yang masih layak konsumsi tetapi tidak terjual. Makanan tersebut umumnya dibuang sehingga menambah sampah makanan dan menimbulkan kerugian ekonomi bagi pelaku industri. Selain itu, belum tersedia wadah yang memudahkan penjualan makanan surplus kepada konsumen dengan harga terjangkau.

Food Waste Stop merupakan web aplikasi untuk kegiatan jual-beli makanan surplus. Food Waste Stop berfokus menjadi solusi permasalahan sampah makanan industri. Selain itu, Food Waste Stop juga mengurangi kerugian ekonomi industri.

## 1.3 Definisi, Istilah, dan Singkatan

Tabel 1.3. Definisi Istilah dan Singkatan

| Singkatan, Akronim, atau Istilah | Penjelasan |
| :--- | :--- |
| *P/L* | *Singkatan dari Perangkat Lunak, yaitu aplikasi yang memberikan perintah kepada komputer untuk menjalankan tugas tertentu.* |
| *DPPL* | *Singkatan dari Deskripsi Perancangan Perangkat Lunak, yaitu dokumen yang menjelaskan rancangan arsitektur, kelas, interaksi antarobjek, dan antarmuka yang menjadi acuan implementasi perangkat lunak.* |
| *SKPL* | *Singkatan dari Spesifikasi Kebutuhan Perangkat Lunak.* |
| *APL* | *Singkatan dari Arsitektur Perangkat Lunak.* |
| *UC* | *Singkatan dari Use Case.* |
| *MVC* | *Model-View-Controller, yaitu pola arsitektur yang memisahkan tampilan (View), pengendali alur (Controller), dan data serta aturan bisnis (Model).* |
| *Visibility* | *Tingkat akses atribut atau operasi suatu kelas. Public berarti dapat diakses oleh kelas lain, sedangkan private hanya dapat diakses dari dalam kelas itu sendiri.* |
| *Signature Operasi* | *Penulisan lengkap suatu operasi yang memuat nama operasi, daftar parameter beserta tipenya, dan tipe nilai kembalian.* |
| *Pseudocode* | *Penulisan langkah-langkah algoritma dengan bahasa yang menyerupai bahasa pemrograman tetapi tidak terikat sintaks bahasa tertentu.* |
| *Query* | *Perintah SQL yang digunakan untuk membaca, menambah, mengubah, atau menghapus data pada database.* |
| *Rancangan Antarmuka* | *Gambaran tata letak layar aplikasi beserta komponen dan aksi yang dapat dilakukan pengguna pada layar tersebut.* |
| *QRIS* | *Quick Response Code Indonesian Standard. Pada aplikasi ini digunakan versi dummy sebagai simulasi pembayaran.* |
| *bcrypt* | *Algoritma hashing password yang menggunakan salt dan faktor biaya sehingga tahan terhadap serangan tebak massal.* |
| *Soft delete* | *Penghapusan data dengan menandainya sebagai nonaktif, bukan menghapusnya secara fisik dari database.* |

## 1.4 Aturan Penomoran

Tabel 1.4. Aturan Penomoran

| Hal/Bagian | Penomoran | Keterangan |
| :--- | :--- | :--- |
| *Kebutuhan Fungsional* | *KFXX* | *Layanan atau fungsi yang harus disediakan sistem, yaitu apa yang dapat dilakukan sistem terhadap masukan dan bagaimana sistem berperilaku pada situasi tertentu* |
| *Kebutuhan Non-Fungsional* | *KNFXX* | *Batasan atau kualitas yang harus dipenuhi sistem, seperti performa, keamanan, keandalan, dan kemudahan penggunaan* |
| *Aktor* | *AXX* | *Pihak di luar sistem (pengguna, perangkat, atau sistem lain) yang berinteraksi dengan sistem* |
| *Use Case* | *UCXX* | *Rangkaian interaksi antara aktor dan sistem untuk mencapai suatu tujuan tertentu* |
| *Kelas* | *CXX* | *Representasi objek dalam sistem yang memiliki atribut dan metode. C01–C07 mengikuti SKPL, sedangkan C08 dan seterusnya adalah kelas baru pada tahap perancangan* |
| *Algoritma* | *Algo-CXX-YY* | *Kerangka algoritma (pseudocode) untuk operasi penting pada perancangan rinci kelas (BAB 5), dengan CXX adalah ID kelas pemilik operasi dan YY adalah nomor urut algoritma pada kelas tersebut* |
| *Query* | *Q-CXX-YY* | *Query SQL yang digunakan oleh operasi pada perancangan rinci kelas (BAB 5), dengan CXX adalah ID kelas pemilik operasi dan YY adalah nomor urut query pada kelas tersebut* |
| *Layar Antarmuka* | *SXX* | *Layar/halaman antarmuka aplikasi pada perancangan antarmuka (BAB 6), dinomori berurutan mulai dari S01* |
| *Objek Antarmuka* | *SXX-OYY* | *Objek yang tampil pada suatu layar antarmuka, dengan SXX adalah ID layar dan YY adalah nomor urut objek pada layar tersebut* |

## 1.5 Referensi
- Dokumen Spesifikasi Kebutuhan Perangkat Lunak (SKPL) Food Waste Stop, K02-G06.
- Dokumen Arsitektur Perangkat Lunak (APL) Food Waste Stop, K02-G06.
- Dokumen Deskripsi Perancangan Perangkat Lunak (DPPL) Food Waste Stop versi sebelumnya (Milestone 7), K02-G06.
- Sommerville, I. (2016). *Software Engineering* (10th ed.). Pearson.
- PowerPoint Rekayasa Perangkat Lunak "Objek, Tanggung Jawab, dan Kolaborasi" & "Stereotipe, Gaya Kendali, dan Lapisan".
- Diagram UML: [https://www.drawio.com/](https://www.drawio.com/), [https://staruml.io/](https://staruml.io/), [https://plantuml.com/](https://plantuml.com/)
- Dokumentasi PostgreSQL 15: [https://www.postgresql.org/docs/15/](https://www.postgresql.org/docs/15/)

## 1.6 Deskripsi Umum Dokumen (Ikhtisar)
BAB 1 berisi pendahuluan dokumen, meliputi tujuan, lingkup masalah, definisi, aturan penomoran, dan referensi. BAB 2 membahas perancangan arsitektur, meliputi lingkungan implementasi, *style/pattern* acuan, identifikasi komponen, dan model arsitektur. BAB 3 berisi realisasi setiap use case dalam bentuk identifikasi kelas, *sequence diagram*, dan diagram kelas. BAB 4 menyajikan diagram kelas perancangan keseluruhan beserta daftar atribut dan metodenya. BAB 5 berisi perancangan rinci setiap kelas, meliputi operasi, atribut, serta algoritma/*query* untuk operasi penting. BAB 6 berisi perancangan antarmuka beserta spesifikasi objek pada setiap layar. BAB 7 berisi matriks kerunutan kelas perancangan terhadap use case.

<br>

---

# BAB 2: Perancangan Arsitektur

## 2.1 Rancangan Lingkungan Implementasi

Tabel 2.1. Rancangan Lingkungan Implementasi

| Komponen | Spesifikasi |
| :--- | :--- |
| *Operating System* | *Pengembangan: Windows/Linux/macOS. Pengguna: OS apa pun yang memiliki web browser modern (Windows, Linux, macOS, Android, iOS)* |
| *Server* | *Server lokal untuk pengembangan dan demonstrasi* |
| *DBMS* | *PostgreSQL 15* |
| *Bahasa Pemrograman* | *TypeScript (front-end), Python 3.11 (back-end), SQL* |
| *Framework* | *Next.js (React) dengan Node.js v20 untuk proses build; FastAPI untuk back-end* |
| *Development Tools* | *Visual Studio Code, Git dan GitHub, draw.io, PlantUML* |
| *Filing System* | *Data terstruktur disimpan di PostgreSQL. Foto listing (PNG/JPG, maks. 10 MB) disimpan sebagai berkas di direktori penyimpanan server, dan path berkasnya disimpan pada atribut `foto` di ListingMakanan* |

## 2.2 Style/Pattern Arsitektur Acuan

Style yang digunakan adalah client-server: client meminta layanan dan server memproses permintaan tersebut. Pattern yang digunakan adalah MVC, dengan View di sisi client (Next.js), serta Controller dan Model di sisi server (FastAPI). Model membaca dan menyimpan data ke database PostgreSQL.

<p align="center">
  <img width="50%" alt="Arsitektur MVC Food Waste Stop" src="https://github.com/user-attachments/assets/c05b7e88-bbfc-4aca-8004-37839e45328c" />
</p>
<p align="center">
<i>Gambar 1. Arsitektur MVC Food Waste Stop</i>
</p>

Alasan pemilihan style/pattern tersebut:
1. Alur Penjual dan Pembeli memiliki tampilan (View) yang terpisah, tetapi dapat memakai logika yang sama (Controller dan Model).
2. Pengguna mengakses sistem dari perangkat yang berbeda, tetapi harus melihat data yang sama, sehingga dibutuhkan server terpusat (client-server).
3. Logika yang membutuhkan keamanan dan konsistensi data, yaitu hashing password (KNF02) dan transaksi pembayaran yang atomik (KNF01), dijalankan di server sehingga tidak dapat dimanipulasi dari sisi client.

## 2.3 Identifikasi Komponen / Modul / Subsistem

Tabel 2.3. Identifikasi Komponen/Modul/Subsistem

| Nama Komponen/Modul/Subsistem | Jenis | Penjelasan |
| :--- | :--- | :--- |
| *LoginView* | *View* | *Menampilkan form login untuk Penjual dan Pembeli, mengirim email dan password ke AuthController melalui HTTPS, menampilkan pesan error, lalu mengarahkan pengguna ke halaman sesuai perannya.* |
| *KatalogView* | *View* | *Menampilkan daftar listing, detail satu listing, serta kolom pencarian dan penyaringan harga kepada Pembeli, dan meneruskan aksinya ke KatalogController.* |
| *ListingView* | *View* | *Menampilkan form tambah dan edit listing, dialog konfirmasi keluar, serta tombol dan dialog konfirmasi hapus listing kepada Penjual, dan meneruskan aksinya ke ListingController.* |
| *PembayaranView* | *View* | *Menampilkan form jumlah porsi, ringkasan pesanan, dan kode QRIS dummy kepada Pembeli, serta meneruskan aksi bayar atau batal ke PembayaranController.* |
| *RewardView* | *View* | *Menampilkan progres poin login, tombol klaim reward, dan kupon yang didapat kepada Pembeli, lalu meneruskan aksi klaim ke RewardController.* |
| *AuthController* | *Controller* | *Memproses login (UC07): meneruskan kredensial ke Validasi, memverifikasi password terhadap hash bcrypt milik Pengguna, lalu jika pengguna adalah Pembeli, memerintahkan RewardLogin mencatat login harian dan menambah poin.* |
| *KatalogController* | *Controller* | *Memproses permintaan melihat listing (UC02), melihat detail (UC03), serta mencari dan menyaring listing (UC04). Hanya listing aktif dengan stok > 0 yang belum melewati batas kedaluwarsa yang dikirim ke View.* |
| *ListingController* | *Controller* | *Memproses penambahan (UC01), pengeditan (UC06), dan penghapusan (UC09) listing. Input diteruskan ke Validasi, dan untuk edit/hapus diperiksa terlebih dahulu bahwa listing adalah milik penjual yang sedang login.* |
| *PembayaranController* | *Controller* | *Memproses checkout dan pembayaran (UC05): membuat Transaksi berstatus menunggu bayar beserta ItemTransaksi, meminta kode QRIS melalui MetodePembayaran, lalu setelah pembayaran dikonfirmasi mengunci dan mengurangi stok ListingMakanan serta menandai Transaksi lunas dalam satu transaksi database (KNF01). Transaksi yang dibatalkan atau melewati batas waktu bayar ditandai batal.* |
| *RewardController* | *Controller* | *Memproses permintaan melihat progres poin dan mengklaim reward (UC08): memeriksa kecukupan poin melalui RewardLogin, mengurangi poin, dan menerbitkan Kupon.* |
| *Pengguna, Penjual, Pembeli* | *Model* | *Merepresentasikan akun pengguna. Pengguna menyimpan data umum (nama, email, hash password), Penjual menambahkan data toko, dan Pembeli menjadi pemilik RewardLogin, Transaksi, dan Kupon.* |
| *ListingMakanan* | *Model* | *Merepresentasikan listing makanan surplus milik Penjual (nama, foto, porsi, kondisi, harga, stok, batas kedaluwarsa, status aktif) beserta aturan ketersediaannya dan operasi untuk mengambil data listing dari database.* |
| *Transaksi, ItemTransaksi* | *Model* | *Merepresentasikan pesanan Pembeli: status, total harga, batas waktu bayar, kode pengambilan, serta daftar listing dan jumlah porsi yang dibeli.* |
| *RewardLogin, Kupon* | *Model* | *Merepresentasikan poin login harian Pembeli beserta tanggal login terakhir, serta kupon potongan harga hasil klaim reward.* |
| *Validasi* | *Pendukung* | *Memvalidasi input listing (field wajib, stok dan harga tidak negatif, foto PNG/JPG maks. 10 MB, batas kedaluwarsa belum lewat) dan input login (format email, password tidak kosong).* |
| *MetodePembayaran, PaymentGatewayAdapter* | *Integrasi Eksternal* | *MetodePembayaran adalah interface pembayaran; PaymentGatewayAdapter merealisasikannya dengan mengirim tagihan ke QRIS dummy, menerima kode QRIS, dan meneruskan status pembayaran ke PembayaranController.* |
| *Database* | *Pendukung* | *Menyimpan seluruh data Model secara persisten pada PostgreSQL 15 dan menjalankan transaksi database yang memenuhi prinsip ACID.* |

## 2.4 Model Arsitektur Perangkat Lunak

### 2.4.1 View Logical View

Logical view dipilih karena memperlihatkan pembagian tanggung jawab antarkomponen MVC dan arah ketergantungannya, sehingga setiap kelas perancangan pada BAB 3 dapat ditelusuri ke komponennya. Setiap View hanya berkomunikasi dengan satu Controller pasangannya melalui HTTPS. Controller memakai Validasi untuk memeriksa input dan memakai Model untuk membaca serta mengubah data. Model menyimpan datanya ke Database. PembayaranController adalah satu-satunya Controller yang berkomunikasi dengan sistem eksternal, yaitu QRIS dummy melalui PaymentGatewayAdapter. AuthController juga memakai Model RewardLogin karena pemberian poin harian terjadi pada saat login.

<p align="center">
<img width="80%" alt="Logical View Food Waste Stop" src="https://github.com/user-attachments/assets/e115d579-4f88-49de-913b-5d40c2c35a95" />
</p>
<p align="center">
<i>Gambar 2. Logical View Food Waste Stop</i>
</p>

<br>

---


# BAB 3: Realisasi Use Case

## 3.1 Use Case 01

**ID Use Case:** *01*  
**Nama Use Case:** *Menambahkan listing makanan surplus*

### 3.1.1 Identifikasi Kelas

Tabel 3.1. Identifikasi Kelas Use Case [UC01]

| No | Nama Kelas Perancangan | Nama Kelas Analisis Terkait |
|:--- | :--- | :--- |
| 1 | *Penjual* | *idPenjual, toko* |
| 2 | *ListingMakanan* | *idListing, namaMakanan, harga, stok, deskripsi, foto* |

### 3.1.2 Sequence Diagram

- **Skenario Normal**

<p align="center">
<img width="55%" alt="Normal UC01" src="../M7/assets/diagram/normal-UC01.png">
</p>
<p align="center">
<i>Gambar 3.1.1 Sequence Diagram [UC01]</i>
</p>

- **Skenario Alternatif 1:  Verifikasi penambahan makanan gagal**

<p align="center">
<img width="55%" alt="skenario1-UC01" src="../M7/assets/diagram/skenario2-UC01.png">
</p>
<p align="center">
<i>Gambar 3.1.2 Sequence Diagram [UC01] - [Verifikasi penambahan makanan gagal]</i>
</p>

- **Skenario Alternatif 2:  Percobaan keluar saat penambahan makanan**

<p align="center">
<img width="55%" alt="skenario2-UC01" src="../M7/assets/diagram/skenario1-UC01.png">
</p>
<p align="center">
<i>Gambar 3.1.3 Sequence Diagram [UC01] - [Percobaan keluar saat penambahan makanan]</i>
</p>

### 3.1.3 Diagram Kelas

<p align="center">
<img alt="diagramKelasUC01.png" src="../M7/assets/diagram/diagramKelasUC01.png" width="35%">
</p>
<p align="center">
<i>Gambar 3.1.4 Diagram Kelas UC02</i>
</p>

## 3.2 Use Case 02

**ID Use Case:** *02*  
**Nama Use Case:** *Melihat listing makanan surplus*

### 3.2.1 Identifikasi Kelas

Tabel 3.1. Identifikasi Kelas Use Case [UC01]

| No | Nama Kelas Perancangan | Nama Kelas Analisis Terkait |
|:--- | :--- | :--- |
| 1 | *Pembeli* | *idPembeli, nama* |
| 2 | *ListingMakanan* | *idListing, namaMakanan, harga, stok, deskripsi, foto* |

### 3.2.2 Sequence Diagram

- **Skenario Normal**

<p align="center">
<img alt="Normal UC02" src="../M7/assets/diagram/normal-UC02.png" width="50%">
</p>
<p align="center">
<i>Gambar 3.2.1 Sequence Diagram [UC02]</i>
</p>

- **Skenario Alternatif 1:  Listing makanan surplus tidak tersedia**

<p align="center">
<img alt="skenario1-UC02" src="../M7/assets/diagram/skenario1-UC02.png" width="50%">
</p>
<p align="center">
<i>Gambar 3.2.2 Sequence Diagram [UC02] - [Verifikasi penambahan makanan gagal]</i>
</p>

### 3.2.3 Diagram Kelas

<p align="center">
<img alt="diagramKelasUC02.png" src="../M7/assets/diagram/diagramKelasUC02.png" width="35%">
</p>
<p align="center">
<i>Gambar 3.2.3 Diagram Kelas UC02</i>
</p>

## 3.3 Use Case 03

**ID Use Case:** *03*  
**Nama Use Case:** *Melihat detail makanan surplus*

### 3.3.1 Identifikasi Kelas

Tabel 3.3. Identifikasi Kelas Use Case [UC03]

| No | Nama Kelas Perancangan | Nama Kelas Analisis Terkait |
|:--- | :--- | :--- |
| 1 | *KatalogView* | *Pembeli* |
| 2 | *KatalogController* | *ListingMakanan* |
| 3 | *ListingMakanan* | *ListingMakanan* |

### 3.3.2 Sequence Diagram

- **Skenario Normal**

<p align="center">
<img width="90%" alt="Sequence Diagram UC03 Skenario Normal" src="../M7/assets/diagram/sequence/sd-uc03-normal.png">
</p>
<p align="center">
<i>Gambar 3.3.1 Sequence Diagram [UC03]</i>
</p>

- **Skenario Alternatif 1: Listing yang dipilih tiba-tiba dihapus**

<p align="center">
<img width="90%" alt="Sequence Diagram UC03 Skenario Alternatif 1" src="../M7/assets/diagram/sequence/sd-uc03-alt1.png">
</p>
<p align="center">
<i>Gambar 3.3.2 Sequence Diagram [UC03] - [Listing yang dipilih tiba-tiba dihapus]</i>
</p>

### 3.3.3 Diagram Kelas

<p align="center">
<img width="100%" alt="Diagram Kelas UC03" src="../M7/assets/diagram/class/cd-uc03.png">
</p>
<p align="center">
<i>Gambar 3.3.3 Diagram Kelas Melihat Detail Makanan Surplus</i>
</p>

## 3.4 Use Case 04

**ID Use Case:** *04*  
**Nama Use Case:** *Menyaring listing makanan surplus*

### 3.4.1 Identifikasi Kelas

Tabel 3.4. Identifikasi Kelas Use Case [UC04]

| No | Nama Kelas Perancangan | Nama Kelas Analisis Terkait |
|:--- | :--- | :--- |
| 1 | *KatalogView* | *Pembeli* |
| 2 | *KatalogController* | *ListingMakanan* |
| 3 | *ListingMakanan* | *ListingMakanan* |

### 3.4.2 Sequence Diagram

- **Skenario Normal**

<p align="center">
<img width="75%" alt="Sequence Diagram UC04 Skenario Normal" src="../M7/assets/diagram/sequence/sd-uc04-normal.png">
</p>
<p align="center">
<i>Gambar 3.4.1 Sequence Diagram [UC04]</i>
</p>

- **Skenario Alternatif 1: Kata kunci yang dicari tidak ada**

<p align="center">
<img width="90%" alt="Sequence Diagram UC04 Skenario Alternatif 1" src="../M7/assets/diagram/sequence/sd-uc04-alt1.png">
</p>
<p align="center">
<i>Gambar 3.4.2 Sequence Diagram [UC04] - [Kata kunci yang dicari tidak ada]</i>
</p>

- **Skenario Alternatif 2: Rentang harga yang dicari tidak ada**

<p align="center">
<img width="90%" alt="Sequence Diagram UC04 Skenario Alternatif 2" src="../M7/assets/diagram/sequence/sd-uc04-alt2.png">
</p>
<p align="center">
<i>Gambar 3.4.3 Sequence Diagram [UC04] - [Rentang harga yang dicari tidak ada]</i>
</p>

### 3.4.3 Diagram Kelas

<p align="center">
<img width="100%" alt="Diagram Kelas UC04" src="../M7/assets/diagram/class/cd-uc04.png">
</p>
<p align="center">
<i>Gambar 3.4.4 Diagram Kelas Menyaring Listing Makanan Surplus</i>
</p>

## 3.5 Use Case 05

**ID Use Case:** *05*  
**Nama Use Case:** *Melakukan Pembayaran*

### 3.5.1 Identifikasi Kelas

Tabel 3.5. Identifikasi Kelas Use Case [UC05]

| No | Nama Kelas Perancangan | Nama Kelas Analisis Terkait |
|:--- | :--- | :--- |
| 1 | *Pembeli* | *Pembeli* |
| 2 | *ListingMakanan* | *ListingMakanan* |
| 3 | *MetodePembayaran* | *MetodePembayaran* |
| 4 | *Transaksi* | *Transaksi* |
| 5 | *ItemTransaksi* | *(kelas baru pada perancangan; rincian listing, jumlah, dan harga satuan dalam Transaksi C06)* |
| 6 | *PembayaranView* | *Pembeli* |
| 7 | *PembayaranController* | *Pembeli* |
| 8 | *PaymentGatewayAdapter* | *MetodePembayaran* |


### 3.5.2 Sequence Diagram

- **Skenario Normal**

<p align="center">
<img alt="Sequence diagram skenario normal UC05" src="../M7/assets/diagram/sequence/sd-uc05-normal.png" width="50%">
</p>
<p align="center">
<i>Gambar 3.5.1 Sequence Diagram [UC05]</i>
</p>

- **Skenario Alternatif [1]: [Pembeli membatalkan pembayaran]**

<p align="center">
<img alt="Sequence diagram skenario alternatif UC05" src="../M7/assets/diagram/sequence/sd-uc05-alternative.png" width="50%">
</p>
<p align="center">
<i>Gambar 3.5.2 Sequence Diagram [UC05] - [Pembeli membatalkan pembayaran]</i>
</p>

### 3.5.3 Diagram Kelas

<p align="center">
<img width="100%" alt="Class07-UC07 - Class drawio" src="../M7/assets/diagram/class/cd-uc05.drawio.png" />
</p>
<p align="center">
<i>Gambar 3.5.2 Diagram Kelas Melakukan Pembayaran</i>
</p>

## 3.6 Use Case 06

**ID Use Case:** *06*  
**Nama Use Case:** *Mengedit Listing*

### 3.6.1 Identifikasi Kelas

Tabel 3.6. Identifikasi Kelas Use Case [UC06]

| No | Nama Kelas Perancangan | Nama Kelas Analisis Terkait |
|:--- | :--- | :--- |
| 1 | *ListingView* | *Penjual* |
| 2 | *ListingController* | *Penjual* |
| 4 | *Penjual* | *Penjual* |
| 5 | *ListingMakanan* | *ListingMakanan* |
| 6 | *Validasi* | *ListingMakanan* |

### 3.6.2 Sequence Diagram

- **Skenario Normal**

<p align="center">
<img alt="Contoh Logical View pada P/L E-Commerce" src="../M7/assets/diagram/sequence/sd-uc06.png" width="50%">
</p>
<p align="center">
<i>Gambar X. Sequence Diagram [UC06]</i>
</p>


### 3.6.3 Diagram Kelas

<p align="center">
<img width="100%" alt="Class06-UC06 - Class drawio" src="../M7/assets/diagram/class/cd-uc06.png" />
</p>
<p align="center">
<i>Gambar 3.6.3 Diagram Kelas Mengedit Listing</i>
</p>

## 3.7 Use Case 07

**ID Use Case:** *07*  
**Nama Use Case:** *Login ke sistem*

### 3.7.1 Identifikasi Kelas

Tabel 3.7. Identifikasi Kelas Use Case [UC07]

| No | Nama Kelas Perancangan | Nama Kelas Analisis Terkait |
|:--- | :--- | :--- |
| 1 | *LoginView* | *tampilkanForm, kirimKredensial, tampilkanPesan, arahkanKeBeranda* |
| 2 | *AuthController* | *login* |
| 3 | *Validasi* | *validasiKredensial* |
| 4 | *Pengguna* | *verifikasiPassword, getPeran* |
| 5 | *Pembeli* | *getPeran* |
| 6 | *Penjual* | *getPeran* |

### 3.7.2 Sequence Diagram

- **Skenario Normal**

<p align="center">
<img width="65%" alt="NORMAL7 drawio" src="https://github.com/user-attachments/assets/51ceae74-b3d8-4c20-adc5-6e0c0bd2837b" />
</p>
<p align="center">
<i>Gambar 3.7.1 Sequence Diagram [UC07]</i>
</p>

- **Skenario Alternatif 1 : Input salah**

<p align="center">
<img width="801" height="890" alt="SISTEM7 drawio" src="https://github.com/user-attachments/assets/12a8f851-2ba7-40e5-b321-809db697fd70" />
</p>
<p align="center">
<i>Gambar 3.5.2 Sequence Diagram [UC07] - Input salah</i>
</p>

- **Skenario Alternatif 2: Sistem gagal**

<p align="center">
<img width="795" height="581" alt="07TADIINPUT drawio" src="https://github.com/user-attachments/assets/b0acdc68-8402-4e35-8de3-c625d3c3c7b5" />
</p>
<p align="center">
<i>Gambar 3.5.2 Sequence Diagram [UC07] - Sistem gagal</i>
</p>


### 3.7.3 Diagram Kelas

<p align="center">
<img width="750" height="487" alt="UC7FIX drawio" src="https://github.com/user-attachments/assets/5f43186f-e33f-4488-985c-8d3dc966cdcb" />
</p>
<p align="center">
<i>Gambar 3.7.2 Diagram Kelas Login Ke Sistem</i>
</p>

## 3.8 Use Case 08

**ID Use Case:** *08*  
**Nama Use Case:** *Mengklaim reward login*

### 3.8.1 Identifikasi Kelas

Tabel 3.8. Identifikasi Kelas Use Case [UC08]

| No | Nama Kelas Perancangan | Nama Kelas Analisis Terkait |
|:--- | :--- | :--- |
| 1 | *RewardView* | *kirimKlaim, tampilkanKupon, tampilkanPesan, tampilkanProgres* |
| 2 | *RewardController* | *klaimReward, lihatProgres, catatLogin* |
| 3 | *RewardLogin* | *cukupUntukKlaim, kurangiPoin* |
| 4 | *Kupon* | *Model data pembuatan objek kupon (isBerlaku)* |
| 5 | *Pembeli* | *getPeran* |

### 3.8.2 Sequence Diagram

- **Skenario Normal**

<p align="center">
<img width="65%" alt="NORMAL8 drawio (1)" src="https://github.com/user-attachments/assets/39501d5b-8e30-44cd-987d-2c1057d69feb" />
</p>
<p align="center">
<i>Gambar 3.8.1 Sequence Diagram [UC08]</i>
</p>

- **Skenario Alternatif 1: Poin tidak mencukupi**

<p align="center">
<img width="631" height="564" alt="POINKURANG8 drawio" src="https://github.com/user-attachments/assets/20d17265-96d2-4607-953e-62a1d75fd77d" />
</p>
<p align="center">
<i>Gambar 3.5.2 Sequence Diagram [UC08] - Poin tidak mencukupi</i>
</p>

- **Skenario Alternatif 2: Sistem gagal**

<p align="center">
<img width="795" height="690" alt="SISTEMGAGAL-8 drawio" src="https://github.com/user-attachments/assets/164b7fc3-3abe-4576-bd98-a91a2f520fbc" />
</p>
<p align="center">
<i>Gambar 3.5.2 Sequence Diagram [UC08] - Sistem gagal</i>
</p>

### 3.8.3 Diagram Kelas

<p align="center">
<img width="734" height="440" alt="UC8FIX drawio" src="https://github.com/user-attachments/assets/8a5d4db4-64d8-4777-9f58-3b7fe3cf4b67" />
</p>
<p align="center">
<i>Gambar 3.8.2 Diagram Kelas Mengklaim Reward Login</i>
</p>

## 3.9 Use Case 09

**ID Use Case:** *09*  
**Nama Use Case:** *Menghapus makana dari listing*

### 3.9.1 Identifikasi Kelas

Tabel 3.9. Identifikasi Kelas Use Case [UC09]

| No | Nama Kelas Perancangan | Nama Kelas Analisis Terkait |
|:--- | :--- | :--- |
| 1 | *Pengguna* | *verifikasiPassword()<br>getPeran() <br>bukaListing()* |
| 2 | *Penjual* | *memilikiListing()<br>hapusListing()* |
| 3 | *ListingMakanan* | *cariById()<br>ambilSemuaTersedia()<br>cariDaftar()<br>isTersedia()<br>ubahData()<br>kurangiStok()<br>nonaktifkan()* |
| 4 | *ListingView* | *tampilkanMenuListing()<br>tampilkanKonfirmasiHapus()<br>hapusMakanan()* |
| 4 | *ListingController* | *tambahListing()<br>ubahListing()<br>hapusListing()<br>isPenjual()* |

### 3.9.2 Sequence Diagram

- **Skenario Normal**

<p align="center">
<img width="55%" alt="happy" src="https://github.com/user-attachments/assets/0d0a9c32-325b-4c81-9305-7430262cf344" />

</p>
<p align="center">
<i>Gambar 3.9.1 Sequence Diagram UC09</i>
</p>

- **Skenario Alternatif 01: Toko belum punya listing**

<p align="center">
<img width="75%" alt="alt" src="https://github.com/user-attachments/assets/5c07730e-b936-4d41-87c9-cbf2e6f0ca33" />
</p>
<p align="center">
<i>Gambar 3.9.2 Sequence Diagram UC09 - Toko belum punya listing</i>
</p>

### 3.9.3 Diagram Kelas

<p align="center">
<img width="75%" alt="cd drawio" src="https://github.com/user-attachments/assets/1593d186-76ec-4c4a-9574-b8bd5581be7e" />

</p>
<p align="center">
<i>Gambar 3.9.2 Diagram Kelas UC09</i>
</p>

---

# BAB 4: Diagram Kelas Keseluruhan

## 4.1 Diagram Kelas

<p align="center">
<img width="1559" height="1009" alt="cdl drawio" src="https://github.com/user-attachments/assets/fdf8aec9-3d79-4873-9fff-5bac79ec2343" />
</p>
<p align="center">
<i>Gambar 4.1. Diagram Kelas Perancangan Keseluruhan Food Waste Stop</i>
</p>

Relasi antarkelas entity:
- Pengguna (abstrak) ◁— Penjual, Pembeli (generalisasi).
- Penjual 1 — 0..\* ListingMakanan.
- Pembeli 1 — 1 RewardLogin.
- Pembeli 1 — 0..\* Transaksi.
- Pembeli 1 — 0..\* Kupon.
- Transaksi 1 ◆— 1..\* ItemTransaksi (komposisi).
- ItemTransaksi 0..\* — 1 ListingMakanan.
- PaymentGatewayAdapter - - ▷ MetodePembayaran (realisasi).

Relasi kelas View dan Controller berupa dependensi: setiap View bergantung pada Controller pasangannya, dan setiap Controller bergantung pada kelas Model serta Validasi atau MetodePembayaran yang dipakainya, sesuai Gambar 2.

`DataListing` pada parameter metode adalah struktur data input form listing (nama, deskripsi, porsi, kondisi, harga, stok, batasKedaluwarsa, foto), bukan kelas domain. `StatusTransaksi` adalah enumerasi bernilai `MENUNGGU_BAYAR`, `LUNAS`, dan `BATAL`. Operasi bertanda `{static}` digambar bergaris bawah pada diagram kelas.

Tabel 4.1. Daftar Kelas Perancangan Keseluruhan

| ID Kelas | Nama Kelas | Atribut | Metode/Operasi |
| :--- | :--- | :--- | :--- |
| *C01* | *Pengguna* «abstract» | *- idPengguna: Integer<br>- nama: String<br>- email: String<br>- password: String* | *+ verifikasiPassword(password: String): Boolean<br>+ getPeran(): String<br>+ bukaListing(): listingMakanan* |
| *C02* | *Penjual* | *- namaToko: String<br>- alamatToko: String* | *+ getPeran(): String<br>+ memilikiListing(listing: ListingMakanan): Boolean* |
| *C03* | *Pembeli* | *namaAkun: String* | *getPeran(): String* |
| *C04* | *ListingMakanan* | *- idListing: Integer<br>- idPenjual: Integer<br>- namaMakanan: String<br>- deskripsi: String<br>- porsi: String<br>- kondisi: String<br>- foto: String<br>- harga: Integer<br>- stok: Integer<br>- batasKedaluwarsa: DateTime<br>- aktif: Boolean* | *+ cariById(idListing: Integer): ListingMakanan {static}<br>+ ambilSemuaTersedia(): List&lt;ListingMakanan&gt; {static}<br>+ cariDaftar(kataKunci: String, hargaMin: Integer, hargaMaks: Integer): List&lt;ListingMakanan&gt; {static}<br>+ isTersedia(waktu: DateTime): Boolean<br>+ ubahData(data: DataListing): void<br>+ kurangiStok(jumlah: Integer): void<br>+ nonaktifkan(): void* |
| *C05* | *MetodePembayaran* «interface» | *–* | *+ buatTagihan(transaksi: Transaksi): String<br>+ cekStatus(idTransaksi: Integer): String* |
| *C06* | *Transaksi* | *- idTransaksi: Integer<br>- idPembeli: Integer<br>- tanggal: DateTime<br>- batasWaktuBayar: DateTime<br>- totalHarga: Integer<br>- status: StatusTransaksi<br>- kodePengambilan: String* | *+ hitungTotal(): Integer<br>+ tandaiLunas(): void<br>+ batalkan(): void<br>+ isLewatBatasWaktu(waktu: DateTime): Boolean* |
| *C07* | *RewardLogin* | *- idReward: Integer<br>- idPembeli: Integer<br>- poinTerkumpul: Integer<br>- tanggalLoginTerakhir: Date<br>- POIN_PER_LOGIN: Integer<br>- POIN_PER_KLAIM: Integer* | *+ catatLogin(tanggal: Date): Boolean<br>+ cukupUntukKlaim(): Boolean<br>+ kurangiPoin(jumlah: Integer): void* |
| *C08* | *ItemTransaksi* | *- idItem: Integer<br>- idListing: Integer<br>- jumlah: Integer<br>- hargaSatuan: Integer* | *+ hitungSubtotal(): Integer* |
| *C09* | *Kupon* | *- kodeKupon: String<br>- idPembeli: Integer<br>- nilaiPotongan: Integer<br>- berlakuSampai: Date<br>- terpakai: Boolean* | *+ isBerlaku(tanggal: Date): Boolean* |
| *C10* | *LoginView* | *–* | *+ tampilkanForm(): void<br>+ kirimKredensial(email: String, password: String): void<br>+ tampilkanPesan(pesan: String): void<br>+ arahkanKeBeranda(peran: String): void* |
| *C11* | *KatalogView* | *–* | *+ pilihListing(idListing: Integer): void<br>+ tampilkanDaftar(daftar: List&lt;ListingMakanan&gt;): void<br>+ tampilkanDetail(listing: ListingMakanan): void<br>+ tampilkanPilihanHarga(): void<br>+ kirimPencarian(kataKunci: String, hargaMin: Integer, hargaMaks: Integer): void<br>+ tampilkanPesan(pesan: String): void* |
| *C12* | *ListingView* | *–* | *+ tampilkanFormTambah(): void<br>+ tampilkanFormEdit(listing: ListingMakanan): void<br>+ kirimListing(data: DataListing): void<br>+ tampilkanKonfirmasiKeluar(): Boolean<br>+ tampilkanKonfirmasiHapus(listing: ListingMakanan): Boolean<br>+ tampilkanPesan(pesan: String): void* |
| *C13* | *PembayaranView* | *–* | *+ tampilkanRingkasan(transaksi: Transaksi): void<br>+ tampilkanQRIS(kodeQRIS: String): void<br>+ kirimBayar(idTransaksi: Integer): void<br>+ kirimBatal(idTransaksi: Integer): void<br>+ tampilkanHasil(transaksi: Transaksi): void<br>+ tampilkanPesan(pesan: String): void* |
| *C14* | *RewardView* | *–* | *+ tampilkanProgres(poin: Integer, bisaKlaim: Boolean): void<br>+ kirimKlaim(): void<br>+ tampilkanKupon(kupon: Kupon): void<br>+ tampilkanPesan(pesan: String): void* |
| *C15* | *AuthController* | *–* | *+ login(email: String, password: String): Pengguna* |
| *C16* | *KatalogController* | *–* | *+ ambilListingTersedia(): List&lt;ListingMakanan&gt;<br>+ ambilDetail(idListing: Integer): ListingMakanan<br>+ cariListing(kataKunci: String, hargaMin: Integer, hargaMaks: Integer): List&lt;ListingMakanan&gt;* |
| *C17* | *ListingController* | *–* | *+ tambahListing(idPenjual: Integer, data: DataListing): ListingMakanan<br>+ ubahListing(idPenjual: Integer, idListing: Integer, data: DataListing): ListingMakanan<br>+ hapusListing(idPenjual: Integer, idListing: Integer): void* |
| *C18* | *PembayaranController* | *- metodePembayaran: MetodePembayaran* | *+ checkout(idPembeli: Integer, idListing: Integer, jumlah: Integer): Transaksi<br>+ konfirmasiBayar(idTransaksi: Integer): Transaksi<br>+ batalkan(idTransaksi: Integer): void<br>+ batalkanLewatBatasWaktu(): void* |
| *C19* | *RewardController* | *–* | *+ lihatProgres(idPembeli: Integer): RewardLogin<br>+ klaimReward(idPembeli: Integer): Kupon* |
| *C20* | *Validasi* | *–* | *+ validasiListing(data: DataListing): List&lt;String&gt;<br>+ validasiKredensial(email: String, password: String): List&lt;String&gt;* |
| *C21* | *PaymentGatewayAdapter* | *- urlGateway: String* | *+ buatTagihan(transaksi: Transaksi): String<br>+ cekStatus(idTransaksi: Integer): String* |

<br>

---

# BAB 5: Perancangan Rinci Kelas

Bagian ini diisi dengan daftar seluruh kelas dalam tabel berikut:

Tabel 5.1. Daftar Kelas Perancangan dan Kelas Analisis Terkait

| No | Nama Kelas Perancangan | Nama Kelas Analisis Terkait |
|:--- | :--- | :--- |
| 1 | *Pengguna* | *verifikasiPassword()<br>getPeran()<br>bukaListing()* |
| 2 | *Penjual* | *Penjual<br>idPenjual, toko<br>getPeran()<br>memilikiListing()<br>hapusListing()* |
| 3 | *Pembeli* | *Pembeli<br>idPembeli, nama<br>getPeran()* |
| 4 | *ListingMakanan* | *ListingMakanan<br>idListing, namaMakanan, harga, stok, deskripsi, foto<br>cariById()<br>ambilSemuaTersedia()<br>cariDaftar()<br>isTersedia()<br>ubahData()<br>kurangiStok()<br>nonaktifkan()* |
| 5 | *KatalogView* | *Pembeli* |
| 6 | *KatalogController* | *ListingMakanan* |
| 7 | *ListingView* | *Penjual<br>tampilkanMenuListing()<br>tampilkanKonfirmasiHapus()<br>hapusMakanan()* |
| 8 | *ListingController* | *Penjual<br>tambahListing()<br>ubahListing()<br>hapusListing()<br>isPenjual()* |
| 9 | *Validasi* | *ListingMakanan<br>validasiKredensial()* |
| 10 | *MetodePembayaran* | *MetodePembayaran* |
| 11 | *Transaksi* | *Transaksi* |
| 12 | *ItemTransaksi* | *(kelas baru pada perancangan; rincian listing, jumlah, dan harga satuan dalam Transaksi C06)* |
| 13 | *PembayaranView* | *Pembeli* |
| 14 | *PembayaranController* | *Pembeli* |
| 15 | *PaymentGatewayAdapter* | *MetodePembayaran* |
| 16 | *LoginView* | *tampilkanForm()<br>kirimKredensial()<br>tampilkanPesan()<br>arahkanKeBeranda()* |
| 17 | *AuthController* | *login()* |
| 18 | *RewardView* | *kirimKlaim()<br>tampilkanKupon()<br>tampilkanPesan()<br>tampilkanProgres()* |
| 19 | *RewardController* | *klaimReward()<br>lihatProgres()<br>catatLogin()* |
| 20 | *RewardLogin* | *cukupUntukKlaim()<br>kurangiPoin()* |
| 21 | *Kupon* | *Model data pembuatan objek kupon (isBerlaku)* |

Untuk **setiap kelas**, identifikasi operasi berdasarkan tanggung jawab kelas beserta *visibility*-nya, serta atribut beserta *visibility* dan tipenya. Buat subbab tersendiri untuk setiap kelas.

## 5.1 Kelas [Nama Kelas 1]

**Nama Kelas:** *[Nama kelas]*  
**ID Kelas:** *[ID kelas]*

Tabel 5.1.1. Operasi Kelas [Nama Kelas 1]

| Nama Operasi | Visibility (private, public) | Keterangan |
| :--- | :--- | :--- |
| *[Signature operasi, termasuk parameter dan tipe kembalian]* | *[Visibility]* | *[Tanggung jawab operasi]* |
| *...* | *...* | *...* |

Tabel 5.1.2. Atribut Kelas [Nama Kelas 1]

| Nama Atribut | Visibility (private, public) | Tipe |
| :--- | :--- | :--- |
| *[Nama atribut]* | *[Visibility]* | *[Tipe sesuai bahasa pemrograman yang digunakan]* |
| *...* | *...* | *...* |

### 5.1.1 Algoritma/Query

Bagian ini diisi untuk kerangka algoritma proses yang dianggap cukup penting. Algoritma dapat dituliskan sebagai *pseudocode*. Implementasi *skeleton code* juga dapat digunakan untuk kelas yang sudah terdefinisi pada bahasa pemrograman tertentu.

**Nama Kelas:** *[Nama kelas]*  
**Nama Operasi:** *[Signature operasi]*  
**ID Algoritma:** *[Algo-001]*

```text
[Tuliskan pseudocode algoritma operasi di sini.]
```

Jika operasi mengacu pada query tertentu, lengkapi tabel berikut. 

Tabel 5.1.1. Query Operasi [Nama Operasi]

| No Query | Query | Keterangan |
| :--- | :--- | :--- |
| *[Q-001]* | *[Tuliskan query]* | *[Fungsi query]* |
| *...* | *...* | *...* |


### 5.1.2 Algoritma/Query

*[Ulangi pola 5.1.1 untuk operasi penting berikutnya pada kelas yang sama, jika ada.]*

## 5.13 Kelas PembayaranView

**Nama Kelas:** *PembayaranView*  
**ID Kelas:** *C13*

Tabel 5.13.1. Operasi Kelas PembayaranView

| Nama Operasi | Visibility (private, public) | Keterangan |
| :--- | :--- | :--- |
| *tampilkanRingkasan(transaksi: Transaksi): void* | *public* | *Menampilkan ringkasan pesanan kepada Pembeli, yaitu nama listing, jumlah porsi, harga satuan, dan total harga dari Transaksi yang dibuat saat checkout.* |
| *tampilkanQRIS(kodeQRIS: String): void* | *public* | *Menampilkan gambar QRIS dummy dari lokasi file yang diterima PembayaranController, beserta tombol untuk melanjutkan simulasi pembayaran.* |
| *kirimBayar(idTransaksi: Integer): void* | *public* | *Meneruskan aksi Pembeli mengetuk tombol bayar ke PembayaranController untuk mengonfirmasi pembayaran transaksi.* |
| *kirimBatal(idTransaksi: Integer): void* | *public* | *Meneruskan aksi Pembeli menutup atau keluar dari halaman pembayaran ke PembayaranController agar transaksi dibatalkan, lalu mengembalikan Pembeli ke halaman sebelumnya.* |
| *tampilkanHasil(transaksi: Transaksi): void* | *public* | *Menampilkan halaman konfirmasi bahwa pembayaran berhasil beserta kode pengambilan pesanan.* |
| *tampilkanPesan(pesan: String): void* | *public* | *Menampilkan pesan informasi atau kesalahan, misalnya stok tidak mencukupi atau batas waktu pembayaran telah lewat.* |

Tabel 5.13.2. Atribut Kelas PembayaranView

| Nama Atribut | Visibility (private, public) | Tipe |
| :--- | :--- | :--- |
| *–* | *–* | *–* |

### 5.13.1 Algoritma/Query

**Nama Kelas:** *PembayaranView*  
**Nama Operasi:** *kirimBayar(idTransaksi: Integer): void*  
**ID Algoritma:** *Algo-C13-01*

```text
Function kirimBayar(idTransaksi)
    nonaktifkan tombol bayar agar tidak terkirim dua kali
    hasil ← PembayaranController.konfirmasiBayar(idTransaksi)
    if hasil adalah error then
        tampilkanPesan(hasil.pesan)
        aktifkan kembali tombol bayar
    else if hasil.status = LUNAS then
        tampilkanHasil(hasil)
    else
        tampilkanPesan("Transaksi dibatalkan karena batas waktu pembayaran telah lewat")
```

### 5.13.2 Algoritma/Query

**Nama Kelas:** *PembayaranView*  
**Nama Operasi:** *kirimBatal(idTransaksi: Integer): void*  
**ID Algoritma:** *Algo-C13-02*

```text
Function kirimBatal(idTransaksi)
    hasil ← PembayaranController.batalkan(idTransaksi)
    if hasil adalah error then
        tampilkanPesan(hasil.pesan)
    kembali ke halaman sebelumnya
```

## 5.14 Kelas PembayaranController

**Nama Kelas:** *PembayaranController*  
**ID Kelas:** *C18*

Tabel 5.14.1. Operasi Kelas PembayaranController

| Nama Operasi | Visibility (private, public) | Keterangan |
| :--- | :--- | :--- |
| *checkout(idPembeli: Integer, idListing: Integer, jumlah: Integer): Transaksi* | *public* | *Memeriksa ketersediaan dan stok listing, membuat Transaksi berstatus MENUNGGU_BAYAR beserta ItemTransaksi, menghitung total harga, lalu meminta kode QRIS dummy melalui MetodePembayaran.* |
| *konfirmasiBayar(idTransaksi: Integer): Transaksi* | *public* | *Memeriksa status pembayaran melalui MetodePembayaran, lalu dalam satu transaksi database mengunci dan mengurangi stok ListingMakanan serta menandai Transaksi lunas (KNF01).* |
| *batalkan(idTransaksi: Integer): void* | *public* | *Menandai Transaksi yang masih berstatus MENUNGGU_BAYAR menjadi BATAL ketika Pembeli menutup atau keluar dari halaman pembayaran.* |
| *batalkanLewatBatasWaktu(): void* | *public* | *Menandai seluruh Transaksi berstatus MENUNGGU_BAYAR yang telah melewati batas waktu bayar menjadi BATAL. Operasi ini dijalankan secara berkala oleh server.* |

Tabel 5.14.2. Atribut Kelas PembayaranController

| Nama Atribut | Visibility (private, public) | Tipe |
| :--- | :--- | :--- |
| *metodePembayaran* | *private* | *MetodePembayaran* |

### 5.14.1 Algoritma/Query

**Nama Kelas:** *PembayaranController*  
**Nama Operasi:** *checkout(idPembeli: Integer, idListing: Integer, jumlah: Integer): Transaksi*  
**ID Algoritma:** *Algo-C18-01*

```text
Function checkout(idPembeli, idListing, jumlah)
    if jumlah ≤ 0 then
        → error "Jumlah porsi tidak valid"
    listing ← ListingMakanan.cariById(idListing)
    if listing = NULL or not listing.isTersedia(waktuSekarang) then
        → error "Listing tidak tersedia"
    if listing.stok < jumlah then
        → error "Stok tidak mencukupi"

    BEGIN TRANSACTION
    transaksi ← new Transaksi(idPembeli, waktuSekarang, waktuSekarang + BATAS_WAKTU_BAYAR, MENUNGGU_BAYAR)
    simpan transaksi                                         // Q-C18-01
    item ← new ItemTransaksi(idListing, jumlah, listing.harga)
    simpan item                                              // Q-C18-02
    transaksi.daftarItem.add(item)
    transaksi.totalHarga ← transaksi.hitungTotal()
    perbarui totalHarga transaksi                            // Q-C18-03
    COMMIT

    kodeQRIS ← metodePembayaran.buatTagihan(transaksi)
    → transaksi (beserta kodeQRIS untuk ditampilkan oleh PembayaranView)
```

Tabel 5.14.3. Query Operasi checkout

| No Query | Query | Keterangan |
| :--- | :--- | :--- |
| *Q-C18-01* | *simpanTransaksi:*<br>`INSERT INTO transaksi (id_pembeli, tanggal, batas_waktu_bayar, total_harga, status) VALUES (@idPembeli, NOW(), NOW() + @batasWaktu, 0, 'MENUNGGU_BAYAR') RETURNING id_transaksi;` | *Menyimpan transaksi baru dan mengambil ID-nya* |
| *Q-C18-02* | *simpanItemTransaksi:*<br>`INSERT INTO item_transaksi (id_listing, jumlah, harga_satuan) VALUES (@idListing, @jumlah, @hargaSatuan) RETURNING id_item;` | *Menyimpan rincian listing dan jumlah porsi yang dibeli* |
| *Q-C18-03* | *perbaruiTotalHarga:*<br>`UPDATE transaksi SET total_harga = @totalHarga WHERE id_transaksi = @idTransaksi;` | *Menyimpan total harga hasil perhitungan* |

### 5.14.2 Algoritma/Query

**Nama Kelas:** *PembayaranController*  
**Nama Operasi:** *konfirmasiBayar(idTransaksi: Integer): Transaksi*  
**ID Algoritma:** *Algo-C18-02*

```text
Function konfirmasiBayar(idTransaksi)
    BEGIN TRANSACTION
    transaksi ← ambil transaksi dan kunci barisnya           // Q-C18-04
    if transaksi = NULL or transaksi.status ≠ MENUNGGU_BAYAR then
        ROLLBACK
        → error "Transaksi tidak dapat dibayar"
    if transaksi.isLewatBatasWaktu(waktuSekarang) then
        transaksi.batalkan()
        perbarui status transaksi                            // Q-C18-06
        COMMIT
        → transaksi
    if metodePembayaran.cekStatus(idTransaksi) ≠ "LUNAS" then
        ROLLBACK
        → error "Pembayaran belum diterima"

    FOR each item IN transaksi.daftarItem
        listing ← ambil listing dan kunci barisnya           // Q-C18-05
        if not listing.isTersedia(waktuSekarang) or listing.stok < item.jumlah then
            ROLLBACK
            → error "Stok tidak mencukupi"
        listing.kurangiStok(item.jumlah)
        perbarui stok listing                                // Q-C18-07

    transaksi.tandaiLunas()          // status ← LUNAS, kodePengambilan dibuat
    perbarui status dan kode pengambilan transaksi           // Q-C18-06
    COMMIT
    → transaksi
```

Seluruh langkah dijalankan dalam satu transaksi database. Jika salah satu langkah gagal, semua perubahan dibatalkan sehingga stok dan status transaksi tetap konsisten (KNF01). Penguncian baris dengan `FOR UPDATE` mencegah dua pembayaran mengurangi stok yang sama secara bersamaan (*lost update*).

Tabel 5.14.4. Query Operasi konfirmasiBayar

| No Query | Query | Keterangan |
| :--- | :--- | :--- |
| *Q-C18-04* | *ambilTransaksiTerkunci:*<br>`SELECT * FROM transaksi WHERE id_transaksi = @idTransaksi FOR UPDATE;` | *Mengambil dan mengunci transaksi yang akan dibayar* |
| *Q-C18-05* | *ambilListingTerkunci:*<br>`SELECT * FROM listing_makanan WHERE id_listing = @idListing FOR UPDATE;` | *Mengambil dan mengunci listing agar stok tidak diubah transaksi lain* |
| *Q-C18-06* | *perbaruiStatusTransaksi:*<br>`UPDATE transaksi SET status = @status, kode_pengambilan = @kodePengambilan WHERE id_transaksi = @idTransaksi;` | *Menyimpan status akhir transaksi (LUNAS atau BATAL) dan kode pengambilan* |
| *Q-C18-07* | *kurangiStokListing:*<br>`UPDATE listing_makanan SET stok = stok - @jumlah WHERE id_listing = @idListing;` | *Mengurangi stok listing sesuai jumlah porsi yang dibeli* |

### 5.14.3 Algoritma/Query

**Nama Kelas:** *PembayaranController*  
**Nama Operasi:** *batalkanLewatBatasWaktu(): void*  
**ID Algoritma:** *Algo-C18-03*

```text
Function batalkanLewatBatasWaktu()
    ubah status seluruh transaksi MENUNGGU_BAYAR yang batas waktu bayarnya
    sudah lewat menjadi BATAL                                // Q-C18-08
```

Tabel 5.14.5. Query Operasi batalkanLewatBatasWaktu

| No Query | Query | Keterangan |
| :--- | :--- | :--- |
| *Q-C18-08* | *batalkanTransaksiKedaluwarsa:*<br>`UPDATE transaksi SET status = 'BATAL' WHERE status = 'MENUNGGU_BAYAR' AND batas_waktu_bayar < NOW();` | *Membatalkan transaksi yang melewati batas waktu bayar. Stok tidak perlu dikembalikan karena stok baru dikurangi saat pembayaran dikonfirmasi* |

## 5.15 Kelas PaymentGatewayAdapter

**Nama Kelas:** *PaymentGatewayAdapter*  
**ID Kelas:** *C21*

Tabel 5.15.1. Operasi Kelas PaymentGatewayAdapter

| Nama Operasi | Visibility (private, public) | Keterangan |
| :--- | :--- | :--- |
| *buatTagihan(transaksi: Transaksi): String* | *public* | *Merealisasikan operasi MetodePembayaran. Mengembalikan lokasi file gambar QRIS dummy untuk ditampilkan kepada Pembeli.* |
| *cekStatus(idTransaksi: Integer): String* | *public* | *Merealisasikan operasi MetodePembayaran. Karena pembayaran hanya disimulasikan, operasi ini selalu mengembalikan status "LUNAS" ketika Pembeli menekan tombol untuk melanjutkan simulasi pembayaran.* |

Tabel 5.15.2. Atribut Kelas PaymentGatewayAdapter

| Nama Atribut | Visibility (private, public) | Tipe |
| :--- | :--- | :--- |
| *urlGateway* | *private* | *String* |

PaymentGatewayAdapter tetap dipisahkan dari PembayaranController melalui interface MetodePembayaran meskipun pembayaran hanya disimulasikan. Dengan demikian, apabila QRIS dummy diganti dengan *payment gateway* sungguhan, hanya kelas ini yang perlu diubah.

## 5.16 Kelas LoginView

**Nama Kelas:** *LoginView*  
**ID Kelas:** *C10*

Tabel 5.16.1. Operasi Kelas LoginView

| Nama Operasi | Visibility (private, public) | Keterangan |
| :--- | :--- | :--- |
| *tampilkanForm(): void* | *public* | *Menampilkan form login berisi kolom email, kolom password, dan tombol masuk untuk Penjual maupun Pembeli.* |
| *kirimKredensial(email: String, password: String): void* | *public* | *Mengirim email dan password yang diisi pengguna ke AuthController melalui HTTPS, lalu menindaklanjuti hasil login.* |
| *tampilkanPesan(pesan: String): void* | *public* | *Menampilkan pesan kesalahan, misalnya format email tidak valid, password kosong, atau email dan password tidak cocok.* |
| *arahkanKeBeranda(peran: String): void* | *public* | *Mengarahkan pengguna ke halaman utama sesuai perannya, yaitu beranda Penjual atau beranda Pembeli.* |

Tabel 5.16.2. Atribut Kelas LoginView

| Nama Atribut | Visibility (private, public) | Tipe |
| :--- | :--- | :--- |
| *–* | *–* | *–* |

### 5.16.1 Algoritma/Query

**Nama Kelas:** *LoginView*  
**Nama Operasi:** *kirimKredensial(email: String, password: String): void*  
**ID Algoritma:** *Algo-C10-01*

```text
Function kirimKredensial(email, password)
    nonaktifkan tombol masuk selama permintaan diproses
    hasil ← AuthController.login(email, password)
    if hasil adalah error then
        tampilkanPesan(hasil.pesan)
        kosongkan kolom password
    else
        arahkanKeBeranda(hasil.getPeran())
    aktifkan kembali tombol masuk
```

## 5.17 Kelas AuthController

**Nama Kelas:** *AuthController*  
**ID Kelas:** *C15*

Tabel 5.17.1. Operasi Kelas AuthController

| Nama Operasi | Visibility (private, public) | Keterangan |
| :--- | :--- | :--- |
| *login(email: String, password: String): Pengguna* | *public* | *Memvalidasi format kredensial melalui Validasi, mencari Pengguna berdasarkan email, memverifikasi password terhadap hash bcrypt, lalu jika pengguna adalah Pembeli, memerintahkan RewardLogin mencatat login harian dan menambah poin (UC07).* |

Tabel 5.17.2. Atribut Kelas AuthController

| Nama Atribut | Visibility (private, public) | Tipe |
| :--- | :--- | :--- |
| *–* | *–* | *–* |

### 5.17.1 Algoritma/Query

**Nama Kelas:** *AuthController*  
**Nama Operasi:** *login(email: String, password: String): Pengguna*  
**ID Algoritma:** *Algo-C15-01*

```text
Function login(email, password)
    galat ← Validasi.validasiKredensial(email, password)
    if galat tidak kosong then
        → error galat

    pengguna ← cari pengguna berdasarkan email               // Q-C15-01
    if pengguna = NULL or not pengguna.verifikasiPassword(password) then
        → error "Email atau password salah"

    if pengguna.getPeran() = "Pembeli" then
        BEGIN TRANSACTION
        reward ← ambil RewardLogin milik pengguna dan kunci barisnya   // Q-C15-02
        if reward.catatLogin(tanggalHariIni) then
            perbarui poin dan tanggal login terakhir         // Q-C15-03
        COMMIT

    → pengguna
```

Tabel 5.17.3. Query Operasi login

| No Query | Query | Keterangan |
| :--- | :--- | :--- |
| *Q-C15-01* | *cariPenggunaByEmail:*<br>`SELECT p.id_pengguna, p.nama, p.email, p.password, CASE WHEN pb.id_pengguna IS NOT NULL THEN 'Pembeli' ELSE 'Penjual' END AS peran FROM pengguna p LEFT JOIN pembeli pb ON pb.id_pengguna = p.id_pengguna WHERE p.email = @email;` | *Mengambil data pengguna beserta hash password, lalu menentukan perannya dari keberadaan baris pada tabel pembeli* |
| *Q-C15-02* | *ambilRewardLoginTerkunci:*<br>`SELECT * FROM reward_login WHERE id_pembeli = @idPengguna FOR UPDATE;` | *Mengambil dan mengunci data poin login milik Pembeli* |
| *Q-C15-03* | *perbaruiRewardLogin:*<br>`UPDATE reward_login SET poin_terkumpul = @poinTerkumpul, tanggal_login_terakhir = @tanggal WHERE id_pembeli = @idPengguna;` | *Menyimpan poin baru dan tanggal login terakhir* |

<br>

---

# BAB 6: Perancangan Antarmuka

## 6.1 Rancangan Antarmuka [ID Layar 1]

Masukkan versi awal prototipe antarmuka, dimana untuk setiap antarmuka/layar, tuliskan spesifikasi rinci objek yang ditampilkan dan reaksi sistem terhadap interaksi pengguna.

**Antarmuka:** *[ID layar]*  
**Nama Layar:** *[Nama layar]*

<p align="center">
<img alt="Contoh Logical View pada P/L E-Commerce" src="./assets/diagram/contoh-design.png" width="50%">
</p>
<p align="center">
<i>Gambar 6.1. Rancangan Antarmuka [ID Layar] - [Nama Layar]</i>
</p>

Tabel 6.1. Spesifikasi Objek Antarmuka [ID Layar]

| Id_Objek | Jenis | Konten | Keterangan |
| :--- | :--- | :--- | :--- |
| *[ID objek]* | *[Jenis objek, misalnya Button, RTF Box, dll]* | *[String yang tampil pada layar]* | *[Reaksi sistem, layar tujuan, tautan, atau ID algoritma yang dijalankan]* |
| *[ID objek]* | *[Jenis objek]* | *[Konten yang ditampilkan]* | *[Reaksi sistem atau nama file terkait beserta deskripsi ringkasnya]* |
| *...* | *...* | *...* | *...* |


## 6.X Rancangan Antarmuka [ID Layar X]

*[Ulangi pola 6.1 untuk layar berikutnya sampai semua layar teridentifikasi]*

## 6.Y Rancangan Antarmuka Keseluruhan

Tuliskan daftar gambar seluruh antarmuka. Berikan ID unik untuk setiap tampilan dan gunakan ID yang sama pada subbab perancangan antarmuka masing-masing.

Tabel 6.Y. Rancangan Antarmuka Keseluruhan

| No | Tampilan Antarmuka |
| :--- | :--- |
| *[I-01]* | <img src="./assets/diagram/contoh-design.png" alt="Contoh Desain" width="400"> |
| *[I-02]* | *[Sisipkan gambar antarmuka I-02]* |
| *[I-XX]* | *[Sisipkan gambar antarmuka berikutnya]* |

<br>

---

# BAB 7: Matriks Kerunutan

Petakan kelas perancangan dengan use case yang terkait. Gunakan **BAB 6 Traceability pada dokumen SKPL** sebagai acuan keterkaitan kelas analisis dan use case, lalu sesuaikan dengan realisasi use case dan kelas perancangan pada BAB 3–BAB 5 DPPL.

Tabel 7.1. Matriks Kerunutan Kelas terhadap Use Case

| Kelas | Use Case Terkait |
| :--- | :--- |
| *[ID kelas - Nama kelas]* | *[ID UC - Nama use case; tuliskan seluruh use case terkait]* |
| *[ID kelas - Nama kelas]* | *[ID UC - Nama use case]* |
| *...* | *...* |
