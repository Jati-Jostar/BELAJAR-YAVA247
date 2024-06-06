# Install dan Enable Packet NTP 

### 5 Juni 2024

---

## Details

1. **Install Chrony**
   ``` 
   dnf install chrony
   ```
   
2. **Konfigurasi Chrony**
    ```
    nano /etc/chrony.conf
    ```
    
3. **Edit chrony.conf**

    Bagian pool ganti dengan ntp server yang diingin kan
    ```
    pool time.google.com iburst
    ```
    
4. **Restart chrony**
    ```
    systemctl restart chronyd
    ```
5. **Enable,Mulai dan check status chrony**
    ```
    systemctl enable chronyd
    systemctl start chronyd
    systemctl status chronyd
    ```
6. **verifikasi apa sudah berhasil**
    ```
    chronyc tracking
    ```
    ![chronyd](https://github.com/Jati-Jostar/BELAJAR-YAVA247/blob/923590ca9dfc829f127a0d9b20a9fa6828873d52/asset/chronyc.png)

    
