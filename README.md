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

## NUMBER 1

### Pemasalah 1

Agar topologi yang kalian buat dapat mengakses keluar, kalian diminta untuk mengkonfigurasi Aura menggunakan iptables, tetapi tidak ingin menggunakan MASQUERADE.

### Solusi
