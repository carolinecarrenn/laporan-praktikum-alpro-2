<h2 align="center"><strong>LAPORAN PRAKTIKUM</strong></h2>
<h2 align="center"><strong>ALGORITMA DAN PEMROGRAMAN 2</strong></h2>

<br>

<h2 align="center"><strong>MODUL IV</strong></h2>
<h2 align="center"><strong> PROSEDUR  </strong></h2> 

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
1. Mahasiswa dapat memahami konsep dasar prosedur (fungsi tanpa return value) dalam bahasa pemrograman Go.
2. Mahasiswa dapat mengimplementasikan prosedur sederhana untuk memecahkan masalah dalam program Go.
3. Mahasiswa dapat memahami perbedaan antara prosedur dan fungsi yang memiliki return value.
   
## Dasar Teori
**Prosedur (Fungsi) dalam Go**

Prosedur adalah bagian fundamental dari pemrograman terstruktur yang memungkinkan program dipecah menjadi bagian-bagian kecil yang dapat dikelola. 
Di Go, prosedur disebut sebagai fungsi (*function*). Fungsi digunakan untuk memisahkan logika program menjadi modul-modul terpisah sehingga lebih mudah dikelola, diuji, dan digunakan kembali. Fungsi ini memiliki komponen berikut:

- Nama Fungsi : Digunakan untuk mengidentifikasi fungsi dan memanggilnya.
- Parameter : Input yang diterima oleh fungsi untuk diproses. Fungsi dapat menerima beberapa parameter.
- Tipe Pengembalian : Nilai yang dikembalikan oleh fungsi. Fungsi dapat mengembalikan satu atau lebih nilai.
- Badan Fungsi : Kode yang dijalankan ketika fungsi dipanggil.

Contoh :
```go
func hitungLuasPersegiPanjang(panjang, lebar int) int {
    return panjang * lebar
}

func main() {
    luas := hitungLuasPersegiPanjang(5, 3)
    fmt.Println("Luas:", luas)
}
```

Dalam contoh ini, fungsi `hitungLuasPersegiPanjang` menerima dua parameter bertipe `int`,
dan mengembalikan nilai hasil perkalian panjang dan lebar sebagai integer.

**Parameter dan Argumen**

- Parameter adalah variabel yang dideklarasikan dalam definisi fungsi.
  Ini adalah nilai-nilai yang akan diterima oleh fungsi ketika dipanggil.
  Go memungkinkan penulisan parameter dengan tipe data eksplisit.
- Argumen adalah nilai yang diberikan ke parameter saat memanggil fungsi.
  Argumen ini bisa berupa variabel, konstanta, atau hasil dari ekspresi lain.

Parameter dengan Tipe yang Sama: Go memungkinkan penulisan parameter yang memiliki tipe data yang sama secara singkat.

Contoh :

```go
func tambah(a, b int) int {
    return a + b
}
```

**Pengembalian Nilai (Return Values)**

Salah satu fitur yang menonjol di Go adalah kemampuannya untuk mengembalikan lebih dari satu nilai dari fungsi. 
Ini sangat berguna ketika sebuah fungsi perlu mengembalikan hasil utama dan informasi tambahan (misalnya, status kesalahan).

Contoh :
```go
func bagi(a, b int) (int, error) {
    if b == 0 {
        return 0, fmt.Errorf("tidak bisa membagi dengan nol")
    }
    return a / b, nil
}

func main() {
    hasil, err := bagi(10, 0)
    if err != nil {
        fmt.Println("Error:", err)
    } else {
        fmt.Println("Hasil:", hasil)
    }
}
```

Dalam contoh ini, fungsi `bagi` mengembalikan dua nilai : hasil pembagian dan potensi kesalahan.

**First-Class Function (Fungsi sebagai Objek Kelas Utama)**

Dalam Go, fungsi adalah `first-class citizen`, yang berarti fungsi dapat diperlakukan seperti objek lainnya, seperti variabel. Fungsi dapat:

- Disimpan dalam variabel.
- Diteruskan sebagai parameter ke fungsi lain.
- Dikembalikan sebagai hasil dari fungsi.

