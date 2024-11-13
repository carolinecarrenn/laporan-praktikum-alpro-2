<h2 align="center"><strong>LAPORAN PRAKTIKUM</strong></h2>
<h2 align="center"><strong>ALGORITMA DAN PEMROGRAMAN 2</strong></h2>

<br>

<h2 align="center"><strong>MODUL VII</strong></h2>
<h2 align="center"><strong> STRUCK & ARRAY </strong></h2> 

<br>

<p align="center">
  
  <img src="https://github.com/user-attachments/assets/741cb565-774a-4298-b1fb-22ebf35822f1" alt="Logo" width="200"/>

</p>

<br>

<p align="center">
  <strong>Disusun Oleh:</strong><br>
  Caroline Carren A.R / 2311102174<br>
  S1 IF 11 05
</p>

<br>

<p align="center">
  <strong>Dosen Pengampu:</strong><br>
  Arif Amrulloh,S.Kom.,M.Kom.
</p>

<br>

<p align="center">
  <strong>PROGRAM STUDI S1 TEKNIK INFORMATIKA</strong><br>
  <strong>FAKULTAS INFORMATIKA</strong><br>
  <strong>TELKOM UNIVERSITY PURWOKERTO</strong><br>
  <strong>2024</strong>
</p>

------

## Daftar Isi
1. [Tujuan Praktikum](#tujuan-praktikum)
2. [Dasar Teori](#dasar-teori)
3. [Guided](#guided)
4. [Unguided](#unguided)
5. [Kesimpulan](#kesimpulan)
6. [Daftar Pustaka](#daftar-pustaka)

## Tujuan Praktikum
1. Mahasiswa mampu memahami konsep dasar struct dan array dalam bahasa pemrograman Go.
2. Mahasiswa mampu mendeklarasikan dan menginisialisasi array serta struct untuk menyimpan data yang kompleks.
3. Mahasiswa mampu mengimplementasikan penggunaan array dan struct untuk menyusun dan mengelola data dalam program Go.

## Dasar Teori

### Array

Array adalah tipe data dasar yang digunakan untuk menyimpan sekumpulan elemen dengan tipe data yang sama. Di bahasa Go, array memiliki ukuran tetap yang ditentukan saat deklarasi.

**Karakteristik Array:**

1. Ukuran Tetap:

   Ukuran array di Go ditentukan saat deklarasi dan tidak dapat diubah selama runtime. Ini membuat array kurang fleksibel dibandingkan tipe data lain seperti slice.

2. Tipe Data Homogen:

   Semua elemen dalam array harus memiliki tipe data yang sama, seperti int, string, atau float64.

3. Indeks Dimulai dari Nol:

   Elemen pertama array berada pada indeks 0, elemen kedua di indeks 1, dan seterusnya.

4. Pengaksesan Elemen:

   Elemen dalam array diakses menggunakan indeks dengan notasi array[index].

**Deklarasi Array:**

Array dapat dideklarasikan dengan menentukan ukuran dan tipe datanya. Ada beberapa cara untuk mendeklarasikan dan menginisialisasi array di Go.

- Deklarasi Array Kosong:

```go
var numbers [5]int // array of 5 integers, initialized to zero values
```

- Inisialisasi Array dengan Nilai:

```go
var primes = [5]int{2, 3, 5, 7, 11} // array dengan panjang 5 dan nilai yang ditentukan
```

- Deklarasi Array dengan Panjang Otomatis:

Go juga memungkinkan kita untuk menentukan array tanpa panjang yang tetap dengan menggunakan [...], yang akan menyesuaikan panjang array sesuai dengan jumlah elemen yang diinisialisasi.

```go
primes := [...]int{2, 3, 5, 7, 11} // array panjang otomatis sesuai jumlah elemen
```

- Penggunaan Array:

Array dapat diakses dan dimodifikasi dengan mengacu pada indeksnya. 

```go
var numbers = [3]int{1, 2, 3}
fmt.Println(numbers[0]) // Output: 1
numbers[0] = 10         // Mengubah nilai elemen pertama menjadi 10
fmt.Println(numbers[0]) // Output: 10
```

- Array Multidimensi:

Go juga mendukung array multidimensi, yang berguna untuk representasi data seperti matriks atau tabel.

```go
var matrix [3][3]int // array 2D dengan 3 baris dan 3 kolom
matrix[0][1] = 5     // menetapkan nilai pada baris 0, kolom 1
```


### Struck

Struct adalah tipe data komposit yang memungkinkan kita mengelompokkan variabel dengan tipe yang berbeda dalam satu entitas. Struct sering digunakan untuk merepresentasikan objek atau entitas yang memiliki beberapa atribut.

**Karakteristik Struct:**
1. Tipe Data Heterogen:

   Field dalam struct dapat memiliki tipe data yang berbeda, memungkinkan penggunaan tipe data yang lebih kompleks.

2. Nama Field:

   Setiap field dalam struct memiliki nama yang unik.

3. Notasi Titik:

   Untuk mengakses atau memodifikasi field, kita menggunakan notasi titik (.).

4. Komposisi Struct:

   Struct mendukung komposisi (embedding), yang memungkinkan struct mengandung struct lain di dalamnya.

- Deklarasi Struct:

Struct dideklarasikan menggunakan kata kunci type, diikuti dengan nama struct, dan diakhiri dengan definisi field di dalam kurung kurawal.

```go
type Person struct {
    Name string
    Age  int
    City string
}
```

Dalam contoh ini, struct Person memiliki tiga field: Name dengan tipe string, Age dengan tipe int, dan City dengan tipe string.

**Inisialisasi Struct:**

- Menggunakan Literals:

```go
var person1 = Person{"Alice", 30, "Jakarta"}
```

- Menggunakan Nama Field (Pengisian Tertentu):

  Ini berguna jika kita ingin mengisi hanya sebagian field dari struct.

```go
person2 := Person{Name: "Bob", City: "Bandung"}
```

- Pointer Struct:

  Go mendukung penggunaan pointer pada struct, yang memungkinkan kita mengubah field struct melalui referensinya.

```go
person3 := &Person{"Charlie", 25, "Surabaya"}
person3.City = "Malang" // perubahan langsung pada alamat memori
```

- Mengakses Field Struct:
  
Field dalam struct diakses menggunakan notasi titik (.).

```go
fmt.Println("Nama:", person1.Name)
fmt.Println("Usia:", person1.Age)
```

- Embedded Structs (Komposisi Struct):

Go mendukung konsep embedding, yang memungkinkan struct memiliki struct lain di dalamnya.

```go
type Address struct {
    City, State string
}

type Person struct {
    Name    string
    Age     int
    Address // embedded struct
}

func main() {
    p := Person{Name: "Alice", Age: 30, Address: Address{City: "Jakarta", State: "DKI"}}
    fmt.Println("Kota:", p.City) // akses langsung ke field dari embedded struct
}
```

Dalam contoh di atas, Person memiliki embedded struct Address, sehingga City dan State dari Address dapat diakses langsung melalui objek Person.

### Perbandingan antara array dan struct:

| Fitur           | Array                                              | Struct                                              |
|-----------------|----------------------------------------------------|-----------------------------------------------------|
| Tipe Data       | Homogen, elemen memiliki tipe data yang sama       | Heterogen, field bisa memiliki tipe data berbeda    |
| Ukuran          | Tetap, ditentukan pada saat deklarasi	             | Dapat berubah, field dapat ditambah/diubah          |
| Penggunaan      | Menyimpan sekumpulan data linear atau sekuensial   | Merepresentasikan objek atau entitas yang kompleks  |
| Akses           | Menggunakan indeks                                 | Menggunakan nama field                              |
| Mutidimensi     | Mendukung array multidimensi                       | Mendukung komposisi atau embedding                  |


## Guided 

### 1. Program sederhana untuk menghitung lama waktu parkir berdasarkan waktu kedatangan dan waktu pulang.

### Source Code :

```go
// Caroline Carren
// 2311102174
// S1 IF 11 5

package main

import "fmt"

// Mendefinisikan tipe data struct bernama 'waktu' yang memiliki atribut jam, menit, dan detik bertipe int
type waktu struct {
	jam, menit, detik int
}

func main() {
	// Mendeklarasikan variabel wParkir, wPulang, dan durasi dengan tipe data waktu
	var wParkir, wPulang, durasi waktu

	// Mendeklarasikan variabel dParkir, dPulang, dan lParkir sebagai variabel integer
	// dParkir dan dPulang akan menyimpan waktu dalam detik, sedangkan lParkir akan menyimpan lama parkir dalam detik
	var dParkir, dPulang, lParkir int

	// Mengambil input dari pengguna untuk waktu parkir dalam bentuk jam, menit, dan detik
	fmt.Scan(&wParkir.jam, &wParkir.menit, &wParkir.detik)

	// Mengambil input dari pengguna untuk waktu pulang dalam bentuk jam, menit, dan detik
	fmt.Scan(&wPulang.jam, &wPulang.menit, &wPulang.detik)

	// Mengonversi waktu parkir (wParkir) menjadi detik, dan menyimpannya ke variabel dParkir
	dParkir = wParkir.detik + wParkir.menit*60 + wParkir.jam*3600

	// Mengonversi waktu pulang (wPulang) menjadi detik, dan menyimpannya ke variabel dPulang
	dPulang = wPulang.detik + wPulang.menit*60 + wPulang.jam*3600

	// Menghitung lama parkir dalam detik dengan mengurangi dPulang dengan dParkir
	lParkir = dPulang - dParkir

	// Mengonversi total durasi parkir dari detik ke jam, menit, dan detik
	durasi.jam = lParkir / 3600        // Menghitung jam dengan membagi total detik dengan 3600
	durasi.menit = lParkir % 3600 / 60 // Menghitung menit dari sisa detik setelah diambil jam
	durasi.detik = lParkir % 3600 % 60 // Menghitung detik dari sisa setelah diambil jam dan menit

	// Menampilkan lama parkir dalam format "jam menit detik"
	fmt.Printf("Lama Parkir : %d jam %d menit %d detik", durasi.jam, durasi.menit, durasi.detik)
}
```

### Output:
![image](https://github.com/user-attachments/assets/488b36fe-9a35-40a0-ad94-46229e2d7e25)

### Full code Screenshot :
![carbon (19)](https://github.com/user-attachments/assets/17d61246-2ddc-4945-9edd-bc5c41e3b2d5)

### Deskripsi Program : 
Program ini menghitung durasi waktu parkir berdasarkan input waktu masuk dan keluar dalam format jam, menit, dan detik. Pengguna diminta memasukkan waktu parkir dan waktu pulang, yang akan dikonversi ke dalam satuan detik untuk memudahkan perhitungan. Selanjutnya, program menghitung lama parkir dengan mengurangi waktu pulang dengan waktu parkir, menghasilkan durasi dalam bentuk detik. Durasi tersebut kemudian dikonversi kembali ke format jam, menit, dan detik untuk ditampilkan ke pengguna. Output program menampilkan total lama parkir dalam format "jam menit detik".

### Algoritma Program :
1. Input Data:
   - Program meminta pengguna untuk memasukkan waktu parkir (wParkir) dalam bentuk jam, menit, dan detik.
   - Program meminta pengguna untuk memasukkan waktu pulang (wPulang) dalam bentuk jam, menit, dan detik.

2. Konversi Waktu ke Detik:
   - Program mengonversi waktu parkir (wParkir) ke detik dengan rumus:
     
     *dParkir=wParkir.detik+(wParkir.menit×60)+(wParkir.jam×3600).*
     
   - Program mengonversi waktu pulang (wPulang) ke detik dengan rumus serupa, menyimpan hasilnya dalam dPulang.

3. Penghitungan Lama Parkir:
   - Program menghitung lama parkir dalam detik dengan rumus:

     *lParkir=dPulang−dParkir.*

4. Konversi Lama Parkir ke Jam, Menit, dan Detik:
   - Durasi parkir dikonversi dari detik ke format jam, menit, dan detik:
     
     *durasi.jam diperoleh dari hasil bagi lParkir / 3600.*

     *durasi.menit diperoleh dari sisa bagi lParkir % 3600 / 60.*

     *durasi.detik diperoleh dari sisa lParkir % 3600 % 60.*

5. Output:
   - Program menampilkan durasi parkir dalam format "X jam Y menit Z detik".
     
### Cara Kerja Program :
1. Memulai Program:
   - Program dijalankan dan meminta pengguna untuk memasukkan waktu parkir (wParkir) dan waktu pulang (wPulang) dalam bentuk jam, menit, dan detik.

2. Konversi ke Detik:
   - Program mengonversi waktu parkir dan waktu pulang dari format jam-menit-detik menjadi total detik untuk kemudahan perhitungan.

3. Menghitung Lama Parkir:
   - Program menghitung lama parkir dalam detik dengan mengurangi dPulang dengan dParkir.

4. Mengonversi Lama Parkir ke Jam, Menit, dan Detik:
   - Lama parkir yang telah dihitung dalam detik kemudian dikonversi kembali ke jam, menit, dan detik menggunakan operasi aritmatika.

5. Menampilkan Hasil:
   - Program menampilkan durasi parkir dalam format yang mudah dibaca, yaitu "X jam Y menit Z detik", untuk menunjukkan lama parkir yang tepat.

### 2. Program sederhana untuk validasi duplikasi nama pada daftar teman.

### Source Code :

```go
// Caroline Carren
// 2311102174
// S1 IF 11 5

package main

import (
	"fmt"
)

// Fungsi untuk mengecek apakah nama sudah ada di dalam slice
func sudahAda(daftarTeman []string, nama string) bool {
	// Loop untuk mengecek setiap nama dalam daftarTeman
	for _, teman := range daftarTeman {
		// Jika nama yang dimasukkan sudah ada dalam daftar, return true
		if teman == nama {
			return true
		}
	}
	// Jika tidak ditemukan, return false
	return false
}

func main() {
	// Slice awal untuk daftar teman dengan beberapa data
	daftarTeman := []string{"Andi", "Budi", "Cici"}

	// Nama-nama baru yang ingin ditambahkan ke daftar
	namaBaru := []string{"Dewi", "Budi", "Eka"}

	// Menambahkan nama baru hanya jika belum ada di daftar
	for _, nama := range namaBaru {
		// Mengecek apakah nama sudah ada dalam daftar
		if !sudahAda(daftarTeman, nama) {
			// Jika belum ada, menambahkannya ke dalam daftar
			daftarTeman = append(daftarTeman, nama)
		} else {
			// Jika nama sudah ada, menampilkan pesan
			fmt.Println("Nama", nama, "sudah ada dalam daftar.")
		}
	}

	// Menampilkan daftar teman akhir setelah penambahan
	fmt.Println("Daftar Teman:", daftarTeman)
}
```

### Output:
![image](https://github.com/user-attachments/assets/d8061cd3-03c0-46f2-9eef-81f86ce6ac38)

### Full code Screenshot :
![carbon (20)](https://github.com/user-attachments/assets/e57b75d8-58e4-4322-a6eb-e8bee9ba31db)

### Deskripsi Program : 
Program ini berfungsi untuk menambah nama-nama baru ke dalam daftar teman dengan syarat nama tersebut belum ada dalam daftar. Pertama, program mengecek setiap nama dalam daftar teman untuk melihat apakah nama yang ingin ditambahkan sudah ada. Jika nama yang akan ditambahkan belum ada, maka nama tersebut akan dimasukkan ke dalam daftar teman. Jika nama sudah ada, program akan memberikan pesan kepada pengguna bahwa nama tersebut sudah ada dalam daftar. Di akhir, program menampilkan daftar teman yang diperbarui.

### Algoritma Program :
1. Input Data:
   - Definisikan slice daftarTeman yang berisi beberapa nama awal.
   - Definisikan slice namaBaru yang berisi nama-nama baru yang ingin ditambahkan ke dalam daftarTeman.

2. Pengecekan Nama dalam Daftar:
   - Buat fungsi sudahAda untuk memeriksa apakah sebuah nama sudah ada di dalam slice daftarTeman:
     - Loop melalui daftarTeman dan periksa setiap nama.
     - Jika nama ditemukan, return true; jika tidak, return false.

3. Penambahan Nama ke Daftar Teman:
   - Loop melalui namaBaru:
   - Untuk setiap nama, panggil fungsi sudahAda untuk memeriksa apakah nama tersebut sudah ada dalam daftarTeman.
   - Jika sudahAda return false, tambahkan nama tersebut ke daftarTeman.
   - Jika sudahAda return true, tampilkan pesan bahwa nama sudah ada dalam daftar.

4. Output:
- Tampilkan daftar teman yang telah diperbarui.

### Cara Kerja Program :
1. Memulai Program:
   - Program dimulai dengan mendefinisikan slice daftarTeman yang berisi beberapa nama awal, serta slice namaBaru yang berisi nama-nama yang ingin ditambahkan.

2. Pengecekan Nama:
   - Program menggunakan fungsi sudahAda untuk memeriksa apakah nama dari namaBaru sudah ada dalam daftarTeman.

3. Menambah Nama Jika Belum Ada:
   - Untuk setiap nama di namaBaru, program memeriksa apakah nama tersebut sudah ada di daftarTeman. Jika belum ada, nama tersebut ditambahkan ke daftarTeman. Jika sudah ada, program menampilkan pesan bahwa nama tersebut sudah ada.

4. Menampilkan Daftar Teman yang Diperbarui:
   - Setelah semua nama diproses, program menampilkan daftarTeman yang telah diperbarui.

5. Akhir Program:
   - Program selesai setelah menampilkan daftar teman yang telah diperbarui.

### 3. Program sederhana untuk menampilkan daftar harga buah menggunakan map.

### Source Code :

```go
// Caroline Carren
// 2311102174
// S1 IF 11 5

package main

import "fmt"

func main() {
	// Membuat map dengan nama buah sebagai kunci dan harga sebagai nilai
	hargaBuah := map[string]int{
		"Apel":   5000, // Kunci "Apel", Nilai 5000
		"Pisang": 3000, // Kunci "Pisang", Nilai 3000
		"Mangga": 7000, // Kunci "Mangga", Nilai 7000
	}

	// Menampilkan harga dari setiap buah
	fmt.Println("Harga Buah:")
	// Melakukan iterasi untuk menampilkan kunci dan nilai dari map
	for buah, harga := range hargaBuah {
		// Menampilkan nama buah dan harganya
		fmt.Printf("%s: Rp%d\n", buah, harga)
	}

	// Menampilkan harga dari buah Mangga secara langsung menggunakan kunci
	fmt.Print("Harga buah Mangga = ", hargaBuah["Mangga"])
}
```

### Output:
![image](https://github.com/user-attachments/assets/2c6dd1a5-8d5a-4fb6-955a-eac544493a81)

### Full code Screenshot :
![carbon (21)](https://github.com/user-attachments/assets/24ccdbf1-54e2-4227-9961-c0817d89b615)

### Deskripsi Program : 
Program ini bertujuan untuk menyimpan dan menampilkan daftar harga buah menggunakan struktur data map di Go. Dalam map ini, nama buah digunakan sebagai kunci dan harga sebagai nilai. Program terlebih dahulu mendefinisikan map dengan beberapa buah dan harga yang sudah diisi, yaitu "Apel", "Pisang", dan "Mangga". Selanjutnya, program menampilkan daftar harga setiap buah dengan melakukan iterasi pada map. Terakhir, program menampilkan harga "Mangga" secara langsung menggunakan kunci "Mangga".

### Algoritma Program :
1. Inisialisasi Data:
   - Buat sebuah map bernama hargaBuah dengan tipe string sebagai kunci dan int sebagai nilai.

2. Isi map hargaBuah dengan beberapa pasangan kunci-nilai:
   - "Apel" -> 5000
   - "Pisang" -> 3000
   - "Mangga" -> 7000

3. Menampilkan Daftar Harga Buah:
   - Cetak teks "Harga Buah:" sebagai judul daftar.

4. Iterasi melalui map hargaBuah menggunakan loop for:
   - Untuk setiap pasangan buah dan harga, tampilkan nama buah (buah) dan harganya (harga) dalam format "Nama: Harga".

5. Menampilkan Harga Buah Tertentu:
   - Cetak harga buah "Mangga" secara langsung dengan mengakses nilai hargaBuah["Mangga"].

### Cara Kerja Program :
1. Memulai Program:
   - Program dimulai dengan membuat sebuah map bernama hargaBuah yang memiliki nama buah sebagai kunci dan harga sebagai nilai.

2. Mengisi Data Buah dan Harga:
   - Map diisi dengan beberapa data buah dan harga, seperti "Apel", "Pisang", dan "Mangga".

3. Menampilkan Daftar Harga:
   - Program menampilkan daftar harga dengan melakukan iterasi pada map hargaBuah. Untuk setiap entri buah dan harga, program menampilkan teks dalam format "<Nama Buah>: Rp<Harga>".

4. Menampilkan Harga Buah Tertentu:
   - Program kemudian menampilkan harga buah "Mangga" secara spesifik dengan mengaksesnya langsung melalui map hargaBuah menggunakan kunci "Mangga".

5. Akhir Program:
   - Program selesai setelah menampilkan harga setiap buah dalam map dan harga buah "Mangga" secara terpisah.


## Unguided 

### 1.Suatu lingkaran didefinisikan dengan koordinat titik pusat (𝑐𝑥,𝑐𝑦) dengan radius 𝑟. Apabila diberikan dua buah lingkaran, maka tentukan posisi sebuah titik sembarang (𝑥,𝑦) berdasarkan dua lingkaran tersebut. Gunakan tipe bentukan titik untuk menyimpan koordinat, dan tipe bentukan lingkaran untuk menyimpan titik pusat lingkaran dan radiusnya.

**Masukan** terdiri dari beberapa tiga baris. Baris pertama dan kedua adalah koordinat titik pusat dan radius dari lingkaran 1 dan lingkaran 2, sedangkan baris ketiga adalah koordinat titik sembarang. Asumsi sumbu x dan y dari semua titik dan juga radius direpresentasikan dengan bilangan bulat. 

**Keluaran** berupa string yang menyatakan posisi titik "Titik di dalam lingkaran 1 dan 2", "Titik di dalam lingkaran 1", "Titik di dalam lingkaran 2", atau "Titik di luar lingkaran 1 dan 2". 

### Source Code :
```go
// Caroline Carren
// 2311102174
// S1 IF 11 5

package main

import (
	"fmt"
	"math"
)

// Mendefinisikan tipe data struct 'Point' untuk merepresentasikan koordinat (X, Y) dari suatu titik
type Point struct {
	X int
	Y int
}

// Mendefinisikan tipe data struct 'Circle' untuk merepresentasikan lingkaran dengan pusat (Center) dan radius
type Circle struct {
	Center Point
	Radius int
}

// Fungsi untuk menghitung jarak antara dua titik (p1 dan p2) menggunakan rumus jarak Euclidean
func distance(p1, p2 Point) float64 {
	return math.Sqrt(float64((p1.X-p2.X)*(p1.X-p2.X) + (p1.Y-p2.Y)*(p1.Y-p2.Y)))
}

// Fungsi untuk menentukan posisi titik relatif terhadap dua lingkaran (circle1 dan circle2)
func checkPointPosition(circle1, circle2 Circle, point Point) string {
	// Menghitung jarak antara titik dan pusat lingkaran pertama
	dist1 := distance(circle1.Center, point)

	// Menghitung jarak antara titik dan pusat lingkaran kedua
	dist2 := distance(circle2.Center, point)

	// Memeriksa apakah titik berada di dalam kedua lingkaran, atau salah satu lingkaran, atau di luar keduanya
	if dist1 <= float64(circle1.Radius) && dist2 <= float64(circle2.Radius) {
		return "Titik di dalam lingkaran 1 dan 2" // Jika titik berada di dalam lingkaran 1 dan 2
	} else if dist1 <= float64(circle1.Radius) {
		return "Titik di dalam lingkaran 1" // Jika titik hanya di dalam lingkaran 1
	} else if dist2 <= float64(circle2.Radius) {
		return "Titik di dalam lingkaran 2" // Jika titik hanya di dalam lingkaran 2
	} else {
		return "Titik di luar lingkaran 1 dan 2" // Jika titik berada di luar kedua lingkaran
	}
}

func main() {
	// Deklarasi dua variabel lingkaran (circle1 dan circle2) dan satu variabel titik (point)
	var circle1, circle2 Circle
	var point Point

	// Mengambil input untuk koordinat pusat dan radius lingkaran 1 dari pengguna
	fmt.Println("Masukkan koordinat titik pusat dan radius lingkaran 1:")
	fmt.Scanln(&circle1.Center.X, &circle1.Center.Y, &circle1.Radius)

	// Mengambil input untuk koordinat pusat dan radius lingkaran 2 dari pengguna
	fmt.Println("Masukkan koordinat titik pusat dan radius lingkaran 2:")
	fmt.Scanln(&circle2.Center.X, &circle2.Center.Y, &circle2.Radius)

	// Mengambil input untuk koordinat titik sembarang dari pengguna
	fmt.Println("Masukkan koordinat titik sembarang:")
	fmt.Scanln(&point.X, &point.Y)

	// Memeriksa posisi titik relatif terhadap kedua lingkaran dan menampilkan hasilnya
	position := checkPointPosition(circle1, circle2, point)
	fmt.Println("Posisi titik:", position)
}
```

### Output:
![image](https://github.com/user-attachments/assets/8a87fc30-f5c5-4709-8970-b63aca70a4b6)

### Full code Screenshot :
![carbon (22)](https://github.com/user-attachments/assets/f80157ef-0e4c-424d-b25d-438744df95aa)

### Deskripsi Program : 
Program ini bertujuan untuk menentukan posisi sebuah titik relatif terhadap dua lingkaran. Pengguna diminta untuk memasukkan data koordinat pusat dan radius dari dua lingkaran, serta koordinat dari titik yang akan diperiksa posisinya. Program menggunakan rumus jarak Euclidean untuk menghitung jarak titik dari pusat kedua lingkaran. Berdasarkan jarak tersebut, program menentukan apakah titik tersebut berada di dalam kedua lingkaran, di dalam salah satu lingkaran, atau di luar keduanya.

### Algoritma Program :
1. Inisialisasi Data:
   - Definisikan struct Point dengan atribut X dan Y untuk merepresentasikan koordinat titik.
   - Definisikan struct Circle dengan atribut Center (tipe Point) dan Radius (tipe int) untuk merepresentasikan lingkaran.

2. Fungsi distance:
   - Buat fungsi distance untuk menghitung jarak antara dua titik (p1, p2) menggunakan rumus Euclidean:
   - Jarak dihitung sebagai

     ![image](https://github.com/user-attachments/assets/18476c5b-8feb-4e68-b795-7c05752285c5)


3. Fungsi checkPointPosition:
   - Buat fungsi checkPointPosition untuk menentukan posisi titik point relatif terhadap dua lingkaran (circle1 dan circle2):
   - Hitung jarak antara titik point dan pusat circle1 (dist1).
   - Hitung jarak antara titik point dan pusat circle2 (dist2).

4. Tentukan posisi titik:
   - Jika dist1 ≤ radius circle1 dan dist2 ≤ radius circle2, titik berada di dalam kedua lingkaran.
   - Jika hanya dist1 ≤ radius circle1, titik berada di dalam lingkaran 1.
   - Jika hanya dist2 ≤ radius circle2, titik berada di dalam lingkaran 2.
   - Jika tidak memenuhi semua kondisi di atas, titik berada di luar kedua lingkaran.

5. Input dan Output:
   - Ambil input dari pengguna untuk koordinat pusat dan radius circle1.
   - Ambil input dari pengguna untuk koordinat pusat dan radius circle2.
   - Ambil input dari pengguna untuk koordinat point.
   - Panggil fungsi checkPointPosition untuk memeriksa posisi point dan tampilkan hasilnya.

### Cara Kerja Program :
1. Memulai Program:
   - Program dimulai dengan mendefinisikan dua lingkaran (circle1 dan circle2) dan satu titik sembarang (point) yang akan digunakan untuk memeriksa posisi titik.

2. Mengambil Input:
   - Program meminta pengguna untuk memasukkan koordinat pusat dan radius dari circle1 dan circle2, serta koordinat point.

3. Menghitung Jarak Titik:
   - Program menggunakan fungsi distance untuk menghitung jarak titik point ke pusat circle1 dan circle2.

4. Menentukan Posisi Titik:
   - Dengan menggunakan fungsi checkPointPosition, program menentukan apakah point berada di dalam atau di luar kedua lingkaran, atau hanya di dalam salah satu lingkaran.

5. Menampilkan Hasil:
   - Program menampilkan posisi titik relatif terhadap kedua lingkaran sesuai hasil pengecekan.

6. Akhir Program:
   - Setelah menampilkan hasil, program selesai.

### 2. Sebuah array digunakan untuk menampung sekumpulan bilangan bulat. Buatlah program yang digunakan untuk mengisi array tersebut sebanyak N elemen nilai. Asumsikan array memiliki kapasitas penyimpanan data sejumlah elemen tertentu. Program dapat menampilkan beberapa informasi berikut:

a.	Menampilkan keseluruhan isi dari array.

b.	Menampilkan elemen-elemen array dengan indeks ganjil saja.

c.	Menampilkan elemen-elemen array dengan indeks genap saja (asumsi indek ke-0 adalah genap).

d.	Menampilkan elemen-elemen array dengan indeks kelipatan bilangan x. x bisa diperoleh dari masukan pengguna.

e.	Menghapus elemen array pada indeks tertentu, asumsi indeks yang hapus selalu valid.Tampilkan keseluruhan isi dari arraynya, pastikan data yang dihapus tidak tampil

f.	Menampilkan rata-rata dari bilangan yang ada di dalam array.

g.	Menampilkan standar deviasi atau simpangan baku dari bilangan yang ada di dalam array tersebut.

h.	Menampilkan frekuensi dari suatu bilangan tertentu di dalam array yang telah diisi tersebut.


### Source Code :
```go
// Caroline Carren
// 2311102174
// S1 IF 11 5

package main

import (
	"fmt"
	"math"
)

func main() {
	// Deklarasi array dengan kapasitas 10 untuk menampung elemen-elemen array
	array := make([]int, 10)

	// Meminta user memasukkan jumlah elemen yang ingin dimasukkan ke dalam array
	var n int
	fmt.Print("Masukkan jumlah elemen (maksimal 10): ")
	fmt.Scanln(&n)

	// Memastikan jumlah elemen tidak melebihi kapasitas array
	if n > 10 {
		n = 10
		fmt.Println("Jumlah elemen dibatasi maksimal 10. Menggunakan 10 elemen.")
	}

	// Meminta user untuk memasukkan nilai-nilai elemen ke dalam array
	fmt.Println("Masukkan elemen array:")
	for i := 0; i < n; i++ {
		var elemen int
		fmt.Scanln(&elemen)
		array[i] = elemen
	}

	for {
		// Menampilkan pilihan menu operasi yang bisa dilakukan pada array
		fmt.Println("\nPilihan menu:")
		fmt.Println("1. Menampilkan keseluruhan isi dari array")
		fmt.Println("2. Menampilkan elemen-elemen array dengan indeks ganjil saja")
		fmt.Println("3. Menampilkan elemen-elemen array dengan indeks genap saja")
		fmt.Println("4. Menampilkan elemen-elemen array dengan indeks kelipatan bilangan x")
		fmt.Println("5. Menghapus elemen array pada indeks tertentu")
		fmt.Println("6. Menampilkan rata-rata dari bilangan yang ada di dalam array")
		fmt.Println("7. Menampilkan standar deviasi atau simpangan baku dari bilangan yang ada di dalam array")
		fmt.Println("8. Menampilkan frekuensi dari suatu bilangan tertentu di dalam array")
		fmt.Println("9. Keluar")

		// Meminta user untuk memilih salah satu menu
		var pilihan int
		fmt.Print("\nMasukkan pilihan: ")
		fmt.Scanln(&pilihan)

		// Memproses pilihan yang dimasukkan oleh user
		switch pilihan {
		case 1:
			tampilkanKeseluruhanIsiArray(array, n)
		case 2:
			tampilkanElemenIndeksGanjil(array, n)
		case 3:
			tampilkanElemenIndeksGenap(array, n)
		case 4:
			tampilkanElemenKelipatan(array, n)
		case 5:
			n = hapusElemenArray(array, n) // Update n after deletion
		case 6:
			tampilkanRataRata(array, n)
		case 7:
			tampilkanStandarDeviasi(array, n)
		case 8:
			tampilkanFrekuensi(array, n)
		case 9:
			fmt.Println("Terima kasih! Program selesai.")
			return // Exit the program
		default:
			fmt.Println("Pilihan tidak valid")
		}
	}
}

// Fungsi untuk menampilkan seluruh isi array
func tampilkanKeseluruhanIsiArray(array []int, n int) {
	fmt.Println("Isi array:")
	for i := 0; i < n; i++ {
		fmt.Println(array[i])
	}
}

// Fungsi untuk menampilkan elemen array dengan indeks ganjil
func tampilkanElemenIndeksGanjil(array []int, n int) {
	fmt.Println("Elemen dengan indeks ganjil:")
	for i := 1; i < n; i += 2 {
		fmt.Println(array[i])
	}
}

// Fungsi untuk menampilkan elemen array dengan indeks genap
func tampilkanElemenIndeksGenap(array []int, n int) {
	fmt.Println("Elemen dengan indeks genap:")
	for i := 0; i < n; i += 2 {
		fmt.Println(array[i])
	}
}

// Fungsi untuk menampilkan elemen array dengan indeks kelipatan bilangan x
func tampilkanElemenKelipatan(array []int, n int) {
	var x int
	fmt.Print("Masukkan bilangan kelipatan: ")
	fmt.Scanln(&x)
	fmt.Println("Elemen dengan indeks kelipatan", x, ":")
	for i := 0; i < n; i++ {
		if i%x == 0 {
			fmt.Println(array[i])
		}
	}
}

// Fungsi untuk menghapus elemen array pada indeks tertentu
func hapusElemenArray(array []int, n int) int {
	var indeks int
	fmt.Print("Masukkan indeks elemen yang ingin dihapus: ")
	fmt.Scanln(&indeks)
	if indeks < 0 || indeks >= n {
		fmt.Println("Indeks tidak valid")
		return n // Return n unchanged
	}
	// Menggeser elemen-elemen setelah elemen yang dihapus untuk menghapusnya
	for i := indeks; i < n-1; i++ {
		array[i] = array[i+1]
	}
	n-- // Mengurangi jumlah elemen
	fmt.Println("Elemen pada indeks", indeks, "telah dihapus")
	return n // Return updated n
}

// Fungsi untuk menampilkan rata-rata dari elemen array
func tampilkanRataRata(array []int, n int) {
	var total int
	// Menghitung total dari seluruh elemen dalam array
	for i := 0; i < n; i++ {
		total += array[i]
	}
	// Menghitung rata-rata
	rataRata := float64(total) / float64(n)
	fmt.Printf("Rata-rata: %.2f\n", rataRata)
}

// Fungsi untuk menghitung dan menampilkan standar deviasi (simpangan baku) dari elemen array
func tampilkanStandarDeviasi(array []int, n int) {
	var total, rataRata float64
	// Menghitung total nilai dalam array
	for i := 0; i < n; i++ {
		total += float64(array[i])
	}
	// Menghitung rata-rata
	rataRata = total / float64(n)

	var totalDeviasi float64
	// Menghitung deviasi dari setiap elemen terhadap rata-rata
	for i := 0; i < n; i++ {
		totalDeviasi += math.Pow(float64(array[i])-rataRata, 2)
	}
	// Menghitung standar deviasi
	standarDeviasi := math.Sqrt(totalDeviasi / float64(n))
	fmt.Printf("Standar deviasi: %.2f\n", standarDeviasi)
}

// Fungsi untuk menampilkan frekuensi kemunculan suatu bilangan di dalam array
func tampilkanFrekuensi(array []int, n int) {
	var bilangan int
	// Meminta user untuk memasukkan bilangan yang ingin dihitung frekuensinya
	fmt.Print("Masukkan bilangan untuk mencari frekuensi: ")
	fmt.Scanln(&bilangan)
	frekuensi := 0
	// Menghitung frekuensi kemunculan bilangan di dalam array
	for i := 0; i < n; i++ {
		if array[i] == bilangan {
			frekuensi++
		}
	}
	fmt.Printf("Frekuensi dari bilangan %d: %d\n", bilangan, frekuensi)
}
```

### Output:
**Jika user memilih menu 1:**
![image](https://github.com/user-attachments/assets/5fca252e-6608-425b-a5eb-bc6ef312d390)

**Jika user memilih menu 2:**
![image](https://github.com/user-attachments/assets/182f341e-49a6-4ba8-876f-e92b6e3ac965)

**Jika user memilih menu 3:**
![image](https://github.com/user-attachments/assets/deb80981-3837-4441-9c8a-03d12a5e44c4)

**Jika user memilih menu 4:**
![image](https://github.com/user-attachments/assets/9405649c-ddc9-4d5f-b452-4c63b55582c8)

**Jika user memilih menu 5:**
![image](https://github.com/user-attachments/assets/80cd95b7-243f-4b2e-8ae5-e4d6c0066f6b)

**Jika user memilih menu 6:**
![image](https://github.com/user-attachments/assets/5e588ffd-3ff3-46d1-9338-34bf0d782b41)

**Jika user memilih menu 7:**
![image](https://github.com/user-attachments/assets/24e4898e-7eb4-41d4-b9ef-6a7bb34e89d8)

**Jika user memilih menu 8:**
![image](https://github.com/user-attachments/assets/37ca1bc2-31c8-4983-9a7d-382a986d32ef)

**Jika user memilih menu 9:**
![image](https://github.com/user-attachments/assets/9d61f116-a8e1-45d1-8dfb-dbeba8f8be35)

### Full code Screenshot :
![carbon (23)](https://github.com/user-attachments/assets/adeda258-9ed6-4a44-b521-3b0b139579cb)

### Deskripsi Program : 
Program ini adalah aplikasi berbasis konsol yang menggunakan array untuk menyimpan dan memanipulasi sejumlah elemen bilangan bulat. Pengguna dapat memilih dari berbagai menu operasi seperti menampilkan isi array, menampilkan elemen pada indeks ganjil atau genap, menghapus elemen tertentu, menghitung rata-rata, mencari standar deviasi, dan menghitung frekuensi suatu bilangan. Dengan array maksimal 10 elemen, program juga membatasi jumlah elemen yang dimasukkan dan memberikan antarmuka interaktif untuk setiap operasi.

### Algoritma Program :
1. Inisialisasi Array:
   - Deklarasikan array dengan kapasitas 10 untuk menampung nilai bilangan bulat.

2. Input Jumlah Elemen:
   - Minta pengguna memasukkan jumlah elemen yang ingin ditambahkan ke array, dengan batas maksimum 10 elemen.

3. Input Elemen Array:
   - Minta pengguna memasukkan nilai untuk setiap elemen array.

4. Pilihan Menu:
   - Tampilkan menu dengan opsi untuk melakukan berbagai operasi pada array:
     - Menampilkan isi array.
     - Menampilkan elemen dengan indeks ganjil atau genap.
     - Menampilkan elemen dengan indeks kelipatan bilangan tertentu.
     - Menghapus elemen array pada indeks tertentu.
     - Menghitung rata-rata nilai elemen.
     - Menghitung standar deviasi nilai elemen.
     - Menghitung frekuensi kemunculan bilangan tertentu.
     - Keluar dari program.

5. Eksekusi Pilihan:
   - Baca pilihan pengguna dan panggil fungsi yang sesuai berdasarkan pilihan:
     - tampilkanKeseluruhanIsiArray: Menampilkan seluruh elemen di array.
     - tampilkanElemenIndeksGanjil: Menampilkan elemen pada indeks ganjil.
     - tampilkanElemenIndeksGenap: Menampilkan elemen pada indeks genap.
     - tampilkanElemenKelipatan: Menampilkan elemen pada indeks kelipatan tertentu.
     - hapusElemenArray: Menghapus elemen di indeks tertentu.
     - tampilkanRataRata: Menghitung dan menampilkan rata-rata elemen.
     - tampilkanStandarDeviasi: Menghitung dan menampilkan standar deviasi elemen.
     - tampilkanFrekuensi: Menampilkan frekuensi kemunculan bilangan tertentu.

6. Keluar Program:
   - Jika pengguna memilih opsi untuk keluar, program menampilkan pesan terima kasih dan mengakhiri eksekusi.

### Cara Kerja Program :
1. Inisialisasi dan Input Elemen:
   - Program dimulai dengan meminta pengguna memasukkan jumlah elemen yang ingin dimasukkan ke dalam array, dibatasi maksimal 10 elemen.
   - Program meminta pengguna untuk mengisi nilai-nilai elemen tersebut satu per satu ke dalam array.

2. Menampilkan Menu Pilihan:
   - Setelah array diisi, program menampilkan menu pilihan yang memungkinkan pengguna untuk melakukan berbagai operasi pada array, seperti menampilkan elemen, menghitung rata-rata, menghapus elemen, dll.
   - Memilih dan Menjalankan Operasi:
     - Pengguna memasukkan nomor pilihan yang diinginkan, dan program menjalankan fungsi sesuai dengan pilihan tersebut:
       - Pilihan 1: Menampilkan seluruh elemen dalam array.
       - Pilihan 2: Menampilkan elemen pada indeks ganjil.
       - Pilihan 3: Menampilkan elemen pada indeks genap.
       - Pilihan 4: Menampilkan elemen pada indeks kelipatan bilangan yang dimasukkan oleh pengguna.
       - Pilihan 5: Menghapus elemen pada indeks tertentu dan memperbarui jumlah elemen dalam array.
       - Pilihan 6: Menghitung dan menampilkan rata-rata elemen dalam array.
       - Pilihan 7: Menghitung dan menampilkan standar deviasi elemen dalam array.
       - Pilihan 8: Menghitung dan menampilkan frekuensi kemunculan suatu bilangan dalam array.

3. Mengulangi Proses:
   - Setelah operasi selesai, program kembali menampilkan menu dan memungkinkan pengguna untuk memilih operasi lain.
   - Program akan terus mengulangi proses ini sampai pengguna memilih untuk keluar dengan memilih Pilihan 9.

4. Mengakhiri Program:
   - Jika pengguna memilih Pilihan 9, program menampilkan pesan akhir dan menghentikan eksekusi.

### 3. Sebuah program digunakan untuk menyimpan dan menampilkan nama-nama klub yang memenangkan pertandingan bola pada suatu grup pertandingan. Buatlah program yang digunakan untuk merekap skor pertandingan bola 2 buah klub bola yang berlaga. Pertama-tama program meminta masukan nama-nama klub yang bertanding, kemudian program meminta masukan skor hasil pertandingan kedua klub tersebut.  Yang disimpan dalam array adalah nama-nama klub yang menang saja. Proses input skor berhenti ketika skor salah satu atau kedua klub tidak valid (negatif). Di akhir program, tampilkan daftar klub yang memenangkan pertandingan. 

**Perhatikan sesi interaksi pada contoh berikut ini (teks bergaris bawah adalah input/read)**

![image](https://github.com/user-attachments/assets/4146434b-4259-4554-b798-d28652eaf506)

### Source Code :
```go
// Caroline Carren
// 2311102174
// S1 IF 11 5

package main

import "fmt"

func main() {
	var klubA, klubB string
	var skorA, skorB int
	var hasil []string

	// Input nama klub
	fmt.Print("Masukkan nama klub A: ")
	fmt.Scanln(&klubA)
	fmt.Print("Masukkan nama klub B: ")
	fmt.Scanln(&klubB)

	// Loop untuk input skor
	for {
		fmt.Printf("Masukkan skor untuk %s dan %s : ", klubA, klubB)
		_, err := fmt.Scanf("%d %d\n", &skorA, &skorB)

		// Cek jika input tidak valid
		if err != nil {
			fmt.Println("Input tidak valid. Pastikan untuk memasukkan dua angka.")
			// Mengosongkan input buffer
			var dummy string
			fmt.Scanln(&dummy)
			continue
		}

		// Break loop jika salah satu skor negatif
		if skorA < 0 || skorB < 0 {
			break
		}

		// Tentukan hasil pertandingan
		if skorA > skorB {
			hasil = append(hasil, klubA) // klubA menang
		} else if skorA < skorB {
			hasil = append(hasil, klubB) // klubB menang
		} else {
			hasil = append(hasil, "Draw") // seri
		}
	}

	// Tampilkan hasil
	fmt.Println("Hasil pertandingan:")
	for i, h := range hasil {
		fmt.Printf("Hasil %d: %s\n", i+1, h)
	}
	fmt.Println("Pertandingan selesai")
}
```

### Output:
![image](https://github.com/user-attachments/assets/339e6f5c-6299-4cb0-aca4-0f8fde334996)

### Full code Screenshot :
![carbon (24)](https://github.com/user-attachments/assets/6a7f4691-1514-43ee-89a7-460c314bdad2)

### Deskripsi Program : 
Program ini memungkinkan pengguna untuk memasukkan hasil pertandingan antara dua klub sepak bola dan menentukan pemenang berdasarkan skor yang dimasukkan. Pengguna diminta untuk menginput nama kedua klub dan skor mereka secara berulang sampai salah satu skor bernilai negatif. Program kemudian memeriksa skor untuk menentukan siapa yang menang, jika ada, atau mencatat hasil sebagai "Draw" jika kedua klub memiliki skor yang sama. Semua hasil pertandingan disimpan dalam sebuah slice dan ditampilkan setelah input selesai. Program menggunakan validasi input untuk memastikan hanya angka yang dimasukkan sebagai skor.

### Algoritma Program :
1. Inisialisasi Variabel:
   - Deklarasikan variabel klubA, klubB untuk nama klub.
   - Deklarasikan variabel skorA, skorB untuk skor pertandingan.
   - Deklarasikan slice hasil untuk menyimpan hasil pertandingan.

2. Input Nama Klub:
   - Input nama klub A dan B.
   - Loop untuk Input Skor:
     - Lakukan loop untuk meminta input skor secara berulang.
     - Cek jika input skor valid (dua angka). Jika tidak, tampilkan pesan kesalahan dan lanjutkan ke input berikutnya.
     - Jika salah satu skor negatif, break dari loop.

3. Menentukan Hasil Pertandingan:
   - Jika skor A lebih besar dari skor B, tambahkan klub A ke slice hasil.
   - Jika skor B lebih besar dari skor A, tambahkan klub B ke slice hasil.
   - Jika skor A sama dengan skor B, tambahkan "Draw" ke slice hasil.

4. Menampilkan Hasil:
   - Tampilkan hasil pertandingan dari slice hasil.

5. Program Selesai:
   - Program selesai dan keluar setelah menampilkan semua hasil.

### Cara Kerja Program :
1. Input Nama Klub:
   - Program pertama-tama meminta pengguna untuk memasukkan nama klub A dan klub B yang akan bertanding.

2. Input Skor Pertandingan:
   - Program memasuki loop untuk meminta pengguna memasukkan skor pertandingan antara klub A dan klub B. Pengguna diminta untuk memasukkan dua angka (skor untuk masing-masing klub) untuk setiap pertandingan.

3. Validasi Input:
   - Program memeriksa apakah input berupa dua angka. Jika input tidak valid (misalnya bukan angka), program menampilkan pesan kesalahan dan meminta input ulang.

4. Menentukan Hasil Pertandingan:
   - Jika skor klub A lebih besar dari klub B, maka klub A dianggap menang dan ditambahkan ke dalam slice hasil.
   - Jika skor klub B lebih besar dari klub A, maka klub B dianggap menang dan ditambahkan ke dalam slice hasil.
   - Jika skor kedua klub sama, maka hasilnya adalah "Draw" yang juga ditambahkan ke dalam slice hasil.

5. Penghentian Input:
   - Program akan berhenti meminta input saat salah satu skor yang dimasukkan bernilai negatif. Ketika hal ini terjadi, loop berhenti dan program melanjutkan untuk menampilkan hasil.

6. Menampilkan Hasil:
   - Setelah loop berhenti, program menampilkan hasil dari setiap pertandingan yang telah dimasukkan, baik itu kemenangan klub A, kemenangan klub B, atau hasil seri.

### 4. Sebuah array digunakan untuk menampung sekumpulan karakter, Anda diminta untuk membuat sebuah subprogram untuk melakukan membalikkan urutan isi array dan memeriksa apakah membentuk palindrom. 

**Lengkapi potongan algoritma berikut ini!**

![image](https://github.com/user-attachments/assets/3092b31f-a121-4949-80ac-c3fdeb038d1e)

![image](https://github.com/user-attachments/assets/44d5811a-66b1-433d-92d7-2e6345c0d105)

![image](https://github.com/user-attachments/assets/81102940-311e-4684-bdce-ef7324507c9b)

### Source Code :
```go
// Caroline Carren
// 2311102174
// S1 IF 11 5

package main

import "fmt"

const NMAX int = 127 // Konstanta untuk batas maksimum jumlah karakter dalam array

// Tipe data tabel adalah array yang menampung hingga 127 karakter bertipe rune (karakter Unicode)
type tabel [NMAX]rune

// Fungsi untuk mengisi array dengan karakter-karakter yang dimasukkan oleh pengguna
func isiArray(t *tabel, n int) {
	/* I.S. Data tersedia dalam piranti masukan
	   F.S. Array t berisi sejumlah n karakter yang dimasukkan user,
	   Proses input berhenti jika karakter yang dimasukkan adalah TITIK ('.') dan n <= NMAX */
	var i int
	var karakter rune
	fmt.Println("Masukkan karakter : ")
	for i = 0; i < n; i++ {
		// Memasukkan karakter satu per satu
		fmt.Scanf("%c", &karakter)
		// Jika karakter yang dimasukkan adalah titik, berhenti memasukkan data
		if karakter == '.' {
			break
		}
		// Menyimpan karakter ke dalam array
		t[i] = karakter
	}
}

// Fungsi untuk mencetak seluruh isi array ke layar
func cetakArray(t tabel, n int) {
	/* I.S. Terdefinisi array t yang berisi sejumlah n karakter
	   F.S. n karakter dalam array muncul di layar */
	for i := 0; i < n; i++ {
		// Mencetak karakter satu per satu
		fmt.Printf("%c", t[i])
	}
	// Menambahkan baris baru setelah mencetak karakter
	fmt.Println()
}

// Fungsi untuk membalikkan urutan karakter dalam array
func balikanArray(t *tabel, n int) {
	/* I.S. Terdefinisi array t yang berisi sejumlah n karakter
	   F.S. Urutan isi array t terbalik */
	for i := 0; i < n/2; i++ {
		// Menyimpan nilai sementara untuk pertukaran
		temp := t[i]
		// Melakukan pertukaran posisi karakter
		t[i] = t[n-i-1]
		t[n-i-1] = temp
	}
}

// Fungsi untuk memeriksa apakah array membentuk palindrom
func palindrom(t tabel, n int) bool {
	/* Mengembalikan true apabila susunan karakter di dalam t membentuk palindrom,
	   dan false apabila sebaliknya. Petunjuk: Manfaatkan prosedur balikanArray */
	var t2 tabel
	// Menyalin array t ke array t2
	copy(t2[:], t[:])
	// Membalikkan array t2
	balikanArray(&t2, n)

	// Memeriksa apakah array t dan t2 sama
	for i := 0; i < n; i++ {
		if t2[i] != t[i] {
			// Jika ada perbedaan, berarti bukan palindrom
			return false
		}
	}
	// Jika semua elemen sama, berarti palindrom
	return true
}

func main() {
	// Deklarasi array untuk menyimpan karakter dan jumlah elemen
	var tab tabel
	var n int
	// Meminta pengguna untuk memasukkan jumlah karakter
	fmt.Println("Masukkan jumlah karakter : ")
	fmt.Scanln(&n)
	// Mengisi array dengan karakter-karakter yang dimasukkan
	isiArray(&tab, n)
	// Menampilkan karakter-karakter yang dimasukkan
	fmt.Println("Karakter yang dimasukkan adalah:")
	cetakArray(tab, n)

	// Memeriksa apakah array membentuk palindrom
	if palindrom(tab, n) {
		// Jika ya, tampilkan pesan palindrom
		fmt.Println("Array ini adalah palindrom.")
	} else {
		// Jika tidak, tampilkan pesan bukan palindrom
		fmt.Println("Array ini bukan palindrom.")
	}
}
```

### Output:
![image](https://github.com/user-attachments/assets/e2212e65-cd4c-4d46-bc77-796124d3da62)

### Full code Screenshot :
![carbon (25)](https://github.com/user-attachments/assets/b93751ff-75fb-472a-9e51-c3d5055be70c)

### Deskripsi Program : 
Program ini digunakan untuk memeriksa apakah urutan karakter yang dimasukkan oleh pengguna membentuk sebuah palindrom. Pengguna diminta untuk memasukkan jumlah karakter yang ingin mereka masukkan, kemudian memasukkan karakter-karakter tersebut satu per satu. Setelah karakter dimasukkan, program akan menampilkan karakter-karakter tersebut, membalik urutan karakter, dan memeriksa apakah urutan karakter tersebut membentuk palindrom.

### Algoritma Program :
1. Deklarasi Variabel:
   - tabel adalah tipe data array yang menampung hingga 127 karakter (rune).
   - tab adalah array yang akan digunakan untuk menyimpan karakter-karakter yang dimasukkan pengguna.
   - n adalah jumlah karakter yang dimasukkan pengguna.

2. Fungsi isiArray:
   - Fungsi ini meminta pengguna memasukkan karakter-karakter.
   - Karakter dimasukkan satu per satu menggunakan fmt.Scanf("%c", &karakter).
   - Input berhenti ketika titik (.) dimasukkan atau jika jumlah karakter sudah mencapai batas yang ditentukan.

3. Fungsi cetakArray:
   - Fungsi ini mencetak seluruh karakter yang ada dalam array ke layar.

4. Fungsi balikanArray:
   - Fungsi ini membalikkan urutan karakter dalam array dengan metode pertukaran elemen (swapping).
   - Untuk membalik array, pertukaran dilakukan antara elemen di posisi i dan n-i-1 hingga mencapai tengah array.

5. Fungsi palindrom:
   - Fungsi ini memeriksa apakah urutan karakter dalam array membentuk palindrom.
   - Fungsi pertama menyalin array t ke dalam array t2.
   - Kemudian, array t2 dibalik menggunakan fungsi balikanArray.
   - Setelah itu, array t2 dibandingkan dengan array t untuk memeriksa kesamaan setiap elemen. Jika semua elemen sama, maka array membentuk palindrom.

6. Program Utama (main):
   - Program meminta input jumlah karakter, kemudian mengisi array dengan karakter-karakter yang dimasukkan oleh pengguna.
   - Karakter yang dimasukkan kemudian ditampilkan di layar.
   - Setelah itu, program memeriksa apakah urutan karakter tersebut membentuk palindrom dan menampilkan hasilnya.

### Cara Kerja Program :
1. Input Jumlah Karakter:
   - Program meminta pengguna untuk memasukkan jumlah karakter yang ingin dimasukkan ke dalam array, yang dibatasi hingga 127 karakter (tergantung nilai konstanta NMAX).

2. Input Karakter:
   - Program meminta pengguna untuk memasukkan karakter satu per satu. Input berhenti jika pengguna memasukkan titik (.) atau jika jumlah karakter yang dimasukkan mencapai batas maksimum.

3. Menampilkan Karakter:
   - Setelah semua karakter dimasukkan, program akan menampilkan urutan karakter yang telah dimasukkan oleh pengguna.

4. Memeriksa Palindrom:
   - Program akan membalik urutan karakter dalam array dan memeriksa apakah array yang dibalik sama dengan array asli.
   - Jika sama, berarti urutan karakter membentuk palindrom. Jika tidak, berarti bukan palindrom.

5. Output Hasil:
   - Program akan mencetak apakah urutan karakter yang dimasukkan membentuk palindrom atau tidak.

## Kesimpulan 
Berdasarkan hasil praktikum, dapat disimpulkan bahwa:
1. Praktikum ini memberikan pemahaman tentang penggunaan array untuk menyimpan dan mengelola sejumlah data dalam program. Array memudahkan pengelolaan data yang memiliki tipe sama dalam satu wadah.
2. Dengan menggunakan struktur data seperti array dan tipe data custom (seperti struktur), kita dapat menangani data yang lebih kompleks dan mengorganisirnya dengan lebih baik dalam program.
3. Dalam praktikum, kita belajar bagaimana mengelola input dari pengguna untuk mengisi array, serta cara menangani input yang tidak valid menggunakan pemeriksaan error.
   
## Daftar Pustaka

[1] A. A. A. Donovan and B. W. Kernighan, *The Go Programming Language*. Boston, MA: Addison-Wesley, 2015.
