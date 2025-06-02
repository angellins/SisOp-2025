## Tugas Tambahan Mencari kasus yang sama dengan tugas sebelumnya dipractice exercise S10-Ch05  
Nama  : Angelina Safara  
NRP   : 3124521004  
Kelas : 1 Teknik Informatika A  

### Shortest Job First (SJF)
Konsep dasar dan contoh non-preemptif SJF dibahas di Bagian 5.3.2, halaman 207.
contoh dengan proses P1 ,P2 ,P3 ,P4 dan waktu burst masing-masing 6, 8, 7, 3 milidetik, beserta Gantt chart dan perhitungan waktu tunggu rata-rata.  
### Shortest Remaining Time First (SRTF)
yang merupakan preemptive SJF, juga dijelaskan di Bagian 5.3.2, halaman 209. Contoh dengan proses P1 ,P 2 ,P3 ,P4 dengan waktu kedatangan dan waktu burst yang berbeda
diberikan, juga dengan Gantt chart dan perhitungan waktu tunggu rata-rata. 
### Round Robin (RR)
Konsep dan implementasi RR dijelaskan di Bagian 5.3.3, halaman 209-210.
Contoh spesifik untuk RR dengan waktu kuantum 4 milidetik diberikan di Bagian 5.3.3, halaman 210. Proses P1 ,P2 ,P3 dengan waktu burst 24, 3, 3 milidetik digunakan untuk ilustrasi, 
termasuk Gantt chart dan perhitungan waktu tunggu rata-rata.

Untuk practice exercise yang relevan pada algoritma ini berada di latihan 5.4
### Jawaban Latihan Praktik 5.4

**Proses yang Diberikan:**

| Process | Burst Time (ms) | Priority |
| :------ | :-------------- | :------- |
| P1      | 2               | 2        |
| P2      | 1               | 1        |
| P3      | 84              | 4        |
| P4      | 4               | 2        |
| P5      | 5               | 3        |

*Diasumsikan semua proses tiba pada waktu 0 dalam urutan P1, P2, P3, P4, P5. Prioritas yang lebih besar menyiratkan prioritas yang lebih tinggi.*

---

### a. Gantt Charts

#### 1. FCFS (First-Come, First-Served)

**Urutan Kedatangan:** P1, P2, P3, P4, P5

| P1 | P2 | P3 | P4 | P5 |
| :-- | :-- | :-- | :-- | :-- |
| 0   | 2  | 3  | 87 | 91 | 96 |

#### 2. SJF (Shortest-Job-First) - Non-Preemptive

**Urutan Eksekusi (berdasarkan Burst Time terpendek):** P2, P1, P4, P5, P3

| P2 | P1 | P4 | P5 | P3 |
| :-- | :-- | :-- | :-- | :-- |
| 0   | 1  | 3  | 7  | 12 | 96 |

#### 3. Priority Scheduling (Non-Preemptive)

**Prioritas: P3 (4) > P5 (3) > P1 (2) & P4 (2) > P2 (1)**
*Untuk prioritas yang sama (P1 dan P4), gunakan FCFS.*

**Urutan Eksekusi:** P3, P5, P1, P4, P2

| P3 | P5 | P1 | P4 | P2 |
| :-- | :-- | :-- | :-- | :-- |
| 0   | 84 | 89 | 91 | 95 | 96 |

#### 4. RR (Round-Robin) - Quantum = 2 ms

| P1 | P2 | P3 | P4 | P5 | P3 | P3 | ... | P3 |
| :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- |
| 0   | 2  | 3  | 5  | 7  | 9  | 11 | ... | 96 |

*Penjelasan RR:*
* P1 berjalan 2ms (selesai)
* P2 berjalan 1ms (selesai)
* P3 berjalan 2ms
* P4 berjalan 2ms
* P5 berjalan 2ms
* P3 berjalan 2ms
* P4 berjalan 2ms (selesai)
* P5 berjalan 2ms (selesai)
* P3 berjalan 2ms (P3 akan terus berjalan 2ms per giliran hingga selesai)

*Untuk memvisualisasikan lebih lengkap, akan ada banyak segmen P3 setelah P4 dan P5 selesai. Total burst P3 adalah 84. Setelah 2ms pertama, sisa 82ms. Setelah 2ms kedua, sisa 80ms. P3 akan membutuhkan 42 segmen (84/2) secara total. P1, P2, P4, P5 akan selesai lebih dulu.*

*Detail lebih lanjut untuk RR:*
* P1: 0 - 2 (selesai)
* P2: 2 - 3 (selesai)
* P3: 3 - 5
* P4: 5 - 7
* P5: 7 - 9
* P3: 9 - 11
* P4: 11 - 13 (selesai)
* P5: 13 - 15 (selesai)
* P3: 15 - 17
* ... (P3 terus berjalan sampai selesai)
* P3 selesai pada waktu 96.

