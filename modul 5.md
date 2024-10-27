### 1. Deret fibonacci adalah sebuah deret dengan nilai suku ke-0 dan ke-1 adalah 0 dan 1, dan nilai suku ke-n selanjutnya adalah hasil penjumlahan dua suku sebelumnya. Secara umum dapat diformulasikan 𝑆𝑛 = 𝑆𝑛+1 + 𝑆𝑛+2 . Berikut ini adalah contoh nilai deret fibonacci hingga suku ke-10. Buatlah program yang mengimplementasikan fungsi rekursif pada deret fibonacci tersebut.

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
Program ini adalah program yang menampilkan deret Fibonacci hingga indeks ke-10 dalam format tabel menggunakan fungsi rekursif. 
Deret Fibonacci adalah urutan angka yang dimulai dari 0 dan 1, di mana setiap angka berikutnya adalah hasil penjumlahan dari dua angka sebelumnya.

### Algoritma Program :
1. Deklarasi Fungsi fibonacci:
   - Fungsi ini menerima parameter n bertipe integer.
   - Jika n adalah 0 atau 1, fungsi mengembalikan nilai n.
   - Jika n > 1, maka fungsi mengembalikan `hasil penjumlahan dari fibonacci(n-1) + fibonacci(n-2)`.

2. Menampilkan Header Tabel:
   - Cetak garis atas tabel dengan dekorasi ASCII.
   - Cetak judul tabel `“Tabel Deret Fibonacci”`.
   - Cetak garis pemisah antara header dan konten.

3. Menampilkan Baris Indeks N:
   - Cetak label `"N"` sebagai header kolom.
   - Untuk i dari 0 hingga 10, cetak nilai i dalam satu baris sebagai indeks deret.

4. Menampilkan Baris Nilai Fibonacci Sn:
   - Cetak label `Sn` sebagai header kolom untuk baris kedua.
   - Untuk setiap nilai i dari 0 hingga 10, panggil `fungsi fibonacci(i)` untuk menghitung nilai deret Fibonacci pada indeks i.
   - Cetak `hasil perhitungan fibonacci(i)` dalam satu baris.

5. Menampilkan Footer Tabel:
   - Cetak garis bawah tabel dengan dekorasi ASCII untuk menutup tampilan.

### Cara Kerja Program :
1. Eksekusi Dimulai dari Fungsi `main`:
   - Program pertama-tama mengeksekusi fungsi `main`, yang berisi seluruh logika pembuatan tabel dan tampilan deret Fibonacci.

2. Mencetak Header Tabel:
   - Karakter ASCII digunakan untuk membuat tampilan dekoratif pada tabel.
   - Judul “Tabel Deret Fibonacci” dicetak di tengah-tengah untuk memberi konteks kepada pengguna.

3. Menampilkan Baris Pertama (Indeks N):
   - Program menggunakan loop `for` untuk mencetak angka dari 0 hingga 10, sebagai indeks `N` di tabel.
   - Setiap angka dicetak dalam format jarak tertentu untuk menjaga tampilan tabel tetap rapi.

4. Menghitung dan Menampilkan Nilai Fibonacci (Baris Kedua Sn):
   - Program menggunakan loop `for` untuk menghitung nilai Fibonacci dari setiap indeks `N` menggunakan fungsi `fibonacci`.
   - Fungsi fibonacci dipanggil secara rekursif untuk menghitung nilai deret Fibonacci pada indeks tertentu.
   - Misalnya, `fibonacci(5)` akan menghitung nilai Fibonacci ke-5 dengan memanggil dirinya sendiri sampai mencapai nilai dasar `fibonacci(0)` dan `fibonacci(1)`.
   - Setiap hasil dari `fibonacci(i)` dicetak di tabel sebagai baris kedua Sn.

5. Menampilkan Footer Tabel:
   - Program menutup tabel dengan dekorasi ASCII agar terlihat rapi dan terstruktur.
     
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
Program ini adalah program yang mencetak pola bintang berbentuk segitiga terbalik berdasarkan input pengguna. 
Program menggunakan fungsi rekursif untuk mencetak pola ini, di mana setiap baris memiliki jumlah bintang yang berkurang satu dibandingkan baris sebelumnya.

