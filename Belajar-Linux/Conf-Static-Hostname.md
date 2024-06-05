
# Konfigurasi Static Hostname FQDN (Full Qualified Domain Name)

## 4 Juni 2024

---

## Details

1. **Gunakan Perintah Berikut untuk Membuka file Hostname**

   ``` 
   nano /etc/hostname
   ```
2. **Ganti Hostname Sesuai dengan yang diinginkan(jati-server.com)**
Untuk contohnya
    ```
    jati-server.com
    ```
    Kemudian Save Ctrl+O dan Ctrl+X
3. **Ganti Hostnamectl dengan hostname yang barusan di ganti**
    ```
    hostnamectl set-hostname jati-server.com
    ```
4. **Check apakah hostname sudah berhasil terganti**
    ```
    hostname -f
    ```
    jika sudah berhasil akan muncul hostname yang diingin kan
    ![Hostname Configuration](https://github.com/Jati-Jostar/BELAJAR-YAVA247/raw/main/asset/hostname.png)
