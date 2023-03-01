EVOLUSI OS:
Evolusi OS (Operating System) adalah proses perubahan yang terjadi pada sistem operasi dari waktu ke waktu. OS adalah perangkat lunak yang mengelola sumber daya komputer dan memungkinkan interaksi antara pengguna dan perangkat keras komputer. Evolusi OS terjadi karena adanya perubahan dalam teknologi komputer dan kebutuhan pengguna.

Sejak diciptakannya komputer pertama pada tahun 1940-an, OS telah mengalami banyak perubahan. Pada awalnya, OS hanya dapat digunakan oleh para ahli komputer dan sangat terbatas dalam fungsinya. Namun, dengan perkembangan teknologi, OS menjadi lebih kompleks dan dapat digunakan oleh banyak orang dengan berbagai kebutuhan.

Pada tahun 1960-an, OS pertama yang digunakan pada mainframe komputer muncul. OS ini dikenal sebagai batch processing system, yang berarti program-program harus dikelompokkan dan dijalankan secara bersamaan. Kemudian, OS timesharing diperkenalkan, yang memungkinkan beberapa pengguna untuk menggunakan komputer secara bersamaan.

Pada tahun 1980-an, munculah OS desktop pertama, seperti MS-DOS dan Mac OS. Kemudian, OS Windows yang populer diluncurkan pada tahun 1990-an. OS ini memiliki antarmuka pengguna yang lebih ramah dan mudah digunakan.

Dalam dekade terakhir, OS telah berkembang dengan cepat dan terus mengalami perubahan besar. Salah satu perubahan besar adalah munculnya OS mobile, seperti Android dan iOS, yang dibuat khusus untuk perangkat seluler seperti smartphone dan tablet. OS juga semakin terintegrasi dengan cloud computing dan teknologi lainnya, sehingga pengguna dapat mengakses data mereka dari mana saja dan kapan saja.

Dalam kesimpulannya, evolusi OS terus berlanjut seiring dengan kemajuan teknologi. OS terbaru mampu memberikan pengalaman yang lebih mudah, cepat, dan aman bagi pengguna dan memungkinkan komputer dan perangkat seluler menjadi lebih terkoneksi dan terintegrasi dengan dunia digital.


Perintah Su dan Sudo:

Perintah su dan sudo adalah perintah yang digunakan pada sistem operasi Linux dan Unix untuk memperoleh hak akses superuser atau root.

Perintah su singkatan dari "switch user" dan digunakan untuk mengalihkan identitas pengguna saat ini menjadi pengguna lain. Dalam kebanyakan distribusi Linux, ketika menjalankan perintah su, kita akan diminta untuk memasukkan password root. Setelah berhasil diotentikasi sebagai root, kita akan memiliki hak akses penuh pada sistem dan bisa melakukan perintah apa saja yang diizinkan oleh sistem.

Contoh penggunaan perintah su adalah:

![](2023-02-27-17-30-25.png)

Perintah sudo singkatan dari "superuser do" dan memungkinkan pengguna untuk menjalankan perintah tertentu dengan hak akses superuser tanpa harus masuk sebagai pengguna root secara penuh. Ketika menjalankan perintah dengan sudo, pengguna akan diminta untuk memasukkan password pengguna mereka sendiri, bukan password root.

Contoh penggunaan perintah sudo adalah:

![](2023-02-27-17-33-19.png)

Perintah di atas memungkinkan pengguna untuk menjalankan perintah apt-get update dengan hak akses superuser tanpa harus masuk sebagai root.

Perbedaan utama antara su dan sudo adalah bahwa su memungkinkan pengguna untuk beralih ke akun root sepenuhnya, sedangkan sudo memberikan hak akses superuser pada perintah tertentu saja. Penggunaan sudo lebih disarankan karena lebih aman dan mengurangi risiko penggunaan yang salah dan tidak sengaja melakukan perintah yang merusak sistem.



Package maintenance pada Linux Ubuntu adalah proses memperbarui, menginstal, dan menghapus paket perangkat lunak pada sistem operasi Ubuntu. Paket perangkat lunak adalah kumpulan file yang terdiri dari program, konfigurasi, dan sumber daya lain yang terkait dengan program tertentu. Sistem manajemen paket di Ubuntu menggunakan Advanced Packaging Tool (APT) untuk mengelola paket perangkat lunak.

Berikut adalah beberapa perintah penting yang digunakan dalam package maintenance di Linux Ubuntu:

