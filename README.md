Tugas 7
1. Jelaskan apa yang dimaksud dengan stateless widget dan stateful widget, dan jelaskan perbedaan dari keduanya.
Jawab: 
Stateless Widget adalah jenis widget yang tidak memiliki state atau kondisi internal. Artinya, mereka tidak dapat mengubah tampilannya sendiri berdasarkan aksi atau perilaku internal. Perubahan tampilan pada widget ini hanya dapat terjadi jika input data yang diterimanya dari luar mengalami perubahan.

Stateless Widgets sepenuhnya bergantung pada parent widget untuk menerima informasi atau data, yang kemudian akan digunakan untuk menampilkan konten atau elemen UI. Jadi, kendali penuh untuk mengubah atau memperbarui tampilan dari stateless widget berada pada parent widget yang mengirimkan data tersebut.

Stateless Widgets hanya memerlukan properti yang sudah ditentukan saat konstruksi awal dan biasanya bersifat final. Dengan kata lain, setelah dibangun, widget ini tidak akan mengubah tampilannya sendiri. Perubahan hanya bisa terjadi jika parent widget mengirimkan data baru yang memicu pembaruan.

Stateful Widget adalah jenis widget yang memungkinkan perubahan tampilan secara dinamis selama masa hidupnya. Artinya, widget ini dapat memperbarui UI berdasarkan perubahan state (kondisi) internalnya, sehingga tampilan widget dapat berubah tanpa harus membuat ulang widget dari awal.

Meskipun stateful widget bersifat immutable (tidak bisa diubah setelah dibuat), widget ini memiliki kelas State yang menyertainya. Kelas State inilah yang bertanggung jawab untuk menyimpan kondisi atau data yang dapat berubah. Jika ada perubahan pada state, widget akan dibangun ulang untuk mencerminkan kondisi terbaru tersebut.

Stateful Widget dapat merespons perubahan yang berasal dari dalam (misalnya, dari aksi pengguna seperti menekan tombol) maupun dari luar (perubahan data dari parent widget). Setiap kali ada perubahan state, widget akan di-re-render atau dibangun ulang untuk memperbarui tampilan UI sesuai kondisi yang baru.

Dari penjelasan di atas, terdapat beberapa perbedaan antara stateless widget dan stateful widget. Dari sisi perubahan data, stateless widget tidak memiliki state internal sehingga datanya tidak dapat berubah secara dinamis setelah widget dibuat, sedangkan stateful widget memiliki state internal yang dapat berubah secara dinamis selama masa hidup widget. Dari sisi interaksi pengguna, stateless widget biasanya digunakan untuk tampilan yang tidak memerlukan interaksi atau hanya menampilkan informasi yang statis, sedangkan stateful widget digunakan untuk tampilan yang dapat berubah berdasarkan interaksi pengguna atau perubahan data. Dari sisi kelas yang terlibat, stateless widge hanya menggunakan satu kelas yang mengimplementasikan StatelessWidget, sedangkan stateful widget menggunakan dua kelas—satu untuk widget itu sendiri (mengimplementasikan StatefulWidget) dan satu lagi untuk state-nya (mengimplementasikan kelas State).

2. Sebutkan widget apa saja yang kamu gunakan pada proyek ini dan jelaskan fungsinya.
Jawab:
a. MaterialApp
Digunakan sebagai root atau struktur dasar aplikasi Flutter. MaterialApp menyediakan berbagai fitur seperti pengaturan tema, pengaturan routing, dan beberapa konfigurasi dasar aplikasi. Pada kode ini, MaterialApp digunakan untuk memberi judul aplikasi dan mengatur tema utama aplikasi dengan skema warna tertentu.

b. Scaffold
Memberikan struktur dasar pada halaman, termasuk AppBar di atas dan body di tengah halaman. Scaffold menyediakan kerangka umum seperti AppBar, FloatingActionButton, Drawer, dan sebagainya.

c. AppBar
Menyediakan area di bagian atas halaman yang biasanya menampilkan judul aplikasi atau elemen navigasi. Dalam proyek ini, AppBar menampilkan teks "Arlic Good Shop" sebagai judul halaman.

