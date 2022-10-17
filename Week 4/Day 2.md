# WRITING WEEK 4 - DAY 2
## GIT & GITHUB LANJUTAN
### Cara Collab Git & GitHub
1. Team leader membuat organization dan menginvite anggota team lalu dijadikan owner
2. Team leader membuat repository pada organization yang telah dibuat
3. Repository dibuat public dan ceklis README
4. Team leader membuat branch bernama `dev`
5. Masing-masing anggota lakukan `git clone` pada repository yang sudah dibuat (1x aja)
6. Bagi tugas pada masing-masing anggota team
7. Pindah ke branch dev `git switch dev`
8. Sebelum ngoding, lakukan `git pull` pada branch dev untuk update kode terbaru
9. Anggota membuat branch dari dev `git branch [nama-branch]`
10. Pindah ke dalam branch yg sudah dibuat `git switch [nama-branch]`
11. Lakukan pengerjaan di dalam branch tersebut
12. Jika fitur sudah selesai, sebelum di push lakukan langkah nomor ke 3, 4, dan 6
13. Lalu `git merge dev` untuk menghindari conflict di github
14. Jika ada conflict, bereskan semuanya
15. Jika sudah aman, commit lalu `git push origin [nama-branch]`
16. Lakukan pull request untuk merge ke branch dev
17. Tunggu pull request di accept oleh team lead
18. Jika sudah, ulangi proses dari nomor 2

*Noted*:
- Organization ibarat akun bersama yang memiliki banyak repository
- Biasanya organization dan repository dibuat oleh team lead
- `git clone` merupakan perintah untuk mendownload repository ke local penyimpanan
- Project git memiliki dua tipe branch:
  - main: primary branch digunakan ketika fitur project sudah stabil, fix, dan bisa diakses publik
  - dev: secondary branch yang tujuannya untuk menampung branch-branch lain
- Penamaan branch dalam branch dev bisa kita sesuaikan dengan fitur yang sedang kita rancang
- Setiap fitur yang kita rancang harus dibuat branch masing-masing fitur

### Perintah Git
- Membuat branch baru
```
    git branch nama_fitur
```
- Melihat list branch
```
    git branch
```
- Pindah ke dalam branch tertentu
```
    git checkout namaBranch_tujuan
```
- Menghapus sebuah branch
```
    git branch -d nama_fitur
```
