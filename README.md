Nama: Meisy Nadia Nababan
<br>NIM: 2341760031
<br>Kelas: SIB 3F
<br>Mata Kuliah: Pemrograman Mobile

TUGAS
3. Membuat project
Membuat proyek Flutter pertama Anda
<br>1. Ketik "flutter new". Pilih perintah Flutter: New Project.

![Screenshot tugas_mobile_pertemuan4](images/01.png)
<br> 2. Berikutnya, pilih Application lalu folder tempat proyek akan dibuat. Folder ini dapat berupa direktori utama Anda, atau direktori seperti C:\flutter project

![Screenshot tugas_mobile_pertemuan4](images/02.png)
<br> 3. Pada panel sebelah kiri VS Code, pastikan bahwa Penjelajah dipilih lalu buka file pubspec.yaml.

![Screenshot flutter_tugas_mobile_pertemuan4](images/03.png)
<br>Ganti konten file ini dengan kode berikut:

![Screenshot flutter_tugas_mobile_pertemuan4](images/04.png)
<br> 4. Berikutnya, buka file konfigurasi lainnya dalam proyek tersebut, analysis_options.yaml.

![Screenshot flutter_tugas_mobile_pertemuan4](images/05.png)
<br> Ganti konten file tersebut dengan kode berikut:

![Screenshot flutter_tugas_mobile_pertemuan4](images/06.png)
<br> 5. Terakhir, buka file main.dart pada direktori lib/.

![Screenshot flutter_tugas_mobile_pertemuan4](images/07.png)
<br>Ganti konten file ini dengan kode berikut:

![Screenshot flutter_tugas_mobile_pertemuan4](images/08.png)
<br> Selagi lib/main.dart terbuka, temukan tombol "play" di pojok kanan atas jendela VS Code lalu klik tombol tersebut.

![Screenshot flutter_tugas_mobile_pertemuan4](images/09.png)
<br> 6. Di bagian bawah lib/main.dart, tambahkan sesuatu pada string di objek Text pertama, dan simpan file tersebut (dengan Ctrl+S atau Cmd+S). Misalnya:

![Screenshot flutter_tugas_mobile_pertemuan4](images/10.png)
<br> Perhatikan bagaimana aplikasi segera berubah tetapi kata yang acak tetap sama. Situasi ini menunjukkan fitur stateful Hot Reload Flutter terkenal yang sedang bekerja. Hot reload dipicu saat Anda menyimpan perubahan untuk file sumber.

![Screenshot flutter_tugas_mobile_pertemuan4](images/11.png)
<br> 7. Berikutnya, tambahkan tombol di bagian bawah Column, tepat di bawah instance Text kedua.

![Screenshot flutter_tugas_mobile_pertemuan4](images/12.png)
<br> Saat Anda menyimpan perubahan, aplikasi diperbarui kembali: Sebuah tombol muncul dan, saat Anda mengklik tombol tersebut, Konsol Debug di VS Code menampilkan pesan button pressed!.

![Screenshot flutter_tugas_mobile_pertemuan4](images/13.png)
<br> 8. Scroll ke MyAppState lalu tambahkan metode getNext.

![Screenshot flutter_tugas_mobile_pertemuan4](images/14.png)
Metode getNext() baru menetapkan ulang current dengan WordPair acak baru. Metode ini juga memanggil notifyListeners()(metode ChangeNotifier) yang memastikan bahwa semua orang yang melihat MyAppState diberi tahu.
<br> 9. Tindakan terakhir adalah memanggil metode getNext dari callback tombol tersebut.

![Screenshot flutter_tugas_mobile_pertemuan4](images/15.png)
Aplikasi akan menghasilkan pasangan kata acak baru setiap kali Anda menekan tombol Next.
![Screenshot flutter_tugas_mobile_pertemuan4](images/16.png)
![Screenshot flutter_tugas_mobile_pertemuan4](images/17.png)
![Screenshot flutter_tugas_mobile_pertemuan4](images/18.png)
Mengekstrak widget
<br> Baris yang bertanggung jawab untuk menampilkan pasangan kata saat ini kini tampak seperti berikut: Text(appState.current.asLowerCase). Untuk mengubahnya menjadi sesuatu yang lebih kompleks, disarankan untuk mengekstrak baris ini ke widget terpisah. Memiliki beberapa widget untuk beberapa bagian logis dari UI Anda adalah cara penting dalam mengelola kompleksitas pada Flutter.
<br> Flutter menyediakan pembantu pemfaktoran ulang untuk mengekstrak widget, tetapi sebelum Anda menggunakannya, pastikan bahwa baris yang akan diekstrak hanya mengakses yang diperlukan. Sekarang baris tersebut mengakses appState, tetapi sebenarnya baris tersebut hanya perlu mengetahui apa pasangan kata saat ini.
<br> 10. Oleh karena itu, tulis ulang widget MyHomePage sebagai berikut:

