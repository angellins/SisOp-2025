## Scheduling Algorithms ##  
Nama : Angelina Safara  
NRP : 3124521004  
Kelas : 1 Teknik Informatika A  

## Tugas pertemuan ke-10  
#### 1: SJF Non-Preemptive (Tanpa Arrival Time)  
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
output:  
![SA](https://github.com/angellins/SisOp-2025/blob/main/scheduling-algorithm/kode1.png)  
Gantt chart:  
| P3 | P1 | P2  | P4  |
0    2    5    10    16
#### 2. SJF Scheduling Algorithm
```
#include<stdio.h>
struct proc
{
    int no,at,bt,it,ct,tat,wt;
};
struct proc read(int i)
{
    struct proc p;
    printf("\nProcess No: %d\n",i);
    p.no=i;
    printf("Enter Arrival Time: ");
    scanf("%d",&p.at);
    printf("Enter Burst Time: ");
    scanf("%d",&p.bt);
    return p;
}
int main()
{
    int  n,j,min=0;
    float avgtat=0,avgwt=0;
    struct proc p[10],temp;
    printf("<--SJF Scheduling Algorithm (Non-Preemptive)-->\n");
    printf("Enter Number of Processes: ");
    scanf("%d",&n);
    for(int i=0;i<n;i++)
        p[i]=read(i+1);
    for(int i=0;i<n-1;i++)
        for(j=0;j<n-i-1;j++)    
            if(p[j].at>p[j+1].at)
            {
            temp=p[j];
            p[j]=p[j+1];
            p[j+1]=temp;
            }
    for(j=1;j<n&&p[j].at==p[0].at;j++)
        if(p[j].bt<p[min].bt)
            min=j;
    temp=p[0];
    p[0]=p[min];
    p[min]=temp;
    p[0].it=p[0].at;
    p[0].ct=p[0].it+p[0].bt;
    for(int i=1;i<n;i++)
    {
        for(j=i+1,min=i;j<n&&p[j].at<=p[i-1].ct;j++)
            if(p[j].bt<p[min].bt)
                min=j;
        temp=p[i];
        p[i]=p[min];
        p[min]=temp;
        if(p[i].at<=p[i-1].ct)
            p[i].it=p[i-1].ct;
        else
            p[i].it=p[i].at;
        p[i].ct=p[i].it+p[i].bt;
    }
    printf("\nProcess\t\tAT\tBT\tCT\tTAT\tWT\tRT\n");
    for(int i=0;i<n;i++)
    {
        p[i].tat=p[i].ct-p[i].at;
        avgtat+=p[i].tat;
        p[i].wt=p[i].tat-p[i].bt;
        avgwt+=p[i].wt;
        printf("P%d\t\t%d\t%d\t%d\t%d\t%d\t%d\n",p[i].no,p[i].at,p[i].bt,p[i].ct,p[i].tat,p[i].wt,p[i].wt);
    }
    avgtat/=n,avgwt/=n;
    printf("\nAverage TurnAroundTime=%f\nAverage WaitingTime=%f",avgtat,avgwt);
}
```
output:  
![SA](https://github.com/angellins/SisOp-2025/blob/main/scheduling-algorithm/kode2.png)  
Gantt chart:  
analisa:  
Output program menunjukkan hasil penjadwalan dengan algoritma SJF Non-Preemptive, di mana proses dengan burst time terkecil dieksekusi lebih dulu setelah arrival time-nya terpenuhi. Proses P3 dijalankan pertama karena tiba paling awal dan memiliki burst time sedang. Proses P1 menyusul karena burst-nya lebih kecil dari P2. Hasilnya, rata-rata Turnaround Time adalah 8.67 dan Waiting Time 3.67. Nilai ini menunjukkan efisiensi cukup baik dalam eksekusi proses berdasarkan durasi terpendek.
#### 3. SRTF Scheduling Algorithm  
```
#include<stdio.h>
#define MAX 9999
struct proc
{
    int no,at,bt,rt,ct,tat,wt;
};
struct proc read(int i)
{
    struct proc p;
    printf("\nProcess No: %d\n",i);
    p.no=i;
    printf("Enter Arrival Time: ");
    scanf("%d",&p.at);
    printf("Enter Burst Time: ");
    scanf("%d",&p.bt);
    p.rt=p.bt;
    return p;
}
int main()
{
    struct proc p[10],temp;
    float avgtat=0,avgwt=0;
    int n,s,remain=0,time;
    printf("<--SRTF Scheduling Algorithm (Preemptive)-->\n");
    printf("Enter Number of Processes: ");
    scanf("%d",&n);
    for(int i=0;i<n;i++)
        p[i]=read(i+1);
    for(int i=0;i<n-1;i++)
        for(int j=0;j<n-i-1;j++)    
            if(p[j].at>p[j+1].at)
            {
            temp=p[j];
            p[j]=p[j+1];
            p[j+1]=temp;
            }
    printf("\nProcess\t\tAT\tBT\tCT\tTAT\tWT\n");
    p[9].rt=MAX;
    for(time=0;remain!=n;time++)
    {
        s=9;
        for(int i=0;i<n;i++)
            if(p[i].at<=time&&p[i].rt<p[s].rt&&p[i].rt>0)
                s=i;
        p[s].rt--;
        if(p[s].rt==0)
        {
            remain++;
            p[s].ct=time+1;
            p[s].tat=p[s].ct-p[s].at;
            avgtat+=p[s].tat;
            p[s].wt=p[s].tat-p[s].bt;
            avgwt+=p[s].wt;
            printf("P%d\t\t%d\t%d\t%d\t%d\t%d\n",p[s].no,p[s].at,p[s].bt,p[s].ct,p[s].tat,p[s].wt);
        }
    }
    avgtat/=n,avgwt/=n;
    printf("\nAverage TurnAroundTime=%f\nAverage WaitingTime=%f",avgtat,avgwt);
}
```
output:  
![SA](https://github.com/angellins/SisOp-2025/blob/main/scheduling-algorithm/kode3.png)  
Gantt chart:  
analisa:  
Program menerapkan algoritma penjadwalan Shortest Remaining Time First (SRTF), yaitu versi preemptive dari SJF. Proses dengan waktu eksekusi tersisa paling pendek akan selalu dijalankan terlebih dahulu. Pada kasus ini, P3 yang tiba paling awal dieksekusi dulu, namun dieksekusi bergantian karena adanya proses baru dengan burst time lebih pendek. Proses P4 yang hanya butuh 1 detik langsung diselesaikan saat tiba di waktu 7. Hasil akhir menunjukkan rata-rata Turnaround Time 5.75 dan Waiting Time 2.25, menandakan efisiensi cukup baik karena proses lebih pendek diprioritaskan.
