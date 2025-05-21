## Scheduling Algorithms ##  
Nama : Angelina Safara  
NRP : 3124521004  
Kelas : 1 Teknik Informatika A  

## Tugas pertemuan ke-10  
### program 1: SJF Non-Preemptive (Tanpa Arrival Time)  
Program ini mengimplementasikan algoritma Shortest Job First (SJF) non-preemptive tanpa mempertimbangkan waktu kedatangan (arrival time diasumsikan 0).  
1. Input Jumlah dan Burst Time Proses  
```
  scanf("%d",&n);  
  for(int i=0;i<n;i++)  
    p[i]=read(i+1);  
```

analisa:  
Pengguna memasukkan jumlah proses n
Program mengisi array p dengan data burst time masing-masing proses
2.	Sorting Sesuai Burst Time (SJF)  
```
for(int i=0;i<n-1;i++)
    for(int j=0;j<n-i-1;j++)
        if(p[j].bt>p[j+1].bt)
            swap(p[j], p[j+1]);
```
analisa:
Menggunakan Bubble Sort
Mengurutkan proses berdasarkan burst time terkecil ke terbesar (SJF)  
3.	Perhitungan CT, TAT, WT, RT
```
for(int i=0;i<n;i++)
{
    ct += p[i].bt;
    p[i].ct = p[i].tat = ct;
    p[i].wt = p[i].tat - p[i].bt;
}
```
analisa:
CT bertambah terus (karena arrival time = 0, maka eksekusi langsung)
TAT = CT (karena AT = 0)
WT = TAT - BT
RT = WT (karena non-preemptive, proses langsung dimulai setelah menunggu)
output
![thread](https://github.com/angellins/SisOp-2025/blob/main/threads/thread.png)