Contoh :
```go
func operasi(oper func(int, int) int, a int, b int) int {
    return oper(a, b)
}

func main() {
    penjumlahan := func(a, b int) int { return a + b }
    hasil := operasi(penjumlahan, 5, 3)
    fmt.Println(hasil) // Output: 8
}
```
Di sini, fungsi *penjumlahan* didefinisikan sebagai fungsi anonim dan disimpan dalam variabel *penjumlahan*. 
Variabel ini kemudian diteruskan sebagai argumen ke fungsi *operasi*.

**Closure**

Closure adalah fungsi yang "membungkus" lingkungannya, yaitu variabel-variabel dari cakupan luar yang dapat diakses di dalam fungsi tersebut, bahkan setelah lingkungannya selesai dieksekusi.

Contoh :
```go
func buatCounter() func() int {
    hitung := 0
    return func() int {
        hitung++
        return hitung
    }
}

func main() {
    counter := buatCounter()
    fmt.Println(counter()) // Output: 1
    fmt.Println(counter()) // Output: 2
}
```

Di sini, fungsi anonim di dalam `buatCounter` dapat mengakses variabel `hitung`, meskipun `hitung` dideklarasikan di luar fungsi tersebut.

**Variadic Function**

Go mendukung fungsi *variadic*, yang artinya fungsi dapat menerima sejumlah argumen yang bervariasi. 
Hal ini memungkinkan lebih banyak fleksibilitas saat memanggil fungsi dengan jumlah argumen yang berbeda-beda.

Contoh :
```go
func cetakAngka(angka ...int) {
    for _, a := range angka {
        fmt.Println(a)
    }
}

func main() {
    cetakAngka(1, 2, 3, 4, 5)
}
```

Fungsi `cetakAngka` di atas dapat menerima jumlah argumen yang tidak terbatas karena menggunakan parameter variadic (`...int`).

**Goroutine dan Concurrency**

Salah satu kekuatan utama Go adalah dukungan bawaan untuk *concurrency*. 
Dengan menggunakan *goroutine*, kita bisa menjalankan fungsi secara paralel tanpa overhead yang signifikan. 
Goroutine adalah fungsi ringan yang berjalan secara bersamaan dengan fungsi lain.

Contoh :
```go
func cetakAngka() {
    for i := 0; i < 5; i++ {
        fmt.Println(i)
    }
}

func main() {
    go cetakAngka()  // Memanggil fungsi sebagai goroutine
    fmt.Scanln()      // Menunggu input untuk mencegah program selesai sebelum goroutine selesai
}
```

Dalam contoh ini, fungsi `cetakAngka` berjalan sebagai goroutine, yang dijalankan secara bersamaan dengan eksekusi utama.

**Error Handling : Panic dan Recover**

Dalam bahasa Go, kesalahan penanganan dapat dilakukan dengan menggunakan mekanisme panic dan recover. Ketika terjadi panic, program akan berhenti, tetapi kita bisa menangkap panic menggunakan recover untuk mencegah program crash.

Contoh :
```go
func bagi(a, b int) int {
    defer func() {
        if r := recover(); r != nil {
            fmt.Println("Kesalahan:", r)
        }
    }()
    if b == 0 {
        panic("pembagian dengan nol tidak diizinkan")
    }
    return a / b
}

func main() {
    fmt.Println(bagi(4, 2))  // Output: 2
    fmt.Println(bagi(4, 0))  // Output: Kesalahan: pembagian dengan nol tidak diizinkan
}
```

**Interface**

Go menggunakan konsep *interface* untuk mendukung pemrograman yang lebih fleksibel. 
*Interface* mendefinisikan sekumpulan metode yang harus diimplementasikan oleh tipe tertentu. 
Jika tipe mengimplementasikan metode-metode tersebut, maka tipe tersebut "memenuhi" interface.

Contoh :
```go
type penggerak interface {
    bergerak() string
}

type mobil struct{}

func (m mobil) bergerak() string {
    return "Mobil bergerak"
}

func jalankan(p penggerak) {
    fmt.Println(p.bergerak())
}

func main() {
    m := mobil{}
    jalankan(m)
}
```