sudo apt update - perintah ini digunakan untuk memperbarui indeks paket perangkat lunak pada sistem. Ini memperbarui informasi paket dari repositori yang tersedia, termasuk paket baru yang tersedia untuk diinstal.

sudo apt upgrade - perintah ini digunakan untuk memperbarui semua paket yang telah diinstal pada sistem.

sudo apt install [nama-paket] - perintah ini digunakan untuk menginstal paket perangkat lunak baru pada sistem.

sudo apt remove [nama-paket] - perintah ini digunakan untuk menghapus paket perangkat lunak dari sistem.

sudo apt autoremove - perintah ini digunakan untuk menghapus paket perangkat lunak yang tidak diperlukan lagi pada sistem.

Selain itu, Ubuntu juga menyediakan software center atau pusat perangkat lunak grafis yang memudahkan pengguna untuk mencari dan menginstal paket perangkat lunak yang dibutuhkan dengan antarmuka grafis yang mudah digunakan.

Dalam menjalankan proses package maintenance, sangat penting untuk memastikan bahwa paket perangkat lunak yang diinstal selalu diperbarui dengan versi terbaru dan tercukupi keamanan perangkat lunak. Hal ini dapat dilakukan dengan secara rutin melakukan update dan upgrade sistem, serta menginstal paket perangkat lunak dari sumber yang terpercaya.




Repository pada Ubuntu adalah tempat penyimpanan online yang berisi paket perangkat lunak yang dapat diinstal pada sistem Ubuntu. Paket-paket tersebut dapat diinstal melalui perintah apt-get atau software center dengan bantuan sumber daya dari repository. Ada beberapa repository yang telah tersedia pada Ubuntu, dan juga bisa menambahkan repository pihak ketiga yang menawarkan paket perangkat lunak tambahan.

Berikut adalah cara untuk menambahkan repository pada Ubuntu:

1. Membuka terminal dan mengetikkan perintah berikut:\
`sudo add-apt-repository [nama-repository]`\
Pada bagian [nama-repository] pengguna harus menggantinya dengan nama repository yang ingin ditambahkan. Contoh:\
`sudo add-apt-repository ppa:example/repository`
2. Setelah itu, sistem akan meminta pengguna untuk mengonfirmasi tindakan tersebut dengan menekan Enter pada keyboard.
3. Setelah berhasil menambahkan repository baru, pengguna harus menjalankan perintah sudo apt update untuk memperbarui indeks paket perangkat lunak pada sistem agar repository yang baru ditambahkan dapat digunakan.

Setelah itu, pengguna dapat mencari dan menginstal paket perangkat lunak yang tersedia dari repository baru tersebut. Namun, penting untuk diingat bahwa menambahkan repository pihak ketiga dapat meningkatkan risiko keamanan sistem, sehingga pengguna harus berhati-hati dan memastikan bahwa repository tersebut terpercaya dan aman.

Untuk mengatur repository di Ubuntu, langkah-langkahnya adalah sebagai berikut:

1. Buka terminal pada Ubuntu dengan menekan tombol Ctrl + Alt + T.
2. Ketik perintah "sudo nano /etc/apt/sources.list" untuk membuka file sources.list dalam editor teks nano.
3. Pada file sources.list, Anda akan melihat daftar repository yang sudah terdaftar di Ubuntu. Setiap repository dinyatakan dengan baris yang dimulai dengan "deb" atau "deb-src".
4. Untuk menambahkan repository baru, salin dan tempelkan baris berikut di akhir file sources.list:
5. deb [sumber]://[nama server]/[direktori]/[versi] [distro] [main] Contoh: deb http://archive.ubuntu.com/ubuntu/ bionic main
6. Baris di atas menunjukkan repository utama Ubuntu yang tersedia pada versi Bionic Beaver.
7. Simpan dan keluar dari editor teks nano dengan menekan tombol Ctrl + X, kemudian tekan Y untuk menyimpan perubahan dan tekan Enter untuk keluar dari editor.
8. Kemudian, jalankan perintah "sudo apt-get update" untuk memperbarui daftar repository Ubuntu dengan repository baru yang telah ditambahkan.
9. Setelah itu, Anda dapat menggunakan perintah "sudo apt-get install" untuk menginstal paket atau program yang tersedia pada repository yang telah ditambahkan.


Multiverse adalah salah satu komponen dari repository Ubuntu yang menyediakan paket perangkat lunak bebas dan terbuka yang tidak dapat didistribusikan di seluruh dunia karena alasan hukum atau lisensi. Paket-paket ini seringkali berisi kode atau konten yang dilindungi hak cipta, paten, atau hak kekayaan intelektual lainnya.

