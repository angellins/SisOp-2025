## Tugas Fork ##  
Nama : Angelina Safara  
NRP : 3124521004  
Kelas : 1 Teknik Informatika A  

## Fork : Parent - Child Process ##  


```
$ ./fork01
```
![fork1](https://github.com/angellins/SisOp-2025/blob/main/screenshots_fork/fork1.png)  
```
$ ./fork02
```
![fork2](https://github.com/angellins/SisOp-2025/blob/main/screenshots_fork/fork2.png)  
penjelasan:  
Kode fork02.cpp punya loop while (1), yang artinya dia akan terus berjalan tanpa henti diulang-ulang terus setiap 2 detik, dengan nilai x yang terus bertambah Jadi, kalau kita jalankan kode ini, outputnya akan terus muncul di layar sampai kita menghentikannya secara manual.  
```
$ ./fork03
```
![fork3](https://github.com/angellins/SisOp-2025/blob/main/screenshots_fork/fork3.png)  
penjelasan:  
Karena ada fork() dan loop for, outputnya akan bercabang dan diulang. Jadi, outputnya akan ada 10 baris, 5 baris dari induk dan 5 baris dari anak, dengan jeda 2 detik antar baris.  
```
$ ./fork04
```
![fork4](https://github.com/angellins/SisOp-2025/blob/main/screenshots_fork/fork4.png)  
```
$ ./fork05
```
![fork5](https://github.com/angellins/SisOp-2025/blob/main/screenshots_fork/fork5.png)  
```
$ ./fork06
```
![fork6](https://github.com/angellins/SisOp-2025/blob/main/screenshots_fork/fork6.png)  
