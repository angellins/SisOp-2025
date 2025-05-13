## CPU scheduling ##  
Nama : Angelina Safara  
NRP : 3124521004  
Kelas : 1 Teknik Informatika A  

## Tugas pertemuan ke-9
## 5.17 Data Proses

| Proses | Burst Time | Prioritas |
|--------|------------|-----------|
| P1     | 5 ms       | 4         |
| P2     | 3 ms       | 1         |
| P3     | 1 ms       | 2         |
| P4     | 7 ms       | 2         |
| P5     | 4 ms       | 3         |

Semua proses datang pada waktu 0, dalam urutan: P1, P2, P3, P4, P5.

---

## a. Gantt Chart untuk Tiap Algoritma

### 1. FCFS (First-Come, First-Served)

Urutan eksekusi: P1 → P2 → P3 → P4 → P5  
| P1 | P2 | P3 | P4 | P5 |  
0    5    8    9    16   20  

### 2. SJF (Shortest Job First)

Urutan eksekusi: P3 → P2 → P5 → P1 → P4  
| P3 | P2 | P5 | P1 | P4 |  
0    1    4    8    13   20  

### 3. Non-preemptive Priority

Urutan eksekusi: P1 (4) → P5 (3) → P3 (2) → P4 (2) → P2 (1)  
| P1 | P5 | P3 | P4 | P2 |  
0 5 9 10 17 20  

### 4. Round Robin (Quantum = 2)  
| P1 | P2 | P3 | P4 | P5 | P1 | P2 | P4 | P5 | P1 | P4 | P4 |  
0 2 4 5 7 9 11 12 14 16 17 19 20  

---

## b. Turnaround Time (TAT)

### FCFS

| Proses | Selesai | TAT |
|--------|---------|-----|
| P1     | 5       | 5   |
| P2     | 8       | 8   |
| P3     | 9       | 9   |
| P4     | 16      | 16  |
| P5     | 20      | 20  |

### SJF

| Proses | Selesai | TAT |
|--------|---------|-----|
| P3     | 1       | 1   |
| P2     | 4       | 4   |
| P5     | 8       | 8   |
| P1     | 13      | 13  |
| P4     | 20      | 20  |

### Non-preemptive Priority

| Proses | Selesai | TAT |
|--------|---------|-----|
| P1     | 5       | 5   |
| P5     | 9       | 9   |
| P3     | 10      | 10  |
| P4     | 17      | 17  |
| P2     | 20      | 20  |

### Round Robin

| Proses | Selesai | TAT |
|--------|---------|-----|
| P1     | 17      | 17  |
| P2     | 12      | 12  |
| P3     | 5       | 5   |
| P4     | 20      | 20  |
| P5     | 19      | 19  |

---

## c. Waiting Time (WT)

### FCFS

| Proses | TAT | Burst | WT |
|--------|-----|-------|----|
| P1     | 5   | 5     | 0  |
| P2     | 8   | 3     | 5  |
| P3     | 9   | 1     | 8  |
| P4     | 16  | 7     | 9  |
| P5     | 20  | 4     | 16 |

### SJF

| Proses | TAT | Burst | WT |
|--------|-----|-------|----|
| P3     | 1   | 1     | 0  |
| P2     | 4   | 3     | 1  |
| P5     | 8   | 4     | 4  |
| P1     | 13  | 5     | 8  |
| P4     | 20  | 7     | 13 |

### Non-preemptive Priority

| Proses | TAT | Burst | WT |
|--------|-----|-------|----|
| P1     | 5   | 5     | 0  |
| P5     | 9   | 4     | 5  |
| P3     | 10  | 1     | 9  |
| P4     | 17  | 7     | 10 |
| P2     | 20  | 3     | 17 |

### Round Robin

| Proses | TAT | Burst | WT |
|--------|-----|-------|----|
| P1     | 17  | 5     | 12 |
| P2     | 12  | 3     | 9  |
| P3     | 5   | 1     | 4  |
| P4     | 20  | 7     | 13 |
| P5     | 19  | 4     | 15 |

---

## d. Rata-rata Waiting Time (WT)

- **FCFS**: (0 + 5 + 8 + 9 + 16) / 5 = **7.6 ms**
- **SJF**: (0 + 1 + 4 + 8 + 13) / 5 = **5.2 ms**
- **Priority**: (0 + 5 + 9 + 10 + 17) / 5 = **8.2 ms**
- **Round Robin**: (12 + 9 + 4 + 13 + 15) / 5 = **10.6 ms**

### ⭐ Kesimpulan:
**Algoritma Shortest Job First (SJF)** menghasilkan rata-rata waktu tunggu **terkecil**, yaitu **5.2 ms**.


