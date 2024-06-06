# Install Packet Apache http

### 5 Juni 2024

---

## Details

1. **Install http(apache)**
   ``` 
   dnf install httpd
   ```
   
2. **Mulai dan Enable httpd**
    ```
    systemctl start httpd
    systemctl enable httpd
    ```
    dan check apakah sudah berjalan dengan
    ```
    systemctl status httpd
    ```
    
3. **Setting Firewall untuk HTTP dan HTTPS**
    ```
    sudo firewall-cmd --permanent --add-service=http
    sudo firewall-cmd --permanent --add-service=https
    sudo firewall-cmd --reload
    ```
    


    
