<h2 align="center"><strong>LAPORAN PRAKTIKUM</strong></h2>
<h2 align="center"><strong>ALGORITMA DAN PEMROGRAMAN 2</strong></h2>

<br>

<h2 align="center"><strong>MODUL VI</strong></h2>
<h2 align="center"><strong> REKURSIF </strong></h2> 

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
1. Mahasiswa diharapkan memahami konsep rekursif dalam pemrograman, termasuk cara kerja fungsi yang memanggil dirinya sendiri.
2. Mahasiswa mampu mengimplementasikan teknik rekursif dalam bahasa Go, serta membedakannya dengan iterasi untuk menyelesaikan permasalahan tertentu.
3. Mahasiswa dapat mengenali dan menangani kondisi khusus (edge case) pada fungsi rekursif, sehingga program dapat berjalan dengan benar untuk berbagai skenario input.

## Dasar Teori
Rekursif adalah konsep di mana suatu fungsi memanggil dirinya sendiri untuk menyelesaikan masalah. Dalam konteks bahasa Go, rekursif sering digunakan untuk menyelesaikan masalah yang dapat dipecah menjadi sub-masalah yang lebih sederhana hingga mencapai kondisi dasar, yang memungkinkan fungsi untuk berhenti memanggil dirinya sendiri.

**1. Konsep Dasar Rekursif**
- Rekursi adalah teknik di mana fungsi menyelesaikan masalah dengan memanggil dirinya sendiri secara bertahap hingga mencapai kondisi akhir (base case), di mana proses rekursif dihentikan.
- Fungsi rekursif umumnya terdiri dari dua bagian utama:
  - Base Case: Kondisi yang menyebabkan fungsi berhenti memanggil dirinya sendiri.
  - Langkah Rekursif: Bagian di mana fungsi memanggil dirinya sendiri dengan parameter yang dimodifikasi, mendekati base case.

**2. Implementasi Fungsi Rekursif dalam Go**

Dalam Go, rekursi digunakan untuk menyelesaikan masalah seperti faktorial, deret Fibonacci, dan traversing pada struktur data seperti pohon atau grafik. Buku The Go Programming Language menjelaskan bahwa setiap pemanggilan rekursif menambah frame pada stack, yang memuat variabel lokal dan status fungsi. Ini berarti rekursi memerlukan perhatian ekstra pada base case agar tidak terjadi infinite loop.

Contoh implementasi rekursif sederhana untuk faktorial:

```go
func faktorial(n int) int {
    if n == 0 {
        return 1 // base case
    }
    return n * faktorial(n-1) // langkah rekursif
}
```

Di sini, faktorial akan terus memanggil dirinya sendiri dengan n yang lebih kecil, hingga n mencapai 0.

**3. Rekursif vs Iterasi**
- Menurut Go in Action, rekursi dapat membuat kode lebih mudah dipahami untuk masalah-masalah yang memiliki struktur berulang secara hierarkis, seperti pohon atau grafik. Namun, rekursi dapat menyebabkan pemborosan memori karena setiap pemanggilan fungsi baru menambahkan frame di stack.
- Rekursi memiliki potensi untuk menimbulkan stack overflow jika base case tidak tercapai dalam jumlah panggilan tertentu.

Contoh iterasi untuk menghitung faktorial:
```go
func faktorialIteratif(n int) int {
    hasil := 1
    for i := 1; i <= n; i++ {
        hasil *= i
    }
    return hasil
}
```

Kedua metode menghasilkan hasil yang sama, tetapi pendekatan rekursif lebih sesuai untuk masalah yang memiliki struktur berulang secara hierarkis.

**4. Manfaat dan Kekurangan Rekursif**
- Menurut Donovan dan Kernighan, rekursi sering kali lebih mudah dimengerti karena secara alami mengikuti alur masalah, tetapi membutuhkan perhatian ekstra terhadap base case.
- Buku Go in Action menekankan bahwa rekursi memungkinkan penulisan kode yang lebih ringkas, tetapi penggunaan berlebihan dapat menyebabkan pemborosan memori dan penurunan performa. Oleh karena itu, penting untuk memilih pendekatan rekursif atau iteratif sesuai dengan konteks permasalahan.


## Guided

### 1. Program yang mencetak angka menurun dari bilangan n hingga 1 menggunakan fungsi rekursif baris.

