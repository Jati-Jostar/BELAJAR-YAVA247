# Install Openjdk 

### 5 Juni 2024

---

## Details

1. **Install Openjdk**
   ``` 
   dnf install java-devel
   ```
   
2. **Cek Apakah instalasi sudah berhasil dengan**
    ```
    java -verison
    ```
    
3. **Konfigurasi JAVA_HOME**
    ```
    nano /etc/profile.d/java.sh
    ```
4. **Tambahkan Baris Berikut**
    ```
    export JAVA_HOME=/usr/lib/jvm/java-11-openjdk
    export PATH=$JAVA_HOME/bin:$PATH
    ```
5. **Aktifkan Perubahaan**
    ```
    source /etc/profile.d/java.sh
    ```
6. **verifikasi apa sudah berhasil**
    ```
    echo $JAVA_HOME
    java -version
    ```
    ![javaversion](https://github.com/Jati-Jostar/BELAJAR-YAVA247/blob/e3d15156f0987bcbf169a03aa8219bc2030ce695/asset/javaopenjdk.png)

    