---

### b. Turnaround Time untuk Setiap Proses

**Turnaround Time = Waktu Selesai - Waktu Kedatangan**
*(Waktu Kedatangan semua proses adalah 0)*

#### FCFS:
* P1: 2 - 0 = **2 ms**
* P2: 3 - 0 = **3 ms**
* P3: 87 - 0 = **87 ms**
* P4: 91 - 0 = **91 ms**
* P5: 96 - 0 = **96 ms**

#### SJF:
* P1: 3 - 0 = **3 ms**
* P2: 1 - 0 = **1 ms**
* P3: 96 - 0 = **96 ms**
* P4: 7 - 0 = **7 ms**
* P5: 12 - 0 = **12 ms**

#### Priority (Non-Preemptive):
* P1: 91 - 0 = **91 ms**
* P2: 96 - 0 = **96 ms**
* P3: 84 - 0 = **84 ms**
* P4: 95 - 0 = **95 ms**
* P5: 89 - 0 = **89 ms**

#### RR (Quantum = 2 ms):
* P1: 2 - 0 = **2 ms**
* P2: 3 - 0 = **3 ms**
* P3: 96 - 0 = **96 ms** (P3 akan terus berputar hingga selesai terakhir)
* P4: 13 - 0 = **13 ms**
* P5: 15 - 0 = **15 ms**

---

### c. Waiting Time untuk Setiap Proses

**Waiting Time = Turnaround Time - Burst Time**

#### FCFS:
* P1: 2 - 2 = **0 ms**
* P2: 3 - 1 = **2 ms**
* P3: 87 - 84 = **3 ms**
* P4: 91 - 4 = **87 ms**
* P5: 96 - 5 = **91 ms**

#### SJF:
* P1: 3 - 2 = **1 ms**
* P2: 1 - 1 = **0 ms**
* P3: 96 - 84 = **12 ms**
* P4: 7 - 4 = **3 ms**
* P5: 12 - 5 = **7 ms**

#### Priority (Non-Preemptive):
* P1: 91 - 2 = **89 ms**
* P2: 96 - 1 = **95 ms**
* P3: 84 - 84 = **0 ms**
* P4: 95 - 4 = **91 ms**
* P5: 89 - 5 = **84 ms**

#### RR (Quantum = 2 ms):
* P1: 2 - 2 = **0 ms**
* P2: 3 - 1 = **2 ms**
* P3: 96 - 84 = **12 ms**
    * (P3 dijalankan 2ms pada (3-5), lalu (9-11), lalu (15-17), ..., Total 42 segmen. Waktu menunggu di antara segmen-segmen ini dihitung.)
    * Waktu tunggu P3 dapat dihitung lebih akurat sebagai: (Waktu mulai 1 - 0) + (Waktu mulai 2 - Waktu selesai 1) + ...
    * P3 dimulai pada t=3. Kembali ke ready queue pada t=5. Dimulai lagi pada t=9. Kembali pada t=11. Dimulai lagi pada t=15. Kembali pada t=17.
    * Total waktu tunggu P3 = (9-5) + (15-11) + ... = 4 + 4 + ...
    * Lebih mudah: Total waktu yang dihabiskan - Total waktu burst = 96 - 84 = 12 ms
* P4: 13 - 4 = **9 ms**
    * (P4 dijalankan pada (5-7). Kembali pada t=7. Dimulai lagi pada t=11. Selesai pada t=13. Waktu tunggu = (5-0) + (11-7) = 5+4 = 9ms)
* P5: 15 - 5 = **10 ms**
    * (P5 dijalankan pada (7-9). Kembali pada t=9. Dimulai lagi pada t=13. Selesai pada t=15. Waktu tunggu = (7-0) + (13-9) = 7+4 = 11ms)

---

### d. Algoritma dengan Waktu Tunggu Rata-rata Minimum

#### Rata-rata Waktu Tunggu:

* **FCFS:** (0 + 2 + 3 + 87 + 91) / 5 = 183 / 5 = **36.6 ms**
* **SJF:** (1 + 0 + 12 + 3 + 7) / 5 = 23 / 5 = **4.6 ms**
* **Priority (Non-Preemptive):** (89 + 95 + 0 + 91 + 84) / 5 = 359 / 5 = **71.8 ms**
* **RR:** (0 + 2 + 12 + 9 + 10) / 5 = 33 / 5 = **6.6 ms**

Dari perhitungan di atas, **SJF (Shortest-Job-First)** menghasilkan waktu tunggu rata-rata minimum yaitu **4.6 ms**.
