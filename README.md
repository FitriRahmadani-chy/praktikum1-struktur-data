MENGIMPLEMENTASIKAN QUEUE DAN STACK DI PYTHON

1. Queue: Struktur data FIFO – elemen pertama yang masuk akan keluar lebih dulu. Python menyediakan queue.Queue untuk membuat antrian dengan metode .put() dan .get().
2. Stack: Struktur data LIFO – elemen terakhir yang masuk akan dikeluarkan pertama. Di Python bisa dibuat dengan list menggunakan .append() dan .pop().

Keduanya berguna untuk manajemen data berurutan dalam algoritma dan progra


1. KODE PROGRAM QUEUE:

from queue import Queue
q = Queue(maxsize = 3)
print(q.qsize())
q.put('a')
q.put('b')
q.put('c')
print("\nFull: ", q.full())
print("\nElements dequeued from the queue")
print(q.get())
print(q.get())
print(q.get())
print("\nEmpty: ", q.empty())
q.put(1)
print("\nEmpty: ", q.empty())
print("Full: ", q.full())



BERIKUT PENJELASANNYA:

1. Mengambil kelas `Queue` dari modul `queue` bawaan Python. Kelas ini menyediakan antrian yang aman digunakan untuk proses beberapa thread (thread-safe), sangat berguna untuk aplikasi serbaguna seperti producer-consumer.

```python
from queue import Queue
```


2. Membuat objek antrian bernama `q` dengan batas maksimal 3 elemen. Artinya, hanya tiga item bisa masuk ke antrian di satu waktu.
   
```python
q = Queue(maxsize = 3)
```


3. Mencetak jumlah elemen saat ini di dalam antrian. Karena antrian baru dibuat, hasilnya pasti `0`.
   
```python
print(q.qsize())
```


4. Menambahkan tiga elemen ke dalam antrian secara berurutan: `'a'`, `'b'`, dan `'c'`. Karena kapasitas maksimal antrian juga 3, setelah tiga baris ini antrian langsung dalam kondisi penuh.

```python
q.put('a')
q.put('b')
q.put('c')
```


5. Mengecek apakah antrian sudah penuh menggunakan metode `.full()`. Hasilnya akan `True`, karena memang sudah ada 3 elemen sesuai kapasitas.

```python
print("\nFull: ", q.full())
```


6. Baris ini hanya untuk memberi tahu bahwa elemen akan diambil (didequeue) dari antrian.

```python
print("\nElements dequeued from the queue")
```


7. Mengambil dan mencetak elemen dari antrian satu per satu. Karena antrian adalah FIFO (first in, first out), urutan cetaknya adalah `'a'`, lalu `'b'`, lalu `'c'`.
```python
print(q.get())
print(q.get())
print(q.get())
```


8. Mengecek apakah antrian kosong setelah semua elemen dikeluarkan. Hasilnya `True`.
   
```python
print("\nEmpty: ", q.empty())
```


9. Menambahkan elemen baru bernilai `1` ke antrian. Sekarang antrian sudah tidak kosong.

```python
q.put(1)
```


10. Kembali mengecek apakah antrian kosong dan apakah sudah penuh. Kali ini hasilnya `Empty: False` dan `Full: False` karena baru satu elemen yang bertumpuk di antrian.

```python
print("\nEmpty: ", q.empty())
print("Full: ", q.full())
```


11. BERIKUT OUTPUT NYA:

    0

Full:  True

Elements dequeued from the queue
a
b
c

Empty:  True

Empty:  False
Full:  False



RANGKUMAN:
Program ini menggunakan struktur data antrian (queue) dari modul standar Python `queue`. Antrian tersebut memiliki kapasitas maksimum tiga item, dan bekerja dengan pola First In, First Out (FIFO), artinya nilai yang pertama ditambahkan akan menjadi yang pertama dikeluarkan.

Susunan alur secara singkat:

1. Antrian dibuat dan dicek ukurannya — awalnya kosong (`0 elemen`).
2. Tiga item (`'a'`, `'b'`, `'c'`) dimasukkan berturut-turut ke dalam antrian.
3. Setelah itu, antrian berada dalam kondisi penuh → divalidasi dengan `.full()` yang mengembalikan `True`.
4. Ketiga elemen tersebut kemudian dikeluarkan satu per satu menggunakan `.get()`.
5. Setelah pengeluaran selesai, antrian kembali kosong → dikonfirmasi oleh `.empty()` yang menghasilkan `True`.
6. Sebuah elemen baru (`1`) ditambahkan.
7. Antrian kini tidak penuh dan tidak kosong — dibuktikan oleh hasil `.empty()` = `False` dan `.full()` = `False`.



2. KODE PROGRAM STACK:

stack = []

stack.append('a')
stack.append('b')
stack.append('c')

print('Intitial stack')
print(stack)

print('\nElements popped from stack:')
print(stack.pop())
print(stack.pop())
print(stack.pop())

print('\nStack after elements are popped:')
print(stack)


PENJELASANNYA:

1. Membuat Antrian Kosong
Pertama-tama, kita siapkan sebuah list kosong yang akan berperan sebagai antrian:

```python
queue = []
```


2.  Menambahkan Data ke Antrian (Enqueue)
Untuk memasukkan elemen ke dalam antrian, kita gunakan metode `append()`:

```python
queue.append('A')
queue.append('B')
queue.append('C')
```

Hasilnya, antrian sekarang berisi: `['A', 'B', 'C']`.


3.  Mengeluarkan Data Pertama (Dequeue)
Data paling awal yang masuk akan keluar terlebih dahulu menggunakan `pop(0)`:

```python
element = queue.pop(0)  # Hasilnya: 'A'
```

Elemen `'A'` telah dikeluarkan dari antrian.


3. Melihat Data di Depan Tanpa Menghapus
Jika ingin mengetahui elemen terdepan tanpa menghapusnya:

```python
first_element = queue[0]  # Akan menghasilkan 'B'
```


4.  Mengecek Apakah Antrian Kosong
Gunakan kode berikut untuk memeriksa apakah masih ada data di antrian:

```python
is_empty = len(queue) == 0
```


5.  Menghitung Banyaknya Data
Gunakan fungsi `len()` untuk mengetahui sisa isi antrian:

```python
size = len(queue)  # Hasilnya: 2
```


6. OUTPUT NYA:

```
Daftar antrian: ['A', 'B', 'C']
Data keluar: A
Data terdepan sekarang: B
Antrian kosong? False
Jumlah data saat ini: 2
```


RANGKUMAN:

1. Queue dapat dibangun menggunakan struktur `list` di Python.
2. Bekerja dengan mekanisme FIFO (First In, First Out), di mana elemen yang pertama masuk diproses lebih dulu.
3. Operasi penting dalam queue:

-`append()` → memasukkan data
-`pop(0)` → menghapus data terdepan
-`queue[0]` → mengecek data terdepan

Queue berguna untuk situasi nyata seperti antrean konsumen, pemrosesan data berurutan, hingga antrian tugas pada sistem operasi.