d. Padding
Menambahkan jarak di sekitar widget tertentu. Di sini, Padding digunakan untuk memberikan jarak di sekitar body dari Scaffold, juga di sekitar beberapa teks untuk estetika tampilan.

e. Column
Menyusun widget secara vertikal (atas-bawah). Dalam proyek ini, Column digunakan untuk menyusun InfoCard dan teks sambutan dalam satu kolom serta menampung widget lainnya secara vertikal.

f. Row
Menyusun widget secara horizontal (kiri-kanan). Row digunakan untuk menampilkan beberapa InfoCard dalam satu baris di bagian informasi pengguna (NPM, Name, dan Class).

g. Text
Digunakan untuk menampilkan teks di layar. Dalam proyek ini, Text digunakan untuk menampilkan berbagai informasi seperti judul, nama, npm, dan pesan sambutan.

h. GridView.count
Membuat tata letak grid dengan jumlah kolom tetap. Dalam proyek ini, GridView.count digunakan untuk menampilkan ItemCard dalam bentuk grid dengan 3 kolom, sehingga setiap ItemCard tersusun dalam bentuk kotak grid.

i. Card
Menyediakan kotak dengan tampilan seperti kartu yang memiliki efek bayangan. Di sini, Card digunakan dalam widget InfoCard untuk menampilkan informasi pengguna dalam bentuk kartu dengan sedikit bayangan di bawahnya.

j. Container
Digunakan untuk mengatur tata letak, ukuran, dan dekorasi dari widget. Container di sini digunakan di dalam Card untuk mengatur padding, lebar, dan menampung Column yang menyusun title dan content dari InfoCard.

k. Material
Menyediakan lapisan dasar material pada widget. Di sini, Material digunakan dalam ItemCard untuk memberikan efek warna sesuai dengan warna item dan juga memungkinkan efek bayangan serta animasi InkWell.

l. InkWell
Widget yang mendeteksi sentuhan dengan efek ripple atau animasi gelombang ketika ditekan. Di dalam ItemCard, InkWell digunakan untuk mendeteksi interaksi pengguna dan menampilkan pesan SnackBar ketika pengguna menekan tombol.

m. SnackBar
Menampilkan notifikasi atau pesan singkat di bagian bawah layar. Dalam proyek ini, SnackBar digunakan untuk memberikan feedback ketika pengguna menekan sebuah item dalam ItemCard, dengan menampilkan pesan seperti "Kamu telah menekan tombol Lihat Daftar Produk!"

n. Center
Memposisikan widget di tengah secara horizontal dan vertikal. Dalam proyek ini, Center digunakan untuk memastikan bahwa teks sambutan berada di tengah tampilan.

o. Icon
Menampilkan ikon di layar. Setiap ItemCard memiliki ikon yang ditentukan dalam ItemHomepage, seperti ikon mood, add, dan logout.

p. SizedBox
Memberikan jarak kosong dengan ukuran tertentu. Dalam proyek ini, SizedBox digunakan untuk menambahkan jarak vertikal antara widget untuk estetika tampilan.

3. Apa fungsi dari setState()? Jelaskan variabel apa saja yang dapat terdampak dengan fungsi tersebut.
Jawab: 
setState() merupakan fungsi yang digunakan dalam StatefulWidget di Flutter untuk memberi tahu framework bahwa ada perubahan pada data atau variabel yang memengaruhi tampilan widget. Ketika setState() dipanggil, Flutter akan melakukan rebuild pada bagian widget yang terpengaruh, sehingga perubahan data dapat langsung ditampilkan pada UI. Hanya variabel yang merupakan bagian dari state dalam StatefulWidget yang akan terdampak oleh setState(). Variabel tersebut biasanya merupakan variabel yang didefinisikan di dalam kelas State dari StatefulWidget.