### Algoritma Program :
1. Fungsi `printStars`:
   - Menerima parameter `n`, yang menentukan jumlah bintang yang akan dicetak pada baris saat ini.
   - Jika `n` sama dengan 0, fungsi berhenti (basis kasus rekursi).
   - Jika `n > 0`, cetak bintang sebanyak `n` pada baris ini, kemudian pindah ke baris berikutnya.
   - Panggil fungsi `printStars` kembali dengan nilai `n-1` untuk mencetak baris berikutnya dengan satu bintang lebih sedikit.

2. Fungsi `main`:
   - Menerima input dari pengguna, yaitu nilai `n`, yang menentukan tinggi segitiga terbalik.
   - Memanggil fungsi `printStars` dengan parameter `n` untuk memulai pencetakan pola bintang.

### Cara Kerja Program :
1. Eksekusi Dimulai dari Fungsi `main`:
   - Program meminta pengguna memasukkan nilai `n` yang mewakili jumlah bintang pada baris pertama segitiga.
   - Nilai `n` diteruskan ke fungsi `printStars` untuk memulai pencetakan pola bintang.

2. Fungsi Rekursif printStars:
   - Jika `n == 0`, fungsi berhenti, dan rekursi berakhir.
   - Jika `n > 0`, fungsi mencetak bintang sebanyak `n` pada baris saat ini.
   - Kemudian, fungsi memanggil dirinya sendiri dengan nilai `n-1`, mengurangi jumlah bintang di setiap baris berikutnya hingga mencapai nol.

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
Program ini adalah program yang mencari semua faktor dari sebuah bilangan bulat positif yang diinput oleh pengguna. 
Program ini bekerja dengan menggunakan fungsi rekursif yang memeriksa setiap angka dari 1 hingga n (bilangan yang dimasukkan) untuk menentukan apakah angka tersebut adalah faktor dari n. Jika sebuah angka adalah faktor dari n, angka tersebut akan dimasukkan ke dalam daftar hasil dan ditampilkan.

### Algoritma Program :
1. Input Bilangan:
   - Minta pengguna untuk memasukkan bilangan bulat positif n yang faktornya ingin dicari.

2. Panggil Fungsi Rekursif faktor:
   - Panggil fungsi faktor dengan dua parameter:
     - n, bilangan yang faktornya akan dicari.
     - i, yang dimulai dari 1 sebagai nilai awal pemeriksaan faktor.

3. Fungsi faktor:
   - Fungsi ini mencari faktor dari bilangan n secara rekursif.

4. Basis Rekursi:
   - Jika `i > n`, fungsi akan mengembalikan nil, yang menandakan akhir dari rekursi.

5. Pemeriksaan Faktor:
   - Jika `n % i == 0`, maka i adalah faktor dari n, dan ditambahkan ke dalam daftar hasil.
   - Panggil faktor kembali dengan nilai `i+1` untuk melanjutkan pencarian faktor hingga mencapai batas n.

6. Cetak Hasil:
   - Setelah semua faktor ditemukan dan dikumpulkan dalam daftar, cetak daftar faktor tersebut ke layar.

### Cara Kerja Program :
Fungsi main:

Fungsi utama main menerima input dari pengguna berupa bilangan bulat positif n.
Setelah menerima input, fungsi memanggil faktor(n, 1) untuk menghitung semua faktor n dimulai dari i=1.
Hasil dari faktor kemudian dicetak sebagai daftar faktor dari n.
Fungsi faktor:

