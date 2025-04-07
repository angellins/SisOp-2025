Nama : Angelina Safara  
NRP : 3124521004  
Kelas : 1 Teknik Informatika A  

Evolusi Sistem Operasi:

Perkembangan sistem operasi telah mengalami transformasi signifikan, di mana fitur-fitur canggih yang awalnya hanya tersedia di komputer mainframe besar kini diadopsi oleh perangkat yang lebih kecil. Fenomena ini dikenal sebagai migrasi fitur. Sistem operasi UNIX, yang dirancang untuk minikomputer PDP-11, menjadi landasan bagi sistem operasi modern seperti Windows, macOS, dan Linux. Hal ini menunjukkan bahwa konsep dasar sistem operasi bersifat universal dan dapat diterapkan pada berbagai jenis komputer, mulai dari mainframe hingga perangkat genggam.

Sejarah Komputer Awal:

Sebelum tahun 1940-an, komputer dirancang untuk menjalankan tugas-tugas spesifik. Namun, gagasan komputer program tersimpan yang lebih umum, yang dikembangkan oleh Alan Turing dan John von Neumann, mengubah paradigma ini. Manchester Mark 1, yang beroperasi pada tahun 1949, dan Ferranti Mark 1, komputer komersial pertama, adalah contoh nyata dari konsep ini. Komputer-komputer awal ini sangat besar dan dioperasikan secara manual dari konsol, dengan program dimasukkan melalui sakelar panel depan, pita kertas, atau kartu berlubang.

Perkembangan Sistem Komputer Khusus:

Seiring waktu, perangkat keras dan perangkat lunak tambahan dikembangkan untuk meningkatkan fungsionalitas komputer. Perangkat seperti pembaca kartu, printer garis, dan pita magnetik menjadi standar. Perangkat lunak seperti perakit, pemuat, dan penghubung dirancang untuk menyederhanakan pemrograman. Perpustakaan fungsi umum memungkinkan penggunaan kembali perangkat lunak, dan driver perangkat dikembangkan untuk mengelola perangkat I/O. Kemunculan kompiler untuk bahasa pemrograman seperti FORTRAN dan COBOL semakin mempermudah proses pemrograman, meskipun operasi komputer menjadi lebih kompleks.

Sistem komputer bersama

Dahulu, programmer harus mengoperasikan komputer secara langsung, yang membuat persiapan menjadi lama dan kurang efisien. Kemudian, operator profesional mulai menggantikan programmer untuk mengoperasikan komputer, sehingga waktu persiapan bisa berkurang. Untuk lebih meningkatkan efisiensi, pekerjaan yang serupa dikelompokkan menjadi batch agar pengaturan tidak perlu dilakukan berulang kali. Namun, muncul masalah baru yaitu CPU sering tidak bekerja saat peralihan antar pekerjaan karena operator harus melakukannya secara manual. Untuk mengatasi ini, diperkenalkan *automatic job sequencing* dengan program *resident monitor* yang secara otomatis mengatur jalannya pekerjaan. Monitor ini menggunakan kartu perintah seperti `$JOB`, `$FTN`, `$RUN`, dan `$END` untuk mendapatkan instruksi, dan terdiri dari interpreter kartu, loader, serta driver perangkat input/output. Inovasi ini membawa manfaat berupa berkurangnya campur tangan manusia dan meningkatnya efisiensi. Akan tetapi, muncul tantangan baru karena perbedaan kecepatan yang signifikan antara CPU dan perangkat input/output seringkali membuat CPU menjadi tidak aktif.

I/O yang tumpang tindih

Dulu, komputer seringkali lambat karena proses memasukkan data (input) dan mengeluarkan hasil (output) menggunakan alat seperti kartu dan printer berjalan sangat pelan, sehingga CPU jadi banyak menunggu. Untuk mengatasinya, muncul ide menggunakan pita magnetik sebagai perantara, di mana data input direkam ke pita dulu baru dibaca komputer, dan hasil output juga ditulis ke pita dulu baru dicetak. Ini membuat CPU lebih sibuk, tapi menambah waktu tunggu. Kemudian, disk hadir sebagai solusi yang lebih baik karena bisa diakses langsung tanpa harus berurutan seperti pita. Lalu, ada inovasi bernama *spooling*, di mana disk digunakan sebagai tempat penyimpanan sementara yang besar untuk data input dan output. Dengan *spooling*, komputer bisa memproses data dan melakukan input/output secara bersamaan, sehingga kerja komputer jadi lebih cepat dan efisien. Ide ini juga menjadi dasar untuk sistem operasi modern yang bisa menjalankan banyak program sekaligus.

