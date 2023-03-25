# 🚀 Tugas Kelompok Routing & Hostname
![](https://www.seekpng.com/png/detail/416-4164571_logo-pens-png-electronic-engineering-polytechnic-institute-of.png)

<p align = center>
LAPORAN RESMI <br>
WORKSHOP ADMINISTRASI JARINGAN </br>

<p align = center>
Dosen Pengampu <br>
Dr. Ferry Astika Saputra ST, M.Sc<br><br>

<p align = center>
Disusun Oleh<br>
Muhammad Fajrul Falah Subakti3121600035<br>
Andriana Wahyu Hapsari3121600040<br>
Alan Tri Arbani Hidayat 3121600056<br>
2 D4 IT B<br><br>


### **Setting IP di Interface**
#
- Buka Konfigurasi dimikrotik -> IP -> Addres
- Tambahkan 2 Interface IP Sebagai Berikut
    ```
    Eth1 :
        > Address : 10.252.108.252
        > Network : 10.252.108.0
    Eth2 :
        > Address : 192.168.2.1
        > Network : 192.168.2.0
    ```
### **Seting Default gateway 0.0.0.0/0 & IP route gateway 10.252.108.212**
#
-  Masuk ke IP->Routes
-  Tambahkan Routingan baru
-  Dan konfigurasikan routing default gatewayna
<img src="./images/No 2.png" width="" height="500" /> <br> <br>
- Dst. Address ialah default gatewaynya atau network yang dituju
- Gateway adalah ip routing

### **Setting DHCP Server via DHCP Setup menjadi 192.168.X.100 - 192.168.X.254**
#
1. Pilih menu IP -> DHCP Server -> Klik DHCP Setup
2. Pada jendela DHCP Server Interface pilih ether2
3. Selanjutnya, ketika diminta menentukan IP Address yang akan digunakan sebagai default-gateway oleh DHCP Client masukkan IP 192.168.2.100 - 192.168.2.254 <br> <br>
<img src="./images/No 3.png" width="" height="500" /> <br> <br>

### **Sambungkan PC atau laptop ke jaringan, cek IP address pastikan IP add dari PC mendapatkan IP add dari dhcp server**
#

- Mengecek apakah komputer sudah mendaptkan dengan menggunakan perintah 
```
ip a
```

Komputer sudah mendapatkan IP dari DHCP Server <br> <br>
<img src="./images/No 4.1.png" width="" height="500" /> <br> <br>


### **Power up nyalakan VM, pastikan konfigurasi jaringan BRIDGE dan pastikan mendapatkan IP add dari dhcp server** 
#
-  Konfigurasikan BRIDGE pada VM yang digunakan dengan cara klik Network configuration di VM => Ubah menjadi BRIDGE Adapter
<br><img src="./images/No 5.png" width="" height="500" /> <br><br>

-  Pastikan mendapat IP DHCP dari Jaringan bridge
    ```
    ip a
    ```
<br><img src="./images/No 42.png" width="" height="500" /> <br><br>
Jika ternyata belum mendapatkan IP maka jalankan perintah : <br>
```
sudo dhclient -v
```
<br><img src="./images/No 5.1.png" width="" height="500" /> <br><br>

### **Konfigurasi IP VM Menjadi Static IP : 192.168.X.10** <br>
#
Konfigurasi IP VM dapat melalui GUI maupun CLI, berikut cara setting IP address static di Ubuntu Dekstop : <br>

-  Buka menu pengaturan, pilih tab jaringan. Kemudian klik ikon pengaturan jaringan.
    <img src="./images/No 61.png" width="" height="500" /><br><br>
-  Selanjutnya pilih tab IPv4. Setelah di bawah Metode IPv4 pilih opsi Manual.
    <img src="./images/No 62.png" width="" height="150" /><br><br>
-  Mengisikan IP Adress, Netmask, dan Gateway sesuai dengan yang ditentukan. Setelah itu apply

    <img src="./images/No 63.png" width="" height="500" /><br><br>

### **Konfigurasi NTP ke 0. id.pool.ntp.org 1. id.pool.ntp.org**
#
**1. Set Up NTP CLient Mengubah Pengaturan jam Sistem**
- Untuk melihat daftar zona waktu menjalankan perintah : <br>
```
sudo timedatectl set-timezone Asia/Jakarta
```

- Mengatur RTC ke UTC, menjalankan perintah <br>
```
sudo timedatectl set-local-rtc false
```
 
<br> 

**2. install NTP server** 
<br>
Sebelum melakukan install maka perlu mengubah kembali IP jaringan yang sebelumnya static menjadi DHCP kembali. <br>
- Pertama update terlebih dahulu server dengan menggunakan perintah <br>
```
sudo apt update && sudo apt -y upgrade
```

- menginstall NTP Srver menggunakan perintah : <br>
```
sudo apt -y install ntp
```
<br>

**3. Konfigurasi NTP Server**
- mengedit `ntp.conf` dengan menggunkan perintah : <br>
```
sudo nano /etc/ntp.conf
``` 
- memberikan command pada <br>
```
#pool 0.ubuntu.pool.ntp.org iburst 
#pool 1.ubuntu.pool.ntp.org iburst 
#pool 2.ubuntu.pool.ntp.org iburst
#pool 3.ubuntu.pool.ntp.org iburst 
#pool 4.ubuntu.pool.ntp.org iburst 
#pool 5.ubuntu.pool.ntp.org iburst
```


- Menambahkan baris  <br>
```
server 0.id.pool.ntp.org
server 1.id.pool.ntp.org
``` 
jika sudah, simpan konfigurasi dan keluar dar teks editor. <br><br>

- Restart NTP service menggunakan perintah : <br>
```
sudo systemctl restart ntp
``` 


- Mengkonfirmasi apakah NTP service telah aktif menggunkan perintah : <br>
```
systemctl status ntp
``` 
- Cek keberhasilan konfigurasi dengan menggunakan command :
```
ntpq -p
``` 
<img src="./images/No 7.png" width="" height="300" /><br><br>

- Mengecek kembali settingan waktu dan tanggal menggunakan perintah : <br>

``` 
timedatectl
```
<br>

### Hasilnya <br> <br>
<img src="./images/No 72.png" width="" height="300" /> <br><br>

### **Konfigurasi sudo**
#
- Masuk ke konfigurasi sudoers

``` 
sudo nano /etc/sudoers
```
- Karena VM adalah Ubuntu tidak perlu menambahkan akses sudoers ke sudoers jika OS adalah Debian maka tambahkan baris seperti dibawah

    <img src="./images/No 82.png" width="" height="300" /> <br>
- Save File dan keluar, maka konfigurasi akan langsung terapply

### **Ganti hostname VM server10.kelompokX.takehome.com**
#
- Sebelum menghubahnya, bisa dicek terlebih dahulu saat ini nama dari hostname sebelum diubah.
    ```
    hostnamectl
    ```
    <img src="./images/No 9.png" width="" height="300" /> <br>

- Untuk mengubahnya gunakan command dibawah (contoh mengubah ke server10.kelompok2.takehome.com)
    ```
    sudo hostnamectl set-hostname server10.kelompok2.takehome.com
    ```

- Coba cek sekali lagi apakah hostname sudah mengalami perubahan
    ```
    hostnamectl
    ```
    <img src="./images/No 92.png" width="" height="300" /> <br>