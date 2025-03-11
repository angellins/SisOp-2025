# Tugas Flowchart
Nama : Angelina safara  
Kelas : 1 Teknik Informatika A  
NRP : 3124521004  
Mata kuliah : Sistem Operasi
## Deskripsi
Berikut adalah tugas minggu ke - 3 membuat flowchart untuk proses dari komputer dinyalakan hingga komputer bisa digunakan:  

## **Gambar Flowchart**
![Flowchart Booting](images/flowchart_boot.png)

# ** Penjelasan Langkah Flowchart Proses Booting Komputer**

## **1. Mulai: Tekan Tombol Power**
Pengguna menyalakan komputer dengan menekan tombol power.

## **2. BIOS/UEFI Mulai**
BIOS (Basic Input Output System) atau UEFI (Unified Extensible Firmware Interface) mulai bekerja untuk melakukan pemeriksaan awal terhadap sistem.

## **3. POST (Power On Self Test)?**
- **POST (Power On Self Test)** adalah proses pengecekan hardware utama (RAM, CPU, keyboard, dll.).
- Jika POST **berhasil**, komputer melanjutkan proses booting.
- Jika POST **gagal**, muncul **Error: POST Failed**, dan komputer menampilkan pesan error.

## **4. Cari Boot Device**
Sistem mencari perangkat boot yang berisi sistem operasi (misalnya, hard disk, SSD, atau USB).

## **5. Boot Device Ditemukan?**
- Jika **boot device ditemukan**, komputer melanjutkan ke langkah selanjutnya.
- Jika **tidak ditemukan**, muncul **Error: Boot Device Not Found**, dan komputer menampilkan pesan error.

## **6. Bootloader Mulai**
Bootloader (misalnya GRUB atau Windows Boot Manager) dijalankan untuk memuat sistem operasi.

## **7. Kernel OS Mulai**
Kernel dari sistem operasi mulai dijalankan.

## **8. Inisialisasi Hardware**
Sistem menginisialisasi semua perangkat keras (seperti prosesor, RAM, dan perangkat penyimpanan).

## **9. Load Driver**
Sistem memuat driver yang diperlukan untuk mengenali perangkat keras seperti kartu grafis, jaringan, dan lainnya.

## **10. Mulai Layanan Sistem**
Semua layanan sistem operasi mulai dijalankan, seperti jaringan dan proses latar belakang.

## **11. Login Screen/Desktop**
Sistem menampilkan layar login atau langsung masuk ke desktop.

## **12. Selesai: Komputer Siap Digunakan**
Komputer siap untuk digunakan oleh pengguna.

---