4. Jelaskan perbedaan antara const dengan final.
Jawab: Terdapat beberapa perbedaan antara const dan final. Dari sisi waktu inisialisasi, final dapat diinisialisasi pada saar run time, sedangkan const harus diinisialisasi pada saat compile time. Dari sisi penggunaan dengan objek, final dapat digunakan untuk objek yang tidak dapat berubah setelah inisialisasi pertama tetapi bisa ditentukan saat run time, sedangkan const dapat digunakan untuk membuat objek yang benar-benar konstan dan tidak akan berubah di seluruh aplikasi. Dari sisi penggunaan dengan variabel top-level, final bisa digunakan secara global, tetapi nilainya hanya bisa diatur satu kali saat pertama kali digunakan, sedangkan const bisa digunakan secara global, misalnya untuk mendefinisikan variabel konstan di luar fungsi.

5. Jelaskan bagaimana cara kamu mengimplementasikan checklist-checklist di atas.
Jawab:
A. Membuat sebuah program Flutter baru dengan tema E-Commerce yang sesuai dengan tugas-tugas sebelumnya.
Step by Step:
    a. Membuat folder baru dengan nama arlicgoodshop
    - Generate proyek flutter baru dengan nama arlicgoodshop dengan menjalankan perintah berikut di terminal:
        flutter create arlicgoodshop

    b. Merapikan struktur proyek terlebih dahulu. 
    Step by Step:
    - Buat file baru bernama menu.dart pada direktori arlicgoodshop/lib.
    - Tambahkan pada baris pertama menu.dart dengan kode berikut:
        import 'package:flutter/material.dart';
    - Dari file main.dart, pindahkan kode baris ke-39 hingga akhir ke file menu.dart
    - Tambahkan kode berikut pada awal file main.dart:
        import 'package:arlicgoodshop/menu.dart';
    
    c. Membuat widget sederhana untuk menampilkan tema warna aplikasi
    Step by Step:
    - Buka file main.dart
    - Cantumkan kode pada main.dart di bagian tema aplikasi yang mempunyai tipe MaterialApp sebagai berikut:
        colorScheme: ColorScheme.fromSwatch(
          primarySwatch: Colors.orange,
        ).copyWith(secondary: Colors.orange[600]),
    
    d. Mengubah sifat widget halaman menu menjadi stateless
    Step by Step:
    - Pada main.dart, kode const  MyHomePage(title: 'Flutter Demo Home Page') diganti menjadi MyHomePage(), saja.
    - Pada menu.dart, untuk mengubah stateful menjadi stateless, hapus seluruh isi dari class MyHomePage, ubah extends StatefulWidget menjadi StatelessWidget, tambah MyHomePage({super.key}); sebagai constructor class MyHomePage, dan hapus seluruh class _MyHomePageState extends State<MyHomePage>.

    e. Membuat card sederhana untuk menampilkan informasi npm, nama, dan kelas:
    Step by Step:
    - Pada class MyHomePage, tambahkan kode berikut:
        final String npm = '2306202694'; // NPM
        final String name = 'Zufar Romli Amri'; // Nama
        final String className = 'PBP D'; // Kelas
    - Buat class baru, yaitu InfoCard pada menu.dart untuk menampilkan card sederhana berupa npm, nama, dan kelas. Berikut kodenya:
class InfoCard extends StatelessWidget {
  // Kartu informasi yang menampilkan title dan content.

  final String title; // Judul kartu.
  final String content; // Isi kartu.

  const InfoCard({super.key, required this.title, required this.content});

  @override
  Widget build(BuildContext context) {
    return Card(
      // Membuat kotak kartu dengan bayangan dibawahnya.
      elevation: 2.0,
      child: Container(
        // Mengatur ukuran dan jarak di dalam kartu.
        width: MediaQuery.of(context).size.width /
            3.5, // menyesuaikan dengan lebar device yang digunakan.
        padding: const EdgeInsets.all(16.0),
        // Menyusun title dan content secara vertikal.
        child: Column(
          children: [
            Text(
              title,
              style: const TextStyle(fontWeight: FontWeight.bold),
            ),
            const SizedBox(height: 8.0),
            Text(content),
          ],
        ),
      ),
    );
  }
}

