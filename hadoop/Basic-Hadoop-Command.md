# Basic Command Hadoop

---

## Details

1. #### Mengelola Directori
    Membuat Direktori
   ``` 
   hdfs dfs -mkdir path/to/direktory
   ```
    Melihat isi Direktori
   ```
   hdfs dfs -ls path/to/direktory
   ```
    Menghapus isi Direktori
   ```
   hdfs dfs -rmdir path/to/direktory
   ```
   Memindahkan atau mengganti Nama
   ```
   hdfs dfs -mv path/to/direktory path/to/otherdirectory
   ```
   Menyalin Direktori
   ```
   hdfs dfs -cp path/to/direktory path/to/otherdirectory
   ```

2. #### Mengelola File
    Mengunggah file local ke HDFS
   ```
   hdfs dfs -put path/to/filedirectory
   ```
    Mengambil file HDFS ke local
   ```
   hdfs dfs -get path/to/filedirectory
   ```
    Melihat isi file
   ```
   hdfs dfs -cat path/to/filedirectory
   ```
    Menghapus file
   ```
   hdfs dfs -rm path/to/filedirectory
   ```
    Memindahkan atau Mengganti Nama Fike
   ```
   hdfs dfs -mv path/to/filedirectory
   ```
    Menampilkan Sebagian Awal File
   ```
   hdfs dfs -head path/to/filedirectory
   ```
    Menampilkan Sebagian Akhir File
   ```
   hdfs dfs -tail path/to/filedirectory
   ```
3. #### Perintah dasar Hadoop Mapreduce
    Menjalankan Job MapReduce
    ```
    hadoop jar $HADOOP_HOME/share/hadoop/mapreduce/hadoop-mapreduce-examples-*.jar wordcount /input/path /output/path
    ```
    Memeriksa Job yang sedang Berjalan
    ```
    hadoop job -list
    ```
    Memeriksa Detail Job
    ```
    hadoop job -status job_id
    ```
    Menghentikan job
    ```
    hadoop job -kill job_id
    ```
    
4. #### Perintah Dasar YARN (Yet Another Resource Negotiator)
    Menjalankan Aplikasi YARN
    ```
    yarn jar /path/to/your-application.jar [command] /input/path /output/path
    ```
    Memeriksa Status Aplikasi YARN
    ```
    yarn application -status application_id
    ```
    Memeriksa Daftar Aplikasi YARN
    ```
    yarn application -list
    ```
    Menghentikan Aplikasi YARN
    ```
    yarn application -kill application_id
    ```

5. #### Perintah Tambahan
    Memulai NameNode
    ```
    hadoop-daemon.sh start namenode
    ```
    Menghentikan NameNode
    ```
    hadoop-daemon.sh stop namenode

    ```
    Memulai DataNode
    ```
    hadoop-daemon.sh start datanode
    ```
    Menghentikan DataNode
    ```
    hadoop-daemon.sh stop datanode
    ```
    Memulai ResourceManager
    ```
    yarn-daemon.sh start resourcemanager
    ```
    Menghentikan NodeManager
    ```
    yarn-daemon.sh stop resourcemanager
    ```
    Memulai NodeManage
    ```
    yarn-daemon.sh start nodemanager
    ```
    Menghentikan NodeManager
    ```
    yarn-daemon.sh stop nodemanager
    ```






