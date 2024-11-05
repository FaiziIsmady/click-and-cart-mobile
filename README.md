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