### Source Code :
```go
package main

import "fmt"

// Fungsi utama
func main() {
	// Deklarasi variabel n untuk menyimpan input pengguna
	var n int

	// Meminta input dari pengguna
	fmt.Print("Masukkan angka: ")
	fmt.Scan(&n)

	// Memanggil fungsi rekursif baris dengan input n
	baris(n)
}

// Fungsi rekursif untuk mencetak angka menurun dari bilangan ke 1
func baris(bilangan int) {
	// Kondisi dasar: jika bilangan == 1, cetak 1 dan hentikan rekursi
	if bilangan == 1 {
		fmt.Println(1)
	} else {
		// Jika bilangan > 1, cetak bilangan, lalu panggil fungsi baris dengan bilangan - 1
		fmt.Println(bilangan)
		baris(bilangan - 1)
	}
}
```
### Output:
![image](https://github.com/user-attachments/assets/f7aa43ad-94b3-4b78-893d-7a3651d08420)

### Full code Screenshot :
![carbon (14)](https://github.com/user-attachments/assets/0503b8d4-f7e0-4fca-a3a3-50c8807a6caa)

### Deskripsi Program : 
Program ini adalah program yang menerima input bilangan n dari pengguna dan kemudian menampilkan urutan angka dari n hingga 1. Proses ini menggunakan fungsi rekursif baris, yang mencetak angka secara menurun dengan setiap pemanggilan fungsi, mengurangi nilai bilangan sebanyak satu hingga mencapai nilai dasar 1.

### Algoritma Program :
1. Memulai Program:
   - Deklarasikan variabel n untuk menyimpan input pengguna.

2. Meminta Input dari Pengguna:
   - Tampilkan pesan: "Masukkan angka:".
   - Baca input dari pengguna dan simpan dalam variabel n.

3. Memanggil Fungsi Rekursif:
   - Panggil fungsi baris(n) dengan parameter n, yang berfungsi untuk mencetak bilangan secara menurun hingga 1.

4. Fungsi Rekursif baris(bilangan):
   - Kondisi Dasar: Jika bilangan == 1, cetak angka 1 dan hentikan rekursi.
   - Langkah Rekursif: Jika bilangan > 1, cetak bilangan, kemudian panggil fungsi baris(bilangan - 1).

5. Mengakhiri Program:
   - Setelah deret bilangan selesai dicetak, program berakhir.
     
### Cara Kerja Program :
1. Memulai Program:
   - Program dimulai dengan deklarasi variabel n yang akan menyimpan nilai input dari pengguna.

2. Meminta Input dari Pengguna:
   - Program menampilkan pesan kepada pengguna untuk memasukkan angka, kemudian membaca input tersebut dan menyimpannya ke dalam variabel n.

3. Memanggil Fungsi Rekursif:
   - Program memanggil fungsi baris(n), yang akan mencetak deret bilangan menurun secara rekursif hingga mencapai 1.

4. Proses dalam Fungsi Rekursif baris(bilangan):
   - Jika bilangan adalah 1, program mencetak angka 1 dan menghentikan proses rekursi.
   - Jika bilangan lebih dari 1, program mencetak angka bilangan, lalu memanggil baris(bilangan - 1) untuk melanjutkan proses ke bilangan berikutnya.

5. Mengakhiri Program:
   - Setelah fungsi baris selesai menjalankan semua proses hingga mencapai kondisi dasar (bilangan == 1), program berakhir.
     
### 2. Program Sederhana untuk penjumlahan deret dari angka n hingga 1 menggunakan fungsi rekursif.

### Source Code :
```go
package main

import "fmt"

// Fungsi rekursif untuk menghitung penjumlahan dari n hingga 1
func penjumlahan(n int) int {
	if n == 1 {
		// Kondisi dasar: jika n == 1, kembalikan 1
		return 1
	} else {
		// Jika n > 1, kembalikan n + penjumlahan(n-1)
		return n + penjumlahan(n-1)
	}
}

// Fungsi utama
func main() {
	// Deklarasi variabel n untuk menyimpan input pengguna
	var n int

	// Meminta input dari pengguna
	fmt.Print("Masukkan angka: ")
	fmt.Scan(&n)

	// Mencetak hasil penjumlahan dari n hingga 1
	fmt.Println(penjumlahan(n))
}
```
### Output:
![image](https://github.com/user-attachments/assets/4861c7eb-ab55-4452-9612-0ae258d31db5)

### Full code Screenshot :
![carbon (15)](https://github.com/user-attachments/assets/145ec0e3-a547-48e3-9d14-08c4555fbf8c)

### Deskripsi Program : 
Program ini menghitung penjumlahan deret dari angka n hingga 1 menggunakan fungsi rekursif. Program meminta pengguna untuk memasukkan nilai n, kemudian menggunakan fungsi rekursif penjumlahan untuk menghitung total dari n + (n-1) + ... + 1 dan menampilkan hasilnya.

### Algoritma Program :
1. Memulai Program:
   - Deklarasikan variabel n untuk menyimpan input dari pengguna.

2. Meminta Input dari Pengguna:
   - Tampilkan pesan: "Masukkan angka:".
   - Baca input dari pengguna dan simpan dalam variabel n.

3. Memanggil Fungsi Rekursif:
   - Panggil fungsi penjumlahan(n) untuk menghitung total penjumlahan dari n hingga 1.

4. Fungsi Rekursif penjumlahan(n):
   - Kondisi Dasar: Jika n == 1, kembalikan nilai 1.
   - Langkah Rekursif: Jika n > 1, hitung n + penjumlahan(n-1).

5. Mencetak Hasil Akhir:
   - Tampilkan hasil yang dikembalikan oleh fungsi penjumlahan(n).

6. Mengakhiri Program:
   - Setelah hasil ditampilkan, program berakhir.

### Cara Kerja Program :
1. Memulai Program:
   - Program dimulai dengan deklarasi variabel n untuk menyimpan input dari pengguna.

2. Meminta Input dari Pengguna:
   - Program meminta pengguna untuk memasukkan angka n, yang kemudian disimpan dalam variabel n.

3. Memanggil Fungsi Rekursif:
   - Program memanggil fungsi penjumlahan(n) yang berfungsi untuk menghitung total penjumlahan dari n hingga 1 menggunakan rekursi.

4. Proses dalam Fungsi Rekursif penjumlahan(n):
   - Jika n bernilai 1, fungsi langsung mengembalikan nilai 1 sebagai kondisi dasar.
   - Jika n lebih dari 1, fungsi menghitung nilai n + penjumlahan(n-1), sehingga proses ini akan terus berlanjut hingga mencapai kondisi dasar (n == 1).

5. Mencetak Hasil Akhir:
   - Nilai total hasil penjumlahan yang dihitung oleh fungsi penjumlahan(n) ditampilkan kepada pengguna.

6. Mengakhiri Program:
   - Setelah menampilkan hasil penjumlahan, program selesai dan berhenti.

### 3. Program Sederhana untuk menghitung nilai 2 pangkat n (2^n) menggunakan fungsi rekursif. Program meminta pengguna memasukkan nilai n, lalu menghitung hasil dari 2^n dengan memanggil fungsi rekursif pangkat

### Source Code :
```go
package main

import "fmt"

// Fungsi rekursif untuk menghitung nilai 2^n
func pangkat(n int) int {
	if n == 0 {
		// Kondisi dasar: jika n == 0, kembalikan 1
		return 1
	} else {
		// Jika n > 0, kembalikan 2 * pangkat(n-1)
		return 2 * pangkat(n-1)
	}
}

// Fungsi utama
func main() {
	// Deklarasi variabel n untuk menyimpan input pengguna
	var n int

	// Meminta input dari pengguna
	fmt.Print("Masukkan nilai n: ")
	fmt.Scan(&n)

	// Mencetak hasil dari 2 pangkat n
	fmt.Println("Hasil dari 2 pangkat", n, "adalah", pangkat(n))
}
```
### Output:
![image](https://github.com/user-attachments/assets/c1b6cc34-fff7-470c-bda0-af676d2870d0)

### Full code Screenshot :
![carbon (16)](https://github.com/user-attachments/assets/929e567f-0330-4406-9fba-12c4abb8432f)

### Deskripsi Program : 
Program ini menghitung nilai 2 pangkat n (2^n) menggunakan fungsi rekursif. Program meminta pengguna memasukkan nilai n, lalu menghitung hasil dari 2^n dengan memanggil fungsi rekursif pangkat.

### Algoritma Program :
1. Memulai Program:
   - Deklarasikan variabel n untuk menyimpan input pengguna.

2. Meminta Input dari Pengguna:
   - Tampilkan pesan: "Masukkan nilai n:".
   - Baca input dari pengguna dan simpan dalam variabel n.

3. Memanggil Fungsi Rekursif pangkat:
   - Panggil fungsi pangkat(n) untuk menghitung nilai 2 pangkat n.

4. Fungsi Rekursif pangkat(n):
   - Kondisi Dasar: Jika n == 0, kembalikan nilai 1 (karena 2^0 = 1).
   - Langkah Rekursif: Jika n > 0, hitung 2 * pangkat(n-1). Proses ini akan berlanjut sampai mencapai kondisi dasar (n == 0).

5. Mencetak Hasil Akhir:
   - Tampilkan hasil yang dikembalikan oleh fungsi pangkat(n).

6. Mengakhiri Program:
   - Setelah hasil ditampilkan, program berakhir.

### Cara Kerja Program :
1. Memulai Program:
   - Program dimulai dengan deklarasi variabel n untuk menyimpan nilai input dari pengguna.

2. Meminta Input dari Pengguna:
   - Program meminta pengguna untuk memasukkan nilai n, yang kemudian disimpan dalam variabel n.

3. Memanggil Fungsi Rekursif:
   - Program memanggil fungsi pangkat(n), yang menggunakan rekursi untuk menghitung nilai 2 pangkat n.

4. Proses dalam Fungsi Rekursif pangkat(n):
   - Jika n adalah 0, fungsi mengembalikan nilai 1 sebagai kondisi dasar.
   - Jika n lebih besar dari 0, fungsi mengembalikan hasil dari 2 * pangkat(n-1). Rekursi ini terus berjalan hingga mencapai kondisi dasar (n == 0), di mana fungsi mulai mengembalikan hasil perhitungan ke setiap langkah rekursi sebelumnya.

5. Mencetak Hasil Akhir:
   - Nilai hasil dari 2^n yang dihitung oleh fungsi pangkat(n) ditampilkan kepada pengguna.

6. Mengakhiri Program:
   - Setelah menampilkan hasil perhitungan, program selesai dan berhenti.

### 4. Program Sederhana untuk menghitung faktorial dari suatu bilangan n yang dimasukkan oleh pengguna.

### Source Code :
```go
package main

import "fmt"

// Deklarasi variabel global n untuk menyimpan input
var n int

// Fungsi rekursif untuk menghitung faktorial dari n
func faktorial(n int) int {
	if n == 0 || n == 1 {
		// Kondisi dasar: jika n == 0 atau n == 1, kembalikan 1
		return 1
	} else {
		// Jika n > 1, kembalikan n * faktorial(n-1)
		return n * faktorial(n-1)
	}
}

// Fungsi utama
func main() {
	// Meminta input dari pengguna
	fmt.Print("Masukkan nilai n: ")
	fmt.Scan(&n)

	// Mencetak hasil faktorial dari n
	fmt.Println("Hasil faktorial dari", n, "adalah", faktorial(n))
}
```
### Output:
![image](https://github.com/user-attachments/assets/3505af86-aa20-4edf-aa36-e182237852da)

### Full code Screenshot :
![carbon (17)](https://github.com/user-attachments/assets/ea332d62-146a-4e6a-ae0e-3756a223d264)

### Deskripsi Program : 
Program ini menghitung faktorial dari suatu bilangan n yang dimasukkan oleh pengguna. Faktorial dari n, dilambangkan sebagai n!, adalah hasil perkalian dari n hingga 1. Program ini menggunakan fungsi rekursif faktorial untuk menghitung nilai faktorial.

### Algoritma Program :
1. Memulai Program:
   - Deklarasikan variabel global n untuk menyimpan input pengguna.

2. Meminta Input dari Pengguna:
   - Tampilkan pesan: "Masukkan nilai n:".
   - Baca input dari pengguna dan simpan dalam variabel n.

3. Memanggil Fungsi Rekursif faktorial:
   - Panggil fungsi faktorial(n) untuk menghitung nilai faktorial dari n.

4. Fungsi Rekursif faktorial(n):
   - Kondisi Dasar: Jika n == 0 atau n == 1, kembalikan nilai 1 (karena 0! = 1 dan 1! = 1).
   - Langkah Rekursif: Jika n > 1, hitung n * faktorial(n-1). Proses ini akan berlanjut sampai mencapai kondisi dasar.

5. Mencetak Hasil Akhir:
   - Tampilkan hasil yang dikembalikan oleh fungsi faktorial(n).

6. Mengakhiri Program:
   - Setelah hasil ditampilkan, program berakhir.

### Cara Kerja Program :
1. Memulai Program:
   - Program dimulai dengan deklarasi variabel global n untuk menyimpan input dari pengguna.

2. Meminta Input dari Pengguna:
   - Program menampilkan pesan untuk memasukkan nilai n, yang kemudian disimpan dalam variabel global n.

3. Memanggil Fungsi Rekursif:
   - Program memanggil fungsi faktorial(n), yang menggunakan rekursi untuk menghitung nilai faktorial dari n.

4. Proses dalam Fungsi Rekursif faktorial(n):
   - Jika n adalah 0 atau 1, fungsi mengembalikan nilai 1 sebagai kondisi dasar.
   - Jika n lebih besar dari 1, fungsi mengembalikan hasil dari n * faktorial(n-1). Rekursi ini terus berjalan hingga mencapai kondisi dasar (n == 1), di mana hasil mulai dikembalikan ke setiap langkah rekursi sebelumnya.

5. Mencetak Hasil Akhir:
   - Nilai faktorial yang dihitung oleh fungsi faktorial(n) ditampilkan kepada pengguna.

6. Mengakhiri Program:
   - Setelah menampilkan hasil perhitungan, program selesai dan berhenti.


## Unguided

### 1. Deret fibonacci adalah sebuah deret dengan nilai suku ke-0 dan ke-1 adalah 0 dan 1, dan nilai suku ke-n selanjutnya adalah hasil penjumlahan dua suku sebelumnya. Secara umum dapat diformulasikan 𝑆𝑛 = 𝑆𝑛-1 + 𝑆𝑛-2 . Berikut ini adalah contoh nilai deret fibonacci hingga suku ke-10. Buatlah program yang mengimplementasikan fungsi rekursif pada deret fibonacci tersebut.

![image](https://github.com/user-attachments/assets/674623a5-4fa7-4c72-a0ed-fdc155b88e7e)

### Source Code :
```go
package main

import "fmt"

// Fungsi rekursif untuk menghitung nilai deret Fibonacci ke-n

func fibonacci(n int) int {
	// Jika n adalah 0 atau 1, kembalikan nilai n (basis kasus rekursi)
	if n <= 1 {
		return n
	}
	// Jika n > 1, panggil fungsi fibonacci secara rekursif
	return fibonacci(n-1) + fibonacci(n-2)
}

func main() {
	// Menampilkan header tabel dengan dekorasi ASCII
	fmt.Println("╔════════════════════════════════════════════════════════════════════╗")
	fmt.Println("║                     Tabel Deret Fibonacci                          ║")
	fmt.Println("╠═════════╦══════════════════════════════════════════════════════════╣")

	// Menampilkan baris pertama dengan indeks N (0 hingga 10)
	fmt.Printf("║  %-5s  ║", "N")
	for i := 0; i <= 10; i++ {
		fmt.Printf(" %-3d ", i) // Menampilkan indeks
	}
	fmt.Println("║") // Akhir dari baris indeks
	fmt.Println("╠═════════╬══════════════════════════════════════════════════════════╣")

	// Menampilkan baris kedua dengan nilai deret Fibonacci untuk setiap N
	fmt.Printf("║  %-5s  ║", "Sn")
	for i := 0; i <= 10; i++ {
		fmt.Printf(" %-3d ", fibonacci(i)) // Menampilkan nilai deret Fibonacci
	}
	fmt.Println("║") // Akhir dari baris nilai Fibonacci
	fmt.Println("╚═════════╩══════════════════════════════════════════════════════════╝")
}
```
### Output:
![image](https://github.com/user-attachments/assets/05662d87-5c6f-40c4-9c48-da1c8d7005e2)

### Full code Screenshot :
![carbon (8)](https://github.com/user-attachments/assets/c9a65fa4-dbac-45d5-857d-7e32c41ab020)

### Deskripsi Program : 
Program ini adalah program yang menampilkan deret Fibonacci hingga indeks ke-10 dalam format tabel menggunakan fungsi rekursif. Deret Fibonacci adalah urutan angka yang dimulai dari 0 dan 1, di mana setiap angka berikutnya adalah hasil penjumlahan dari dua angka sebelumnya.

### Algoritma Program :
1. Memulai Program:
   - Tampilkan header tabel menggunakan dekorasi ASCII untuk menampilkan informasi tentang deret Fibonacci.

2. Menampilkan Indeks N:
   - Buat baris pertama tabel yang menampilkan indeks N dari 0 hingga 10.

3. Menampilkan Nilai Deret Fibonacci:
   - Buat baris kedua tabel untuk menampilkan nilai dari deret Fibonacci untuk setiap indeks N yang dihitung menggunakan fungsi rekursif fibonacci.

4. Fungsi Rekursif fibonacci(n):
   - Kondisi Dasar: Jika n adalah 0 atau 1, kembalikan nilai n (basis kasus rekursi).
   - Langkah Rekursif: Jika n > 1, kembalikan hasil dari fibonacci(n-1) + fibonacci(n-2).

5. Mengakhiri Program:
   - Setelah tabel selesai ditampilkan, program berakhir.

### Cara Kerja Program :
1. Menampilkan Header Tabel:
   - Program dimulai dengan menampilkan header tabel yang berisi informasi tentang deret Fibonacci, menggunakan dekorasi ASCII untuk mempercantik tampilan.

2. Menampilkan Indeks N:
   - Baris pertama tabel menampilkan kolom untuk indeks N. Program menggunakan loop untuk mencetak nilai dari 0 hingga 10 dalam format yang rapi.

3. Menghitung dan Menampilkan Nilai Deret Fibonacci:
   - Baris kedua tabel menampilkan kolom untuk nilai deret Fibonacci (Sn). Program menggunakan loop yang sama untuk memanggil fungsi fibonacci(i) untuk setiap indeks dari 0 hingga 10, dan menampilkan hasilnya.

4. Proses dalam Fungsi Rekursif fibonacci(n):
   - Fungsi fibonacci(n) memeriksa nilai n. Jika n adalah 0 atau 1, fungsi langsung mengembalikan nilai n.
   - Jika n lebih besar dari 1, fungsi memanggil dirinya sendiri secara rekursif untuk menghitung fibonacci(n-1) dan fibonacci(n-2), hingga mencapai kondisi dasar.

5. Mengakhiri Program:
   - Setelah semua nilai Fibonacci dicetak dalam tabel, program menyelesaikan proses dan berhenti. Tabel ditutup dengan dekorasi ASCII yang sesuai.
  
### 2. Buatlah sebuah program yang digunakan untuk menampilkan pola bintang berikut ini dengan menggunakan fungsi rekursif. N adalah masukan dari user.

**Contoh masukan dan keluaran:**

![image](https://github.com/user-attachments/assets/e3611b71-5b44-49cc-a8e4-f77d632d176b)


### Source Code :
```go
package main

import "fmt"

// Fungsi untuk mencetak pola bintang dalam bentuk segitiga terbalik
func printStars(n int) {
	if n == 0 {
		return
	}

	// Cetak bintang sebanyak nilai n pada baris ini
	for i := 0; i < n; i++ {
		fmt.Print("*")
	}
	fmt.Println()

	// Panggil fungsi printStars dengan nilai n - 1
	printStars(n - 1)
}

func main() {
	var n int
	fmt.Print("Masukkan nilai N: ")
	fmt.Scanln(&n)
	printStars(n)
}
```
### Output:
![image](https://github.com/user-attachments/assets/70e4d930-9b15-4418-ab06-0d6c00ba4279)

### Full code Screenshot :
![carbon (9)](https://github.com/user-attachments/assets/c01c963a-3255-480a-96d6-e2466d2ce6d3)

### Deskripsi Program : 
Program ini adalah program yang mencetak pola bintang berbentuk segitiga terbalik berdasarkan input pengguna. Program menggunakan fungsi rekursif untuk mencetak pola ini, di mana setiap baris memiliki jumlah bintang yang berkurang satu dibandingkan baris sebelumnya.

### Algoritma Program :
1. Memulai Program:
   - Program dimulai dengan mendefinisikan fungsi printStars yang akan digunakan untuk mencetak pola bintang.

2. Menerima Input dari Pengguna:
   - Minta pengguna untuk memasukkan nilai n, yang akan digunakan sebagai tinggi segitiga terbalik.

3. Fungsi printStars(n):
   - Kondisi Dasar: Jika n adalah 0, fungsi akan mengembalikan kontrol ke pemanggil tanpa mencetak apa pun.
   - Mencetak Bintang: Dalam setiap panggilan fungsi, program mencetak n bintang pada baris saat ini.
   - Panggilan Rekursif:Fungsi memanggil dirinya sendiri dengan parameter n - 1 untuk mencetak baris berikutnya dengan jumlah bintang yang lebih sedikit.

4. Mengakhiri Program:
   - Setelah semua panggilan fungsi selesai, program berakhir.

### Cara Kerja Program :
1. Mendefinisikan Fungsi:
   - Fungsi printStars(n) didefinisikan untuk mencetak pola bintang.

2. Menerima Input dari Pengguna:
   - Minta pengguna untuk memasukkan nilai n melalui input, yang akan menentukan tinggi segitiga terbalik.

3. Proses dalam Fungsi printStars(n):
   - Jika n sama dengan 0, fungsi berhenti dan tidak melakukan apa-apa.
   - Jika n lebih besar dari 0:Fungsi mencetak bintang sebanyak n di baris saat ini.
   - Setelah itu, fungsi memanggil dirinya sendiri dengan n - 1, sehingga pada panggilan berikutnya, akan mencetak satu baris bintang lebih sedikit.

4. Mencetak Hasil Akhir:
   - Proses ini berlanjut hingga semua baris dari segitiga terbalik dicetak, dimulai dari n bintang hingga 1 bintang.

5. Mengakhiri Program:
   - Setelah seluruh pola tercetak, program selesai dan berhenti.


### 3. Buatlah program yang mengimplementasikan rekursif untuk menampilkan faktor bilangan dari suatu N, atau bilangan yang apa saja yang habis membagi N.

**Masukan terdiri dari sebuah bilangan bulat positif N.**

**Keluaran terdiri dari barisan bilangan yang menjadi faktor dari N (terurut dari 1 hingga N ya).**

**Contoh masukan dan keluaran:**

![image](https://github.com/user-attachments/assets/0dd755dd-2a90-4f7d-860c-98525aeffc9e)

### Source Code :
```go
package main

import "fmt"

// Fungsi utama
func main() {
	var n int
	fmt.Print("Masukkan bilangan bulat positif: ")
	fmt.Scanln(&n)

	// Memanggil fungsi faktor dan mencetak hasilnya
	fmt.Println("Faktor dari", n, "adalah:", faktor(n, 1))
}

// Fungsi rekursif untuk mencari faktor bilangan
func faktor(n, i int) []int {
	// Basis rekursi: jika i lebih besar dari n, kembalikan nil
	if i > n {
		return nil
	}

	// Jika i adalah faktor dari n, tambahkan i ke dalam slice hasil
	if n%i == 0 {
		return append([]int{i}, faktor(n, i+1)...)
	}

	// Jika i bukan faktor dari n, lanjutkan ke nilai berikutnya
	return faktor(n, i+1)
}
```

### Output:
![image](https://github.com/user-attachments/assets/dd74f8c5-227b-4372-8b4f-38408a3ac196)

### Full code Screenshot :
![carbon (10)](https://github.com/user-attachments/assets/6b4c0b7b-926b-4190-ab3f-53df83d226dc)

### Deskripsi Program : 
Program ini adalah program yang mencari semua faktor dari sebuah bilangan bulat positif yang diinput oleh pengguna. Program ini bekerja dengan menggunakan fungsi rekursif yang memeriksa setiap angka dari 1 hingga n (bilangan yang dimasukkan) untuk menentukan apakah angka tersebut adalah faktor dari n. Jika sebuah angka adalah faktor dari n, angka tersebut akan dimasukkan ke dalam daftar hasil dan ditampilkan.

### Algoritma Program :
1. Memulai Program:
   - Deklarasikan variabel n untuk menyimpan input dari pengguna.

2. Menerima Input dari Pengguna:
   - Tampilkan pesan untuk meminta pengguna memasukkan bilangan bulat positif.
   - Baca input dari pengguna dan simpan dalam variabel n.

3. Memanggil Fungsi faktor:
   - Panggil fungsi faktor(n, 1) untuk mencari faktor-faktor dari n, dimulai dari 1.

4. Fungsi Rekursif faktor(n, i):
   - Kondisi Basis Rekursi: Jika i lebih besar dari n, kembalikan nil untuk menandakan bahwa pencarian faktor telah selesai.

5. Pemeriksaan Faktor:
   - Jika n % i == 0, berarti i adalah faktor dari n. Tambahkan i ke dalam slice hasil dan lanjutkan pencarian dengan i + 1.
   - Jika n % i != 0, lanjutkan dengan memanggil fungsi faktor dengan parameter i + 1.

6. Mencetak Hasil:
   - Setelah mendapatkan semua faktor dari fungsi faktor, cetak hasilnya.

7. Mengakhiri Program:
   - Program berakhir setelah hasil faktor dicetak.

### Cara Kerja Program :
1. Menampilkan Permintaan Input:
   - Program meminta pengguna untuk memasukkan bilangan bulat positif melalui input.

2. Memanggil Fungsi faktor:
   - Setelah mendapatkan input, fungsi faktor dipanggil dengan parameter n (bilangan yang dimasukkan) dan 1 (awal pencarian faktor).

3. Proses dalam Fungsi faktor(n, i):
   - Fungsi memeriksa kondisi basis; jika i lebih besar dari n, pencarian berakhir.
   - Jika i adalah faktor dari n, i ditambahkan ke dalam slice hasil menggunakan append, dan fungsi dipanggil kembali dengan i + 1.
   - Jika i bukan faktor, fungsi hanya melanjutkan dengan i + 1.

4. Mengumpulkan Hasil:
   - Seluruh faktor yang ditemukan akan dikumpulkan dalam bentuk slice dan dikembalikan ke fungsi main.

5. Mencetak Hasil Akhir:
   - Hasil yang dikembalikan dari fungsi faktor dicetak dengan format yang sesuai, menampilkan semua faktor dari n.

6. Mengakhiri Program:
   - Setelah semua faktor dicetak, program selesai dan berhenti.



### 4. Buatlah program yang mengimplementasikan rekursif untuk menampilkan barisan bilangan tertentu.

**Masukan terdiri dari sebuah bilangan bulat positif N.**

**Keluaran terdiri dari barisan bilangan dari N hingga 1 dan kembali ke N.**

**Contoh masukan dan keluaran:**

![image](https://github.com/user-attachments/assets/8f7befc8-a4d8-400a-8255-922300f2e9de)

### Source Code :
```go
package main

import "fmt"

// Fungsi utama
func main() {
	var n int
	fmt.Print("Masukkan bilangan bulat positif N: ")
	fmt.Scanln(&n)

	// Memanggil fungsi rekursif untuk mencetak pola
	printRecursive(n)
}

// Fungsi rekursif untuk mencetak angka dari n hingga 1, lalu kembali dari 1 hingga n
func printRecursive(n int) {
	// Basis rekursi: jika n mencapai 1, cetak 1 dan hentikan rekursi
	if n == 1 {
		fmt.Print(n, " ")
		return
	}

	// Mencetak nilai n dalam urutan menurun
	fmt.Print(n, " ")

	// Memanggil fungsi secara rekursif dengan n-1
	printRecursive(n - 1)

	// Mencetak nilai n kembali dalam urutan menaik
	fmt.Print(n, " ")
}
```
### Output:

![image](https://github.com/user-attachments/assets/96a54c58-6137-4cc5-8b19-61cf8139341e)

### Full code Screenshot :

![carbon (11)](https://github.com/user-attachments/assets/86e645a1-e818-42a2-9560-41c5e8e908b3)

### Deskripsi Program : 
Program ini adalah program yang meminta input berupa bilangan bulat positif n dan menggunakan fungsi rekursif untuk mencetak urutan angka dari n hingga 1, lalu kembali dari 1 ke n. 
Program ini menampilkan pola simetris yang dimulai dari n ke 1 dan kembali ke n.

### Algoritma Program :
1. Memulai Program:
   - Deklarasikan variabel n untuk menyimpan input dari pengguna.

2. Menerima Input dari Pengguna:
   - Tampilkan pesan untuk meminta pengguna memasukkan bilangan bulat positif N.
   - Baca input dari pengguna dan simpan dalam variabel n.

3. Memanggil Fungsi Rekursif printRecursive:
   - Panggil fungsi printRecursive(n) untuk mulai mencetak pola angka.

4. Fungsi Rekursif printRecursive(n):
   - Kondisi Basis Rekursi: Jika n mencapai 1, cetak angka 1 dan hentikan rekursi dengan return.

5. Mencetak Angka Menurun:
   - Cetak angka n diikuti dengan spasi.
   - Panggil fungsi printRecursive(n - 1) untuk melanjutkan proses pencetakan dengan nilai yang lebih kecil.

6. Mencetak Angka Menaik:
   - Setelah kembali dari panggilan rekursif, cetak angka n lagi, menciptakan efek pantulan.

7. Mengakhiri Program:
   - Program berakhir setelah semua angka tercetak dalam urutan yang diinginkan.

### Cara Kerja Program :
1. Menampilkan Permintaan Input:
   - Program meminta pengguna untuk memasukkan bilangan bulat positif.

2. Memanggil Fungsi printRecursive:
   - Setelah mendapatkan input, fungsi printRecursive dipanggil dengan parameter n untuk mulai mencetak pola angka.

3. Proses dalam Fungsi printRecursive(n):
   - Fungsi pertama-tama memeriksa apakah n sama dengan 1. Jika ya, angka 1 dicetak, dan fungsi mengembalikan kontrol ke pemanggil.
   - Jika n lebih besar dari 1, fungsi mencetak n dan kemudian memanggil dirinya sendiri dengan n - 1.
   - Setelah panggilan rekursif kembali, angka n dicetak lagi, menghasilkan pola yang diinginkan.

4. Mencetak Hasil Akhir:
   - Proses ini berlanjut hingga semua angka dari n hingga 1 dan kembali ke n dicetak dengan urutan yang benar.

5. Mengakhiri Program:
   - Setelah seluruh pola dicetak, program selesai dan berhenti.

### 5. Buatlah program yang mengimplementasikan rekursif untuk menampilkan barisan bilangan ganjil.

**Masukan terdiri dari sebuah bilangan bulat positif N.**

**Keluaran terdiri dari barisan bilangan ganjil dari 1 hingga N.**

**Contoh masukan dan keluaran:**

![image](https://github.com/user-attachments/assets/a7cb62f2-1d92-47b4-98e4-26de25472d8c)

### Source Code :
```go
package main

import "fmt"

// Fungsi utama
func main() {
	fmt.Println("╔════════════════════════════════╗")
	fmt.Println("║         Bilangan Ganjil        ║")
	fmt.Println("╚════════════════════════════════╝")

	var n int
	fmt.Print("Masukkan bilangan bulat positif N: ")
	fmt.Scanln(&n)

	// Menampilkan header tabel
	fmt.Printf("\nBilangan ganjil dari 1 hingga %d:\n", n)
	fmt.Println("╔════════════════════════════════════════╗")
	printOddNumbers(1, n, 5) // Memanggil fungsi untuk menampilkan bilangan ganjil dengan 5 kolom per baris
	fmt.Println("╚════════════════════════════════════════╝")
}

// Fungsi untuk mencetak bilangan ganjil dari 1 hingga n dalam format tabel
func printOddNumbers(i, n, columns int) {
	count := 0 // Variabel untuk menghitung jumlah angka pada baris saat ini
	for ; i <= n; i += 2 {
		fmt.Printf("║ %-6d", i) // Menampilkan bilangan ganjil dengan lebar 6 karakter
		count++

		// Jika sudah mencapai jumlah kolom, pindah ke baris berikutnya
		if count%columns == 0 {
			fmt.Print("║\n") // Menutup baris dan mulai yang baru
		}
	}

	// Menutup baris jika kolom belum penuh di akhir loop
	if count%columns != 0 {
		for count%columns != 0 {
			fmt.Print("║       ") // Tambahkan ruang kosong jika kolom belum penuh
			count++
		}
		fmt.Println("║") // Menutup baris terakhir setelah kolom penuh
	}
}
```
### Output:
![image](https://github.com/user-attachments/assets/a1e19ca4-3925-402c-b224-efaf33f3fc59)

### Full code Screenshot :
![carbon (12)](https://github.com/user-attachments/assets/0d815ac7-71c8-420b-b012-de6d144c6be7)

### Deskripsi Program : 
Program ini adalah program yang mencetak bilangan ganjil dari 1 hingga n dalam format tabel dengan 5 kolom per baris. 
Dengan menggunakan `fungsi printOddNumbers`, program memastikan bahwa tabel rapi, dan baris yang tidak penuh akan diberi kolom kosong di akhir.

### Algoritma Program :
Memulai Program:

Tampilkan judul program dengan dekorasi ASCII.
Menerima Input dari Pengguna:

Deklarasikan variabel n untuk menyimpan input dari pengguna.
Tampilkan pesan untuk meminta pengguna memasukkan bilangan bulat positif N.
Baca input dari pengguna dan simpan dalam variabel n.
Menampilkan Header Tabel:

Cetak header tabel yang menjelaskan isi tabel (bilangan ganjil dari 1 hingga N).
Memanggil Fungsi printOddNumbers:

Panggil fungsi printOddNumbers(1, n, 5) untuk mencetak bilangan ganjil dari 1 hingga n, dengan 5 kolom per baris.
Fungsi printOddNumbers(i, n, columns):

Inisialisasi:
Variabel count digunakan untuk menghitung jumlah bilangan ganjil yang telah dicetak pada baris saat ini.
Pencetakan Bilangan Ganjil:
Dalam loop, mulai dari i dan tambahkan 2 setiap iterasi untuk mendapatkan bilangan ganjil.
Cetak setiap bilangan ganjil dengan lebar 6 karakter.
Setelah mencetak bilangan, tingkatkan count.
Pengaturan Kolom:
Jika count mencapai jumlah kolom yang ditentukan (columns), tutup baris dan mulai baris baru.
Menutup Baris Terakhir:
Jika loop berakhir tetapi kolom belum penuh, tambahkan ruang kosong untuk kolom yang tersisa dan tutup baris terakhir.
Mengakhiri Program:

Program berakhir setelah semua bilangan ganjil dicetak dalam format tabel.

### Cara Kerja Program :
Menampilkan Judul Program:

Program dimulai dengan menampilkan judul "Bilangan Ganjil" dalam format tabel.
Input dari Pengguna:

Program meminta pengguna untuk memasukkan bilangan bulat positif N, yang akan digunakan sebagai batas atas dalam pencetakan bilangan ganjil.
Menampilkan Tabel Bilangan Ganjil:

Setelah menerima input, program mencetak header tabel yang menunjukkan rentang bilangan ganjil yang akan ditampilkan.
Proses dalam Fungsi printOddNumbers:

Fungsi memulai dari 1 dan mencetak setiap bilangan ganjil hingga mencapai n.
Setiap bilangan dicetak dalam format yang telah ditentukan, dan program memeriksa jumlah kolom untuk memastikan tampilan tabel tetap rapi.
Fungsi juga menangani situasi di mana tidak semua kolom terisi pada baris terakhir dengan menambahkan ruang kosong yang diperlukan.
Mencetak Hasil Akhir:

Setelah semua bilangan ganjil dicetak, program menutup tabel dan selesai.
Mengakhiri Program:

Program berakhir dengan menampilkan hasil pencetakan dalam format tabel.

### 6. Buatlah program yang mengimplementasikan rekursif untuk mencari hasil pangkat dari dua buah bilangan.

**Masukan terdiri dari bilangan bulat x dan y.**

**Keluaran terdiri dari hasil x dipangkatkan y.**

**Catatan: diperbolehkan menggunakan asterik "*", tapi dilarang menggunakan import "math".**

**Contoh masukan dan keluaran:**

![image](https://github.com/user-attachments/assets/ef7d2146-26df-4760-8882-a11e4a87bfc5)

### Source Code :
```go
package main

import "fmt"

// Fungsi untuk menghitung pangkat x^y secara rekursif
func power(x, y int) int {
	// Basis rekursi: jika y == 0, maka hasilnya adalah 1
	if y == 0 {
		return 1
	}
	// Menghitung x * power(x, y-1)
	return x * power(x, y-1)
}

// Fungsi utama
func main() {
	var x, y int

	// Header Program
	fmt.Println("=========================================")
	fmt.Println("          PROGRAM KALKULATOR PANGKAT     ")
	fmt.Println("=========================================")

	// Input pengguna untuk bilangan x
	fmt.Print("Masukkan bilangan bulat (x): ")
	fmt.Scanln(&x)

	// Input pengguna untuk pangkat y
	fmt.Print("Masukkan pangkat (y): ")
	fmt.Scanln(&y)
	fmt.Println("-----------------------------------------")

	// Kalkulasi hasil pangkat
	result := power(x, y)

	// Menampilkan hasil
	fmt.Printf("Hasil dari %d ^ %d adalah: %d\n", x, y, result)
	fmt.Println("=========================================")
}
```
### Output:
![image](https://github.com/user-attachments/assets/1a88be65-1c21-4291-8539-3369fe481b6a)

### Full code Screenshot :
![carbon (13)](https://github.com/user-attachments/assets/b8ff7055-9beb-4cdc-a5f6-21e0c606fdac)

### Deskripsi Program : 
Program ini adalah program yang menggunakan fungsi rekursif power untuk menghitung `x^y` dan meminta input x dan y dari pengguna. 
Hasil akhir perhitungan ditampilkan dalam format yang rapi di layar. 
Program ini menekankan penggunaan rekursi untuk menghitung eksponen.

### Algoritma Program :
Memulai Program:

Tampilkan header program yang menjelaskan fungsinya sebagai kalkulator pangkat.
Menerima Input dari Pengguna:

Deklarasikan variabel x dan y untuk menyimpan input dari pengguna.
Tampilkan pesan untuk meminta pengguna memasukkan bilangan bulat x.
Baca input dari pengguna dan simpan dalam variabel x.
Tampilkan pesan untuk meminta pengguna memasukkan pangkat y.
Baca input dari pengguna dan simpan dalam variabel y.
Menghitung Hasil Pangkat:

Panggil fungsi power(x, y) untuk menghitung hasil dari 𝑥^𝑦.
Menampilkan Hasil:

Tampilkan hasil perhitungan dalam format yang jelas dan mudah dibaca.
Mengakhiri Program:

Program berakhir setelah menampilkan hasil perhitungan.

### Cara Kerja Program :
Menampilkan Header Program:

Program dimulai dengan menampilkan judul "PROGRAM KALKULATOR PANGKAT" yang memberikan informasi tentang fungsi program.
Input dari Pengguna:

Pengguna diminta untuk memasukkan bilangan bulat x yang merupakan basis dari pangkat.
Selanjutnya, pengguna diminta untuk memasukkan pangkat y yang akan diterapkan pada x.
Menghitung Hasil Pangkat:

Program menggunakan fungsi rekursif power untuk menghitung hasil pangkat:
Basis Rekursi: Jika y sama dengan 0, fungsi mengembalikan 1 (karena 𝑥^0 = 1).
Jika y lebih besar dari 0, fungsi akan mengalikan x dengan hasil dari power(x, y-1), yang berarti menghitung 𝑥^𝑦− 1.
Menampilkan Hasil Akhir:

Setelah menghitung hasil, program mencetak hasil dari perhitungan dalam format yang jelas, menunjukkan nilai x, y, dan hasilnya.
Mengakhiri Program:

Program berakhir setelah menampilkan hasil, memberikan pengalaman interaktif kepada pengguna.


## Kesimpulan 
Berdasarkan hasil praktikum, dapat disimpulkan bahwa pemahaman tentang konsep rekursif sangat penting dalam memecahkan masalah yang berulang.

1. Penggunaan rekursif mempermudah penyelesaian masalah dengan struktur hierarkis atau yang dapat dibagi menjadi sub-masalah kecil, seperti perhitungan faktorial dan deret Fibonacci.
2. Penerapan rekursif perlu memperhatikan kondisi dasar yang tepat agar program tidak mengalami infinite loop atau stack overflow.
3. Dengan memahami kapan menggunakan rekursif atau iterasi, mahasiswa dapat menulis kode yang lebih efisien dan sesuai dengan kebutuhan program.

## Daftar Pustaka
[1] A. A. A. Donovan and B. W. Kernighan, *The Go Programming Language*. Boston, MA: Addison-Wesley, 2015.

[2] W. Kennedy, B. Ketelsen, and E. St. Martin, *Go in Action*. Greenwich, CT: Manning Publications, 2016.
