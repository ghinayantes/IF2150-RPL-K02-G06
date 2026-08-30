<h1>
IF2150 REKAYASA PERANGKAT LUNAK
<br>
TUGAS 1
<br>
TOPIC BRAINSTORMING
</h1>
<br>

## *Food Waste Stop*

### Untuk: *Aurelia Jennifer*

Dipersiapkan oleh:
| Informasi | Keterangan |
| --- | --- |
| Kelas | *\[K02\]* |
| Kelompok | *\[G06\]*  |

| NIM | Nama |
|---|---|
| *13525120* | *Nadia Aulia Syafarani* |
| *13525041* | *Renata Puspanegara Ninagan* |
| *13525119* | *Ghina Emelia Yantes* |
| *13525017* | *Cendra Asih Chairunnisa* |
| *13525089* | *Sherin Felicia Danessa* |
---

<br>
<br>

# BAB 1: Analisis Permasalahan

## 1.1 Latar Belakang Masalah
Tuliskan deskripsi permasalahan yang kalian pilih secara naratif dan spesifik. Tambahkan keterkaitan permasalahan tersebut dengan Tujuan Pembangunan Berkelanjutan (SDGs) yang telah disepakati. Dukung argumen kalian dengan data yang kredibel, serta jelaskan urgensi mengapa masalah ini perlu dan layak untuk segera diselesaikan.

## 1.2 Analisis Kondisi Saat Ini
  Saat ini, makanan yang tidak terjual di lingkungan kampus tidak memiliki mekanisme khusus untuk menawarkan kembali makanan berlebihan tersebut. Sehingga, penjual biasanya mengolahnya secara mandiri, seperti dengan membuangnya atau menyimpannya. Namun, penyimpanan yang dilakukan selama jangka waktu tertentu dapat menurunkan kualitas dan kelayakan makanan tersebut untuk dikonsumsi. Di sisi lain, mahasiswa juga tidak memiliki informasi makanan berlebih yang masih layak dan dapat dibeli dengan harga yang lebih rendah secara terpusat. Akibatnya, mahasiswa yang membutuhkan makanan dengan harga yang lebih terjangkau tidak selalu mengetahui keberadaannya di kantin kampus.
	Kondisi ini menyebabkan makanan yang sebenarnya masih layak untuk dikonsumsi terbuang dan menjadi food waste, serta penjual juga dapat kehilangan kesempatan untuk memperoleh pendapatan tambahan dari makanan yang tidak habis terjual. Oleh karena itu, diperlukan sebuah sistem yang dapat menghubungkan makanan berlebih dari penjual dengan mahasiswa secara terstruktur, serta memberikan keuntungan bagi penjual dan juga mahasiswa sebagai penggunanya.


---

# BAB 2: Analisis Solusi

## 2.1 Deskripsi Perangkat Lunak
  Solusi yang kami ajukan yaitu software berupa web application gamifikasi bagi mahasiswa untuk membangun kebiasaan mengurangi food waste. Platform web application dipilih dikarenakan aksesibilitasnya yang tinggi. Dengan ini, pengguna dapat langsung mengaksesnya tanpa perlu mengunduh aplikasi tambahan.
  Untuk mendorong pengguna, diberikan sistem minigame di mana apabila mereka melakukan kegiatan yang mengurangi limbah makanan, maka mereka akan mendapatkan poin tertentu. Salah satu metode mengurangi limbah makanan yang difasilitasi yaitu pengurangan limbah makanan dengan membeli makanan berlebih dari kantin. Perangkat lunak ini memungkinkan penjual untuk mendata daftar produk yang berlebih, mengunggah foto beserta stok yang tersisa, dan menginformasikan harga diskon. Dengan begini, pihak kantin dapat mengurangi limbah makanan yang diproduksi dan pengguna bisa dengan cepat mendapatkan informasi mengenai sisa makanan yang ada. Opsi challenge lain yang bisa diberikan adalah pengguna dapat mengumpulkan limbah makanan mereka untuk diberikan kepada pihak ketiga agar dapat diolah. Untuk setiap task akan diminta bukti, dan ketika bukti sudah diberikan maka poin akan bertambah. 
	Nilai unik dari perangkat lunak ini adalah sistem game yang diimplementasikan dengan konsep daily task. Selain itu, penerapan reward di akhir setelah terkumpul cukup poin akan membuat pengguna menjadi lebih terdorong untuk terus melakukannya. Konsep reward ini akan dilakukan dengan UI telur yang dapat ‘diberi makan’ poin, yang kemudian akan menetas ketika poin sudah cukup. Hal ini dapat memecahkan salah satu masalah dalam pendorongan SDG, yaitu retensi dan konsistensi pelaku. Dengan mendorong konsep game, maka aktivitas pendukungan SDG 12 akan terasa lebih seru dan menarik, sehingga dapat membentuk kebiasaan jangka panjang bagi pengguna.