B. Membuat tiga tombol sederhana dengan ikon dan teks & mengimplementasikan warna-warna yang berbeda untuk setiap tombol:
    - Melihat daftar produk (Lihat Daftar Produk)
    - Menambah produk (Tambah Produk)
    - Logout (Logout)
Step by Step: 
    - Buat class baru bernama ItemHomePage pada menu.dart dengan atributnya berupa name, icon, dan color sebagai berikut:
        class ItemHomepage {
            final String name;
            final IconData icon;
            final Color color;
        ItemHomepage(this.name, this.icon, this.color);
        }
    - Buat list of ItemHomePage yang berisi tombol-tombol yang ingin ditambahkan pada class MyHomePage beserta dengan atribut teks, icon, dan warna yang berbeda untuk setiap tombolnya sebagai berikut.
        class MyHomePage extends StatelessWidget {  
        ...
        final List<ItemHomepage> items = [
            ItemHomepage("Lihat Daftar Produk", Icons.shopping_bag, Colors.green),
            ItemHomepage("Tambah Produk", Icons.add, Colors.orange),
            ItemHomepage("Logout", Icons.logout, Colors.red),
        ];
        ...
        }

C.  Memunculkan Snackbar dengan tulisan:
- "Kamu telah menekan tombol Lihat Daftar Produk" ketika tombol Lihat Daftar Produk ditekan.
- "Kamu telah menekan tombol Tambah Produk" ketika tombol Tambah Produk ditekan.
- "Kamu telah menekan tombol Logout" ketika tombol Logout ditekan.
Step by Step:
    - Buat class Item Card untuk menampilkan tombol-tombol di atas. Apabila tombol ditekan, akan ditampilkan snackbar sesuai dengan pesan masing-masing tombol. Berikut kodenya:
class ItemCard extends StatelessWidget {
  final ItemHomepage item;

  const ItemCard(this.item, {super.key});

  @override
  Widget build(BuildContext context) {
    return Material(
      // Menggunakan warna spesifik dari item.
      color: item.color,
      borderRadius: BorderRadius.circular(12),
      child: InkWell(
        onTap: () {
          ScaffoldMessenger.of(context)
            ..hideCurrentSnackBar()
            ..showSnackBar(SnackBar(
                content: Text("Kamu telah menekan tombol ${item.name}!")));
        },
        child: Container(
          padding: const EdgeInsets.all(8),
          child: Center(
            child: Column(
              mainAxisAlignment: MainAxisAlignment.center,
              children: [
                Icon(
                  item.icon,
                  color: Colors.white,
                  size: 30.0,
                ),
                const Padding(padding: EdgeInsets.all(3)),
                Text(
                  item.name,
                  textAlign: TextAlign.center,
                  style: const TextStyle(color: Colors.white),
                ),
              ],
            ),
          ),
        ),
      ),
    );
  }
}

Tugas 8
1. Apa kegunaan const di Flutter? Jelaskan apa keuntungan ketika menggunakan const pada kode Flutter. Kapan sebaiknya kita menggunakan const, dan kapan sebaiknya tidak digunakan?
Jawab: 
Const digunakan untuk membuat objek yang bersifat immutable dan diinisialisasi saat waktu kompilasi (compile-time constant). Saat menggunakan const, Flutter hanya akan membuat satu instance dari objek yang sama dalam memori, bahkan jika objek tersebut digunakan berkali-kali di berbagai tempat. Hal ini dapat membantu meningkatkan efisiensi memori dan performa aplikasi.

Berikut beberapa keuntungan menggunakan const di flutter:
a. Menghemat Memori: Objek yang identik akan berbagi instance yang sama di memori.
b. Peningkatan Performa: Objek const diinisialisasi saat kompilasi, sehingga runtime tidak perlu lagi membuat objek baru. 
c. Keamanan dan Prediktabilitas: Objek const bersifat immutable, sehingga nilainya tidak dapat diubah setelah inisialisasi.

Sebaiknya, gunakan const ketika objek yang didefinisikan tidak perlu diubah, misalnya, widget dasar seperti Text, Icon, SizedBox, atau Padding yang selalu sama tampilannya di aplikasi.

