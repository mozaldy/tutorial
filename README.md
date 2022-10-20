# Tutorial Debian 11
Ini adalah tutorial untuk Debian 11, distro Linux yang sering digunakan sebagai sistem operasi oleh berbagai server. Diharapkan bahwa tutorial ini dapat membantu anda untuk menguasai sistem operasi ini dengan baik agar manfaat-manfaat dari Debian bisa anda gunakan sebaik mungkin.
## Daftar Isi
- [Daftar Isi](#daftar-isi)
- [Prasyarat (Prerequisite)](#prasyarat)
- [1. Konfigurasi Interfaces Jaringan](#konfigurasi-interfaces-jaringan)
- [2. Konfigurasi Sources APT](#konfigurasi-sources-apt)
- [3. Instalasi Links](#instalasi-links)
- [4. Instalasi Calender/Cal](#instalasi-cal)
## Prasyarat
- Debian 11
- Koneksi Internet
  - Apabila menggunakan VirtualBox, pastikan bahwa Network Adapter Debian menggunakan NAT di Settings -> Network
- Perlu diketahui:
  - `nano` adalah editor text/file dari debian, cara pakai:
    - Save text/file yang dirubah dengan: `F2` -> `Y` -> `Enter.`
  - `#` Memiliki artian bahwa terminal sedang dijalankan oleh SuperUser/SU.
  - `$` Memiliki artian bahwa terminal sedang dijalankan oleh User/Non-SuperUser.
  - Didalam file konfigurasi Linux, simbol `#` digunakan untuk mendeklarasikan comment, artinya baris text setelah simbol `#` tidak akan dibaca oleh sistem.
## Konfigurasi Interfaces Jaringan
- Di terminal Debian
  - ```
    $ su 
    # nano /etc/network/interfaces
    ```
    - Tambahkan:
      ```
      auto enp0s3
      iface enp0s3 inet dhcp
      ```
    - Apabila ada baris selain itu yang memiliki `enp0s3`, tambah simbol '`#`' di depannya, contoh:
      ```
      #allow-hotplug enp0s3
      #iface enp0s3 inet dhcp
      ```
    ```
    # /etc/init.d/networking restart
    ```
## Konfigurasi Sources APT
- Di terminal Debian
  - ```
    # nano /etc/apt/sources.list
    ```
    - Tambahkan:
      ```
      deb http://mirror.poliwangi.ac.id/debian/ bullseye main contrib non-free
      ```
    - Apabila ada baris selain itu yang memiliki `deb`/`deb-src`, tambah simbol '`#`' di depannya, contoh:
      ```
      #deb http://deb.debian.org/debian/ bullseye main
      #deb-src http://deb.debian.org/debian/ bullseye main
      ```
    ```
    # apt update -y
    ```
## Instalasi Links
- Di terminal debian
  - ```
    # apt install links -y
    # links google.com
    ```
## Instalasi Cal
- Di terminal debian
  - ```
    # apt install bsdmainutils -y
    # cal
## Instalasi Mail
- Di terminal debian
  - ```
    # apt install mailnutils -y
    # mail test@gmail.com
      
