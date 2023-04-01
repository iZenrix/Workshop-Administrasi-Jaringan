# **LAPORAN RESMI WORKSHOP ADMINISTRASI JARINGAN** </br>

## **Sub-Bab**

Domain Name Service (DNS)

## **Dosen Pengampu** </br>

Dr. Ferry Astika Saputra ST, M.Sc</br>

## **Disusun Oleh**</br>

Muhammad Fajrul Falah Subakti - 3121600035</br>
Andriana Wahyu Hapsari - 3121600040</br>
Alan Tri Arbani Hidayat - 3121600056</br>
2 D4 IT B</br></br>

---

## **Domain Name Service (DNS)**

Domain Name Service **(DNS)** adalah layanan Internet yang memetakan alamat IP dan nama domain yang memenuhi syarat **(FQDN)** satu sama lain. Dengan cara ini, DNS mengurangi kebutuhan untuk mengingat alamat IP. Komputer yang menjalankan DNS disebut ***name servers***. Ubuntu dilengkapi dengan **BIND** (Berkley Internet Naming Daemon), program yang paling umum digunakan untuk mengelola name servers di Linux.

</br>

---

## **Installation**

Untuk menginstall BIND9, pada terminal jalankan perintah berikut:

```
sudo apt install bind 9
```

</br>

---

## **Overview**

File konfigurasi DNS disimpan di direktori `/etc/bind`. File konfigurasi utama adalah `/etc/ bind/named.conf`, yang dalam tata letak yang disediakan oleh paket menyertakan berkas-berkas berikut:

- ```/etc/bind/named.conf.options```: opsi DNS global
- ```/etc/bind/named.conf.local```: untuk zona User
- ```/etc/bind/named.conf.default-zones```: zona default seperti localhost.
  
</br>

---

## **Caching Nameserver**

Konfigurasi default bertindak sebagai *caching server*. Cukup hapus komentar dan edit bagian *forwarders* di ``` /etc/bind/named.conf. ``` untuk mengatur alamat IP server DNS ISP Anda.

</br>

<img src="./images/Caching Nameserver.png" width="" height="350" />

</br>
Untuk mengaktifkan konfigurasi baru, mulai ulang server DNS. Dari prompt terminal dengan perintah berikut:

```
sudo systemctl restart bind9.service
```

</br>

---

## **Forward Zone File (Domain ke IP)**

Untuk menambahkan zona DNS ke BIND9 dan mengubah BIND9 menjadi server Primer, edit bagian ```/etc/bind/named.conf.local```:

<img src="./images/Forward Zone File.png" width="" height="350" />

Sekarang gunakan *zone file* yang sudah ada sebagai template untuk membuat berkas ```/etc/bind/db.example.com``` dengan menggunakan perintah berikut:

```
sudo cp /etc/bind/db.local /etc/bind/db.example.com
```

</br>

*Forward Zone File (Template db.local)*:
</br>

<img src="./images/Forward Zone File (template dblocal).png" width="" height="350" />

</br>

*Forward Zone File (Setelah diedit)*:
</br>

<img src="./images/Forward Zone File (after edit).png" width="" height="350" />

</br>

Restart BIND9 agar perubahan dapat diterapkan:

```
sudo systemctl restart bind9.service
```

</br>

---

## **Reverse Zone File (IP ke Domain)**

Sekarang setelah zona disiapkan dan mengubah nama domain menjadi Alamat IP, zona Reverse perlu ditambahkan untuk memungkinkan DNS mengubah Alamat IP menjadi nama. Edit pada bagian ```/etc/bind/named.conf.local``` dan tambahkan syntax berikut:

```
zone ”1.168.192.in−addr.arpa”{
    type master;
    file”/etc/bind/db.192”;
};
```

Sekarang, buat file ```/etc/bind/db.192:``` dengan perintah:

```
sudo cp /etc/bind/db.127 /etc/bind/db.192
```

Selanjutnya, edit ```/etc/bind/db.192``` dengan mengubah opsi yang sama dengan ```/etc/bind/db.example.com```:

</br>
*Reverse Zone File (Template db.127)*:
</br>

<img src="./images/Reverse Zone File (template db127).png" width="" height="350" />

</br>

*Reverse Zone File (Setelah diedit)*:
</br>

<img src="./images/Reverse Zone file (After Edit).png" width="" height="350" />

</br>

Setelah membuat *Reverse Zone File*, mulai ulang BIND9:

```
sudo systemctl restart bind9.service
```

</br>

---

## Testing

Langkah pertama dalam menguji BIND9 adalah menambahkan Alamat IP nameserver ke host resolver. Nameserver utama
harus dikonfigurasi seperti halnya host lain untuk memeriksa ulang berbagai hal. Buka DNS client
untuk mengetahui detail tentang cara menambahkan alamat nameserver ke network client. Edit nameserver dan parameter untuk domain pada file ```/etc/resolv.conf```:

*resolv.conf (Sebelum diedit)*:
</br>

<img src="./images/resolv conf (before edit).png" width="" height="350" />

</br>

*resolv.conf (Setelah diedit)*:
</br>

<img src="./images/resolvf conf (after edit).png" width="" height="350" />

</br>

Terdapat banyak cara untuk melakukan testing, pada kali ini kelompok kami menggunakan metode *ping* untuk mengetahui apakah konfigurasi sudah berhasil atau belum. Command yang diperlukan:

```
ping www.example.com
```

Screenshoot testing di server:
<img src="./images/Testing ping on server.png" width="" height="350" />

</br>

Testing pada PC client

Atur *dns/resolv.conf* terlebih dahulu pada PC client:

<img src="./images/Resolvconf Sebelum testing di pc client.png" width="" height="350" />

Testing ping berhasil di PC Client:

<img src="./images/Testing ping on PC Client.png" width="" height="350" />

</br>

Sekian dan Terima Kasih 😊😊
