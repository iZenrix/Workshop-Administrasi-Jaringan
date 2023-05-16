
# Instalasi Web Server & FTP

![](https://www.seekpng.com/png/detail/416-4164571_logo-pens-png-electronic-engineering-polytechnic-institute-of.png)


## Anggota Kelompok:

- Muhammad Fajrul Falah Subakti (3121600035)
- Andriana Wahyu Hapsari (3121600040)
- Alan Tri Arbani Hidayat (3121600056)


## Instalasi Web Server (Apache)

Berikut adalah langkah-langkah instal Apache:

- Memperbarui paket yang tersedia ke versi terbaru: 

    ```
    sudo apt update
    ```

- Menginstal Apache dengan menjalankan perintah berikut: 

    ```
    sudo apt install apache2
    ```

    <img src="./gambar/install_apache.JPG">

Setelah instalasi selesai, Selanjutnya menyesuaikan pengaturan firewall untuk menginsinkan akses dari luar ke port web default.

- Melihat list dari ufw application yang tersedia:

    ```
    sudo ufw app list
    ```
    
    <img src="./gambar/ufw_app_list.JPG">

- Untuk mengizinkan apache diakses dari jaringan public yakni port 80 untuk HTTP, menjalankan perintah:

    ```
    sudo ufw allow in 'Apache'
    ```

- Setelah instalasi apache dan konfigurasi firewall pada langkah sebelumnya, selanjutnya mengecek status dari apache dengan perintah dibawah ini.

    ```
    sudo systemctl status apache2
    ```
    
    <img src="./gambar/check_apache_installation.JPG">

- Untuk memastikan berjalan dengan cara mengakses alamat IP dari server atau komputer yang terinstal Apache
    
    <img src="./gambar/test_apache.JPG">



## Instalasi MySQL

Pada Ubuntu 22.04 MySQL 8 sudah dimasukan sebagai versi default di repositori Jammy Jellyfish (nama ubuntu 22.04). Berikut cara melakukan instalasi MySQL.

- Melakukan instalasi MySQL dengan perintah:

    ```
    sudo apt install mysql-server
    ```

    <img src="./gambar/install_MySQL_server.JPG">

- Setelah proses instalasi selesai, kemudian cek status apakah MySQL sudah berjalan dengan perintah:

    ```
    sudo service mysql status
    ```

    <img src="./gambar/mySQL_status.JPG">

- Untuk melihat versi MySQL :

    ```
    mysqladmin -u root -p version
    ```

    <img src="./gambar/mysql_version.JPG">



## Instalasi PHP

- Menginstal PHP, modul Apache PHP serta menggunakan MySQL dengan PHP menjalankan perintah:

    ```
    sudo apt install php libapache2-mod-php php-mysql
    ```

    <img src="./gambar/install_PHP.JPG">

- Setelah instalasi selesai, jalankan perintah berikut untuk mengonfirmasi versi PHP

    ```
    php -v
    ```

    <img src="./gambar/php_version.JPG">

## Instalasi FTP Server (PROFTPD)
- Melakukan instalasi PROFTPD:

    ```
    sudo apt install proftpd -y
    ```

    <img src="./gambar/install_ProFTPD.JPG">

- Memulai layanan dan mengaktifkan proftpd dengan perintah:

    ```
    sudo systemctl start proftpd
    sudo systemctl enable proftpd
    ```

- Cek status apakah sudah berjalan:

    ```
    sudo systemctl status proftpd
    ```

    <img src="./gambar/install _ProFTPD_2.JPG">






    
    