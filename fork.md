## Fork : Parent - Child Process ##  
Nama : Angelina Safara  
NRP : 3124521004  
Kelas : 1 Teknik Informatika A    

  fork() adalah sebuah system call atau fungsi khusus yang digunakan dalam sistem operasi mirip Unix (seperti Linux dan macOS) untuk membuat proses baru. Proses yang membuat proses baru ini disebut proses induk (parent process), dan proses yang baru dibuat disebut proses anak (child process). Proses anak ini pada dasarnya adalah salinan dari proses induk, dengan ruang alamat dan status eksekusi yang hampir identik.

  Setelah fork() dipanggil, baik proses induk maupun proses anak akan melanjutkan eksekusi dari titik yang sama dalam kode program. Proses induk dapat menggunakan nilai kembalian dari fork() untuk membedakan antara dirinya dan proses anak. Pada proses anak, fork() mengembalikan nilai 0, sedangkan pada proses induk, fork() mengembalikan Process ID (PID) dari proses anak yang baru dibuat. Jika terjadi kesalahan saat membuat proses anak, fork() akan mengembalikan nilai negatif.  
  
```
$ ./fork01
```
![fork1](https://github.com/angellins/SisOp-2025/blob/main/screenshots_fork/fork1.png)  
```
[Proses Utama] (PID: ..., PPID: ...)
```
penjelasan fork01:  
Kode fork01.cpp hanya mencetak informasi tentang proses yang sedang berjalan, dan tidak membuat proses baru. Karena kode ini tidak menggunakan fork(), pohon prosesnya sangat sederhana dan hanya ada satu proses yang berjalan, yaitu proses utama yang menjalankan kode ini.  

```
$ ./fork02
```
![fork2](https://github.com/angellins/SisOp-2025/blob/main/screenshots_fork/fork2.png)  
```
                                  [Proses Utama] (PID: ..., PPID: ...)
                                          |
                                          | fork()
                                          |
                        --------------------------------------
                        |                                    |
            [Proses Induk] (PID: ..., PPID: ...)   [Proses Anak] (PID: ..., PPID: ...)
                        |                                    |
                        | (Loop Tak Terbatas)                | (Loop Tak Terbatas)
                        |                                    |
                        | ... (Terus Berjalan)               | ... (Terus Berjalan)
```
penjelasan fork02:  
Kode fork02.cpp punya loop while (1), yang artinya dia akan terus berjalan tanpa henti diulang-ulang terus setiap 2 detik, dengan nilai x yang terus bertambah. Jadi, kalau kita jalankan kode ini, outputnya akan terus muncul di layar sampai kita menghentikannya secara manual.  
  
```
$ ./fork03
```
![fork3](https://github.com/angellins/SisOp-2025/blob/main/screenshots_fork/fork3.png)  
```
                                  [Proses Utama (fork03)] (PID: ..., PPID: ...)
                                          |
                                          | fork()
                                          |
                        --------------------------------------
                        |                                    |
            [Proses Induk (fork03)] (PID: ..., PPID: ...)   [Proses Anak (fork03)] (PID: ..., PPID: ...)
                        |                                    |
                        | (Loop 5 kali)                       | (Loop 5 kali)
                        |                                    |
                        | (Selesai)                           | (Selesai)
```
penjelasan fork03:  
Karena ada fork() dan loop for, outputnya akan bercabang dan diulang. Jadi, outputnya akan ada 10 baris, 5 baris dari induk dan 5 baris dari anak, dengan jeda 2 detik antar baris.  

```
$ ./fork04
```
![fork4](https://github.com/angellins/SisOp-2025/blob/main/screenshots_fork/fork4.png)  
```
                                  [Proses Utama (fork04)] (PID: ..., PPID: ...)
                                          |
                                          | fork()
                                          |
                        --------------------------------------
                        |                                    |
            [Proses Induk (fork04)] (PID: ..., PPID: ...)   [Proses Anak (fork04)] (PID: ..., PPID: ...)
                        |                                    |
                        | (Menunggu Anak)                     | (Menjalankan Kode Anak)
                        |                                    |
                        | (Selesai setelah Anak selesai)      | (Selesai)
```
penjelasan fork04:  
Proses induk mencetak pesan dan menunggu proses anak selesai menggunakan wait(). Proses anak mencetak pesan dan kemudian keluar.
```
$ ./fork05
```
![fork5](https://github.com/angellins/SisOp-2025/blob/main/screenshots_fork/fork5.png)  
```
                                  [Proses Utama (fork05)] (PID: ..., PPID: ...)
                                          |
                                          | fork()
                                          |
                        --------------------------------------
                        |                                    |
            [Proses Induk (fork05)] (PID: ..., PPID: ...)   [Proses Anak (ls -l /home)] (PID: ..., PPID: ...)
                        |                                    |
                        | (Menunggu Anak)                     | (Menjalankan ls -l /home)
                        |                                    |
                        | (Selesai setelah Anak selesai)      | (Selesai)
```
penjelasan fork05:  
Proses anak menjalankan perintah ls -l /home menggunakan execl(). Output dari perintah ls -l /home (yaitu, daftar file dan direktori di dalam direktori /home) ditampilkan. Setelah proses anak selesai, proses induk keluar (wait()).
```
$ ./fork06
```
![fork6](https://github.com/angellins/SisOp-2025/blob/main/screenshots_fork/fork6.png)  
```
                                  [Proses Utama (fork06)] (PID: ..., PPID: ...)
                                          |
                                          | fork()
                                          |
                        --------------------------------------
                        |                                    |
            [Proses Induk (fork06)] (PID: ..., PPID: ...)   [Proses Anak (fork03)] (PID: ..., PPID: ...)
                        |                                    |
                        | (Menunggu Anak)                     | (Menjalankan fork03)
                        |                                    |
                        | (Selesai setelah Anak selesai)      | (Selesai)
```
penjelasan fork06:
Fungsi execl() mengganti kode yang sedang berjalan dengan kode dari program lain (fork03). Fungsi wait() membuat proses induk menunggu hingga proses anak selesai.
