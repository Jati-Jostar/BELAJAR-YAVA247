# Konfigurasi Static IP Address

### 5 Juni 2024

---

## Details

1. **Pastikan Anda Mendapatkan IP Bridgenya**

    untuk mengeceknya anda bisa menggunakan

   ``` 
   ip addr show
   ```
   
2. **Buka file ifcfg-enp0s3 untuk konfigurasi ip menjadi static**

    ```
    nano /etc/sysconfig/network-scripts/ifcfg-enp0s3
    ```
    Ubah bagian berikut
    
    ```sh
    BOOTPROTO=static
    IPADDR=192.168.1.100
    NETMASK=255.255.255.0
    ```
    Save dan Exit
3. **Ganti Hostnamectl dengan hostname yang barusan di ganti**
    ```
    hostnamectl set-hostname jati-server.com
    ```
4. **Restart NetworkManager**
    ```
    systemctl restart NetworkManager
    ```
5. **Cek apakah IP Static telah berhasil dibuat**
    ```
    ip addr show
    ```
    ![IP static](https://github.com/Jati-Jostar/BELAJAR-YAVA247/blob/bc3ecf8a751a1195e382faffb346271d21388628/asset/ipstatic.png)
