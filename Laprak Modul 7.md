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
### Full code Screenshot :
### Deskripsi Program : 
### Algoritma Program :
### Cara Kerja Program :

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
### Full code Screenshot :
### Deskripsi Program : 
### Algoritma Program :
### Cara Kerja Program :

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
### Full code Screenshot :
### Deskripsi Program : 
### Algoritma Program :
### Cara Kerja Program :

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
### Full code Screenshot :
### Deskripsi Program : 
### Algoritma Program :
### Cara Kerja Program :

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
### Full code Screenshot :
### Deskripsi Program : 
### Algoritma Program :
### Cara Kerja Program :


### 3. Sebuah program digunakan untuk menyimpan dan menampilkan nama-nama klub yang memenangkan pertandingan bola pada suatu grup pertandingan. Buatlah program yang digunakan untuk merekap skor pertandingan bola 2 buah klub bola yang berlaga. Pertama-tama program meminta masukan nama-nama klub yang bertanding, kemudian program meminta masukan skor hasil pertandingan kedua klub tersebut.  Yang disimpan dalam array adalah nama-nama klub yang menang saja. Proses input skor berhenti ketika skor salah satu atau kedua klub tidak valid (negatif). Di akhir program, tampilkan daftar klub yang memenangkan pertandingan. 

**Perhatikan sesi interaksi pada contoh berikut ini (teks bergaris bawah adalah input/read)**

![image](https://github.com/user-attachments/assets/4146434b-4259-4554-b798-d28652eaf506)


### Source Code :
```go
```
### Output:
### Full code Screenshot :
### Deskripsi Program : 
### Algoritma Program :
### Cara Kerja Program :


### 4. Sebuah array digunakan untuk menampung sekumpulan karakter, Anda diminta untuk membuat sebuah subprogram untuk melakukan membalikkan urutan isi array dan memeriksa apakah membentuk palindrom. 

**Lengkapi potongan algoritma berikut ini!**

![image](https://github.com/user-attachments/assets/3092b31f-a121-4949-80ac-c3fdeb038d1e)

![image](https://github.com/user-attachments/assets/44d5811a-66b1-433d-92d7-2e6345c0d105)

![image](https://github.com/user-attachments/assets/81102940-311e-4684-bdce-ef7324507c9b)

### Source Code :
```go
```
### Output:
### Full code Screenshot :
### Deskripsi Program : 
### Algoritma Program :
### Cara Kerja Program :





## Kesimpulan 
## Daftar Pustaka

[1] A. A. A. Donovan and B. W. Kernighan, *The Go Programming Language*. Boston, MA: Addison-Wesley, 2015.