Atlas

Atlas adalah komputer canggih yang dikembangkan di Universitas Manchester, Inggris pada akhir tahun 1950-an, yang memiliki beberapa fitur keren seperti sistem batch dan spooling untuk menjalankan banyak pekerjaan secara berurutan dan menyimpan data sementara untuk mempercepat proses. Komputer ini juga punya *device driver* yang terintegrasi dan cara khusus untuk program meminta bantuan sistem operasi melalui instruksi yang disebut *extra codes*. Dalam mengelola memori, Atlas menggunakan drum sebagai memori utama yang besar dan core memory yang lebih cepat sebagai *cache*, serta menerapkan *demand paging* dan memori virtual dengan pemetaan melalui memori asosiatif. Spesifikasinya mencakup kata-kata 48-bit, alamat desimal 24-bit, memori drum sebesar 98 ribu kata dan memori core sebesar 16 ribu kata, dengan ukuran halaman 512 kata dan 32 frame yang tersedia. Untuk mengganti halaman di memori, Atlas menggunakan algoritma pintar yang melihat riwayat akses memori, mencoba memprediksi berdasarkan pola pengulangan, dan menggunakan informasi tentang kapan terakhir kali suatu bagian memori digunakan.

XDS-940

XDS-940 adalah sistem operasi awal yang pintar karena bisa menjalankan banyak program sekaligus dengan cara mengatur memori yang lebih modern, yaitu dengan membagi-bagi memori menjadi bagian-bagian kecil. Sistem ini bahkan bisa membuat program berbagi kode dan punya cara khusus untuk program meminta bantuan sistem operasi. Dengan kemampuannya mengatur banyak proses dan membuat mereka berkomunikasi, XDS-940 jadi salah satu sistem operasi pertama yang memungkinkan banyak orang memakai komputer yang sama dalam waktu yang berbeda-beda.

THE

Sistem operasi THE dibuat di Belanda pada tahun 1960-an untuk komputer EL X8 yang punya memori kecil. Keistimewaan THE adalah desainnya yang rapi seperti kue lapis dan cara kerjanya yang menggunakan banyak program kecil yang bekerja bersama-sama dan saling menunggu giliran. Program-program ini bertugas menjalankan tugas seperti menerjemahkan kode, menjalankan program, dan mencetak hasil.  
Untuk mengatur siapa yang duluan menggunakan "otak" komputer (CPU), THE punya cara pintar dengan memberikan prioritas lebih tinggi kepada program yang baru atau yang sering berinteraksi dengan perangkat lain. Karena memori komputernya kecil, THE menggunakan cara khusus untuk membagi-bagi memori. Karena hanya bisa mengerti bahasa Algol, program penterjemah bahasa ini otomatis membantu mengatur memori. Jika data yang dibutuhkan belum ada di memori utama, data itu akan diambil dari penyimpanan yang lebih besar. THE juga punya cara untuk mencegah masalah "saling tunggu" antar program.  
Ada juga sistem mirip bernama Venus yang juga punya desain berlapis dan cara kerja program yang saling menunggu giliran. Tapi, Venus lebih cepat karena bagian dalamnya dibuat dengan cara yang lebih canggih. Tidak seperti THE yang menjalankan satu tugas besar dalam satu waktu, Venus bisa dipakai oleh banyak orang sekaligus. Venus juga punya cara yang lebih pintar dalam mengatur memori dengan menggabungkan dua cara sekaligus.

RC 4000

RC 4000 adalah sistem operasi yang dibuat pada akhir 1960-an dengan ide yang beda. Alih-alih jadi sistem biasa, RC 4000 lebih fokus membuat "inti" sistem yang bisa dipakai untuk banyak jenis komputer. Cara kerjanya seperti membangun rumah dengan bagian-bagian yang bisa dipasang-pasang.  
Di dalam RC 4000, semua bagian sistem, termasuk program dan alat seperti printer, berkomunikasi dengan mengirim "surat" atau pesan. Pesan-pesan ini diurus oleh inti sistem. Bayangkan seperti bermain dengan teman, kalian semua berbicara lewat satu orang yang menyampaikan pesan. Cara ini membuat semua bagian sistem bekerja sama dengan teratur dan menjadi salah satu ide penting untuk membuat sistem operasi yang lebih modern.

