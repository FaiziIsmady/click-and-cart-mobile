# click-and-cart: All your needs in one click

# Contents
- [Data Diri](#data-diri)<br>
- [Tugas 7](#tugas-7)<br>

## Data Diri
**Nama : Muhammad Faizi Ismady Supardjo**<br>
**NPM : 2306244955**<br>
**Kelas : PBP C**<br>


## Tugas 7
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