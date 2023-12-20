# Jarkom-Modul-5-B14-2023

## Kontributor

| Nama Kontributor | NRP |
|------------------|-----|
| Gabrielle Immanuel Osvaldo Kurniawan | 5025211135 |
| Muhammad Arkan Karindra Darvesh | 5025211236 |

## Table of Contents

- [VLSM](#vlsm)

## Pembagian Subnet

<img width="581" alt="TopoMod5" src="https://github.com/Arkandrvesh/Jarkom-Modul-5-B14-2023/assets/116497822/b7eb34ce-bd65-4b05-a5bb-be51d87c2377">

Keterangan :

- Richter adalah DNS Server
- Revolte adalah DHCP Server
- Sein dan Stark adalah Web Server
- Jumlah Host pada SchwerMountain adalah 64
- Jumlah Host pada LaubHills adalah 255
- Jumlah Host pada TurkRegion adalah 1022
- Jumlah Host pada GrobeForest adalah 512

## VLSM (Variable Length Subnet Masking)

Menentukan jumlah alamat IP yang dibutuhkan oleh tiap subnet dan melabel netmask berdasarkan jumlah IP yang dibutuhkan.

| **Subnet ** | **Jumlah IP** | **Netmask** |
| :---------: | :-----------: | :---------: |
|     A1      |       2       |     /30     |
|     A2      |       2       |     /30     |
|     A3      |      66       |     /25     |
|     A4      |      256      |     /24     |
|     A5      |       2       |     /30     |
|     A6      |       2       |     /30     |
|     A7      |       2       |     /30     |
|     A8      |       2       |     /30     |
|     A9      |     1023      |     /21     |
|     A10     |      514      |     /22     |
|  **Total**  |   **1871**    |   **/20**   |

## VLSM Tree
Subnet besar yang dibentuk memiliki NID 192.185.0.0 dengan netmask /20 sehingga pembagian IP berdasarkan NID dan netmask dihitung sesuai dengan pohon berikut.

<img width="599" alt="Capture" src="https://github.com/Arkandrvesh/Jarkom-Modul-5-B14-2023/assets/116497822/c7408952-9d8c-4815-b17f-444c1ab12280">

<img width="894" alt="Capture1" src="https://github.com/Arkandrvesh/Jarkom-Modul-5-B14-2023/assets/116497822/a727f93c-7aaa-49a6-9392-fcfe4b5f1c72">

Pada metode Variable Length Subnet Masking (VLSM), proses penurunan subnet dilakukan berdasarkan panjang (length) subnet mask yang lebih kecil. Sebagai contoh, jika kita memiliki subnet awal dengan prefix /20, maka akan dilakukan penurunan menjadi subnet yang lebih kecil, misalnya menjadi /21. Pembagian alamat IP dalam VLSM mengikuti suatu tabel tertentu. Selanjutnya, apabila terdapat subnet yang dapat dialokasikan, kita langsung melaksanakan proses alokasi tersebut. Pendekatan ini diulang secara berulang hingga seluruh subnet selesai dialokasikan sesuai kebutuhan.

## Pembagian IP VLSM
| Subnet | Node           | IP          | Netmask         | Length | NID         | Broadcast    |
| ------ | -------------- | ----------- | --------------- | ------ | ----------- | ------------ |
| A1     | Fern           | 192.185.0.1   | 255.255.255.252 | 30     | 192.185.14.128   | 192.185.14.131    |
|        | Revolte        | 192.185.0.2   | 255.255.255.252 | 30     |             |              |
|        |                |             |                 |        |             |              |
| A2     | Fern           | 192.185.0.5   | 255.255.255.252 | 30     | 192.185.14.132   | 192.185.14.135    |
|        | Richter        | 192.185.0.6   | 255.255.255.252 | 30     |             |              |
|        |                |             |                 |        |             |              |
| A3     | Himmel         | 192.185.0.129 | 255.255.255.128 | 25     | 192.185.14.0 | 192.185.14.127  |
|        | Fern           | 192.185.0.130 | 255.255.255.128 | 25     |             |              |
|        | SchwerMountain | DHCP        | 255.255.255.128 | 25     |             |              |
|        |                |             |                 |        |             |              |
| A4     | Himmel         | 192.185.1.1   | 255.255.255.000 | 24     | 192.185.12.0   | 192.185.13.255  |
|        | LaubHills      | DHCP        | 255.255.255.000 | 24     |             |              |
|        |                |             |                 |        |             |              |
| A5     | Frieren        | 192.185.0.9   | 255.255.255.252 | 30     | 192.185.14.136   | 192.185.14.139   |
|        | Himmel         | 192.185.0.10  | 255.255.255.252 | 30     |             |              |
|        |                |             |                 |        |             |              |
| A6     | Frieren        | 192.185.0.13  | 255.255.255.252 | 30     | 192.185.14.140  | 192.185.14.143   |
|        | Stark          | 192.185.0.14  | 255.255.255.252 | 30     |             |              |
|        |                |             |                 |        |             |              |
| A7     | Aura           | 192.185.0.17  | 255.255.255.252 | 30     | 192.185.14.144  | 192.185.14.147   |
|        | Frieren        | 192.185.0.18  | 255.255.255.252 | 30     |             |              |
|        |                |             |                 |        |             |              |
| A8     | Aura           | 192.185.0.21  | 255.255.255.252 | 30     | 192.185.14.148  | 192.185.14.151   |
|        | Heiter         | 192.185.0.22  | 255.255.255.252 | 30     |             |              |
|        |                |             |                 |        |             |              |
| A9     | Heiter         | 192.185.8.1   | 255.255.248.000 | 21     | 192.185.0.0   | 192.185.7.255 |
|        | TurkRegion     | DHCP        | 255.255.248.000 | 21     |             |              |
|        |                |             |                 |        |             |              |
| A10    | Heiter         | 192.185.4.1   | 255.255.252.000 | 22     | 192.185.8.0   | 192.185.11.255  |
|        | Sein           | 192.185.4.2   | 255.255.252.000 | 22     |             |              |
|        | GrabForest     | DHCP        | 255.255.252.000 | 22     |             |              |

## Topologi GNS

<img width="435" alt="topoGNS-M5" src="https://github.com/Arkandrvesh/Jarkom-Modul-5-B14-2023/assets/116497822/86fbc5f8-fbc4-4e0b-a7a8-6b098ff6ad9c">

## Route and Subneting

### Konfigurasi
- Revolte

```bash
auto eth0
iface eth0 inet static
	address 192.185.14.130
	netmask 255.255.255.252
	gateway 192.185.14.129
```

- Richter

```bash
auto eth0
iface eth0 inet static
	address 192.185.14.134
	netmask 255.255.255.252
	gateway 192.185.14.133
```

- Fern

```bash
auto eth0
iface eth0 inet static
	address 192.185.14.3
	netmask 255.255.255.128
	gateway 192.185.14.1

auto eth1
iface eth1 inet static
	address 192.185.14.133
	netmask 255.255.255.252

auto eth2
iface eth2 inet static
	address 192.185.14.129
	netmask 255.255.255.252
```

- SchewerMountain1

```bash
auto eth0
iface eth0 inet dahcp
```

- LaubHills

```bash
# DHCP config for eth0
auto eth0
iface eth0 inet dhcp
```

- Himmel

```bash
auto eth0
iface eth0 inet static
	address 192.185.14.138
	netmask 255.255.255.252
	gateway 192.185.14.137

auto eth1
iface eth1 inet static
	address 192.185.14.1
	netmask 255.255.255.128

auto eth2
iface eth2 inet static
	address 192.185.12.1
	netmask 255.255.254.0
```

- Frieren

```bash
auto eth0
iface eth0 inet static
	address 192.185.14.146
	netmask 255.255.255.252
	gateway 192.185.14.145

auto eth1
iface eth1 inet static
	address 192.185.14.137
	netmask 255.255.255.252

auto eth2
iface eth2 inet static
	address 192.185.14.141
	netmask 255.255.255.252
```

- Stark

```
auto eth0
iface eth0 inet static
	address 192.185.14.142
	netmask 255.255.255.252
	gateway 192.185.14.141
```

- Aura

```bash
auto eth0
iface eth0 inet dhcp

auto eth1
iface eth1 inet static
	address 192.185.14.145
	netmask 255.255.255.252

auto eth2
iface eth2 inet static
	address 192.185.14.149
	netmask 255.255.255.252
```

- Heiter

```bash
auto eth0
iface eth0 inet static
	address 192.185.14.150
	netmask 255.255.255.252
	gateway 192.185.14.149

auto eth1
iface eth1 inet static
	address 192.185.8.1
	netmask 255.255.252.0

auto eth2
iface eth2 inet static
	address 192.185.0.1
	netmask 255.255.248.0
```

- TurkRegion

```bash
# DHCP config for eth0
auto eth0
iface eth0 inet dhcp
```

- Sein

```bash
auto eth0
iface eth0 inet static
	address 192.185.8.2
	netmask 255.255.255.0
	gateway 192.185.8.1
```

- GrabForest

```bash
# DHCP config for eth0
auto eth0
iface eth0 inet dhcp
```

## Routing
- Himmel

```
route add -net 192.185. netmask 255.255.255.252 gw 192.185.
route add -net 192.185. netmask 255.255.255.252 gw 192.185.
```

- Frieren

```
route add -net 192.185. netmask 255.255.255.252 gw 192.185
route add -net 192.185. netmask 255.255.255.252 gw 192.185.
route add -net 192.185. netmask 255.255.255.128 gw 192.185.
route add -net 192.185. netmask 255.255.255.0 gw 192.185.
```

- Aura

```
route add -net 192.185. netmask 255.255.255.252 gw 192.185.
route add -net 192.185. netmask 255.255.255.252 gw 192.185.
route add -net 192.185. netmask 255.255.255.128 gw 192.185.
route add -net 192.185. netmask 255.255.255.0 gw 192.185.
route add -net 192.185. netmask 255.255.255.252 gw 192.185.
route add -net 192.185. netmask 255.255.255.252 gw 192.185.

route add -net 192.185. netmask 255.255.248.0 gw 192.185.
route add -net 192.185. netmask 255.255.252.0 gw 192.185.
```

## Konfigurasi DHCP

### DHCP  Server

Pada DHCP Server, kita akan menginstall isc-dhcp-server dengan perintah

```bash
apt-get update
wait
apt-get install isc-dhcp-server -y
wait

echo '
INTERFACESv4="eth0"
INTERFACESv6=""
' > /etc/default/isc-dhcp-server

cp ~/dhcpd.conf /etc/dhcp/dhcpd.conf

service isc-dhcp-server restart
```

Kemudian pada file dhcpd.conf, kita akan mengkonfigurasi seperti berikut

```bash

option domain-name "example.org";
option domain-name-servers ns1.example.org, ns2.example.org;

default-lease-time 600;
max-lease-time 7200;

ddns-update-style none;

subnet 192.185. netmask 255.255.255.252 {
}

subnet 192.185. netmask 255.255.255.128 {
    range 192.185. 192.185.;
    option routers 192.185.;
    option broadcast-address 192.185.;
    option domain-name-servers 192.185.;
    default-lease-time 180;
    max-lease-time 5760;
}

subnet 192.185. netmask 255.255.255.0 {
    range 192.185. 192.185.;
    option routers 192.185.;
    option broadcast-address 192.185.;
    option domain-name-servers 192.185.;
    default-lease-time 180;
    max-lease-time 5760;
}

subnet 192.185. netmask 255.255.248.0 {
    range 192.185. 192.185.;
    option routers 192.185.;
    option broadcast-address 192.185.;
    option domain-name-servers 192.185.;
    default-lease-time 180;
    max-lease-time 5760;
}

subnet 192.185. netmask 255.255.252.0 {
    range 192.185. 192.185.;
    option routers 192.185.;
    option broadcast-address 192.185.;
    option domain-name-servers 192.185.;
    default-lease-time 180;
    max-lease-time 5760;
}
```

- `option domain-name-servers` adalah DNS Server yang akan digunakan
- `default-lease-time` adalah waktu lease default
- `max-lease-time` adalah waktu lease maksimal
- `subnet` adalah subnet yang akan digunakan
- `range` adalah range IP yang akan digunakan
- `option routers` adalah IP dari router yang akan digunakan
- `option broadcast-address` adalah IP broadcast yang akan digunakan

### DHCP Relay

Install isc-dhcp-relay pada route **Himmel dan Heiter** dengan perintah

```bash
# Configuration DHCP Relay
apt-get update
wait
apt-get install isc-dhcp-relay -y
wait

echo '
SERVERS="192.185.14.130"
INTERFACES="eth0 eth1 eth2"
OPTIONS="-m replace"
' >  /etc/default/isc-dhcp-relay

echo '
net.ipv4.ip_forward=1
' >  /etc/sysctl.conf
```

`apt-get update`: Baris ini mengupdate daftar paket yang tersedia dari repositori paket Linux. Ini merupakan langkah yang baik untuk dilakukan sebelum menginstal paket baru, untuk memastikan daftar paket terbaru.

`wait`: Ini adalah perintah untuk memberikan jeda atau menunggu sementara proses pembaruan selesai sebelum melanjutkan ke langkah selanjutnya.

`apt-get install isc-dhcp-relay -y`: Baris ini menginstal paket ISC DHCP Relay dengan memberikan opsi -y untuk menyetujui secara otomatis seluruh permintaan konfirmasi instalasi.

`echo '...' > /etc/default/isc-dhcp-relay`: Baris ini menulis teks konfigurasi ke dalam file /etc/default/isc-dhcp-relay. File ini digunakan untuk mengonfigurasi opsi-opsi default untuk layanan ISC DHCP Relay.

`echo '...' > /etc/sysctl.conf`: Baris ini menulis konfigurasi untuk menerapkan IP forwarding ke dalam file /etc/sysctl.conf. IP forwarding diperlukan agar paket dapat diteruskan antara antarmuka yang berbeda pada router.

`net.ipv4.ip_forward=1`: Konfigurasi IP forwarding yang dinyatakan di atas, yang akan diaktifkan setelah me-restart sistem atau menjalankan perintah sysctl -p untuk mengaktifkannya tanpa restart.

Dalam konfigurasi `isc-dhcp-relay`, server DHCP yang dituju adalah "192.185.14.130", dan antarmuka yang digunakan adalah "eth0", "eth1", dan "eth2". Opsi -m replace digunakan untuk mengganti daftar server DHCP yang mungkin sudah ada sebelumnya.

Setelah menjalankan skrip ini, disarankan untuk me-restart layanan ISC DHCP Relay dan menyelaraskan konfigurasi dengan menggunakan perintah service isc-dhcp-relay restart atau systemctl restart isc-dhcp-relay, tergantung pada versi sistem operasi yang Anda gunakan.

## Konfigurasi DNS
```
apt-get update
wait

apt-get install bind9 -y
wait
cp ~/named.conf.options /etc/bind/

service bind9 restart
```

- `named.conf.options` adalah konfigurasi DNS Server

Berikut adalah isi dari file `named.conf.options`

```bash
options {
        directory "/var/cache/bind";

        forwarders {
                192.168.122.1;
        };

        allow-query{any;};
        auth-nxdomain no;
        listen-on-v6 { any; };
};
```

- `forwarders` adalah DNS Server yang akan digunakan untuk forward
- `allow-query` adalah opsi untuk mengizinkan query dari semua IP
- `auth-nxdomain no` adalah opsi untuk mengizinkan domain yang tidak ada

## Konfigurasi Web Server

Untuk konfigurasi web server, kita akan menginstall nginx pada node **Sein dan Stark** dengan perintah

```bash
apt-get update
wait
apt-get install nginx -y
wait
cp ~/index.nginx-debian.html /var/www/html
service nginx start
apt-get install netcat -y
```

- `index.nginx-debian.html` adalah file html yang akan ditampilkan pada web server nanti
- `netcat` adalah aplikasi yang digunakan untuk mengirimkan data ke web server

## Pertanyaan

### No 1

Agar topologi yang kalian buat dapat mengakses keluar, kalian diminta untuk mengkonfigurasi Aura menggunakan iptables, tetapi tidak ingin menggunakan MASQUERADE.

### Proses

Pada node **Aura**, kita akan mengkonfigurasi iptables dengan perintah

```bash
ip=$(ip -o addr show up primary scope global eth0 |
      while read -r num dev fam addr rest; do echo ${addr%/*}; done)
echo $ip

iptables -t nat -A POSTROUTING -o eth0 -j SNAT --to $ip
```

- `-t nat` adalah opsi untuk menambahkan rule pada tabel nat
- `-A POSTROUTING` adalah opsi untuk menambahkan rule pada chain POSTROUTING
- `-s` adalah opsi untuk menentukan source IP
- `-o` adalah opsi untuk menentukan interface
- `-j SNAT` adalah opsi untuk melakukan SNAT
- `--to-source` adalah opsi untuk menentukan IP yang akan digunakan untuk SNAT

- ### Testing

Pada web server melakukan ping ke google.com dengan perintah

```bash
ping google.com
```
contoh ping pada Ritcher
![image](https://github.com/Arkandrvesh/Jarkom-Modul-5-B14-2023/assets/116497822/9ebe18dc-b2ac-4952-bcd4-b3058609b639)


### No 2

Kalian diminta untuk melakukan drop semua TCP dan UDP kecuali port 8080 pada TCP.

### Proses

Untuk melakukan drop semua TCP dan UDP kecuali port 8080 pada TCP, kita akan mengkonfigurasi iptables pada node **Heiter** dengan perintah

```bash
# Allow incoming TCP traffic on port 8080
iptables -A INPUT -p tcp --dport 8080 -j ACCEPT

# Drop all other incoming TCP traffic
iptables -A INPUT -p tcp -j DROP

# Drop all other incoming UDP traffic
iptables -A INPUT -p udp -j DROP
```

- `iptables -A INPUT -p tcp --dport 8080 -j ACCEPT` adalah opsi untuk menambahkan rule pada chain INPUT untuk menerima koneksi TCP pada port 8080

- `iptables -A INPUT -p tcp ! --dport 8080 -j DROP` adalah opsi untuk menambahkan rule pada chain INPUT untuk menolak koneksi TCP yang tidak menuju ke port 8080

### Testing

![image](https://github.com/Arkandrvesh/Jarkom-Modul-5-B14-2023/assets/116497822/4b19be70-e95e-499e-94f6-45a6d46c7895)
![image](https://github.com/Arkandrvesh/Jarkom-Modul-5-B14-2023/assets/116497822/fdb7973f-a925-45c0-a1e4-d5bd25bd81ad)


### No 3

Kepala Suku North Area meminta kalian untuk membatasi DHCP dan DNS Server hanya dapat dilakukan ping oleh maksimal 3 device secara bersamaan, selebihnya akan di drop.

### Solusi

Untuk membatasi DHCP dan DNS Server hanya dapat dilakukan ping oleh maksimal 3 device secara bersamaan, kita akan mengkonfigurasi iptables pada node **Revolte** dan **Richter** dengan perintah

```bash
iptables -F
iptables -A INPUT -p icmp --icmp-type echo-request -m connlimit --connlimit-above 3 --connlimit-mask 0 -j DROP
```

- `iptables -F` adalah opsi untuk menghapus semua rule yang ada
- `iptables -A INPUT -p icmp -m connlimit --connlimit-above 3 --connlimit-mask 0 -j DROP` adalah opsi untuk menambahkan rule pada chain INPUT untuk menolak koneksi ICMP yang lebih dari 3
- `--connlimit-above 3` adalah opsi untuk menentukan batas koneksi
- `--connlimit-mask 0` adalah opsi untuk menentukan mask

### Testing

Untuk melakukan testing, kita akan menggunakan node **Revolte** dan **Richter**. Untuk membuat perbandingan antara koneksi yang belum di batasi dan koneksi yang sudah di batasi, kita akan menggunakan netcat pada node **Revolte** dan **Richter**

pada percobaan ke4 akan berhenti
![image](https://github.com/Arkandrvesh/Jarkom-Modul-5-B14-2023/assets/116497822/5ec1a769-31fb-43e5-aacd-b86780cbd5b6)


### No 4

Lakukan pembatasan sehingga koneksi SSH pada Web Server hanya dapat dilakukan oleh masyarakat yang berada pada GrobeForest.

### Proses

Untuk melakukan pembatasan koneksi SSH pada Web Server hanya dapat dilakukan oleh masyarakat yang berada pada GrobeForest, kita akan mengkonfigurasi iptables pada node **Sein** dan **Stark** dengan perintah

```bash
iptables -F

# Allow SSH (TCP port 22) from hosts in subnet 
iptables -A INPUT -p tcp --dport 22 -s 192.185.8.0/22 -j ACCEPT

# Drop SSH (TCP port 22) from all other sources
iptables -A INPUT -p tcp --dport 22 -j DROP
```


### Testing

Untuk melakukan testing tersebut kita akan menggunakan netcat pada node **Sein** dan **Stark** dengan perintah

```
nc -1 -p 22
```

jalanin file no4.sh pada **GrobeForest**
```bash
apt-get update
apt-get install netcat -y

nc 192.185.8.2 22
```
![image](https://github.com/Arkandrvesh/Jarkom-Modul-5-B14-2023/assets/116497822/8f618b5b-65df-4b9a-8f06-40cc957f090e)
![image](https://github.com/Arkandrvesh/Jarkom-Modul-5-B14-2023/assets/116497822/8dc5e4e6-338c-4a5d-8bee-a69fd9bbda98)



### No 5

Selain itu, akses menuju WebServer hanya diperbolehkan saat jam kerja yaitu Senin-Jumat pada pukul 08.00-16.00.

### Proses

Untuk melakukan pembatasan akses menuju WebServer hanya diperbolehkan saat jam kerja yaitu Senin-Jumat pada pukul 08.00-16.00, kita akan mengkonfigurasi iptables pada node **Sein** dan **Stark** dengan perintah

```bash
iptables -F

iptables -A INPUT -m time --weekdays Mon,Tue,Wed,Thu,Fri --timestart 08:00 --timestop 16:00 -j ACCEPT

iptables -A INPUT -j DROP
```

### Testing

Cek Date
![image](https://github.com/Arkandrvesh/Jarkom-Modul-5-B14-2023/assets/116497822/e0bb50d1-5e38-4770-9124-cdbfae78c7e3)

Untuk melakukan testing tersebut kita akan menggunakan netcat pada node **Sein** dan **Stark** dengan perintah

```
nc -l -p 80
```
![image](https://github.com/Arkandrvesh/Jarkom-Modul-5-B14-2023/assets/116497822/fcebf419-c519-4895-b4cd-59a998a2cc58)


### No 6

Lalu, karena ternyata terdapat beberapa waktu di mana network administrator dari WebServer tidak bisa stand by, sehingga perlu ditambahkan rule bahwa akses pada hari Senin - Kamis pada jam 12.00 - 13.00 dilarang (istirahat maksi cuy) dan akses di hari Jumat pada jam 11.00 - 13.00 juga dilarang (maklum, Jumatan rek).

### Preoses

Untuk melakukan pembatasan akses pada hari Senin - Kamis pada jam 12.00 - 13.00 dilarang dan akses di hari Jumat pada jam 11.00 - 13.00 juga dilarang, kita akan mengkonfigurasi iptables pada node **Sein** dan **Stark** dengan perintah

### Run file di **Sein** dan **Stark** file no6.sh
```
iptables -F

iptables -A INPUT -m time --weekdays Mon,Tue,Wed,Thu,Fri --timestart 08:00 --timestop 16:00 -j ACCEPT

iptables -A INPUT -j DROP

iptables -A INPUT -m time --weekdays Mon,Tue,Wed,Thu --timestart 12:00 --timestop 13:00 -j DROP

iptables -A INPUT -m time --weekdays Fri --timestart 11:00 --timestop 13:00 -j DROP

```
-`iptables -F`: Perintah ini menghapus (flush) semua aturan yang ada di tabel filter. Ini efektif menghapus semua aturan dari rantai INPUT, OUTPUT, dan FORWARD.

-`iptables -A INPUT -m time --weekdays Mon,Tue,Wed,Thu,Fri --timestart 08:00 --timestop 16:00 -j ACCEPT`: Aturan ini mengizinkan lalu lintas masuk (rantai INPUT) pada hari kerja yang ditentukan (Senin hingga Jumat) antara pukul 08:00 dan 16:00. Opsi -m time digunakan untuk mencocokkan berdasarkan waktu, dan opsi -j ACCEPT digunakan untuk menerima lalu lintas yang sesuai.

-`iptables -A INPUT -j DROP`: Aturan ini menambahkan (-A) aturan DROP umum ke rantai INPUT. Ini berarti bahwa semua lalu lintas yang tidak secara eksplisit diizinkan oleh aturan sebelumnya akan dijatuhkan (ditolak).

-`iptables -A INPUT -m time --weekdays Mon,Tue,Wed,Thu --timestart 12:00 --timestop 13:00 -j DROP`: Aturan ini menolak lalu lintas masuk pada hari kerja (Senin hingga Kamis) antara pukul 12:00 dan 13:00.

-`iptables -A INPUT -m time --weekdays Fri --timestart 11:00 --timestop 13:00 -j DROP`: Aturan ini menolak lalu lintas masuk pada hari Jumat antara pukul 11:00 dan 13:00.

Secara ringkas:

Aturan pertama mengizinkan lalu lintas masuk pada hari kerja dari pukul 08:00 hingga 16:00.
Aturan kedua menolak semua lalu lintas masuk.
Aturan ketiga menolak lalu lintas masuk pada hari kerja dari pukul 12:00 hingga 13:00.
Aturan keempat menolak lalu lintas masuk pada hari Jumat dari pukul 11:00 hingga 13:00.
Aturan-aturan ini dapat berguna untuk mengendalikan akses ke server berdasarkan pembatasan waktu. Perlu diingat bahwa aturan-aturan ini hanya memengaruhi lalu lintas masuk, dan Anda mungkin perlu aturan tambahan untuk rantai OUTPUT dan FORWARD tergantung pada kebutuhan spesifik Anda.

### Testing

Untuk melakukan testing tersebut kita akan menggunakan netcat pada node **Sein** dan **Stark** dengan perintah

`nc -l -p 80`

![image](https://github.com/Arkandrvesh/Jarkom-Modul-5-B14-2023/assets/116497822/c853710a-efa0-43f7-9aaa-21857db69ec1)



### Pemasalah 7

Karena terdapat 2 WebServer, kalian diminta agar setiap client yang mengakses Sein dengan Port 80 akan didistribusikan secara bergantian pada Sein dan Stark secara berurutan dan request dari client yang mengakses Stark dengan port 443 akan didistribusikan secara bergantian pada Sein dan Stark secara berurutan.

### Solusi

Untuk melakukan pembagian beban pada web server, kita akan mengkonfigurasi iptables pada node **Sein** dan **Stark** dengan perintah

```bash
# Flush existing rules
iptables -t nat -F
iptables -t nat -A PREROUTING -i eth0 -p tcp --dport 80 -m statistic --mode nth --every 2 --packet 0 -j DNAT --to-destination 192.185.8.2:80
iptables -t nat -A PREROUTING -i eth0 -p tcp --dport 80 -m statistic --mode nth --every 2 --packet 1 -j DNAT --to-destination 192.185.14.142:80

# For HTTPS traffic
iptables -t nat -A PREROUTING -i eth0 -p tcp --dport 443 -m statistic --mode nth --every 2 --packet 0 -j DNAT --to-destination 192.185.8.2:443
iptables -t nat -A PREROUTING -i eth0 -p tcp --dport 443 -m statistic --mode nth --every 2 --packet 1 -j DNAT --to-destination 192.185.14.142:443
```

### Testing

Untuk mencoba soal no 7 kita hanya tinggal melakukan pemangilan berulang kali dengan menggunakan curl

### Permasalahan 8

Karena berbeda koalisi politik, maka subnet dengan masyarakat yang berada pada Revolte dilarang keras mengakses WebServer hingga masa pencoblosan pemilu kepala suku 2024 berakhir. Masa pemilu (hingga pemungutan dan penghitungan suara selesai) kepala suku bersamaan dengan masa pemilu Presiden dan Wakil Presiden Indonesia 2024.

### Solusi

Untuk mengerjakan nomor ini diperlukan bantuan --datestart dan --datestop untuk melakukan pembatasan akses pada hari-hari tertentu. Disini diperlukan subnet dari Revolte karena pembatasn yang diinginkan adalah terhadap subnet. Disini subnet kami adalah terdapat pada A1 dimana memiliki ip 10.15.0.0/30 dan menentukan protokol yang digunakan sebagai berikut

```bash
iptables -A INPUT -s DHCP_Subnet -m time --datestart 2023-01-01T00:00 --datestop 2024-06-26T23:59 -j DROP
```
-`iptables -A INPUT`: Ini menambahkan aturan ke rantai INPUT. -A berarti "append" atau menambahkan aturan ke akhir rantai.

-`-s DHCP_Subnet`: Opsi ini menentukan sumber (source) dari lalu lintas yang akan dipengaruhi oleh aturan ini. "DHCP_Subnet" mengacu pada subnet DHCP tertentu. Ini berarti aturan ini akan mempengaruhi lalu lintas yang berasal dari alamat IP dalam subnet DHCP tersebut.

-`-m time --datestart 2023-01-01T00:00 --datestop 2024-06-26T23:59`: Ini menggunakan modul waktu untuk menentukan rentang waktu pada saat aturan ini berlaku. Aturan ini akan berlaku mulai dari tanggal 1 Januari 2023 pukul 00:00 hingga tanggal 26 Juni 2024 pukul 23:59. Selama periode ini, aturan ini akan mempengaruhi lalu lintas yang memenuhi syarat.

-`-j DROP`: Ini menentukan tindakan yang akan diambil jika lalu lintas memenuhi syarat. Dalam hal ini, tindakan yang diambil adalah menolak (DROP) lalu lintas tersebut.

### Testing

Untuk melakukan testing tersebut kita akan menggunakan netcat pada node **Sein** dan **Stark** dengan perintah
`nc -l -p 80`


### Pemasalah 9

Sadar akan adanya potensial saling serang antar kubu politik, maka WebServer harus dapat secara otomatis memblokir alamat IP yang melakukan scanning port dalam jumlah banyak (maksimal 20 scan port) di dalam selang waktu 10 menit.

### Solusi

Untuk mengerjakan nomor ini diperlukan bantuan --hitcount dan --seconds untuk melakukan pembatasan akses pada hari-hari tertentu. Selanjutnya kita bisa mengatur settingan dari iptables sebagai berikut pada file baru no9.sh:

```bash
iptables -F
iptables -N scan_port

iptables -A INPUT -m recent --name scan_port --update --seconds 600 --hitcount 20 -j DROP
iptables -A FORWARD -m recent --name scan_port --update --seconds 600 --hitcount 20 -j DROP

iptables -A INPUT -m recent --name scan_port --set -j ACCEPT
iptables -A FORWARD -m recent --name scan_port --set -j ACCEPT

```

### Testing

Kita bisa melakukan testing untuk menentukan apakah port tersebut terbuka atau tidak pada node **SchewerMountain**


### Pemasalah 10

Karena kepala suku ingin tau paket apa saja yang di-drop, maka di setiap node server dan router ditambahkan logging paket yang di-drop dengan standard syslog level.

### Solusi

Untuk melakukan logging paket yang di-drop, kita akan mengkonfigurasi iptables pada node **Sein** dan **Stark** dengan perintah

Pada kali ini kita akan meneruskan permaslahan ke 9 dan menambahakan script berikut ini :

```bash
iptables -A INPUT  -j LOG --log-level debug --log-prefix 'Packet Drop 1/second --limit-burst 10
```

-`LOG --log-prefix "Portscan detected: " --log-level 4` dengan tujuan untuk mengarahkan paket yang memenuhi aturan untuk dilakukan logging.

-`iptables -A INPUT`: Ini menambahkan aturan ke rantai INPUT. -A berarti "append" atau menambahkan aturan ke akhir rantai INPUT.

-`-j LOG`: Ini menunjukkan bahwa jika paket memenuhi aturan ini, maka paket tersebut akan dicatat (log) ke sistem log. Tidak ada tindakan (ACCEPT atau DROP) yang diambil, tetapi informasi tentang paket tersebut akan dicatat.

-`--log-level debug`: Opsi ini menentukan tingkat log yang akan digunakan. Dalam hal ini, tingkat log ditetapkan sebagai "debug". Ini menentukan seberapa rinci informasi yang akan dicatat. Tingkat log yang umum adalah "info", "warn", "err", dan "debug".

-`--log-prefix 'Packet Drop 1/second --limit-burst 10'`: Opsi ini menetapkan awalan (prefix) yang akan ditambahkan ke pesan log untuk membantu mengidentifikasi log tersebut. Dalam hal ini, pesan log akan dimulai dengan teks "Packet Drop 1/second" dan juga mencakup opsi --limit-burst 10, yang menetapkan batas lonjakan untuk pesan log. Dengan batas ini, sistem akan mencatat pesan log setidaknya sekali per detik, tetapi dapat mencapai lonjakan hingga 10 pesan log sekaligus jika diperlukan.

Karena pada log sebelumnya kita menentukan level log 4 (warning), selanjutnya kita perlu melakukan konfigurasi pada etc/rsyslog.d/50-default.conf untuk menambahkan configurasi kernel.warning -/var/log/iptables.log sehingga seperti configurasi dibawah ini

```
#
# First some standard log files.  Log by facility.
#
auth,authpriv.*                 /var/log/auth.log
*.*;auth,authpriv.none          -/var/log/syslog
#cron.*                         /var/log/cron.log
#daemon.*                       -/var/log/daemon.log
kern.*                          -/var/log/kern.log
kernel.warning                  -/var/log/iptables.log
#lpr.*                          -/var/log/lpr.log
mail.*                          -/var/log/mail.log
#user.*                         -/var/log/user.log

#
# Logging for the mail system.  Split it up so that
# it is easy to write scripts to parse these files.
#
#mail.info                      -/var/log/mail.info
#mail.warn                      -/var/log/mail.warn
mail.err                        /var/log/mail.err
```

jika sudah kita perlu melakukan menjalankan command touch /var/log/iptables.log dan menjalankan /etc/init.d/rsyslog restart untuk melakukan restart syslog supaya konfigurasi baru dapat diterapkan kedalam syslog dan hasil log bisa masuk kedalam iptables.log
