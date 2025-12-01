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

## Soal 3
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
