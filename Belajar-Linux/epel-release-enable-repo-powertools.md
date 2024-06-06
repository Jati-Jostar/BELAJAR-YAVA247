# Install epel-release dan enable Repository powertools

### 5 Juni 2024

---

## Details

1. **Install dnf-plugins-core kalau belum terinstall**
   ``` 
   dnf install dnf-plugins-core
   ```
   
2. **Install epel-release**
    ```
    dnf install epel-release
    ```
    
3. **Aktifkan repo powertools**
    ```
    dnf config-manager --set-enabled powertools
    ```
4. **Verifikasi apakah repo sudah berhasil*
    ```
    dnf repolist
    ```
    ![repolist](https://github.com/Jati-Jostar/BELAJAR-YAVA247/blob/1e4425ca823f344e7005f98f5723babf0d7a70ed/asset/repolist.png)

    
