### Linux Directory
#
- Print Working Directory (pwd)
    | Command   | Fungsi |
    |--------|------|
    | pwd | nampilin direktori yang kamu akses sekarang. |
    | pwd -L  | Menampilkan jalur logis direktori kerja saat ini kalau kamu pake link.|
    | pwd -P | Menampilkan jalur fisik direktori kerja saat ini kalau pake link. |

#
- Change Directory (cd)
    | Command   | Fungsi |
    |--------|------|
    | cd         | Berpindah antara direktori.                             |
    | cd ~ or cd | Selalu membawa pengguna ke direktori utama.            |
    | cd .       | Pindah ke direktori yang sama.|
    | cd ~username | Memungkinkan pengguna tetap berada di direktori utama dari username. |
    | cd dir     | masuk ke subdir direktori yang depannya nga ada /. |
    | cd ..      | Kembali 1 langkah ke belakang dari direktori sekarang.  |
    | cd -       | kembali ke direktori sebelumnya.             |
#
- List (ls)
    | Command   | Fungsi      |
    |------------------------|-----------------|
    | ls         | nampilin isi direktori. 
    | ls -a                  | Menampilkan seluruh daftar direktori saat ini termasuk berkas tersembunyi.          |
    | ls -l                  | Menampilkan daftar dalam format daftar panjang(data lengkap berkas kaya mode user besar file tanggal file dibuat).                                           |
    | ls -lh                 | Menampilkan ukuran berkas dalam format yang mudah dibaca manusia.                         |
    | ls -lhS                | Menampilkan daftar dalam urutan menurun (terbesar di atas) berdasarkan ukuran berkas.     |
    | ls -l --block-size=[SIZE] | Menampilkan berkas dalam format ukuran tertentu.                                         |
    | ls -d */               | Menampilkan hanya subdirektori.                                                          |
    | ls -g atau ls -lG      | Mengecualikan kolom informasi grup dan pemilik.                                          |
    | ls -n                  | Menampilkan ID grup dan pemilik sebagai angka, bukan nama.                               |
    | ls --color=[VALUE]     | Menampilkan daftar dalam warna atau tanpa warna.                                          |
    | ls -li                 | Menampilkan nomor indeks berkas jika berada di kolom pertama.                             |
    | ls -p                  | Mengidentifikasi direktori dengan menandai menggunakan garis miring (/) di belakang.       |
    | ls -r                  | Menampilkan daftar dalam urutan terbalik.                                                |
    | ls -R                  | Akan menampilkan isi subdirektori juga.                                                  |
    | ls -lX                 | Mengelompokkan berkas dengan ekstensi yang sama dalam daftar.                             |
    | ls -lt                 | Mengurutkan daftar dengan menampilkan berkas yang baru diubah di bagian atas.             |
    | ls ~                   | Menampilkan isi direktori beranda.                                                       |
    | ls ../                 | Menampilkan isi direktori induk.                                                          |
    | ls --version           | Memeriksa versi dari perintah ls.                                                          |

#
- Make Directory (mkdir)
    | Command             | Fungsi       |
    |----------|-----------------|
    | mkdir      | Membuat direktori baru.  
    | mkdir -p, -parents      | Membuat direktori beserta subdirektorinya.             |
    | mkdir -v, -verbose      | Menampilkan pesan untuk setiap direktori yang dibuat.   |
    | mkdir -m (mode) (nama_dir)    | Buat dir baru sekalian ngeset modenya        |

#
- Remove Directory (rmdir)
    | Command   | Fungsi |
    |--------|------|
    | rmdir | Menghapus direktori |
    |rmdir -p, -parents | Menghapus direktori beserta subdirektorinya jika ada |
