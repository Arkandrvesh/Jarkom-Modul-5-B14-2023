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