Sebaiknya, tidak gunakan const ketika objek yang didefinisikan bersifat dinamis atau sering berubah karena flutter tidak bisa mengoptimalkan objek dinamis saat kompilasi.

2. Jelaskan dan bandingkan penggunaan Column dan Row pada Flutter. Berikan contoh implementasi dari masing-masing layout widget ini!
Jawab:
Column dan Row merupakan dua widget utama untuk membuat layout secara vertikal dan horizontal. Keduanya dapat digunakan untuk menyusun beberapa widget dalam satu baris atau kolom dengan mudah.

Berikut beberapa karakteristik yang membedakan penggunaan Column dan Row. Dari sisi orientasi, Column menyusun widget secara vertikal, sedangkan Row menyusun widget secara horizontal. Dari sisi Main Axis, Column memiliki arah vertikal, sedangkan Row memiliki arah horizontal. Dari sisi Cross Axis, Column memiliki arah horizonal, sedangkan Raw memiliki arah vertikal. Dari sisi scroll, Column yang panjang dapat dibungkus dengan SingleChildScrollView untuk scroll vertikal, sedangkan Row dapat dibungkus dengan SingleChildScrollView untuk scroll horizontal.

Contoh implementasi Column:

Column(children: [
  Text(
    'Arlic Good Shop',
    textAlign: TextAlign.center,
    style: TextStyle(
      fontSize: 24,
      fontWeight: FontWeight.bold,
      color: Colors.white,
    ),
  ),
  Padding(padding: EdgeInsets.all(8)),
  Text(
    "Ayo beli produk terbaikmu disini!",
    style: TextStyle(
      fontSize: 15,
      color: Colors.white,
      fontWeight: FontWeight.normal,
    ),
    textAlign: TextAlign.center,
  ),
],
),

Contoh implementasi Row:

Row(
  mainAxisAlignment: MainAxisAlignment.spaceAround, // Menyusun widget dengan jarak yang sama di antara mereka secara horizontal
  crossAxisAlignment: CrossAxisAlignment.center, // Menyusun widget di tengah secara vertikal
  children: [
    Icon(Icons.home),
    Icon(Icons.star),
    Icon(Icons.settings),
  ],
);


3. Sebutkan apa saja elemen input yang kamu gunakan pada halaman form yang kamu buat pada tugas kali ini. Apakah terdapat elemen input Flutter lain yang tidak kamu gunakan pada tugas ini? Jelaskan!
Jawab: 
Pada tugas kali ini, elemen input yang digunakan pada halaman form adalah TextFormField. TextFormField digunakan untuk setiap input Nama, Amount, dan Description.

Tentunya, terdapat elemen input Flutter lain yang tidak digunakan pada tugas ini. Elemen yang tidak digunakan sebagai berikut:
a. Checkbox: Digunakan untuk memilih opsi ya/tidak (boolean). Misalnya, bisa digunakan untuk menandai apakah item ini aktif atau tidak.
b. Switch: Mirip dengan Checkbox, tetapi berbentuk sakelar on/off. Umumnya digunakan untuk mengatur pengaturan atau fitur yang bisa diaktifkan atau dinonaktifkan.
c. Radio: Digunakan untuk memilih satu dari beberapa opsi (satu pilihan dari beberapa). Cocok untuk memilih kategori item atau tipe item yang hanya memiliki satu pilihan.

dan elemen lainnya yang belum perlu digunakan pada tugas kali ini.


4. Bagaimana cara kamu mengatur tema (theme) dalam aplikasi Flutter agar aplikasi yang dibuat konsisten? Apakah kamu mengimplementasikan tema pada aplikasi yang kamu buat?
Jawab:
Berikut yang saya lakukan untuk mengatur tema dalam aplikasi Flutter agar aplikasi yang dibuat konsisten.
a. Menentukan Tema Utama (ThemeData): Saya sudah menentukan tema utama untuk aplikasi dengan mendefinisikan ThemeData di dalam MaterialApp. Saya menggunakan colorScheme untuk mengatur warna aplikasi secara konsisten. Berikut implementasinya:

theme: ThemeData(
  colorScheme: ColorScheme.fromSwatch(
    primarySwatch: Colors.orange,
  ).copyWith(secondary: Colors.orange[600]),
  useMaterial3: true,
),

b. Menggunakan Warna dari Tema di Widget: Di dalam ItemEntryFormPage, Saya bisa mengambil warna utama dan sekunder dari colorScheme yang telah diatur. Berikut adalah contoh penggunaan warna tema di AppBar dan ElevatedButton dalam halaman Saya:

appBar: AppBar(
  title: const Center(
    child: Text('Form Tambah Item'),
  ),
  backgroundColor: Theme.of(context).colorScheme.primary,  // Mengambil warna utama dari tema
  foregroundColor: Colors.white,
),

c. Mengambil Manfaat Konsistensi Tema: Dengan menentukan colorScheme di ThemeData, Saya bisa menggunakan Theme.of(context).colorScheme.primary atau Theme.of(context).colorScheme.secondary di seluruh widget lainnya yang membutuhkan warna sesuai tema aplikasi. Ini memastikan semua elemen mengikuti tema yang sama dan membuat aplikasi terlihat konsisten.

5. Bagaimana cara kamu menangani navigasi dalam aplikasi dengan banyak halaman pada Flutter?
Jawab: 
Untuk menangani navigasi dalam aplikasi Flutter dengan banyak halaman, Kita dapat menggunakan widget Navigator dan metode navigasi yang disediakan, seperti push(), pop(), dan pushReplacement(). Berikut ini adalah cara menggunakan masing-masing metode sesuai kebutuhan:
a. Menambah Halaman Baru ke Stack dengan push()
Gunakan Navigator.push() untuk menambahkan halaman baru di atas halaman yang sedang ditampilkan. Ini berarti halaman baru akan ditambahkan ke paling atas dari stack, sehingga pengguna dapat kembali ke halaman sebelumnya dengan tombol Back di perangkat. Berikut contoh implementasinya:

Navigator.push(
context,
MaterialPageRoute(
  builder: (context) => const ItemEntryFormPage(),
));

Contoh implementasi di atas akan memindahkan pengguna ke ItemEntryFormPage tanpa menghapus elemen sebelumnya dari stack.

b. Kembali ke Halaman Sebelumnya dengan pop()
Gunakan Navigator.pop() untuk menutup halaman yang sedang aktif dan kembali ke halaman sebelumnya di stack. Ini sangat berguna ketika pengguna ingin kembali tanpa menambahkan halaman baru ke stack. Berikut contoh implementasinya:

onPressed: () {
  Navigator.pop(context);
}

Metode ini menghapus halaman yang sedang ditampilkan dari stack dan kembali ke halaman yang berada di bawahnya.

c. Mengganti Halaman di Stack dengan pushReplacement()
Gunakan Navigator.pushReplacement() jika kita ingin mengganti halaman saat ini dengan halaman baru tanpa menambahkannya ke stack. Halaman baru akan menggantikan halaman saat ini di stack. Berikut contoh implementasinya:

Navigator.pushReplacement(
context,
MaterialPageRoute(
  builder: (context) => MyHomePage(),
));

pushReplacement() berguna saat kita tidak ingin pengguna bisa kembali ke halaman sebelumnya, seperti saat berpindah dari halaman login ke halaman utama setelah login berhasil.

d. Menggunakan nvigasi yang Lebih Kompleks dengan popUntil(), canPop(), dan maybePop()

  - popUntil(): Menghapus halaman dari stack hingga kondisi tertentu terpenuhi, memungkinkan kita untuk kembali ke halaman tertentu tanpa memerlukan banyak pop() manual.
  - canPop(): Memeriksa apakah ada halaman lain dalam stack sebelum memanggil pop().
  - maybePop(): Mirip dengan pop(), tetapi hanya berfungsi jika ada halaman yang bisa di-pop.

Dengan menggunakan Navigator dan berbagai metodenya, kita dapat membuat sistem navigasi yang fleksibel dan intuitif di dalam aplikasi.