Paket-paket di dalam komponen multiverse tidak diinstal secara otomatis pada Ubuntu, tetapi pengguna dapat mengakses dan menginstalnya dengan menambahkan multiverse ke dalam sumber perangkat lunak pada sistem. Untuk menambahkan multiverse ke dalam sumber perangkat lunak, pengguna dapat mengikuti langkah-langkah berikut:

1. Buka terminal dan ketikkan perintah berikut:\
`sudo add-apt-repository multiverse`
2. Setelah itu, sistem akan meminta pengguna untuk mengonfirmasi tindakan tersebut dengan menekan Enter pada keyboard.
3. Setelah berhasil menambahkan multiverse ke dalam sumber perangkat lunak, pengguna harus menjalankan perintah sudo apt update untuk memperbarui indeks paket perangkat lunak pada sistem agar repository multiverse dapat digunakan.

Setelah itu, pengguna dapat mencari dan menginstal paket perangkat lunak yang tersedia dari multiverse menggunakan perintah apt-get atau melalui software center.

Penting untuk diingat bahwa paket perangkat lunak di dalam multiverse mungkin tidak sepenuhnya terbuka, dan pengguna harus memperhatikan lisensi dan aturan penggunaan untuk setiap paket yang diinstal dari multiverse.



Apt (atau Advanced Package Tool) adalah sebuah sistem manajemen paket pada distribusi Linux, termasuk pada sistem operasi Ubuntu dan Debian. Apt digunakan untuk mengelola paket perangkat lunak pada sistem dan memungkinkan pengguna untuk dengan mudah menginstal, menghapus, dan memperbarui perangkat lunak yang ada pada sistem.

Apt bekerja dengan menggunakan file sumber perangkat lunak, yaitu file yang berisi daftar paket perangkat lunak yang tersedia untuk diinstal pada sistem. File sumber ini disimpan di dalam repository, yaitu server online yang menyediakan paket perangkat lunak untuk diunduh dan diinstal. Repository pada Ubuntu biasanya terdiri dari beberapa komponen, seperti main, universe, restricted, dan multiverse.

Untuk mengelola paket perangkat lunak pada Ubuntu, pengguna dapat menggunakan perintah-perintah Apt pada terminal, seperti:

1. `apt-get update`: perintah ini digunakan untuk memperbarui daftar paket perangkat lunak dari repository yang terpasang pada sistem.
2. `apt-get upgrade`: perintah ini digunakan untuk memperbarui paket perangkat lunak yang telah terpasang pada sistem.
3. `apt-get install [nama-paket]`: perintah ini digunakan untuk menginstal paket perangkat lunak baru pada sistem.
4. `apt-get remove [nama-paket]`: perintah ini digunakan untuk menghapus paket perangkat lunak yang telah terpasang pada sistem.
5. `apt-cache search [kata-kunci]`: perintah ini digunakan untuk mencari paket perangkat lunak berdasarkan kata kunci tertentu.

Apt juga dapat digunakan dengan antarmuka grafis, seperti Ubuntu Software Center, yang memudahkan pengguna untuk mencari dan menginstal paket perangkat lunak dengan antarmuka yang lebih mudah digunakan.

Dalam keseluruhan, Apt merupakan alat yang sangat berguna untuk mengelola paket perangkat lunak pada sistem operasi Ubuntu dan membantu pengguna untuk memperbarui, menginstal, dan menghapus perangkat lunak dengan mudah dan efisien.



Instalasi Package:

MC

MC adalah singkatan dari Midnight Commander, yaitu sebuah program manajer file berbasis teks yang tersedia di berbagai sistem operasi Linux. Program ini memungkinkan pengguna untuk mengelola dan mengorganisir file dan direktori pada sistem dengan antarmuka yang mudah digunakan dan berbasis pada mode teks.

Midnight Commander memungkinkan pengguna untuk melakukan berbagai tugas pada file dan direktori, seperti menyalin, memindahkan, menghapus, dan mengubah nama. Selain itu, program ini juga mendukung beberapa protokol untuk akses jarak jauh, seperti FTP dan SFTP, dan memungkinkan pengguna untuk mengakses file pada sistem yang terhubung melalui jaringan.

MC dilengkapi dengan berbagai fitur, seperti pemformatan teks, editing teks, dan tampilan dua panel untuk memudahkan pengguna dalam mencari dan mengelola file pada sistem. Selain itu, program ini juga mendukung beberapa fitur tambahan seperti pilihan pengaturan tampilan, pilihan shortcut keyboard, dan dukungan untuk ekstensi.

