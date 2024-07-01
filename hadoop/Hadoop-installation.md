[O# HADOOP INSTALLATION

---

## Details

1. **Install JDK 1.8.0**

   ``` 
   su
   dnf -y install java-1.8.0-openjdk- wget
   ```
   Pastikan sudah di install dengan benar dengan
   ```
   java -version
   ```
2. **Buat User Baru Untuk Instalasi Hadoopnya**
    ```
    $ useradd hadoopjati
    $ passwd hadoopjati
    ```
3. **Download file RPM Hadoopnya**
    Disini saya menggunakan versi 3.3.6
    ```
    $ wget https://dlcdn.apache.org/hadoop/common/hadoop-3.3.6/hadoop-3.3.6.tar.gz
    ```
    kemudian extrak dan ganti nama dengan hadoop saja
    ```
    $ tar -zxf hadoop-3.3.6.tar.gz
    $ mv hadoop-3.3.6 hadoop
    ```
4. **Konfigurasi Hadoop Enviroment**,
    Masuk ke ~/.bashrc untuk menambah konfigurasi
    ```
    vi ~/.bashrc
    ```
    Tambahkan Baris Berikut
    ```
    export JAVA_HOME=/usr/lib/jvm/jre-1.8.0-openjdk-1.8.0.412.b08-2.el8.x86_64
    export HADOOP_HOME=/home/hadoopjati/hadoop
    export HADOOP_INSTALL=$HADOOP_HOME
    export HADOOP_MAPRED_HOME=$HADOOP_HOME
    export HADOOP_COMMON_HOME=$HADOOP_HOME
    export HADOOP_HDFS_HOME=$HADOOP_HOME
    export HADOOP_YARN_HOME=$HADOOP_HOME
    export HADOOP_COMMON_LIB_NATIVE_DIR=$HADOOP_HOME/lib/native
    export PATH=$PATH:$HADOOP_HOME/sbin:$HADOOP_HOME/bin
    ```
    kemudian save dan terapkan perubahan
    ```
    source ~/.bashrc
    ```
4. **Konfigurasi HDFS((hadoop-env.sh, core-site.xml, hdfs-site.xml, mapred-site.xml, yarn-site.xml)**
   ***Buat 2 file datanode dan namenode di bawah home user***
    ```
    $ mkdir -p ~/hadoopdata/hdfs/{namenode,datanode}
    ```
    ***konfigurasi hadoop-env.sh***
    ```
    $ vi $HADOOP_HOME/etc/hadoop/hadoop-env.sh
    ```
    ***hilangkan # dan ganti bagian***
    ```
    # export JAVA_HOME=
    (Jadi seperti di bawah)
    export JAVA_HOME=/usr/lib/jvm/jre-1.8.0-openjdk-1.8.0.412.b08-2.el8.x86_64
    ```
    sesuaikan versi dan lokasi dari Openjdk yang kalian download
    
    ***Pindah ke $HADOOP_HOME/etc/hadoop dan edit file file berikut***,
      core-site.xml
    ```
    <configuration>
        <property>
                <name>fs.defaultFS</name>
                <value>hdfs://jati.local:9000</value>
        </property>
    </configuration>
    ```
    hdfs-site.xml
    ```
    <configuration>
        <property>
                <name>dfs.replication</name>
                <value>1</value>
        </property>
        <property>
                <name>dfs.name.dir</name>
                <value>file:///home/hadoopjati/hadoopdata/hdfs/namenode</value>
        </property>
        <property>
                <name>dfs.data.dir</name>
                <value>file:///home/hadoopjati/hadoopdata/hdfs/datanode</value>
        </property>
    </configuration>
    ```
    mapred-site.xml
    ```
    <configuration>
    <property>
        <name>yarn.app.mapreduce.am.env</name>
        <value>HADOOP_MAPRED_HOME=${full path of your hadoop distribution directory}</value>
    </property>
    <property>
        <name>mapreduce.map.env</name>
        <value>HADOOP_MAPRED_HOME=${full path of your hadoop distribution directory}</value>
    </property>
    <property>
        <name>mapreduce.reduce.env</name>
        <value>HADOOP_MAPRED_HOME=${full path of your hadoop distribution directory}</value>
    </property>
    <property>
        <name>mapreduce.framework.name</name>
        <value>yarn</value>
    </property>
    </configuration>
    ```
    yarn-site.xml
    ```
    <configuration>

    <property>
        <name>yarn.resourcemanager.hostname</name>
        <value>jati-server.com</value>
    </property>
    <property>
        <name>yarn.nodemanager.aux-services</name>
        <value>mapreduce_shuffle</value>
    </property>
    <property>
        <name>yarn.nodemanager.aux-services.mapreduce.shuffle.class</name>
        <value>org.apache.hadoop.mapred.ShuffleHandler</value>
    </property>

    </configuration>
    ```
4. **Memformat namenode**
    ```
    $ hdfs namenode -format
    ```
5. **Setting firewall**
    ```
    firewall-cmd --permanent --add-port=9870/tcp
    firewall-cmd --permanent --add-port=8088/tcp
    firewall-cmd --reload
    ```
6. **Start Dfs**
    ```
    $ start-dfs.sh
    ```
7. **Start Yarn**
    ```
    $ start-yarn.sh
    ```
8. **Periksa tampilan UI di web**
ipVM:9870 untuk HDFSnya
     ![](https://github.com/Jati-Jostar/BELAJAR-YAVA247/raw/main/asset/HadoopUI.png)
    dan
ipVM:8088 untuk YARNnya
    ![](https://github.com/Jati-Jostar/BELAJAR-YAVA247/raw/main/asset/YarnUI.png)