Fungsi faktor bekerja secara rekursif untuk memeriksa setiap nilai i dari 1 hingga n.
Pemeriksaan Faktor:
Jika i adalah faktor dari n (artinya n % i == 0), maka i ditambahkan ke dalam hasil menggunakan fungsi append.
Jika i bukan faktor dari n, fungsi akan melanjutkan dengan nilai i+1.
Rekursi:
Setelah memeriksa apakah i adalah faktor atau bukan, fungsi faktor akan memanggil dirinya sendiri dengan faktor(n, i+1).
Ketika i > n, fungsi mengembalikan nil untuk mengakhiri rekursi.

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
1. Menerima Input:
   - Minta pengguna untuk memasukkan bilangan n.

2. Panggil `printRecursive` dengan Parameter n:
   - Fungsi `printRecursive` digunakan untuk mencetak urutan angka dari n ke 1, dan kembali lagi ke n.
     - Fungsi Rekursif `printRecursive(n)`:
       - Basis Rekursi:
         - Jika n adalah 1, cetak 1 dan akhiri rekursi dengan return.
       - Langkah Rekursif:
         - Cetak nilai n, lalu panggil `printRecursive(n - 1)` untuk melanjutkan ke angka berikutnya dalam urutan menurun.
         - Setelah kembali dari pemanggilan rekursif, cetak n lagi untuk menghasilkan urutan menaik.

### Cara Kerja Program :
1. Fungsi main:
   - Fungsi utama main meminta pengguna untuk memasukkan bilangan bulat positif n, yang akan menentukan jumlah baris segitiga terbalik yang akan dicetak.
   - Setelah menerima input, fungsi memanggil `printStars(n)` untuk mencetak pola segitiga terbalik bintang berdasarkan nilai n.

2. Fungsi printStars:
   - Fungsi `printStars(n int)` menerima satu parameter n, yang merupakan jumlah bintang yang akan dicetak pada baris pertama.

3. Basis Rekursi:
   - Jika n sama dengan 0, fungsi mengembalikan (exit) tanpa mencetak apa pun. Ini merupakan kondisi akhir yang menghentikan rekursi.

4. Pencetakan Bintang:
   - Fungsi melakukan `looping dari 0 hingga n`, mencetak karakter bintang (*) sebanyak n kali pada baris saat ini.
   - Setelah mencetak bintang untuk baris tersebut, fungsi mencetak newline `(fmt.Println())` untuk memindahkan ke baris berikutnya.

5. Rekursi:
   - Setelah mencetak bintang untuk baris saat ini, fungsi memanggil dirinya sendiri dengan parameter `n - 1`, yang berarti akan mencetak baris berikutnya dengan satu bintang lebih sedikit.
   - Proses ini berlanjut hingga n mencapai 0, pada titik yang mana fungsi tidak lagi mencetak bintang.

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
1. Menerima Input dari Pengguna:
   - Program meminta pengguna memasukkan bilangan bulat positif n.
   - Panggil printOddNumbers(1, n, 5):
     - Fungsi ini dipanggil dengan parameter:
       - 1 sebagai bilangan awal yang akan dicetak.
       - n sebagai batas maksimum bilangan ganjil.
       - 5 sebagai jumlah kolom per baris.
   - Fungsi `printOddNumbers(i, n, columns)`:
     - Inisialisasi variabel count untuk menghitung jumlah angka pada baris saat ini.
     - Gunakan loop for untuk mencetak bilangan ganjil dari 1 hingga n dengan penambahan 2 pada setiap iterasi `(i += 2)`.
     - Setiap bilangan ganjil dicetak dengan lebar tetap 6 karakter.
     - Jika jumlah angka pada baris (count) sudah mencapai jumlah kolom yang ditentukan (5 kolom), maka program memulai baris baru.
   - Mengisi Kolom yang Kosong:
     - Jika baris terakhir belum penuh, maka tambahkan ruang kosong hingga kolom penuh sebelum menutup baris.

### Cara Kerja Program :
1. Fungsi main:
   - Fungsi utama main mulai dengan mencetak header program `"Bilangan Ganjil"` dalam bentuk dekorasi ASCII.
   - Fungsi kemudian meminta pengguna untuk memasukkan bilangan bulat positif n, yang akan menjadi batas maksimum untuk bilangan ganjil yang akan dicetak.
   - Setelah menerima input, fungsi memanggil `printOddNumbers(1, n, 5)`, untuk mencetak bilangan ganjil dari 1 hingga n dengan 5 kolom per baris.
   - Program mencetak hasil dalam format tabel yang rapi dan terstruktur.