MC dapat diinstal pada sistem operasi Linux dengan menggunakan package manager, seperti apt-get pada Ubuntu atau yum pada Red Hat. Untuk menginstal MC pada Ubuntu, pengguna dapat menggunakan perintah berikut di terminal:

```
sudo apt-get update
sudo apt-get install mc
```

Setelah berhasil diinstal, pengguna dapat membuka Midnight Commander dengan mengetikkan perintah mc pada terminal.

Secara keseluruhan, MC adalah program manajer file yang kuat dan fleksibel yang dapat membantu pengguna Linux dalam mengorganisir dan mengelola file pada sistem dengan mudah dan efisien.


Net tools

Net-tools adalah sebuah package perangkat lunak pada sistem operasi Linux yang terdiri dari serangkaian utilitas jaringan dasar yang digunakan untuk mengelola jaringan pada sistem. Package ini mencakup beberapa perintah yang berguna untuk mendiagnosis dan mengkonfigurasi jaringan pada sistem, seperti ifconfig, netstat, arp, dan route.

Berikut ini adalah beberapa utilitas jaringan yang termasuk dalam package net-tools:

1. ifconfig: digunakan untuk menampilkan dan mengkonfigurasi antarmuka jaringan pada sistem, seperti alamat IP, netmask, dan MAC address.
2. netstat: digunakan untuk menampilkan statistik jaringan pada sistem, seperti koneksi aktif, port yang digunakan, dan jumlah paket yang ditransfer.
3. arp: digunakan untuk menampilkan tabel ARP pada sistem, yang berisi informasi tentang alamat IP dan MAC address dari host di dalam jaringan.
4. route: digunakan untuk menampilkan dan mengatur tabel routing pada sistem, yang digunakan untuk menentukan jalur yang diambil oleh paket data dalam jaringan.

Selain itu, package net-tools juga mencakup utilitas lain seperti hostname, dnsdomainname, dan ipmaddr, yang dapat membantu pengguna dalam mengelola jaringan pada sistem.

Net-tools biasanya sudah terinstal secara default pada banyak distribusi Linux, seperti Ubuntu dan Debian. Namun, pada beberapa distribusi yang lebih baru, seperti CentOS dan Fedora, net-tools telah digantikan oleh package jaringan yang lebih baru, seperti iproute2.

Secara keseluruhan, package net-tools adalah kumpulan utilitas jaringan dasar yang berguna untuk mengelola dan mendiagnosis jaringan pada sistem operasi Linux.


Htop

HTOP adalah package perangkat lunak open-source yang merupakan alternatif dari perintah top pada sistem operasi Linux. Perintah top digunakan untuk menampilkan informasi terkini tentang penggunaan sumber daya pada sistem, seperti pemakaian CPU, pemakaian RAM, dan informasi tentang proses yang sedang berjalan.

HTOP memperluas fungsionalitas top dengan menambahkan antarmuka pengguna yang lebih interaktif dan informatif. Dalam tampilan HTOP, pengguna dapat melihat informasi tentang penggunaan CPU dan RAM pada sistem dalam bentuk grafis, serta mengelola proses yang sedang berjalan dengan mudah menggunakan shortcut keyboard.

Beberapa fitur utama dari package HTOP antara lain:

1. Tampilan informasi penggunaan CPU dan RAM dalam bentuk grafis dan teks.
2. Kemampuan untuk mengurutkan proses berdasarkan berbagai parameter, seperti penggunaan CPU, penggunaan memori, dan waktu mulai.
3. Kemampuan untuk mematikan atau menghentikan proses secara langsung dari antarmuka HTOP.
4. Kemampuan untuk mengubah prioritas proses dan membatalkan pembatasan sumber daya.
5. Shortcut keyboard yang mudah digunakan untuk mengelola proses dengan cepat dan efisien.

HTOP tersedia di banyak distribusi Linux dan dapat diinstal menggunakan package manager seperti apt pada Ubuntu atau yum pada Red Hat. Untuk menginstal HTOP pada Ubuntu, pengguna dapat menggunakan perintah berikut di terminal:
```
sudo apt-get update
sudo apt-get install htop
```

Setelah berhasil diinstal, pengguna dapat membuka HTOP dengan mengetikkan perintah htop pada terminal.

Secara keseluruhan, HTOP adalah package perangkat lunak yang sangat berguna untuk memantau dan mengelola proses pada sistem operasi Linux, dengan antarmuka pengguna yang lebih interaktif dan informatif daripada perintah top bawaan pada Linux.
