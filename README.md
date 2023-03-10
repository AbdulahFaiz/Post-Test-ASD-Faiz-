# Post-Test-ASD-Faiz-

Nama  : Abdulah Faiz Tedjo Putro
NIM   : 2209116026
Kelas : Sistem Informasi A 2022

![image](https://user-images.githubusercontent.com/121870536/224312914-574df8c1-c473-4d6d-acb6-764ac1ec266a.png)

import os : digunakan untuk mengimpor modul os yang berisi fungsi-fungsi untuk berinteraksi dengan sistem operasi yang digunakan.
os.system("cls")  : digunakan untuk membersihkan konsol (terminal) pada sistem operasi Windows dengan menggunakan perintah "cls" (clear screen).

def merge_sort(arr):    : mendefinisikan fungsi merge_sort yang menerima parameter arr (array) untuk diurutkan menggunakan algoritma merge sort.
if len(arr) <= 1: return arr  : merupakan kondisi dasar dari rekursi merge sort, dimana jika panjang array arr sama dengan atau kurang dari 1 maka langsung dikembalikan.
tengah = len(arr) // 2    : digunakan untuk menentukan indeks tengah dari array arr.
kiri = arr[:tengah]   : membagi array arr menjadi 2 bagian, yaitu array kiri dan kanan.
kanan = arr[tengah:]    : membagi array arr menjadi 2 bagian, yaitu array kiri dan kanan.
kiri = merge_sort(kiri)   : memanggil fungsi merge sort rekursif untuk mengurutkan array kiri.
kanan = merge_sort(kanan)   : memanggil fungsi merge sort rekursif untuk mengurutkan array kanan.
return merge(kiri, kanan)   : memanggil fungsi merge untuk menggabungkan dan mengurutkan kembali array kiri dan kanan.

![image](https://user-images.githubusercontent.com/121870536/224314470-fd159b68-3cf6-4423-afbf-639881e863a6.png)

return merge(kiri, kanan)   : memanggil fungsi merge untuk menggabungkan dan mengurutkan kembali array kiri dan kanan.
def merge(kiri, kanan):   : mendefinisikan fungsi merge yang menerima 2 parameter array, yaitu kiri dan kanan, untuk menggabungkan dan mengurutkan kembali array kiri dan kanan.
hasil = []    : membuat array kosong hasil yang akan digunakan untuk menampung hasil penggabungan array kiri dan kanan.
while kiri and kanan:   : melakukan pengulangan selama array kiri dan kanan tidak kosong.
if kiri[0] < kanan[0]:    : membandingkan nilai pertama pada array kiri dan kanan, jika nilai pada kiri lebih kecil maka dimasukkan ke dalam array hasil.
hasil.append(kiri.pop(0))   : jika nilai pada kiri lebih kecil, maka nilai tersebut dihapus dan dimasukkan ke dalam array hasil.
else: hasil.append(kanan.pop(0))    : jika nilai pada kanan lebih kecil, maka nilai tersebut dihapus dan dimasukkan ke dalam array hasil.
if kiri: hasil += kiri    : menambahkan sisa nilai pada array kiri ke dalam array hasil.
elif kanan: hasil += kanan    : menambahkan sisa nilai pada array kanan ke dalam array hasil.
return hasil    : mengembalikan array hasil yang sudah terurut.

![image](https://user-images.githubusercontent.com/121870536/224314982-4620b58e-f691-4011-b761-377c23c135e4.png)

def jumpSearch(arr, x):  : Mendefinisikan sebuah fungsi bernama jumpSearch dengan dua parameter, yaitu arr yang merupakan sebuah array, dan x yang merupakan sebuah nilai.
n = len(arr)  : Mendefinisikan variabel n yang menyimpan panjang array arr.
step = int(n ** 0.5)  : Mendefinisikan variabel step yang diinisialisasi dengan nilai akar kuadrat dari n yang telah dibulatkan ke bawah.
prev = 0  : Mendefinisikan variabel prev yang diinisialisasi dengan nilai 0.
while arr[min(step, n) - 1] < x:  : Melakukan perulangan while selama nilai elemen di indeks min(step, n) - 1 pada array arr masih lebih kecil dari nilai x. Nilai step akan terus di-increment dengan nilai akar kuadrat dari n hingga nilai elemen pada indeks min(step, n) - 1 pada array arr lebih besar atau sama dengan nilai x atau nilai prev melebihi atau sama dengan n.
prev = step : Mengupdate nilai prev dengan nilai step.
step += int(n ** 0.5)   : Mengupdate nilai step dengan nilai akar kuadrat dari n yang telah dibulatkan ke bawah.
if prev >=n:  : Mengecek apakah nilai prev sudah melebihi atau sama dengan n. Jika iya, maka fungsi akan mengembalikan nilai -1.
while arr[prev] < x:  : Melakukan perulangan while selama nilai elemen pada indeks prev pada array arr masih lebih kecil dari nilai x. Variabel prev akan terus di-increment hingga nilai elemen pada indeks prev pada array arr lebih besar atau sama dengan nilai x atau nilai prev sudah melebihi atau sama dengan min(step, n).
prev += 1 : Mengupdate nilai prev dengan nilai prev + 1.
if prev == min(step, n):  : Mengecek apakah nilai prev sudah melebihi atau sama dengan min(step, n). Jika iya, maka fungsi akan mengembalikan nilai -1.
return -1   : Mengembalikan nilai -1 jika nilai x tidak ditemukan pada array arr.
if arr[prev] == x:  : Mengecek apakah nilai elemen pada indeks prev pada array arr sama dengan nilai x. Jika iya, maka fungsi akan mengembalikan nilai prev.
return prev   : Mengembalikan nilai prev jika nilai x ditemukan pada array arr pada indeks prev.
return -1   : Mengembalikan nilai -1 jika nilai x tidak ditemukan pada array arr.

![image](https://user-images.githubusercontent.com/121870536/224316860-0db9a3fe-5df7-4b0b-8332-b51bde26f257.png)

def sort_nested_dataset(dataset) :  : mendefinisikan sebuah fungsi bernama sort_nested_dataset dengan parameter berupa dataset
sorted = []   : inisialisasi variabel sorted sebagai sebuah array kosong untuk menampung elemen-elemen dari dataset yang berupa string.
nested = {}   : inisialisasi variabel nested sebagai sebuah dictionary kosong untuk menampung elemen-elemen dari dataset yang berupa array dan akan diurutkan dengan menggunakan fungsi merge_sort.
for i in range(len(dataset)):   : loop sebanyak panjang dataset, dimulai dari indeks 0.
if type(dataset[i]) == str :    : jika elemen ke-i dari dataset berupa string,
sorted.append(dataset[i])   : tambahkan elemen tersebut ke dalam array sorted.
else :    : jika elemen ke-i dari dataset berupa array,
nested[i] = merge_sort(dataset[i])    : urutkan elemen tersebut menggunakan fungsi merge_sort, lalu tambahkan ke dalam dictionary nested dengan kunci berupa indeks elemen tersebut di dalam dataset.
sorted = merge_sort(sorted)   : urutkan array sorted menggunakan fungsi merge_sort.
for i in nested :   : loop sebanyak kunci yang ada di dalam dictionary nested.
sorted.insert(i, nested[i])   : sisipkan elemen di dalam nested pada indeks yang sesuai dengan kuncinya di dalam array sorted.
return sorted   : mengembalikan array sorted yang sudah terurut.

![image](https://user-images.githubusercontent.com/121870536/224317414-7afdf6ae-35b8-4415-b01d-890dbf74c268.png)

while(True):  : adalah perulangan yang akan terus berjalan selama kondisinya benar atau selama tidak ada statement break yang dijalankan di dalam blok perulangan.
dataset = ["arsel", "avivah", "daiva", ["wahyu", "wibi"]]   : adalah contoh dataset berisi nilai-nilai bertipe string dan list.
datasetsorted = sort_nested_dataset(dataset)  : memanggil fungsi sort_nested_dataset untuk mengurutkan dataset yang berisi list dengan nilai-nilai bertipe string.
print(dataset)  : untuk menampilkan isi dataset sebelum diurutkan.
x = (input("Masukkan Nama : "))   : untuk meminta input dari user berupa nama.
for index in range(len(datasetsorted)):   : untuk melakukan perulangan pada data yang sudah diurutkan.
if type(datasetsorted[index]) == list:  : untuk mengecek apakah nilai pada indeks index bertipe list.
kolom = jumpSearch(datasetsorted[index], x)   : memanggil fungsi jumpSearch untuk mencari nilai x pada list yang ada di dalam nested list.
if kolom != -1:   : mengecek apakah nilai x ditemukan pada list yang ada di dalam nested list.
print(f'{x} berada di array index ke - {index} kolom {kolom}')  : menampilkan pesan bahwa nilai x ditemukan pada array index ke - index pada kolom kolom.
else:   : statement ini dijalankan jika nilai pada indeks index bertipe string.
if datasetsorted[index] == x:   : untuk mengecek apakah nilai pada indeks index sama dengan nilai x.
print(f'{x} berada di array index ke - {index}')  : menampilkan pesan bahwa nilai x ditemukan pada array index ke - index.
