# click-and-cart: All your needs in one click

# Contents
- [Data Diri](#data-diri)<br>
- [Tugas 7](#tugas-7)<br>
- [Tugas 8](#tugas-8)<br>
- [Tugas 9](#tugas-9)<br>

## Data Diri
**Nama : Muhammad Faizi Ismady Supardjo**<br>
**NPM : 2306244955**<br>
**Kelas : PBP C**<br>


## Tugas 7
- [Contents](#contents)<br>

**1. Jelaskan apa yang dimaksud dengan stateless widget dan stateful widget, dan jelaskan perbedaan dari keduanya.**<br>
stateless widget dan stateful widget adalah dua jenis widget utama dalam Flutter.<br>
1.1 Stateless Widget<br>
- Definisi: Stateless Widget adalah widget yang tidak dapat berubah selama runtime. Artinya, setelah widget ini dirender (ditampilkan) di layar, tampilannya tidak akan berubah, kecuali aplikasi di-rebuild atau hot reloaded secara manual.
- Contoh Penggunaan: Stateless Widget cocok digunakan untuk elemen statis pada aplikasi, seperti teks, ikon, atau tombol dengan tampilan yang tetap dan tidak bergantung pada data dinamis.<br>
- Contoh Kode:
```bash
class MyStatelessWidget extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Text('Hello, Stateless Widget!');
  }
}
```

1.2 Stateful Widget<br>
- Definisi: Stateful Widget adalah widget yang memiliki state, yaitu data atau status yang dapat berubah selama aplikasi berjalan. Jika ada perubahan pada state, widget ini akan dirender ulang untuk mencerminkan perubahan tersebut.
- Contoh Penggunaan: Stateful Widget cocok digunakan untuk elemen yang dinamis atau interaktif, seperti counter, formulir, daftar yang dapat diperbarui, atau tombol yang mengubah tampilan berdasarkan interaksi pengguna.
- Contoh Kode:
```bash
class MyStatefulWidget extends StatefulWidget {
  @override
  _MyStatefulWidgetState createState() => _MyStatefulWidgetState();
}

class _MyStatefulWidgetState extends State<MyStatefulWidget> {
  int counter = 0;

  void incrementCounter() {
    setState(() {
      counter++;
    });
  }

  @override
  Widget build(BuildContext context) {
    return Column(
      children: [
        Text('Counter: $counter'),
        ElevatedButton(
          onPressed: incrementCounter,
          child: Text('Increment'),
        ),
      ],
    );
  }
}
```


**2. Sebutkan widget apa saja yang kamu gunakan pada proyek ini dan jelaskan fungsinya.**<br>
Pada proyek ini, saya menggunakan beberapa widget Flutter, di antaranya adalah:

- MaterialApp<br>
Fungsi: MaterialApp adalah widget utama untuk aplikasi Flutter yang mengikuti desain Material. Widget ini mendefinisikan tema aplikasi, rute, dan widget halaman utama (home). Dalam proyek ini, MaterialApp digunakan untuk mengatur tema warna dan tampilan utama aplikasi.

- Scaffold<br>
Fungsi: Scaffold menyediakan struktur dasar untuk halaman dengan AppBar, Body, Floating Action Button, Drawer, dll. Dalam proyek ini, Scaffold digunakan untuk membuat tata letak dasar halaman utama, termasuk bagian AppBar dan Body.

- AppBar<br>
Fungsi: AppBar adalah widget yang menampilkan header atau bagian atas halaman. Ini biasanya berisi judul, ikon, atau tindakan lain. Pada proyek ini, AppBar digunakan untuk menampilkan judul "Click and Cart" di bagian atas halaman.

- Padding<br>
Fungsi: Padding memberikan ruang atau jarak di sekitar widget anak (child). Pada proyek ini, Padding digunakan untuk memberikan jarak di sekitar elemen-elemen agar tampil lebih rapi.

- Column<br>
Fungsi: Column adalah widget tata letak yang menyusun widget anaknya secara vertikal (dari atas ke bawah). Pada proyek ini, Column digunakan untuk menyusun elemen-elemen seperti InfoCard dan teks sambutan di halaman utama.

- Row<br>
Fungsi: Row adalah widget tata letak yang menyusun widget anaknya secara horizontal (dari kiri ke kanan). Dalam proyek ini, Row digunakan untuk menyusun InfoCard secara horizontal, menampilkan informasi seperti NPM, Nama, dan Kelas.

- Text<br>
Fungsi: Text digunakan untuk menampilkan teks. Pada proyek ini, Text digunakan di berbagai tempat untuk menampilkan judul, deskripsi, dan informasi lainnya di dalam halaman.

- GridView<br>
Fungsi: GridView adalah widget untuk menampilkan daftar item dalam bentuk grid atau kotak-kotak. Dalam proyek ini, GridView.count digunakan untuk menampilkan ItemCard dalam bentuk grid 3 kolom.

- Card<br>
Fungsi: Card digunakan untuk menampilkan informasi di dalam sebuah kotak dengan bayangan (elevation) untuk efek kedalaman. Pada proyek ini, Card digunakan dalam InfoCard untuk menampilkan informasi NPM, Nama, dan Kelas dengan tampilan yang lebih rapi.

- Center<br>
Fungsi: Center digunakan untuk menempatkan widget anaknya di tengah-tengah. Pada proyek ini, Center digunakan untuk memusatkan elemen-elemen tertentu di dalam halaman agar lebih simetris.

- Icon<br>
Fungsi: Icon digunakan untuk menampilkan ikon grafis, biasanya sebagai representasi visual dari suatu tindakan atau item. Dalam proyek ini, Icon digunakan dalam ItemCard untuk menampilkan ikon seperti "Lihat Daftar Produk", "Tambah Produk", dan "Logout".

- Material<br>
Fungsi: Material digunakan untuk membungkus widget dengan efek material (seperti warna, bayangan, dan efek klik). Pada proyek ini, Material digunakan dalam ItemCard untuk memberikan warna latar belakang pada kartu item dengan efek material yang dapat ditekan.

- InkWell<br>
Fungsi: InkWell adalah widget yang membuat efek klik (ripple) pada widget anaknya. Pada proyek ini, InkWell digunakan di dalam ItemCard untuk memberikan efek ketika kartu ditekan.

- SnackBar<br>
Fungsi: SnackBar adalah widget yang menampilkan pesan singkat di bagian bawah layar. Pada proyek ini, SnackBar digunakan untuk memberikan notifikasi saat pengguna menekan sebuah item dalam ItemCard.

**3. Apa fungsi dari setState()? Jelaskan variabel apa saja yang dapat terdampak dengan fungsi tersebut.**
Fungsi `setState()` dalam Flutter digunakan untuk memberi tahu framework bahwa state objek telah berubah, dan widget yang terkait perlu dirender ulang. Dengan memanggil `setState()`, kita bisa memperbarui tampilan aplikasi agar mencerminkan perubahan data atau status secara real-time.

Cara Kerja `setState()`
Ketika `setState()` dipanggil, Flutter:

i. Menandai widget sebagai "perlu diperbarui".<br>
ii. Merender ulang bagian dari widget tree yang terkait dengan perubahan state.<br>
iii. Menampilkan tampilan terbaru yang sudah diperbarui sesuai dengan perubahan pada variabel-variabel di dalamnya.<br>
Contoh Penggunaan `setState()`
Misalnya, pada aplikasi counter sederhana, setiap kali tombol ditekan, variabel `_counter` bertambah 1, dan `setState()` digunakan untuk memperbarui tampilan angka pada layar.
```bash
int _counter = 0;

void _incrementCounter() {
  setState(() {
    _counter++;
  });
}
```
Dalam contoh ini, setiap kali `_incrementCounter` dipanggil, fungsi `setState()` akan memperbarui tampilan angka (`_counter`) di layar.

Semua variabel yang didefinisikan di dalam kelas state (kelas yang terkait dengan `StatefulWidget`) dan diubah dalam fungsi `setState()` akan berdampak pada tampilan. Flutter akan merender ulang tampilan sesuai dengan perubahan tersebut, memungkinkan pengalaman pengguna yang lebih responsif dan dinamis.

**4. Jelaskan perbedaan antara const dengan final.**
4.1 final
- Definisi: `final` digunakan untuk mendeklarasikan variabel yang hanya bisa diinisialisasi satu kali dan tidak dapat diubah setelah itu. Namun, inisialisasi `final` dilakukan pada saat runtime (saat program dijalankan).
- Penggunaan: `final` cocok digunakan untuk variabel yang nilainya diperoleh saat runtime atau tidak diketahui saat kompilasi.

4.2 const
- Definisi: `const` digunakan untuk mendeklarasikan nilai konstan yang bersifat kompilasi, yang berarti nilainya harus diketahui dan ditentukan pada saat kompilasi (compile-time constant).
- Penggunaan: `const` digunakan untuk nilai yang benar-benar konstan dan diketahui sebelum program dijalankan. Biasanya digunakan untuk nilai konstan seperti angka atau string literal, atau untuk widget statis dalam Flutter.

**5. Jelaskan bagaimana cara kamu mengimplementasikan checklist-checklist di atas.**<br>
5.1 Membuat sebuah program Flutter baru dengan tema E-Commerce yang sesuai dengan tugas-tugas sebelumnya.
- Menginisasi aplikasi flutter baru dengan command `flutter create click_and_cart_mobile` untuk start aplikasi saya dalam bentuk mobile.

- Membuat file baru pada direktori `/lib` dengan nama `main.dart` untuk mengatur antara `main.dart` dengan `menu.dart`

- Membuat `main.dart` sebagai base aplikasi. Isi sebagai berikut:
```bash
import 'package:flutter/material.dart';
import 'package:click_and_cart/menu.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  // This widget is the root of your application.
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      theme: ThemeData(
         colorScheme: ColorScheme.fromSwatch(
       primarySwatch: Colors.deepPurple,
        ).copyWith(secondary: Colors.deepPurple[400]),
        useMaterial3: true,
      ),
      home: MyHomePage(),
    );
  }
}
```

5.2  Membuat tiga tombol sederhana dengan ikon dan teks, serta warna berbeda-beda
- Isi file `menu.dart` dengan kode berikut:
Untuk membuat list items berisi instance of `ItemHomepage` serta membuat class `ItemHomepage`
```bash
    final List<ItemHomepage> items = [
         ItemHomepage("Lihat Daftar Produk", Icons.mood, Colors.red),
         ItemHomepage("Tambah Produk", Icons.add, Colors.blue),
         ItemHomepage("Logout", Icons.logout, Colors.purple),
     ];
```

```bash
class ItemHomepage {
     final String name;
     final IconData icon;
     final Color color;


     ItemHomepage(this.name, this.icon, this.color);
 }
```

5.3 Memunculkan snackbar
- Isi `menu.dart` sebagai berikut
```bash

  @override
  Widget build(BuildContext context) {
    return Material(
      // Menentukan warna latar belakang dari tema aplikasi.
      color: item.color,
      // Membuat sudut kartu melengkung.
      borderRadius: BorderRadius.circular(12),
      
      child: InkWell(
        // Aksi ketika kartu ditekan.
        onTap: () {
          // Menampilkan pesan SnackBar saat kartu ditekan.
          ScaffoldMessenger.of(context)
            ..hideCurrentSnackBar()
            ..showSnackBar(
              SnackBar(content: Text("Kamu telah menekan tombol ${item.name}!"))
            );
        },
        // Container untuk menyimpan Icon dan Text
        child: Container(
          padding: const EdgeInsets.all(8),
          child: Center(
            child: Column(
              // Menyusun ikon dan teks di tengah kartu.
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
```
blok kode dibawah akan menyesuaikan item mana yang ditekan pengguna
```bash
..showSnackBar(
              SnackBar(content: Text("Kamu telah menekan tombol ${item.name}!"))
            );
```

## Tugas 8
- [Contents](#contents)<br>

**1. Apa kegunaan const di Flutter? Jelaskan apa keuntungan ketika menggunakan const pada kode Flutter. Kapan sebaiknya kita menggunakan const, dan kapan sebaiknya tidak digunakan?**<br>
Di Flutter, keyword `const` digunakan untuk membuat objek yang immutable atau tidak dapat diubah setelah diinisialisasi. `const` digunakan untuk mendeklarasikan objek yang bersifat konstan, artinya nilai objek tersebut sudah diketahui pada saat compile-time dan tidak akan berubah selama masa hidup aplikasi. Contohnya adalah `Text`, `Container`, atau objek lain yang isinya tidak akan diubah.

Keuntungan Menggunakan `const` di Flutter
- Optimalisasi Kinerja: Objek yang dideklarasikan sebagai `const` hanya akan dibuat sekali dalam memori dan akan digunakan ulang jika diperlukan di tempat lain sehingga objek tidak perlu dibuat ulang setiap kali widget dibangun kembali.

- Stabilitas Aplikasi: `const` memastikan bahwa nilai objek tidak akan berubah, yang mengurangi kemungkinan bug.

- Hot Reload yang Lebih Baik: Karena Flutter mendukung hot reload, penggunaan `const` memungkinkan sistem untuk mengidentifikasi bahwa objek tidak berubah, sehingga tidak perlu dibangun ulang saat hot reload.

Kapan Sebaiknya Menggunakan `const`
- Widget statis
- Nilai Tetap
- Dalam List atau Collection, seperti dalam `listview` atau `column`

Kapan Sebaiknya Tidak Menggunakan `const`
- Widget dinamis
- Nilai yang bergantung pada fungsi atau variabel

**2. Jelaskan dan bandingkan penggunaan Column dan Row pada Flutter. Berikan contoh implementasi dari masing-masing layout widget ini!**<br>
Di Flutter, `Column` dan `Row` adalah widget layout yang digunakan untuk menyusun widget lainnya dalam bentuk vertikal dan horizontal.

Column
- Definisi: Widget layout yang menyusun child secara vertikal (dari atas ke bawah).
- Use case: Ingin membuat tampilan bertumpuk ke bawah, seperti daftar item, dll
- Implementasi kode:
```bash
Column(
  mainAxisAlignment: MainAxisAlignment.center,
  crossAxisAlignment: CrossAxisAlignment.start,
  children: [
    Text("Item 1"),
    Text("Item 2"),
    Text("Item 3"),
  ],
);
```

Row
- Definisi: Widget layout yang menyusun child secara horizontal (dari kanan ke kiri).
- Use case: Membuat tampilan sejajar secara mendatar, seperti tombol-tombol yang disejajarkan secara horizontal atau item dalam satu baris.
- Implementasi kode:
```bash
Row(
  mainAxisAlignment: MainAxisAlignment.spaceAround,
  crossAxisAlignment: CrossAxisAlignment.center,
  children: [
    Icon(Icons.home),
    Icon(Icons.favorite),
    Icon(Icons.settings),
  ],
);
```
mainAxisAlignment: Mengatur sepanjang sumbu utama (column y, row x)<br>
crossAxixAlignment: Mengatur sepanjang sumbu sekunder (column x, row y)

**3. Sebutkan apa saja elemen input yang kamu gunakan pada halaman form yang kamu buat pada tugas kali ini. Apakah terdapat elemen input Flutter lain yang tidak kamu gunakan pada tugas ini? Jelaskan!**<br>

Elemen Input yang Digunakan<br>

- TextFormField<br>
Fungsi: Digunakan untuk menerima input teks dari pengguna, seperti nama produk dan ulasan.<br>
Implementasi: Terdapat beberapa TextFormField pada halaman form untuk input produk, review, dan kuantitas produk.Setiap TextFormField menggunakan validator untuk memastikan input tidak kosong dan sesuai dengan format yang diinginkan (contohnya, memastikan Product Quantity adalah angka).<br>

- ElevatedButton<br>
Fungsi: Digunakan sebagai tombol untuk menyimpan atau mengirim data yang sudah diisi di form.<br>
Implementasi: Digunakan sebagai tombol "Save" di bagian bawah form untuk menyimpan input pengguna. Ketika tombol ini ditekan, aplikasi memvalidasi data dan menampilkan dialog konfirmasi jika input valid.<br>

Elemen Input Flutter Lain yang Tidak Digunakan<br>

- Radio<br>
Fungsi: Radio button digunakan untuk memilih satu opsi dari beberapa pilihan yang ada. Ini cocok untuk pilihan eksklusif, misalnya memilih jenis kategori produk (misalnya makanan, minuman, atau elektronik).
Alasan: Pada form ini tidak ada kebutuhan untuk memilih salah satu opsi dari beberapa pilihan.

- Checkbox<br>
Fungsi: Checkbox digunakan untuk memilih atau mengaktifkan beberapa opsi (ya/tidak). Biasanya dipakai ketika ada pengaturan tambahan atau opsi boolean, misalnya pilihan "Tersedia untuk diskon".<br>
Alasan: Form ini tidak memerlukan input dengan pilihan ya/tidak atau pilihan boolean.<br>

- Switch<br>
Fungsi: Mirip dengan checkbox, tetapi digunakan dalam bentuk saklar untuk mengatur pengaturan on/off, seperti mengaktifkan atau menonaktifkan suatu fitur.<br>
Alasan: Tidak ada fitur atau pengaturan dalam form ini yang membutuhkan on/off toggle.

- DatePicker<br>
Fungsi: DatePicker digunakan untuk memilih tanggal tertentu, misalnya tanggal produksi atau tanggal kadaluarsa.<br>
Alasan: Form ini tidak memerlukan input tanggal dari pengguna.

- Slider<br>
Fungsi: Slider digunakan untuk memilih nilai dalam rentang tertentu, misalnya untuk menetapkan harga atau kuantitas dalam rentang tertentu.<br>
Alasan: Input kuantitas dalam form ini diisi dengan TextFormField, bukan rentang yang memerlukan slider.

- DropdownButton<br>
Fungsi: DropdownButton memungkinkan pengguna untuk memilih satu opsi dari daftar opsi yang dapat dipilih, misalnya memilih kategori produk.<br>
Alasan: Semua input diisi secara langsung oleh pengguna melalui teks, sehingga dropdown tidak diperlukan.

**4. Bagaimana cara kamu mengatur tema (theme) dalam aplikasi Flutter agar aplikasi yang dibuat konsisten? Apakah kamu mengimplementasikan tema pada aplikasi yang kamu buat?**<br>
Flutter memungkinkan kita untuk mengatur tema aplikasi melalui `ThemeData` yang diterapkan pada `MaterialApp`.

Saya mengimplementasikan tema pada aplikasi dengan mengatur warna utama (primary) dan warna sekunder (secondary) dalam `ThemeData`.

- Warna Utama (Primary Color):<br>
Saya menggunakan `primarySwatch` dengan warna `Colors.deepPurple`. Warna ini diterapkan pada elemen yang menggunakan `Theme.of(context).colorScheme.primary`.

- Warna Sekunder (Secondary Color):
`Secondary` pada `colorScheme` diatur ke `Colors.deepPurple[400]`. Warna sekunder ini dapat digunakan untuk elemen lain yang tidak utama.

- Material Design 3 (MD3):
Saya menggunakan MD3 dengan mengset `useMaterial3: true`

Berikut adalah kode saya dimana komponennya mengimplementasikan tema pada aplikasi.<br>
4.1 AppBar (`lib/screens/menu.dart`)
```bash
appBar: AppBar(
  title: const Text(
    'Click and Cart',
    style: TextStyle(
      color: Colors.white,
      fontWeight: FontWeight.bold,
    ),
  ),
  backgroundColor: Theme.of(context).colorScheme.primary,
  iconTheme: const IconThemeData(color: Colors.white),
),
```

4.2 ElevatedButton (`lib/screens/productentry_form.dart`)
```bash
ElevatedButton(
  style: ButtonStyle(
    backgroundColor: MaterialStateProperty.all(
        Theme.of(context).colorScheme.primary),
  ),
  onPressed: () {
    // Logic untuk tombol Save
  },
  child: const Text(
    "Save",
    style: TextStyle(color: Colors.white),
  ),
),
```

4.3 Drawer (`lib/widgets/left_drawer.dart`)
```bash
DrawerHeader(
  decoration: BoxDecoration(
    color: Theme.of(context).colorScheme.primary,
  ),
  child: const Column(
    children: [
      Text(
        'Click and Cart',
        textAlign: TextAlign.center,
        style: TextStyle(
          fontSize: 24,
          fontWeight: FontWeight.bold,
          color: Colors.white,
        ),
      ),
      Padding(padding: EdgeInsets.all(8)),
      Text(
        "Ayo beli kebutuhan mu setiap hari disini!",
        textAlign: TextAlign.center,
        style: TextStyle(
          fontSize: 15,
          color: Colors.white,
          fontWeight: FontWeight.normal,
        ),
      ),
    ],
  ),
),
```

**5. Bagaimana cara kamu menangani navigasi dalam aplikasi dengan banyak halaman pada Flutter?**<br>
Saya menangani navigasi dalam aplikasi Flutter dengan menggunakan Navigator dan MaterialPageRoute untuk berpindah antar halaman.<br>

Penjelasan:<br>
Navigasi dalam Flutter biasanya ditangani dengan Navigator, yang memungkinkan aplikasi berpindah antar halaman (disebut sebagai "route"). Navigator menggunakan stack-based navigation, dimana setiap berpindah ke halaman baru, halaman tersebut ditambahkan ke atas stack, dan ketika kembali, halaman tersebut dihapus dari stack.

Implementasi:<br>
5.1 Navigasi dengan `Navigator.push`<br>
`Navigator.push` digunakan untuk berpindah ke halaman baru dan menambahkannya ke stack, sehingga pengguna bisa menekan tombol "back" untuk kembali ke halaman sebelumnya.<br>
Dalam aplikasi saya, `Navigator.push` digunakan saat berpindah dari halaman `MyHomePage` ke halaman `ProductEntryFormPage`.

Contoh pada file `lib/widgets/product_card.dart`:
```bash
if (item.name == "Tambah Produk") {
  Navigator.push(
    context,
    MaterialPageRoute(builder: (context) => const ProductEntryFormPage()),
  );
}
```
Saat pengguna menekan tombol "Tambah Produk" pada kartu, aplikasi akan menggunakan `Navigator.push` untuk membuka halaman `ProductEntryFormPage`.

5.2 Navigasi dengan `Navigator.pushReplacement`<br>
`Navigator.pushReplacement` digunakan untuk menggantikan halaman saat ini dengan halaman baru, sehingga halaman sebelumnya dihapus dari stack.<br>
Digunakan dalam aplikasi saat membuka halaman utama (`MyHomePage`) dari drawer. Metode ini cocok untuk skenario di mana Anda tidak ingin pengguna kembali ke halaman sebelumnya dengan tombol "back".

Contoh pada file `lib/widgets/left_drawer.dart`:
```bash
onTap: () {
  Navigator.pushReplacement(
    context,
    MaterialPageRoute(
      builder: (context) => MyHomePage(),
    ),
  );
},
```
Ketika pengguna memilih opsi "Halaman Utama" dari drawer, aplikasi akan menggunakan `Navigator.pushReplacement` untuk membuka halaman utama (`MyHomePage`), menggantikan halaman sebelumnya di stack.


## Tugas 9
- [Contents](#contents)<br>

**1. Jelaskan mengapa kita perlu membuat model untuk melakukan pengambilan ataupun pengiriman data JSON? Apakah akan terjadi error jika kita tidak membuat model terlebih dahulu?**<br>

Mengapa Membuat Model?

- Struktur Data yang Konsisten: Model memastikan data JSON memiliki format yang sesuai dengan database. Misalnya, tipe data seperti CharField untuk teks atau IntegerField untuk angka akan secara otomatis divalidasi.

- Validasi Otomatis: Dengan model, Django memvalidasi data sebelum menyimpannya ke database. Ini membantu menghindari kesalahan seperti memasukkan teks ke kolom angka atau data kosong pada field yang wajib diisi.

- Konversi ke/Dari JSON: Model mempermudah konversi data ke format JSON dengan serializer bawaan Django. Data dari database dapat langsung diubah menjadi JSON tanpa menulis kode tambahan.

- Integrasi dengan Database: Model berfungsi sebagai representasi tabel di database, sehingga mempermudah pengelolaan data (CRUD) tanpa menulis query SQL secara manual.

- Keamanan: Model melindungi aplikasi dari data tidak valid dan serangan seperti SQL Injection. Django memastikan data yang masuk sesuai dengan field yang didefinisikan.

Apa yang Terjadi Jika Tidak Membuat Model?

- Data Tidak Terstruktur: Data JSON harus diolah dan divalidasi secara manual, yang rawan kesalahan dan inkonsistensi.

- Validasi Manual: Anda perlu memeriksa data satu per satu sebelum menyimpannya ke database, yang meningkatkan kompleksitas kode.

- Kesulitan Manajemen Database: Tanpa model, Anda harus menulis query SQL secara manual, yang lebih lambat, rentan error, dan sulit dipelihara.

- Risiko Keamanan: Tidak ada validasi otomatis, sehingga data tidak valid atau serangan seperti SQL Injection bisa menyebabkan error atau kerentanan.

Kesimpulannya, model penting untuk menjaga struktur, validasi, dan keamanan data dalam aplikasi Django.

**2. Jelaskan fungsi dari library http yang sudah kamu implementasikan pada tugas ini**<br>
Library http yang diimplementasikan pada tugas ini digunakan untuk mengirimkan permintaan HTTP dari aplikasi Flutter ke backend (misalnya, Django) dan menerima respons. Fungsi utamanya antara lain:

- Mengirim Data ke Server:<br>
Library http memungkinkan pengiriman data (misalnya, JSON) dari Flutter ke backend menggunakan metode seperti POST atau PUT.
Contoh: Mengirim data produk yang dimasukkan pengguna ke endpoint Django menggunakan http.post().

- Mengambil Data dari Server:<br>
http digunakan untuk mengambil data dari server melalui metode seperti GET.
Contoh: Mengambil daftar produk dari endpoint Django yang menyediakan data dalam format JSON.

- Menghubungkan Frontend dan Backend:<br>
Library ini menghubungkan aplikasi Flutter (frontend) dengan server Django (backend), memungkinkan komunikasi dua arah.

- Pemrosesan Respons:<br>
Library ini mengembalikan respons dari server yang dapat diolah di Flutter, seperti memeriksa status (200 OK untuk sukses) atau menampilkan pesan error (400 Bad Request).

**3. Jelaskan fungsi dari CookieRequest dan jelaskan mengapa instance CookieRequest perlu untuk dibagikan ke semua komponen di aplikasi Flutter.**<br>

Fungsi dari CookieRequest:

- Menyimpan dan Mengelola Cookie:<br>
CookieRequest digunakan untuk menyimpan cookie yang diterima dari server, seperti token autentikasi atau informasi sesi. Cookie ini akan digunakan pada setiap permintaan HTTP berikutnya untuk menjaga sesi pengguna tetap aktif.

- Mengotentikasi Pengguna:<br>
CookieRequest memungkinkan pengiriman cookie bersama dengan permintaan HTTP, yang berguna untuk endpoint yang membutuhkan autentikasi, seperti mengambil data pribadi pengguna atau mengakses resource yang dilindungi.

- Mempermudah Komunikasi dengan Backend:<br>
Dengan CookieRequest, Anda tidak perlu menambahkan cookie secara manual pada setiap permintaan HTTP. Library ini secara otomatis menyisipkan cookie yang tersimpan saat mengirim permintaan ke server.

- Pengelolaan Sesi Pengguna:<br>
Setelah login berhasil, cookie sesi pengguna disimpan oleh CookieRequest. Selama sesi tersebut valid, pengguna dapat mengakses fitur-fitur yang memerlukan autentikasi tanpa harus login ulang.

Mengapa Instance CookieRequest Perlu Dibagikan ke Semua Komponen di Aplikasi?

- Menjaga Konsistensi Sesi:<br>
Dengan membagikan instance CookieRequest ke seluruh aplikasi, semua komponen dapat menggunakan cookie yang sama untuk mengakses server. Ini memastikan sesi pengguna tetap konsisten di seluruh halaman.

- Kemudahan Akses:<br>
Komponen seperti halaman login, daftar produk, atau halaman checkout mungkin memerlukan autentikasi yang sama. Dengan membagikan instance, semua komponen dapat mengakses CookieRequest tanpa perlu membuat ulang atau mengelola cookie secara terpisah.

- Efisiensi:<br>
Instance yang dibagikan mengurangi duplikasi dan overhead dalam mengelola cookie. Semua komponen cukup menggunakan instance yang sama untuk memanfaatkan cookie yang telah ada.

- Menghindari Error pada Autentikasi:<br>
Jika setiap komponen menggunakan instance CookieRequest yang berbeda, cookie tidak akan sinkron, sehingga dapat menyebabkan error autentikasi atau kehilangan data sesi.

**4. Jelaskan mekanisme pengiriman data mulai dari input hingga dapat ditampilkan pada Flutter.**<br>
Mekanisme pengiriman data dimulai dari input pengguna melalui formulir di Flutter. Pengguna mengisi data pada form yang divalidasi secara lokal di Flutter, seperti memastikan bahwa data tidak kosong atau sesuai format tertentu (misalnya angka untuk harga). Setelah validasi berhasil, data dikirim ke server menggunakan metode HTTP (seperti POST) melalui library seperti CookieRequest.

Di server, data yang diterima diproses oleh backend, misalnya Django, yang membaca data JSON dari request. Data ini kemudian disimpan ke database menggunakan model yang telah didefinisikan. Setelah data berhasil diproses, server mengirimkan respons ke Flutter, biasanya dalam bentuk status keberhasilan (seperti {"status": "success"}) atau data yang diperbarui.

Di Flutter, jika data dari server diperlukan, aplikasi mengambil data kembali menggunakan metode HTTP (seperti GET). Data yang diterima dari server dalam format JSON diubah menjadi objek model Dart, sehingga sesuai dengan struktur data di aplikasi. Terakhir, data tersebut ditampilkan ke interface aplikasi menggunakan widget Flutter, seperti ListView atau GridView, sehingga pengguna dapat melihat hasilnya.

**5. Jelaskan mekanisme autentikasi dari login, register, hingga logout. Mulai dari input data akun pada Flutter ke Django hingga selesainya proses autentikasi oleh Django dan tampilnya menu pada Flutter.**<br>

Mekanisme autentikasi dimulai saat pengguna memasukkan data login atau register melalui formulir di Flutter. Data yang diinputkan pengguna, seperti username dan password, divalidasi terlebih dahulu di sisi Flutter untuk memastikan formatnya benar. Setelah validasi, data dikirim ke server Django melalui permintaan HTTP POST menggunakan CookieRequest.

Pada Django, server memproses permintaan:

- Untuk login:<br>
Django memeriksa apakah kredensial pengguna cocok dengan data di database. Jika cocok, Django menginisialisasi sesi pengguna dan mengirimkan cookie autentikasi yang disimpan di Flutter.
Untuk register: Django memvalidasi data akun baru, membuat akun di database, dan mengirimkan respons keberhasilan atau kesalahan.

- Setelah respons diterima oleh Flutter:<br>
Jika login berhasil, cookie atau token autentikasi disimpan oleh CookieRequest, yang akan digunakan untuk mengidentifikasi pengguna di sesi berikutnya.
Data tambahan, seperti profil pengguna atau preferensi, dapat diambil dari server menggunakan token autentikasi untuk menampilkan menu utama.

- Saat logout:<br>
Flutter mengirim permintaan HTTP POST ke Django untuk menghapus sesi pengguna.
Django menghapus cookie autentikasi dan mengakhiri sesi pengguna.
Flutter menghapus cookie dari CookieRequest dan kembali ke halaman login.
Hasil Akhir: Setelah login berhasil, menu utama ditampilkan di Flutter dengan data pengguna yang relevan diambil dari server. Token atau cookie memastikan setiap permintaan berikutnya tetap terautentikasi selama sesi aktif.

**6. Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas secara step-by-step! (bukan hanya sekadar mengikuti tutorial).**<br>

6.1 Registrasi pada flutter<br>
pada `lib/screens/register.dart`
```bash
import 'dart:convert';
import 'package:flutter/material.dart';
import 'package:click_and_cart/screens/login.dart';
import 'package:pbp_django_auth/pbp_django_auth.dart';
import 'package:provider/provider.dart';

class RegisterPage extends StatefulWidget {
  const RegisterPage({super.key});

  @override
  State<RegisterPage> createState() => _RegisterPageState();
}

class _RegisterPageState extends State<RegisterPage> {
  final _usernameController = TextEditingController();
  final _passwordController = TextEditingController();
  final _confirmPasswordController = TextEditingController();

  @override
  Widget build(BuildContext context) {
    final request = context.watch<CookieRequest>();
    return Scaffold(
      appBar: AppBar(
        title: const Text('Register'),
        leading: IconButton(
          icon: const Icon(Icons.arrow_back),
          onPressed: () {
            Navigator.pop(context);
          },
        ),
      ),
      body: Center(
        child: SingleChildScrollView(
          padding: const EdgeInsets.all(16.0),
          child: Card(
            elevation: 8,
            shape: RoundedRectangleBorder(
              borderRadius: BorderRadius.circular(12.0),
            ),
            child: Padding(
              padding: const EdgeInsets.all(20.0),
              child: Column(
                mainAxisSize: MainAxisSize.min,
                children: <Widget>[
                  const Text(
                    'Register',
                    style: TextStyle(
                      fontSize: 24.0,
                      fontWeight: FontWeight.bold,
                    ),
                  ),
                  const SizedBox(height: 30.0),
                  TextFormField(
                    controller: _usernameController,
                    decoration: const InputDecoration(
                      labelText: 'Username',
                      hintText: 'Enter your username',
                      border: OutlineInputBorder(
                        borderRadius: BorderRadius.all(Radius.circular(12.0)),
                      ),
                      contentPadding:
                          EdgeInsets.symmetric(horizontal: 12.0, vertical: 8.0),
                    ),
                    validator: (value) {
                      if (value == null || value.isEmpty) {
                        return 'Please enter your username';
                      }
                      return null;
                    },
                  ),
                  const SizedBox(height: 12.0),
                  TextFormField(
                    controller: _passwordController,
                    decoration: const InputDecoration(
                      labelText: 'Password',
                      hintText: 'Enter your password',
                      border: OutlineInputBorder(
                        borderRadius: BorderRadius.all(Radius.circular(12.0)),
                      ),
                      contentPadding:
                          EdgeInsets.symmetric(horizontal: 12.0, vertical: 8.0),
                    ),
                    obscureText: true,
                    validator: (value) {
                      if (value == null || value.isEmpty) {
                        return 'Please enter your password';
                      }
                      return null;
                    },
                  ),
                  const SizedBox(height: 12.0),
                  TextFormField(
                    controller: _confirmPasswordController,
                    decoration: const InputDecoration(
                      labelText: 'Confirm Password',
                      hintText: 'Confirm your password',
                      border: OutlineInputBorder(
                        borderRadius: BorderRadius.all(Radius.circular(12.0)),
                      ),
                      contentPadding:
                          EdgeInsets.symmetric(horizontal: 12.0, vertical: 8.0),
                    ),
                    obscureText: true,
                    validator: (value) {
                      if (value == null || value.isEmpty) {
                        return 'Please confirm your password';
                      }
                      return null;
                    },
                  ),
                  const SizedBox(height: 24.0),
                  ElevatedButton(
                    onPressed: () async {
                      String username = _usernameController.text;
                      String password1 = _passwordController.text;
                      String password2 = _confirmPasswordController.text;

                      // Cek kredensial
                      // TODO: Ganti URL dan jangan lupa tambahkan trailing slash (/) di akhir URL!
                      // Untuk menyambungkan Android emulator dengan Django pada localhost,
                      // gunakan URL http://10.0.2.2/
                      final response = await request.postJson(
                          "http://127.0.0.1:8000/auth/register/",
                          jsonEncode({
                            "username": username,
                            "password1": password1,
                            "password2": password2,
                          }));
                      if (context.mounted) {
                        if (response['status'] == 'success') {
                          ScaffoldMessenger.of(context).showSnackBar(
                            const SnackBar(
                              content: Text('Successfully registered!'),
                            ),
                          );
                          Navigator.pushReplacement(
                            context,
                            MaterialPageRoute(
                                builder: (context) => const LoginPage()),
                          );
                        } else {
                          ScaffoldMessenger.of(context).showSnackBar(
                            const SnackBar(
                              content: Text('Failed to register!'),
                            ),
                          );
                        }
                      }
                    },
                    style: ElevatedButton.styleFrom(
                      foregroundColor: Colors.white,
                      minimumSize: Size(double.infinity, 50),
                      backgroundColor: Theme.of(context).colorScheme.primary,
                      padding: const EdgeInsets.symmetric(vertical: 16.0),
                    ),
                    child: const Text('Register'),
                  ),
                ],
              ),
            ),
          ),
        ),
      ),
    );
  }
}
```

6.2 Login pada flutter <br>
pada `lib/screens/login.dart`

```bash
import 'package:click_and_cart/screens/menu.dart';
import 'package:flutter/material.dart';
import 'package:pbp_django_auth/pbp_django_auth.dart';
import 'package:provider/provider.dart';
import 'package:click_and_cart/screens/register.dart';

void main() {
  runApp(const LoginApp());
}

class LoginApp extends StatelessWidget {
  const LoginApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Login',
      theme: ThemeData(
        useMaterial3: true,
        colorScheme: ColorScheme.fromSwatch(
          primarySwatch: Colors.deepPurple,
        ).copyWith(secondary: Colors.deepPurple[400]),
      ),
      home: const LoginPage(),
    );
  }
}

class LoginPage extends StatefulWidget {
  const LoginPage({super.key});

  @override
  State<LoginPage> createState() => _LoginPageState();
}

class _LoginPageState extends State<LoginPage> {
  final TextEditingController _usernameController = TextEditingController();
  final TextEditingController _passwordController = TextEditingController();

  @override
  Widget build(BuildContext context) {
    final request = context.watch<CookieRequest>();

    return Scaffold(
      appBar: AppBar(
        title: const Text('Login'),
      ),
      body: Center(
        child: SingleChildScrollView(
          padding: const EdgeInsets.all(16.0),
          child: Card(
            elevation: 8,
            shape: RoundedRectangleBorder(
              borderRadius: BorderRadius.circular(12.0),
            ),
            child: Padding(
              padding: const EdgeInsets.all(20.0),
              child: Column(
                mainAxisSize: MainAxisSize.min,
                children: [
                  const Text(
                    'Login',
                    style: TextStyle(
                      fontSize: 24.0,
                      fontWeight: FontWeight.bold,
                    ),
                  ),
                  const SizedBox(height: 30.0),
                  TextField(
                    controller: _usernameController,
                    decoration: const InputDecoration(
                      labelText: 'Username',
                      hintText: 'Enter your username',
                      border: OutlineInputBorder(
                        borderRadius: BorderRadius.all(Radius.circular(12.0)),
                      ),
                      contentPadding:
                          EdgeInsets.symmetric(horizontal: 12.0, vertical: 8.0),
                    ),
                  ),
                  const SizedBox(height: 12.0),
                  TextField(
                    controller: _passwordController,
                    decoration: const InputDecoration(
                      labelText: 'Password',
                      hintText: 'Enter your password',
                      border: OutlineInputBorder(
                        borderRadius: BorderRadius.all(Radius.circular(12.0)),
                      ),
                      contentPadding:
                          EdgeInsets.symmetric(horizontal: 12.0, vertical: 8.0),
                    ),
                    obscureText: true,
                  ),
                  const SizedBox(height: 24.0),
                  ElevatedButton(
                    onPressed: () async {
                      String username = _usernameController.text;
                      String password = _passwordController.text;

                      // Cek kredensial
                      // Untuk menyambungkan Android emulator dengan Django pada localhost,
                      // gunakan URL http://10.0.2.2/
                      final response = await request
                          .login("http://127.0.0.1:8000/auth/login/", {
                        'username': username,
                        'password': password,
                      });

                      if (request.loggedIn) {
                        String message = response['message'];
                        String uname = response['username'];
                        if (context.mounted) {
                          Navigator.pushReplacement(
                            context,
                            MaterialPageRoute(
                                builder: (context) => MyHomePage()),
                          );
                          ScaffoldMessenger.of(context)
                            ..hideCurrentSnackBar()
                            ..showSnackBar(
                              SnackBar(
                                  content:
                                      Text("$message Selamat datang, $uname.")),
                            );
                        }
                      } else {
                        if (context.mounted) {
                          showDialog(
                            context: context,
                            builder: (context) => AlertDialog(
                              title: const Text('Login Gagal'),
                              content: Text(response['message']),
                              actions: [
                                TextButton(
                                  child: const Text('OK'),
                                  onPressed: () {
                                    Navigator.pop(context);
                                  },
                                ),
                              ],
                            ),
                          );
                        }
                      }
                    },
                    style: ElevatedButton.styleFrom(
                      foregroundColor: Colors.white,
                      minimumSize: Size(double.infinity, 50),
                      backgroundColor: Theme.of(context).colorScheme.primary,
                      padding: const EdgeInsets.symmetric(vertical: 16.0),
                    ),
                    child: const Text('Login'),
                  ),
                  const SizedBox(height: 36.0),
                  GestureDetector(
                    onTap: () {
                      Navigator.push(
                        context,
                        MaterialPageRoute(
                            builder: (context) => const RegisterPage()),
                      );
                    },
                    child: Text(
                      'Don\'t have an account? Register',
                      style: TextStyle(
                        color: Theme.of(context).colorScheme.primary,
                        fontSize: 16.0,
                      ),
                    ),
                  ),
                ],
              ),
            ),
          ),
        ),
      ),
    );
  }
}
```

6.3 Mengintegrasikan Sistem Autentikasi Django dengan Flutter<br>
Integrasi autentikasi Django dengan Flutter dilakukan dengan:

- Menyiapkan endpoint autentikasi di Django (login, logout, register).
- Mengonfigurasi CORS di Django untuk mengizinkan komunikasi antara Flutter dan backend.
- Menggunakan package pbp_django_auth untuk mengelola autentikasi di Flutter.
- Menyimpan token autentikasi di CookieRequest untuk digunakan dalam sesi aktif.
- Menavigasi pengguna ke halaman utama setelah login berhasil.

6.4 Membuat model custom
- Buat data dan ambil menggunakan JSON, masukkan ke website `quicktype`. Copy text dari quicktype untuk diintegrasikan ke flutter.

Buat `lib/models/product_entry.dart` sebagai referensi model
```bash
// To parse this JSON data, do
//
//     final productEntry = productEntryFromJson(jsonString);

import 'dart:convert';

List<ProductEntry> productEntryFromJson(String str) => List<ProductEntry>.from(json.decode(str).map((x) => ProductEntry.fromJson(x)));

String productEntryToJson(List<ProductEntry> data) => json.encode(List<dynamic>.from(data.map((x) => x.toJson())));

class ProductEntry {
    String model;
    String pk;
    Fields fields;

    ProductEntry({
        required this.model,
        required this.pk,
        required this.fields,
    });

    factory ProductEntry.fromJson(Map<String, dynamic> json) => ProductEntry(
        model: json["model"],
        pk: json["pk"],
        fields: Fields.fromJson(json["fields"]),
    );

    Map<String, dynamic> toJson() => {
        "model": model,
        "pk": pk,
        "fields": fields.toJson(),
    };
}

class Fields {
    int user;
    String name;
    int price;
    String description;
    int quantity;

    Fields({
        required this.user,
        required this.name,
        required this.price,
        required this.description,
        required this.quantity,
    });

    factory Fields.fromJson(Map<String, dynamic> json) => Fields(
        user: json["user"],
        name: json["name"],
        price: json["price"],
        description: json["description"],
        quantity: json["quantity"],
    );

    Map<String, dynamic> toJson() => {
        "user": user,
        "name": name,
        "price": price,
        "description": description,
        "quantity": quantity,
    };
}
```

6.5 Menampilkan daftar produk
Pada `lib/screens` buat file `list_productentry.dart` dengan isi berikut
```bash

import 'package:flutter/material.dart';
import 'package:click_and_cart/models/product_entry.dart';
import 'package:click_and_cart/widgets/left_drawer.dart';
import 'package:pbp_django_auth/pbp_django_auth.dart';
import 'package:provider/provider.dart';

class ProductEntryPage extends StatefulWidget {
  const ProductEntryPage({super.key});

  @override
  State<ProductEntryPage> createState() => _ProductEntryPageState();
}

class _ProductEntryPageState extends State<ProductEntryPage> {
  Future<List<ProductEntry>> fetchMood(CookieRequest request) async {
    // TODO: Ganti URL dan jangan lupa tambahkan trailing slash (/) di akhir URL!
    final response = await request.get('http://127.0.0.1:8000/json/');
    
    // Melakukan decode response menjadi bentuk json
    var data = response;
    
    // Melakukan konversi data json menjadi object ProductEntry
    List<ProductEntry> listMood = [];
    for (var d in data) {
      if (d != null) {
        listMood.add(ProductEntry.fromJson(d));
      }
    }
    return listMood;
  }

  @override
  Widget build(BuildContext context) {
    final request = context.watch<CookieRequest>();
    return Scaffold(
      appBar: AppBar(
        title: const Text('Product List'),
      ),
      drawer: const LeftDrawer(),
      body: FutureBuilder(
        future: fetchMood(request),
        builder: (context, AsyncSnapshot snapshot) {
          if (snapshot.data == null) {
            return const Center(child: CircularProgressIndicator());
          } else {
            if (!snapshot.hasData) {
              return const Column(
                children: [
                  Text(
                    'Belum ada data product pada malaccan mobile.',
                    style: TextStyle(fontSize: 20, color: Color(0xff59A5D8)),
                  ),
                  SizedBox(height: 8),
                ],
              );
            } else {
              return ListView.builder(
                itemCount: snapshot.data!.length,
                itemBuilder: (_, index) => Container(
                  margin:
                      const EdgeInsets.symmetric(horizontal: 16, vertical: 12),
                  padding: const EdgeInsets.all(20.0),
                  child: Column(
                    mainAxisAlignment: MainAxisAlignment.start,
                    crossAxisAlignment: CrossAxisAlignment.start,
                    children: [
                      Text(
                        "${snapshot.data![index].fields.name}",
                        style: const TextStyle(
                          fontSize: 18.0,
                          fontWeight: FontWeight.bold,
                        ),
                      ),
                      const SizedBox(height: 10),
                      Text("${snapshot.data![index].fields.quantity}"),
                      const SizedBox(height: 10),
                      Text("${snapshot.data![index].fields.price}"),
                      const SizedBox(height: 10),
                      Text("${snapshot.data![index].fields.description}")
                    ],
                  ),
                ),
              );
            }
          }
        },
      ),
    );
  }
}
```