CTSS

CTSS adalah sistem operasi *time-sharing* eksperimental dari MIT yang diperkenalkan pada tahun 1961, memungkinkan hingga 32 pengguna berinteraksi secara langsung melalui terminal. Sistem ini dijalankan pada komputer IBM 7090 dan menggunakan strategi penjadwalan *multilevel feedback queue*, yang menyesuaikan waktu eksekusi program berdasarkan performa sebelumnya. Meskipun sederhana dan terbatas, CTSS membuktikan bahwa konsep *time-sharing* layak digunakan, dan menjadi cikal bakal bagi pengembangan sistem-sistem lanjutan seperti MULTICS.

MULTICS

MULTICS merupakan lanjutan dari sistem CTSS yang dirancang untuk memberikan layanan komputasi seperti halnya layanan utilitas umum, seperti listrik. Sistem ini memperkenalkan konsep inovatif seperti *paged segmentation*, integrasi alamat virtual ke dalam sistem berkas, dan arsitektur berlapis yang mendukung keamanan proses. Ditulis sebagian besar dalam PL/1 dan dikembangkan untuk mendukung multiprosesor, MULTICS menjadi tonggak penting dalam sejarah sistem operasi modern, yang kemudian menginspirasi lahirnya UNIX dan banyak fitur keamanan serta struktur direktori yang kita kenal saat ini.

IBM OS/360

Perkembangan sistem operasi IBM menunjukkan evolusi dari sistem batch sederhana ke sistem *time-sharing* yang kompleks. IBM/360 dengan OS/360 mencoba menyatukan platform IBM yang beragam, namun kompleksitas dan keterbatasan arsitektur membatasi performa dan fleksibilitasnya. Meski *virtual memory* dan fitur-fitur lanjutan ditambahkan di versi-versi berikutnya seperti MVS, IBM tetap menghadapi tantangan dalam mewujudkan visi *time-sharing* seperti pada TSS/360. Kegagalan TSS/360 dan MULTICS mencerminkan bahwa solusi komputasi besar tidak selalu praktis, terutama ketika teknologi komputasi mulai bergeser ke arah sistem yang lebih kecil dan terdistribusi seperti minikomputer dan PC.

TOPS-20

TOPS-20, sistem operasi warisan dari TENEX, menjadi puncak inovasi *time-sharing* yang dikembangkan dari komputer PDP-10 oleh BBN dan kemudian diadopsi oleh DEC. Dengan fitur *virtual memory* dan antarmuka baris perintah yang interaktif, TOPS-20 menjelma menjadi sistem *time-sharing* paling populer saat itu. Namun, seiring berjalannya waktu dan pergeseran teknologi, DEC menghentikan pengembangan sistem 36-bit ini dan beralih ke arsitektur 32-bit VAX dan sistem operasi VMS yang lebih modern dan *business-oriented*.

CP/M and MS/DOS

Perkembangan komputer pribadi dimulai dari mesin sederhana yang menjalankan satu program pada satu waktu. CP/M menjadi standar awal bagi komputer berbasis Intel 8080, menyediakan antarmuka teks dan fungsionalitas dasar. Namun, kehadiran IBM PC membawa perubahan besar. MS-DOS, hasil kerja sama IBM dengan Microsoft, menjadi penerus CP/M untuk prosesor 16-bit Intel 8086. Dengan fitur yang lebih kaya namun tetap sederhana, MS-DOS mendominasi era awal komputer pribadi meski tanpa dukungan fitur modern seperti proteksi memori.

Sistem Operasi Macintosh dan Windows

Kemunculan CPU 16-bit mendorong sistem operasi komputer pribadi menjadi lebih canggih. Apple Macintosh menjadi pelopor GUI untuk pengguna rumahan pada 1984, namun kalah saing dengan Windows yang berjalan di berbagai merek komputer. Seiring perkembangan teknologi, komputer pribadi menyamai kemampuan mainframe, menggeser minikomputer dan membuka era baru untuk server. Kini, Windows dan Mac OS terus bersaing, sementara Linux makin diminati oleh kalangan teknis dan bahkan digunakan untuk pendidikan global melalui proyek seperti OLPC.

Mach