![Screenshot flutter_tugas_mobile_pertemuan4](images/19.png)
<br> Pada menu Refactor, pilih Extract Widget. Tetapkan nama, seperti BigCard, lalu klik Enter.
<br> 11. Tindakan ini secara otomatis membuat class baru, BigCard, di akhir file saat ini. Class tersebut akan terlihat seperti berikut:

![Screenshot flutter_tugas_mobile_pertemuan4](images/20.png)
<br> Sekarang saatnya membuat widget baru ini menjadi UI tebal yang kita bayangkan di awal bagian ini.
Temukan class BigCard dan metode build() yang berada di dalamnya. Sama seperti sebelumnya, panggil menu Refactor pada widget Text. Namun, kali ini Anda tidak akan mengekstrak widget.
<br> Sebagai gantinya, pilih Wrap with Padding. Tindakan ini menciptakan widget induk baru di sekitar widget Text bernama Padding. Setelah menyimpannya, Anda akan melihat bahwa kata acak tersebut telah memiliki ruang yang lebih luas.

![Screenshot flutter_tugas_mobile_pertemuan4](images/21.png)

<br> 12, Tingkatkan padding dari nilai default 8.0. Misalnya, gunakan 20 untuk padding yang lebih luas. Berikutnya, mari kita naik satu tingkat lebih tinggi. Tempatkan kursor Anda pada widget Padding, buka menu Refactor, lalu pilih Wrap with widget....
<br> Tindakan ini memungkinkan Anda untuk menentukan widget induk. Ketik "Card" dan tekan Enter.

![Screenshot flutter_tugas_mobile_pertemuan4](images/22.png)
<br> Kode ini menggabungkan widget Padding, dan juga Text, dengan widget Card.

![Screenshot flutter_tugas_mobile_pertemuan4](images/23.png)
<br>Untuk membuat kartu menjadi lebih menarik, beri warna yang lebih kaya pada kartu tersebut. Karena ada baiknya untuk menjaga skema warna yang konsisten, gunakan Theme aplikasi untuk memilih warna.
<br> 13. Buat perubahan berikut untuk metode build() BigCard.

![Screenshot flutter_tugas_mobile_pertemuan4](images/24.png)
Kini, kartu telah diwarnai dengan warna primer aplikasi:

![Screenshot flutter_tugas_mobile_pertemuan4](images/25.png)
<br> Anda dapat mengubah warna ini serta skema warna keseluruhan aplikasi dengan men-scroll ke atas ke MyApp dan mengubah warna seed untuk ColorScheme di sana.

<br> 14. Kartu tersebut masih memiliki masalah: ukuran teks terlalu kecil dan warnanya membuat teks sulit dibaca. Untuk memperbaiki masalah ini, buat perubahan berikut pada metode build() BigCard. 

![Screenshot flutter_tugas_mobile_pertemuan4](images/26.png)
Kini, aplikasi akan terlihat seperti berikut:

![Screenshot flutter_tugas_mobile_pertemuan4](images/27.png)
<br> Setelah pasangan kata acak dihadirkan dengan gaya visual yang cukup, saatnya menempatkan UI di tengah jendela/layar aplikasi.

<br> 15. Pertama, ingatlah bahwa BigCard adalah bagian dari Column. Secara default, kolom menggabungkan turunan kolom di bagian atas, tetapi kita dapat mengganti ini dengan mudah. Buka metode build() MyHomePage, dan buat perubahan berikut:

![Screenshot flutter_tugas_mobile_pertemuan4](images/28.png)
<br> Tindakan ini menempatkan turunan dalam Column di tengah pada sumbu utamanya (vertikal).

![Screenshot flutter_tugas_mobile_pertemuan4](images/29.png)
<br> Turunan UI telah ditempatkan di tengah pada sumbu silang kolom (dengan kata lain, turunan UI telah ditempatkan di tengah secara horizontal). Namun, Column itu sendiri tidak ditempatkan di tengah dalam Scaffold. Kita dapat memverifikasi ini menggunakan Widget Inspector.

![Screenshot flutter_tugas_mobile_pertemuan4](images/30.png)

<br> Kini, aplikasi akan terlihat seperti berikut:
![Screenshot flutter_tugas_mobile_pertemuan4](images/31.png)
<br> 16. Dengan perubahan opsional, MyHomePage mencakup kode berikut:

![Screenshot flutter_tugas_mobile_pertemuan4](images/32.png)
<br> Aplikasinya akan terlihat seperti berikut:

![Screenshot flutter_tugas_mobile_pertemuan4](images/33.png)
<br> 17. Menambahkan logika bisnis
Scroll ke MyAppState dan tambahkan kode berikut:

![Screenshot flutter_tugas_mobile_pertemuan4](images/34.png)
Menambahkan tombol
<br> Dengan terselesaikannya "logika bisnis", saatnya untuk mengerjakan antarmuka pengguna kembali. Meletakkan tombol ‘Like' di sebelah kiri tombol ‘Next' memerlukan Row. Widget Row adalah padanan horizontal dari Column, yang telah Anda lihat sebelumnya.

Pertama, gabungkan tombol yang ada pada Row. Buka metode build() MyHomePage, letakkan kursor pada ElevatedButton, buka menu Refactor dengan Ctrl+. atau Cmd+., lalu pilih Wrap with Row.
![Screenshot flutter_tugas_mobile_pertemuan4](images/35.png)
UI kembali ke tempat sebelumnya.
![Screenshot flutter_tugas_mobile_pertemuan4](images/36.png)
<br> 18. Berikut satu cara untuk menambahkan tombol kedua untuk MyHomePage. Kali ini, gunakan konstruktor ElevatedButton.icon() untuk membuat tombol dengan ikon. Di bagian atas metode build, pilih ikon yang sesuai tergantung pada apakah pasangan kata saat ini sudah berada di favorit atau tidak. Selain itu, perhatikan penggunaan SizedBox lagi, untuk menjaga jarak antara kedua tombol.

![Screenshot flutter_tugas_mobile_pertemuan4](images/37.png)
output kode:
![Screenshot flutter_tugas_mobile_pertemuan4](images/38.png)
<br> 19. Untuk mencapai inti dari langkah ini secepat mungkin, pisahkan MyHomePage menjadi 2 widget terpisah.
<br> Pilih keseluruhan MyHomePage, hapus, dan gantikan dengan kode berikut:

![Screenshot flutter_tugas_mobile_pertemuan4](images/39.png)
<br> Saat disimpan, Anda akan melihat sisi visual UI telah siap—tetapi tidak bekerja. Mengklik ♥︎ (hati) pada kolom samping navigasi tidak melakukan apa pun.

![Screenshot flutter_tugas_mobile_pertemuan4](images/40.png)
<br> 20. Widget stateful baru hanya perlu melacak satu variabel: selectedIndex. Buat 3 perubahan berikut untuk _MyHomePageState:

![Screenshot flutter_tugas_mobile_pertemuan4](images/41.png)
output kode:
![Screenshot flutter_tugas_mobile_pertemuan4](images/42.png)
<br> 21. Tempatkan kode berikut di bagian atas metode build _MyHomePageState, tepat sebelum return Scaffold:

![Screenshot flutter_tugas_mobile_pertemuan4](images/43.png)
output kode:
![Screenshot flutter_tugas_mobile_pertemuan4](images/44.png)

![Screenshot flutter_tugas_mobile_pertemuan4](images/45.png)
<br> 22. Sekarang kode Anda dapat memutuskan untuk menampilkan label dengan membuat kueri constraints saat ini atau tidak. Buat perubahan baris tunggal berikut untuk metode build _MyHomePageState:

![Screenshot flutter_tugas_mobile_pertemuan4](images/46.png)
output kode:
![Screenshot flutter_tugas_mobile_pertemuan4](images/47.png)

![Screenshot flutter_tugas_mobile_pertemuan4](images/48.png)
<br> Pekerjaan yang tersisa hanya mengganti Placeholder itu dengan layar Favorites yang sebenarnya. Pembahasan itu dibahas di bagian berikutnya.
<br> 23. Berikut ini hanyalah salah satu cara untuk menerapkan halaman favorit. Bagaimana halaman ini diterapkan (semoga) akan menginspirasi Anda untuk bermain dengan kode—meningkatkan UI dan membuat UI sesuai keinginan Anda.
<br> Berikut class FavoritesPage baru:

![Screenshot flutter_tugas_mobile_pertemuan4](images/49.png)
output kode:
![Screenshot flutter_tugas_mobile_pertemuan4](images/50.png)

![Screenshot flutter_tugas_mobile_pertemuan4](images/51.png)
<br> 24. Bereksperimenlah lebih lanjut dengan aplikasi yang Anda buat selama menjalani lab ini.

![Screenshot flutter_tugas_mobile_pertemuan4](images/52.png)
![Screenshot flutter_tugas_mobile_pertemuan4](images/53.png)
jika dihapus
![Screenshot flutter_tugas_mobile_pertemuan4](images/54.png)