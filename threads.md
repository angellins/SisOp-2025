## Threads and Concurrency ##  
Nama : Angelina Safara  
NRP : 3124521004  
Kelas : 1 Teknik Informatika A  

## Tugas pertemuan ke-7  

## 1. Konsep Thread
- Single Thread adalah model eksekusi tugas di mana hanya ada satu alur (thread) yang menjalankan serangkaian instruksi secara berurutan. 
Dalam sistem single thread, setiap tugas harus diselesaikan sebelum beralih ke tugas berikutnya, sehingga tidak ada paralelisme. 
Konsep ini sederhana dan mudah diprediksi, tetapi kurang efisien untuk tugas-tugas yang membutuhkan waktu lama atau menunggu sumber daya eksternal (seperti I/O). 
Contohnya adalah program yang membaca file besar tanpa bisa melakukan operasi lain selama proses pembacaan berlangsung.  
- Multithread memungkinkan beberapa alur (thread) berjalan secara bersamaan dalam satu proses, sehingga tugas-tugas dapat dieksekusi secara paralel atau tumpang-tindih (overlapping). 
Ini meningkatkan efisiensi dan responsivitas, terutama pada sistem multi-core. Misalnya, sebuah aplikasi dapat menggunakan satu thread untuk antarmuka pengguna (UI) 
dan thread lain untuk komputasi berat tanpa membuat UI freeze. Namun, multithread memerlukan manajemen yang hati-hati untuk menghindari race condition dan deadlock.
![thread](https://github.com/angellins/SisOp-2025/blob/main/threads/thread.png) 

## 2. Programming Exercise
   
### a. Penerapan threads pada contoh SumTask.java  
![a](https://github.com/angellins/SisOp-2025/blob/main/threads/a.png)  
Program SumTask.java menggunakan konsep multithreading dengan membagi proses penjumlahan elemen array ke dalam beberapa thread yang berjalan secara paralel. 
Output dari program ini menunjukkan hasil penjumlahan seluruh elemen array secara akurat dan cepat. Java mempermudah implementasi thread karena sudah menyediakan class bawaan seperti Thread dan Runnable.

### b. penerapan Thread di Linux (thrd-posix.c)  
![b](https://github.com/angellins/SisOp-2025/blob/main/threads/b.png)  
Program thrd-posix.c menggunakan pustaka POSIX Threads (Pthreads) di sistem operasi Linux untuk membagi proses penjumlahan ke beberapa thread. 
Saat dijalankan dengan parameter jumlah elemen array, output yang dihasilkan berupa total penjumlahan yang dilakukan oleh thread-thread tersebut secara paralel. 
Implementasi ini memberikan kontrol yang tinggi terhadap proses pembuatan dan penggabungan thread (pthread_create dan pthread_join).  

### c. penerapan thread di Microsoft Windows (thrd-win32.c).  
![c](https://github.com/angellins/SisOp-2025/blob/main/threads/c.png)  
Program thrd-win32.c menerapkan multithreading dengan menggunakan API Windows (CreateThread) untuk menjalankan beberapa thread yang menghitung sebagian dari total array.
Meskipun prinsip kerjanya mirip dengan versi Linux, penggunaan WinAPI memerlukan pemahaman lebih terhadap struktur dan fungsi bawaan Windows. Dengan kontrol tingkat rendah 
terhadap thread dan memori, program ini cocok untuk pengembangan aplikasi desktop Windows yang menuntut efisiensi dan optimalisasi kerja CPU.  

## Practice Exercises  

### 4.1
**Apa perbedaan antara proses dan program?**

Sebuah **program** adalah entitas pasif seperti file berisi kumpulan instruksi. Sebaliknya, **proses** adalah entitas aktif, yang sedang dieksekusi. Proses mencakup kode program, nilai counter, stack, data section, dan heap.

---

### 4.2
**Apa saja kemungkinan transisi status proses di sistem operasi modern? Jelaskan setiap transisi secara singkat.**

Status proses:
- **New**: Proses sedang dibuat.
- **Ready**: Proses siap dijalankan dan menunggu giliran CPU.
- **Running**: Proses sedang dieksekusi di CPU.
- **Waiting**: Proses menunggu suatu event (misal: input).
- **Terminated**: Proses selesai dieksekusi.

Transisi:
- *New → Ready*: Setelah proses dibuat dan siap dijadwalkan.
- *Ready → Running*: Saat proses mendapatkan giliran CPU.
- *Running → Waiting*: Proses menunggu suatu event (I/O).
- *Running → Ready*: Proses dihentikan sementara oleh scheduler.
- *Waiting → Ready*: Event selesai, proses siap dijalankan.
- *Running → Terminated*: Proses selesai atau dihentikan.

---

### 4.3
**Berikan dua contoh kegiatan yang dapat menyebabkan transisi dari “running” ke “waiting”.**

1. Proses membaca file dari disk (I/O operation).
2. Proses menunggu masukan dari pengguna (keyboard input).

---

### 4.4
**Berikan dua contoh kegiatan yang dapat menyebabkan transisi dari “waiting” ke “ready”.**

1. File berhasil dibaca dari disk (I/O selesai).
2. Pengguna memberikan input melalui keyboard.

---

### 4.5
**Berikan dua contoh kegiatan yang dapat menyebabkan transisi dari “ready” ke “running”.**

1. Scheduler memilih proses tersebut untuk dieksekusi.
2. Proses lain yang sedang berjalan dihentikan, sehingga proses ini dapat dijalankan.

---

### 4.6
**Apa perbedaan antara scheduler CPU dan dispatcher?**

- **CPU Scheduler**: Memilih salah satu proses dari antrian ready untuk dijalankan.
- **Dispatcher**: Mengalihkan kontrol CPU dari proses lama ke proses baru, termasuk menyimpan dan memuat konteks, dan melompat ke instruksi proses tersebut.

---

### 4.7
**Apa yang dimaksud dengan preemptive dan non-preemptive scheduling?**

- **Preemptive Scheduling**: CPU dapat dialihkan dari proses yang sedang berjalan ke proses lain. Contoh: saat proses prioritas lebih tinggi datang.
- **Non-preemptive Scheduling**: CPU tidak akan dialihkan hingga proses selesai atau masuk ke keadaan menunggu.