Mach adalah sistem operasi yang dikembangkan di Carnegie Mellon University (CMU) pada pertengahan 1980-an sebagai penerus dari sistem Accent. Meskipun mengambil konsep komunikasi dari Accent, banyak fitur penting Mach—seperti manajemen memori virtual dan sistem thread—dibangun dari nol. Tujuan Mach adalah untuk tetap kompatibel dengan UNIX (khususnya 4.3 BSD), mendukung komputasi paralel dan terdistribusi, serta memiliki kernel yang lebih sederhana dan fleksibel.  
Awalnya, Mach dikembangkan dengan menggantikan bagian-bagian kernel BSD secara bertahap. Pada 1986, sistem ini sudah berjalan di mesin DEC VAX, kemudian diperluas ke arsitektur lain seperti SUN dan IBM. Puncaknya adalah Mach 3, yang memperkenalkan arsitektur microkernel: semua fitur UNIX dipindahkan ke server user-mode, sementara kernel hanya menangani fungsi dasar seperti manajemen memori dan komunikasi antar proses.  
Pendekatan ini memungkinkan Mach untuk menjalankan beberapa sistem operasi sekaligus di atas satu kernel, mirip seperti konsep mesin virtual. Komunikasi antar proses dilakukan secara eksklusif lewat pesan, yang juga diintegrasikan dengan sistem memori virtual untuk efisiensi. Mach juga mendukung multiprocessing secara alami, dengan penggunaan thread ringan di dalam satu proses.  
Pada akhir 1980-an, Mach menarik perhatian industri saat dijadikan basis untuk sistem OSF/1 oleh Open Software Foundation dan juga NeXTSTEP—sistem yang dikembangkan oleh Steve Jobs setelah meninggalkan Apple. Walaupun OSF/1 dan NeXTSTEP tidak mendominasi pasar, kernel Mach tetap hidup di balik layar. Kini, ia menjadi bagian inti dari kernel XNU milik Apple, yang digunakan dalam macOS dan iOS, meskipun sudah mengalami banyak modifikasi.

HYDRA

Sistem keamanan komputer yang pintar dan fleksibel. Hydra punya aturan dasar tentang siapa boleh melakukan apa pada file atau program. Pengguna juga bisa membuat aturan tambahan. Kalau sebuah program mau melakukan sesuatu, Hydra akan mengecek dulu apakah program itu punya "izin" yang benar. Ada juga cara aman agar program bisa saling membantu tanpa menimbulkan masalah. Hydra seperti bangunan yang punya banyak lapisan perlindungan untuk menjaga semuanya tetap aman dan teratur.  
Amplifikasi kemampuan adalah cara agar sebuah program bisa melakukan sesuatu yang biasanya tidak diizinkan. Amplifikasi berguna agar program bisa melakukan tugas tertentu dengan benar. Namun, ada risiko kalau program yang mendapatkan izin khusus ini ternyata berbuat tidak semestinya, misalnya merusak data. Hydra mengatasi masalah ini dengan membatasi bagaimana amplifikasi bisa terjadi.  
Hydra membuat layanan berjalan sebagai program terpisah dengan aturan sendiri. Program utama tidak bisa langsung mengakses data penting milik layanan. Hydra menyediakan cara khusus agar program utama bisa meminta layanan, dan layanan akan memberikan hasilnya tanpa membahayakan data miliknya atau data program utama. Hydra dibangun seperti tumpukan lapisan perlindungan. Di bagian paling bawah ada "inti" sistem yang sangat penting dan punya kendali penuh. Di atas inti ini, ada subsistem-subsistem yang mengatur sumber daya seperti memori atau file. Pembuat subsistem bisa menentukan aturan sendiri tentang bagaimana sumber daya ini digunakan oleh program lain

CAP

Sistem CAP punya dua jenis "izin" atau kemampuan. Yang pertama adalah data capability. Ini seperti kunci biasa yang memberikan hak standar untuk membaca, menulis, dan menjalankan bagian-bagian penyimpanan data (seperti file). Yang kedua adalah software capability. Ini adalah jenis izin yang lebih khusus dan dilindungi oleh cpu kecil di dalam komputer CAP. Izin ini bisa dibuat oleh programer sebagai bagian dari prosedur yang dilindungi. Dengan izin ini, sebuah program bisa sementara waktu mendapatkan hak khusus untuk membaca atau mengubah data tertentu. Ini seperti memberikan "kartu akses khusus" yang hanya berlaku untuk tugas tertentu. Meskipun begitu, sistem CAP tetap punya aturan dasar yang tidak bisa dilanggar, yaitu program biasa tidak bisa langsung mengakses bagian-bagian penting dari sistem tanpa izin yang benar.
