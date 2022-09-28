# Writing and Presentation Test
## Day 1: Unix Command Line
Shell merupakan perantara yang digunakan antara user dan sistem operasi untuk berinteraksi atau memerintah sistem melalui perintah tertulis. Command Line Interface (CLI) merupakan jenis shell yang berbasis teks. Jadi, shell merupakan software terminal yang memproses semua perintah yang user ketik di CLI lalu shell menginstruksikan sistem operasi untuk menjalankan perintah tersebut.

### Mengakses CLI dan Menggunakan Terminal
- Mengakses CLI dapat dilakukan dengan berbagai tipe shell
- Terdapat 2 tipe shell yang populer, yaitu Windows shell (Windows) dan Bash (Linux dan MacOS)
- Menggunakan terminal:
  - Membuka jendela terminal
  - Mengetik perintah pada terminal

### File System Structure
- Proses yang mengatur dimana dan bagaimana sebuah data disimpan dan diakses dalam disk penyimpanan (storage device)
- Struktur sistem file dan direktori disusun seperti pohon (tree)

### Terminal Commands
1. Melihat current working directory

    Dengan **pwd** (print working directory)
```
pwd
```

2. Melihat isi file dari sebuah direktori

    Dengan **ls** (lists)
```
ls
```

3. Pindah direktori

    Dengan **cd** (change directory)
```
cd /tujuanDirektori
```

4. Melihat isi file

    Terdapat 3 command:
    - **head** (melihat 10 baris pertama dari file text)
    - **tail** (melihat 10 baris terakhir dari file text)
    - **cat** (melihat seluruh isi dari file text)
```
head namaFile.ekstensiFile
tail namaFile.ekstensiFile
cat namaFile.ekstensiFile
```

> Jika ingin melihat bagian isi file sesuai baris yang diinginkan
```
head -baris <namaFile.ekstensiFile
```

5. Membuat file dan direktori

    Terdapat 2 command:
    - **touch** (membuat sebuah file)
    - **mkdir** (membuat sebuah direktori)
```
touch namaFile.ekstensiFile
mkdir 'namaFolder'
```

6. Menyalin file dan direktori

    Terdapat 2 command:
    - **cp** (menyalin file)
    - **cp -R** (menyalin direktori)
```
cp namaFileCopy.ekstensiFile namaFilePaste.ekstensiFile
cp -R namaFolderCopy namaFolderPaste
```

7. Memindahkan/rename file dan direktori

    Terdapat 2 command:
    - **mv** (memindahkan/rename file)
    - **mv -R** (memindahkan/rename direktori)
```
mv namaOldFile.ekstensiFile namaNewFile.ekstensiFile
mv -R namaOldFolder namaNewFolder
```

8. Menghapus file dan direktori

    Terdapat 2 command:
    - **rm** (menghapus file)
    - **rm -R** atau **rm -d** (menghapus direktori)
```
rm namaFile.ekstensiFile
rm -R namaOldFolder namaNewFolder
```

## Day 1: Git dan GitHub
### 'WHY' Git & GitHub Tools Wajib
Seorang programmer tidak akan pernah bekerja sendirian. File yang disimpan dengan git akan melacak setiap perubahan yang terjadi. Jika file disimpan dengan git dan diupload ke github maka programmer dapat berkerja sama dengan mudah tanpa harus ribet copy paste file aplikasi.

### Git
Git adalah aplikasi yang dapat melacak setiap perubahan yang terjadi pada suatu file atau folder. Git merupakan software berbasis version control system yang bertujuan untuk menyimpan database pada semua orang yang terlibat dalam penyusunan code.

### GitHub
GitHub adalah layanan cloud yang berguna untuk menyimpan dan mengelola sebuah repository atau project. GitHub merupakan platform yang mirip dengan google drive tetapi postingannya berkaitan dengan pemrograman.

### Alur Kerja Git & GitHub
1. Download dan install git

2. Check apakah instalasi berhasil
```
git --version
```

3. Melakukan setup awal
```
git config --global user.name "usernameKamu"
git config --global user.email emailKamu@gmail.com
```

4. Check apakah setup awal berhasil
```
git config --list
```

5. Membuat repository
```
git init
```

6. Tambahkan file ke repository
```
git add namaFile
```

7. Melakukan commit dan memberi keterangan pada setiap perubahan
```
git commit -m "Pesan"
```

8. Melakukan push project ke github

## Membuat Repository Git