## 2.2 Asumsi dan Batasan
  Asumsi dari sisi pengguna adalah mahasiswa sebagai pembeli dan penjual kantin sebagai penyedia makanannya. Mahasiswa bersedia membeli makanan dengan harga yang lebih rendah selama makanan masih layak untuk dikonsumsi dan penjual bertanggung jawab dalam memastikan makanan yang ditawarkan masih layak dan aman untuk dikonsumsi. Sistem reward dari konsep game dapat menjadi salah satu motivasi yang dapat mendorong mahasiswa untuk menggunakan layanan. 
	Untuk asumsi teknis, sistem dapat diakses oleh mahasiswa maupun penjual melalui perangkatnya masing-masing yang terhubung dengan internet. Data menu, transaksi, akun pengguna, dan reward tersimpan secara terpusat.

---

# BAB 3: Spesifikasi Kebutuhan dan Proses Bisnis

## 3.1 Identifikasi Aktor
Buatlah daftar seluruh aktor (pengguna) yang akan berinteraksi langsung dengan sistem solusi yang kalian kembangkan. Berikan penjelasan singkat mengenai peran dan karakteristik dari masing-masing aktor tersebut.

| Aktor | Deskripsi |
| :--- | :--- |
| *Pembeli : Pengelola sisa makanan menjadi kompos, pakan ternak* | *Pengguna ini bertindak sebagai pihak yang bertanggung jawab untuk memproses transaksi harian dan melayani pembayaran pelanggan. Karakteristik dari pengguna ini adalah mengutamakan kecepatan dan keakuratan saat bertransaksi.* |
| *Penjual : Kantin ITB* | *Pengguna ini bertindak sebagai pihak yang bertindak sebagai penjual sisa makanan bekas kantin  setiap harinya dan menetapkan harga dengan memerhatikan berat serta kualitasnya/standar. Karakteristik ini mengutamakan tempat deskripsi barang.* |


## 3.2 Kebutuhan Pengguna Awal
Definisikan apa yang ingin dicapai oleh pengguna saat menggunakan sistem ini dalam format *User Story* (Sebagai [Aktor], saya ingin [Aktivitas/Kebutuhan], sehingga [Tujuan/Nilai]). Pastikan kalian berfokus pada "apa yang ingin dilakukan pengguna".

| ID | Aktor | Kebutuhan / Aktivitas | Tujuan / Nilai |
| :--- | :--- | :--- | :--- |
| US-01 | *Penjual : Kantin ITB* |  *Memasukkan barang ke penjualan* | *Instruksi mudah diikuti (proses tidak ribet) dan deskripsi cukup (berat, kondisi, komposisi utama)* |
| US-02 | *Pembeli : Pengelola sisa makanan menjadi kompos* | *Mengecek barang * | *Tampilan mudah ditangkap informasi barangnya (tidak ribet)* |

## 3.3 Model Proses Bisnis
Buatlah *Activity Diagram* atau *Swimlane Diagram* yang menunjukkan alur kerja proses bisnis dari sistem solusi. Diagram ini harus memvisualisasikan bagaimana alur operasional di dunia nyata berjalan lebih efisien dengan adanya interaksi antara aktor (yang didefinisikan pada poin 3.1) dan sistem perangkat lunak. Perhatikan notasi yang digunakan dalam pembuatannya.
<br>

<p align="center">
<img alt="Contoh Activity Diagram" src="./assets/diagram/diagram-act-1.avif" width="70%"> 
</p>
<p align="center">
<i>Gambar 1. Contoh Activity Diagram</i>
</p>

<br>

# Referensi
- Badan Pangan Nasional. Publikasi Badan Pangan Nasional. Diakses pada 30 Agustus 2026, dari https://pustaka.badanpangan.go.id/publikasi/d296c101daa88a51f6ca8cfc1ac79b50
- United Nations Environment Programme (UNEP). (2024). Food Waste Index Report 2024. Diakses pada 30 Agustus 2026, dari https://www.unep.org/resources/publication/food-waste-index-report-2024
