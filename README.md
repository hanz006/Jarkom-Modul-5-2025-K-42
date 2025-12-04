# Jarkom-Modul-5-2025-K-42
| Nama | NRP |
| :-------- | :------- | 
| S. Farhan Baig | 5027241097| 
| Dimas Satya Andhika | 5027241032 |

# MISI 1
## Soal 1
● Narya: Berfungsi sebagai DNS Server. <br>
● Vilya: Berfungsi sebagai DHCP Server. <br> 
● Web Servers: Palantir dan IronHills. <br> 
● Client (Pasukan): <br> 
    ● Khamul: 5 host (Target/Burnice). <br> 
    ● Cirdan: 20 host (Lycaon). <br> 
    ● Isildur: 30 host (Policeboo). <br> 
    ● Durin: 50 host (Caesar). <br> 
    ● Gilgalad: 100 host (Ellen). <br> 
    ● Elendil: 200 host (Jane).
    
## Soal 2
<img width="2078" height="1356" alt="Frame 5" src="https://github.com/user-attachments/assets/0941f2e5-f972-41d6-b25e-b556d01568a3" />
<img width="1176" height="534" alt="image" src="https://github.com/user-attachments/assets/e7ef8c22-cf4e-43b0-8f48-d6dccbce6f56" />
<img width="821" height="641" alt="Modul 5_Jarkom_K42drawio drawio" src="https://github.com/user-attachments/assets/a9b9f2b8-c063-482f-bc4d-8bcf4b3342c4" />

### Osgilath
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet dhcp

auto eth1
iface eth1 inet static
    address 192.232.1.213
    netmask 255.255.255.252

auto eth2
iface eth2 inet static
    address 192.232.1.217
    netmask 255.255.255.252

auto eth3
iface eth3 inet static
    address 192.232.1.225
    netmask 255.255.255.252
```
### Moria
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
    address 192.232.1.218
    netmask 255.255.255.252
    gateway 192.232.1.217

auto eth1
iface eth1 inet static
    address 192.232.1.209
    netmask 255.255.255.252

auto eth2
iface eth2 inet static
    address 192.232.1.221
    netmask 255.255.255.252

auto eth3
iface eth3 inet manual
```
### Wilderland
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
    address 192.232.1.222
    netmask 255.255.255.252
    gateway 192.232.1.221

auto eth1
iface eth1 inet static
    address 192.232.1.129
    netmask 255.255.255.192

auto eth2
iface eth2 inet static
    address 192.232.1.193
    netmask 255.255.255.248
```
### Rivendell
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
    address 192.232.1.214
    netmask 255.255.255.252
    gateway 192.232.1.213

auto eth1
iface eth1 inet static
    address 192.232.1.201
    netmask 255.255.255.248
```
### Minastir
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
    address 192.232.1.226
    netmask 255.255.255.252
    gateway 192.232.1.225

auto eth1
iface eth1 inet static
    address 192.232.0.1
    netmask 255.255.255.0

auto eth2
iface eth2 inet static
    address 192.232.1.229
    netmask 255.255.255.252
```
### Pelargir
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
    address 192.232.1.230
    netmask 255.255.255.252
    gateway 192.232.1.229

auto eth1
iface eth1 inet static
    address 192.232.1.237
    netmask 255.255.255.252

auto eth2
iface eth2 inet static
    address 192.232.1.233
    netmask 255.255.255.252

```
### AnduinBanks
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
    address 192.232.1.238
    netmask 255.255.255.252
    gateway 192.232.1.237

auto eth1
iface eth1 inet static
    address 192.232.1.1
    netmask 255.255.255.128
```
### Elendil, Isildur, Gilgalad, Cirdan
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet dhcp
```

## soal 3
Buatlah file konfirgurasi rute pada node node berikut
### Osgilath
```
#!/bin/bash
ip route add 192.232.1.208/30 via 192.232.1.218
ip route add 192.232.1.220/30 via 192.232.1.218
ip route add 192.232.1.128/26 via 192.232.1.218
ip route add 192.232.1.192/29 via 192.232.1.218

ip route add 192.232.1.200/29 via 192.232.1.214

ip route add 192.232.0.0/24 via 192.232.1.226
ip route add 192.232.1.0/25 via 192.232.1.226
ip route add 192.232.1.228/30 via 192.232.1.226
ip route add 192.232.1.232/30 via 192.232.1.226
ip route add 192.232.1.236/30 via 192.232.1.226
```
### Minastir
```
#!/bin/bash
ip route add 192.232.1.232/30 via 192.232.1.230
ip route add 192.232.1.236/30 via 192.232.1.230
ip route add 192.232.1.0/25   via 192.232.1.230
```
### Pelargir
```
#!/bin/bash
ip route add 192.232.1.0/25 via 192.232.1.238
```

## Soal 4 (Setelah 2.1)
### Vilya
`Vilya` akan berpaeran sebagai DHCP Server. Pastikan `Vilya` dapat mengakses internet dengan `ping 8.8.8.8` setelah itu tambahkan DNS Resolver
```
nano /etc/resolv.conf
```
isi dengan
```
nameserver 8.8.8.8
nameserver 1.1.1.1
```
Sehabis itu barulah update dan install DHCP Server
```
apt-get update
apt-get install isc-dhcp-server -y
```
Set intefaces dari DHCP Server dengan
```
nano /etc/default/isc-dhcp-server
```
dan isi seperti berikut
```
INTERFACESv4="eth0"
INTERFACESv6=""
```
lalu edit file DHCP Server dengan
```
nano /etc/dhcp/dhcpd.conf
```
isi dengan
```
authoritative;

# SUBNET TEMPAT VILYA BERADA (WAJIB ADA & KOSONG)
subnet 192.232.1.200 netmask 255.255.255.248 {
}

# ===== A9 SUBNET =====
subnet 192.232.0.0 netmask 255.255.255.0 {
    range 192.232.0.10 192.232.0.200;
    option routers 192.232.0.1;
    option broadcast-address 192.232.0.255;
    option domain-name-servers 192.232.1.203;
}

# ===== A13 SUBNET =====
subnet 192.232.1.0 netmask 255.255.255.128 {
    range 192.232.1.10 192.232.1.120;
    option routers 192.232.1.1;
    option broadcast-address 192.232.1.127;
    option domain-name-servers 192.232.1.203;
}
```
Setelah melakukan semua config di atas, restart DHCP Server dan cek statusnya dengan
```
service isc-dhcp-server restart
service isc-dhcp-server status
```
Pastikan outputnya `active (running)`

### Minastir, ArduinBanks, Wilderland

# Misi 2
## Soal 1
Gunakan config di bawah pada node `Osgilath` untuk menghubungkan ke `NAT`
```
echo 1 > /proc/sys/net/ipv4/ip_forward
iptables -t nat -A POSTROUTING -s 192.232.0.0/23 -o eth0 -j SNAT --to-source 192.168.122.72

```