2. Fungsi printOddNumbers:
   - Fungsi `printOddNumbers(i, n, columns)` menerima tiga parameter: `i (bilangan awal), n (bilangan batas atas), dan columns (jumlah kolom per baris).`

3. Inisialisasi:
   - Fungsi ini menginisialisasi variabel count untuk menghitung jumlah bilangan ganjil yang sudah dicetak pada baris saat ini.

4. Looping dan Pencetakan Bilangan Ganjil:
   - Fungsi melakukan looping dari i hingga n, dengan penambahan 2 di setiap iterasi (`i += 2`), untuk mencetak bilangan ganjil.
   - Setiap bilangan ganjil dicetak dengan format yang ditentukan (║ %-6d) untuk memastikan lebar yang konsisten.
   - Pindah ke Baris Berikutnya:
     - Setelah mencetak satu bilangan, fungsi memeriksa apakah jumlah bilangan pada baris (count) sudah mencapai jumlah kolom yang ditentukan (columns).
     - Jika count adalah kelipatan dari columns, fungsi mencetak baris baru (║\n) untuk memulai baris baru.
   - Mengisi Kolom Kosong:
     - Setelah loop selesai, jika baris terakhir belum penuh (jumlah bilangan ganjil kurang dari jumlah kolom yang diinginkan), fungsi menambahkan ruang kosong (║ ) hingga kolom penuh.
     - Baris terakhir ditutup dengan ║, menyelesaikan tabel.

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
1. Header Program:
   - Cetak header atau judul program.
     
2. Input dari Pengguna:
   - Minta pengguna memasukkan bilangan bulat x sebagai dasar.
   - Minta pengguna memasukkan bilangan bulat y sebagai pangkat.

3. Panggil Fungsi power(x, y):
   - Fungsi ini menghitung x^y secara rekursif.
   - Jika `y == 0`, fungsi langsung mengembalikan nilai 1.
   - Jika `y > 0`, fungsi memanggil `power(x, y-1)` untuk mengalikan x hingga nilai y berkurang menjadi 0.

4. Cetak Hasil:
   - Tampilkan hasil x^y kepada pengguna.

### Cara Kerja Program :
1. Fungsi main:
   - Fungsi utama main menerima input dari pengguna berupa dua bilangan bulat: x (bilangan dasar) dan y (pangkat).
   - Setelah menerima input, fungsi mencetak header program untuk memberikan konteks tentang apa yang akan dilakukan oleh program.
   - Fungsi kemudian memanggil `power(x, y)` untuk menghitung nilai `x^y` secara rekursif.
   - Hasil dari kalkulasi tersebut kemudian dicetak sebagai output, menampilkan hasil perhitungan pangkat ke pengguna.

2. Fungsi power:
   - Fungsi power bekerja secara rekursif untuk menghitung nilai pangkat dari x yang dipangkatkan dengan y.

3. Basis Rekursi:
   - Basis rekursi diatur sedemikian rupa sehingga jika nilai y sama dengan 0, fungsi akan mengembalikan nilai 1 (karena `x^0` selalu sama dengan `1`).

4. Rekursi:
   - Jika y lebih dari 0, fungsi melakukan penghitungan dengan memanggil dirinya sendiri: `x * power(x, y-1)`.
   - Setiap pemanggilan rekursif mengurangi nilai y hingga mencapai 0, sehingga fungsi power dapat menghitung nilai pangkat secara bertahap.

5. Pengembalian Hasil:
   - Setelah mencapai basis rekursi dan semua pemanggilan selesai, fungsi mengembalikan hasil perhitungan ke pemanggilan sebelumnya, hingga akhirnya hasil akhir (`nilai x^y`) dapat ditampilkan kepada pengguna.