Dalam contoh ini, tipe *mobil* mengimplementasikan metode *bergerak*, 
sehingga dapat digunakan di fungsi *jalankan* yang menerima tipe *penggerak*.

**Anonymous Function**

Fungsi anonim adalah fungsi tanpa nama yang biasanya didefinisikan dan dipanggil secara langsung. Fungsi ini berguna untuk operasi sederhana yang tidak perlu nama khusus.

Contoh :
```go
func main() {
    hasil := func(a, b int) int {
        return a + b
    }(3, 4)
    fmt.Println(hasil)  // Output: 7
}
```

## Guided 

### 1. Program fungsi yang digunakan untuk menghitung nilai faktorial dan permutasi

### Source Code :
```go
package main

import "fmt"

// Fungsi utama program
func main() {
	var a, b int
	// Menerima input dari pengguna
	fmt.Scan(&a, &b)
	// Memeriksa apakah a >= b
	if a >= b {
		// Jika ya, panggil prosedur hitungPermutasi(a, b)
		hitungPermutasi(a, b)
	} else {
		// Jika tidak, panggil prosedur hitungPermutasi(b, a)
		hitungPermutasi(b, a)
	}
}

// Prosedur untuk menghitung faktorial dari n
func hitungFaktorial(n int) {
	var hasil int = 1
	var i int
	// Loop untuk menghitung faktorial
	for i = 1; i <= n; i++ {
		hasil = hasil * i
	}
	fmt.Println("Faktorial dari", n, "adalah", hasil)
}

// Prosedur untuk menghitung permutasi P(n, r)
func hitungPermutasi(n, r int) {
	hitungFaktorial(n)
	hitungFaktorial(n - r)
	var hasil int = 1
	var i int
	// Loop untuk menghitung faktorial n
	for i = 1; i <= n; i++ {
		hasil = hasil * i
	}
	var hasil2 int = 1
	// Loop untuk menghitung faktorial n-r
	for i = 1; i <= n-r; i++ {
		hasil2 = hasil2 * i
	}
	fmt.Println("Permutasi dari", n, "dan", r, "adalah", hasil/hasil2)
}
```

### Output:

![image](https://github.com/user-attachments/assets/72df8599-6620-48f5-b10b-9d32aaa7a733)

### Full code Screenshot :
![carbon (7)](https://github.com/user-attachments/assets/5ef1e5e3-4463-4b67-9d13-398d77982a64)

### Deskripsi Program :
Program ini menerima dua bilangan bulat dari pengguna, lalu memeriksa bilangan mana yang lebih besar. 
Program akan menghitung nilai permutasi dari bilangan yang lebih besar sebagai 𝑛 dan bilangan yang lebih kecil sebagai 𝑟.
Hasil dari permutasi dihitung menggunakan rumus 𝑃(𝑛,𝑟)= 𝑛!/(𝑛−𝑟)!, dimana 𝑛! adalah faktorial dari 𝑛 dan (𝑛−𝑟)! adalah faktorial 𝑛−𝑟.

### Algoritma Program :
1. Input Data:
   - Pengguna diminta untuk memasukkan dua bilangan bulat.

2. Pemilihan Nilai 𝑛 dan 𝑟
   - Program memeriksa apakah bilangan pertama (𝑎) lebih besar atau sama dengan bilangan kedua (𝑏).
   - Jika benar (𝑎 ≥ 𝑏), program akan menghitung permutasi 𝑃(𝑎,𝑏). Jika salah, program menghitung 𝑃(𝑏,𝑎).

3. Penghitungan Faktorial:
   - Program memiliki fungsi faktorial untuk menghitung faktorial dari suatu bilangan 𝑛 menggunakan loop dari 1 sampai 𝑛.

4. Penghitungan Permutasi:
   - Fungsi permutasi menghitung permutasi 𝑃(𝑛,𝑟) dengan menggunakan hasil faktorial dari 𝑛 dan 𝑛−𝑟, lalu membagi 𝑛! dengan (𝑛-𝑟)!.

5. Output:
   - Hasil perhitungan permutasi ditampilkan di layar.
     
### Cara Kerja Program :
1. Memulai Program:
   - Program dimulai dan menunggu input dari pengguna. Pengguna diminta untuk memasukkan dua bilangan 𝑎 dan 𝑏.

2. Memeriksa Kondisi:
   - Jika 𝑎 ≥ 𝑏, maka program menghitung 𝑃(𝑎,𝑏) dengan memanggil `fungsi permutasi(a, b)`.
   - Jika 𝑎 < 𝑏, program menghitung 𝑃(𝑏,𝑎).

3. Menghitung Faktorial:
   - Program menggunakan fungsi faktorial untuk menghitung 𝑛! dan (𝑛−𝑟)!.

4. Menghitung Permutasi:
   - Setelah mendapatkan nilai faktorial 𝑛! dan (𝑛−𝑟)!, program membagi 𝑛! dengan (𝑛−𝑟)! untuk mendapatkan hasil permutasi.

5. Menampilkan Hasil:
   - Program menampilkan hasil perhitungan permutasi ke layar.
     
### 2. Program fungsi yang digunakan untuk menghitung luas dan keliling sebuah persegi berdasarkan panjang sisi yang dimasukkan oleh pengguna

### Source Code :
```go
package main

import "fmt"

// Prosedur untuk menghitung luas persegi
func hitungLuas(sisi float64) {
	var luas float64 = sisi * sisi
	fmt.Printf("Luas persegi : %.2f\n", luas)
}

// Prosedur untuk menghitung keliling persegi
func hitungKeliling(sisi float64) {
	var keliling float64 = 4 * sisi
	fmt.Printf("Keliling persegi : %.2f\n", keliling)
}

func main() {
	var sisi float64

	// Tanya pengguna untuk memasukkan sisi persegi
	fmt.Print("Masukkan sisi persegi : ")
	fmt.Scanln(&sisi)

	// Panggil prosedur untuk menghitung luas dan keliling
	hitungLuas(sisi)
	hitungKeliling(sisi)
}
```

### Output:
![image](https://github.com/user-attachments/assets/9a1de1ca-fbee-41db-bce4-4948977be305)

### Full code Screenshot :
![carbon (6)](https://github.com/user-attachments/assets/45fc0e3b-cf6b-4f1c-9a75-087384cc8ea1)

### Deskripsi Program : 
Program ini menerima input berupa panjang sisi persegi dari pengguna, kemudian menghitung luas dan kelilingnya dengan menggunakan rumus :

- Luas Persegi : sisi x sisi
- Keliling Persegi : 4 x sisi
  
### Algoritma Program :
1. Input Data:
   - Program meminta pengguna untuk memasukkan panjang sisi persegi.

2. Menghitung Luas:
   - Fungsi `hitungLuas` menerima input panjang sisi dan mengembalikan hasil dari perkalian panjang sisi dengan dirinya sendiri (sisi x sisi).

3. Menghitung Keliling:
   - Fungsi `hitungKeliling` menerima input panjang sisi dan mengembalikan hasil dari perkalian panjang sisi dengan 4 (4 × sisi).

4. Menampilkan Hasil:
   - Program menampilkan hasil perhitungan luas dan keliling dalam format dengan dua desimal.
     
### Cara Kerja Program :
1. Memulai Program:
   - Program dimulai dan pengguna diminta untuk memasukkan panjang sisi persegi.

2. Menghitung Luas dan Keliling:
   - Program menghitung luas persegi menggunakan fungsi hitungLuas, dengan rumus sisi × sisi.
   - Program menghitung keliling persegi menggunakan fungsi hitungKeliling, dengan rumus 4 × sisi.

3. Menampilkan Hasil:
   - Program mencetak hasil perhitungan luas dan keliling ke layar dengan format dua desimal.


## Unguided 

### 1. Minggu ini, mahasiswa Fakultas Informatika mendapatkan tugas dari mata kuliah matematika diskrit untuk mempelajari kombinasi dan permutasi. Jonas salah seorang mahasiswa, iseng untuk mengimplementasikannya ke dalam suatu program. Oleh karena itu bersediakah kalian membantu Jonas? (tidak tentunya ya :p)
**Masukan terdiri dari empat buah bilangan asli 𝑎, 𝑏, 𝑐, dan 𝑑 yang dipisahkan oleh spasi, dengan syarat 𝑎 ≥ 𝑐 dan 𝑏 ≥ 𝑑.
Keluaran terdiri dari dua baris. Baris pertama adalah hasil permutasi dan kombinasi 𝒂 terhadap
𝑐, sedangkan baris kedua adalah hasil permutasi dan kombinasi 𝑏 terhadap 𝑑.**

**Catatan: permutasi (𝑃) dan kombinasi (𝐶) dari 𝑛 terhadap 𝑟 (𝑛 ≥ 𝑟) dapat dihitung dengan menggunakan persamaan berikut!**

![image](https://github.com/user-attachments/assets/4978402f-272c-4bae-8ac4-e554843517a4)

Contoh : 

![image](https://github.com/user-attachments/assets/b7167807-34f3-4c61-91e9-3bdcc494c253)

### Source Code :
```go
package main

import (
	"fmt"
	"strconv"
)

func main() {
	fmt.Println("================================")
	fmt.Println("Program Permutasi & Kombinasi")
	fmt.Println("================================")

	var a, b, c, d int
	a, b, c, d = inputAngka()

	// Validasi input
	if !isValidInput(a, b, c, d) {
		fmt.Println("Input tidak valid. Pastikan a >= c dan b >= d.")
		return
	}

	// Hitung dan tampilkan hasil
	tampilkanHasil(a, b, c, d)
}

// Prosedur fungsi untuk menerima input angka dari pengguna
func inputAngka() (int, int, int, int) {
	var inputA, inputB, inputC, inputD string
	fmt.Print("Masukkan bilangan asli a: ")
	fmt.Scanln(&inputA)
	fmt.Print("Masukkan bilangan asli b: ")
	fmt.Scanln(&inputB)
	fmt.Print("Masukkan bilangan asli c: ")
	fmt.Scanln(&inputC)
	fmt.Print("Masukkan bilangan asli d: ")
	fmt.Scanln(&inputD)

	// Mengkonversi input string menjadi integer
	a, _ := strconv.Atoi(inputA)
	b, _ := strconv.Atoi(inputB)
	c, _ := strconv.Atoi(inputC)
	d, _ := strconv.Atoi(inputD)

	return a, b, c, d
}

// Prosedur untuk fungsi memvalidasi input
func isValidInput(a, b, c, d int) bool {
	return a >= c && b >= d
}

// Fungsi untuk menghitung faktorial dari n
func faktorial(n int) int {
	hasil := 1
	for i := 1; i <= n; i++ {
		hasil *= i
	}
	return hasil
}

// Fungsi untuk menghitung permutasi P(n, r)
func permutasi(n, r int) int {
	return faktorial(n) / faktorial(n-r)
}

// Fungsi untuk menghitung kombinasi C(n, r)
func kombinasi(n, r int) int {
	return faktorial(n) / (faktorial(r) * faktorial(n-r))
}

// Fungsi untuk menampilkan hasil perhitungan
func tampilkanHasil(a, b, c, d int) {
	fmt.Println("--------------------------------")
	fmt.Println("Hasil Perhitungan:")
	fmt.Printf("P(%d, %d) = %d!/(%d-%d)! = %d\n", a, c, a, a, c, permutasi(a, c))
	fmt.Printf("C(%d, %d) = %d!/((%d!)*(%d-%d)!) = %d\n", a, c, a, c, a, c, kombinasi(a, c))
	fmt.Printf("P(%d, %d) = %d!/(%d-%d)! = %d\n", b, d, b, b, d, permutasi(b, d))
	fmt.Printf("C(%d, %d) = %d!/((%d!)*(%d-%d)!) = %d\n", b, d, b, d, b, d, kombinasi(b, d))
	fmt.Println("--------------------------------")
}
```

### Output:
![image](https://github.com/user-attachments/assets/559f565b-c256-44c2-bad9-3017dad92b71)

![image](https://github.com/user-attachments/assets/c64d011b-8bba-4485-9e66-0deda18735c6)

### Full code Screenshot :
![carbon (8)](https://github.com/user-attachments/assets/ae8bf92e-6da5-41a0-ad93-48e603371e45)

### Deskripsi Program : 
Program ini menerima empat bilangan dari pengguna: 𝑎, 𝑏, 𝑐, dan 𝑑. Kemudian, program menghitung permutasi dan kombinasi dari 𝑃(𝑎,𝑐), 𝐶(𝑎,𝑐), 𝑃(𝑏,𝑑), dan 𝐶(𝑏,𝑑), dengan validasi bahwa 𝑎 ≥ 𝑐 dan 𝑏 ≥ 𝑑. 
Hasilnya ditampilkan dalam format yang rapi.

1. Permutasi (𝑃(𝑛,𝑟)):
   - Menghitung jumlah cara mengatur 𝑟 objek dari 𝑛 objek tanpa memperhatikan urutan.
   - Rumus : 𝑃(𝑛,𝑟)= 𝑛!/(𝑛−𝑟)!

2. Kombinasi (𝐶(𝑛,𝑟)):
   - Menghitung jumlah cara memilih 𝑟 objek dari 𝑛 objek tanpa memperhatikan urutan.
   - Rumus : 𝐶(𝑛,𝑟) = 𝑛!/𝑟!(𝑛−𝑟)!
     
### Algoritma Program :
1. Menerima Input dari Pengguna:
   - Program meminta pengguna memasukkan empat bilangan: 𝑎, 𝑏, 𝑐, dan 𝑑. Input berupa string lalu dikonversi menjadi integer menggunakan fungsi `strconv.Atoi`.

2. Validasi Input:
   - Program memvalidasi bahwa 𝑎 ≥ 𝑐 dan 𝑏 ≥ 𝑑. Jika tidak valid, program menampilkan pesan kesalahan dan keluar.

3. Perhitungan Faktorial:
   - Fungsi faktorial(n) menghitung faktorial dari bilangan 𝑛 menggunakan loop sederhana.

4. Perhitungan Permutasi:
   - Fungsi permutasi(𝑛,𝑟) menggunakan rumus permutasi 𝑃(𝑛,𝑟)= 𝑛!/(𝑛−𝑟)! dengan memanfaatkan fungsi faktorial.

5. Perhitungan Kombinasi:
   - Fungsi kombinasi (𝑛,𝑟) menggunakan rumus kombinasi 𝐶(𝑛,𝑟) = 𝑛!/𝑟!(𝑛−𝑟)!.

6. Menampilkan Hasil:
   - Program menampilkan hasil perhitungan permutasi dan kombinasi untuk dua pasang bilangan 
(𝑎,𝑐) dan (𝑏,𝑑) dalam format yang terstruktur.

### Cara Kerja Program :
1. Memulai Program:
   - Program dimulai dengan menampilkan judul "Program Permutasi & Kombinasi" dan meminta pengguna memasukkan empat bilangan asli.

2. Memvalidasi Input:
   - Program memeriksa apakah nilai 𝑎 ≥ 𝑐 dan 𝑏 ≥ 𝑑.
   - Jika valid, program melanjutkan perhitungan.
   - Jika tidak, program memberikan pesan kesalahan.

3. Menghitung dan Menampilkan Hasil:
   - Program menghitung permutasi dan kombinasi menggunakan dua fungsi terpisah (`permutasi` dan `kombinasi`), lalu menampilkan hasil dalam bentuk formula matematika beserta hasil akhirnya.
     
### 2. Program Sederhana untuk Membaca dan Menampilkan Nama

### Source Code :
```go
```
### Output:
### Full code Screenshot :
### Deskripsi Program : 
### Algoritma Program :
### Cara Kerja Program :

### 1. Program Sederhana untuk Membaca dan Menampilkan Nama

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

[2] W. Kennedy, B. Ketelsen, and E. St. Martin, *Go in Action*. Greenwich, CT: Manning Publications, 2016.
