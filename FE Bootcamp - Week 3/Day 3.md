# WRITING FE WEEK 3 - DAY 3
## REACT TESTING
- Testing: pengujian
- Testing pada react untuk memeriksa bahwa code sudah sesuai harapan
- Testing membantu memastikan dan mengetahui celah yang belum teratasi tetapi tidak menyelesaikan bug
- Selain itu, manfaat testing adalah
  - Meningkatkan stabilitas program jika testing terstruktur dengan baik
  - Software engineer dapat menyadari jika terjadi penuruan performa
  - Digunakan sebagai desain (TDD)
- Testing terbagi menjadi dua jenis, yaitu:
  - Manual testing (dilakukan manual dengan analisis manusia)
  - Automated testing (dilakukan dengan code)

### Automated testing
Secara umum, automated terbagi menjadi tiga, yaitu:
- Unit test: membuat komponen dari yang paling kecil seperti functionya bakal di test apakah sesuai ekspetasi kita atau tidak. Setiap buat code lakukan unit test
- Integration test: satu aplikasi terhubung ke system lain, contoh database
-	End-to-end: test yang dilihat dari sisi user (workflow dari awal sampai akhir)
![image](https://user-images.githubusercontent.com/85722923/201525871-cba0f54f-3a8f-4ee9-8e56-622e2b3e2ac3.png)

### Menulis Testing
Menulis testing itu lama, spesifikasi testing harus dibuat dengan jelas. Dua cara menulis testing:
1. Buat fitur lalu testing (biasanya digunakan perusahaan startup)
2. Buat code testing dulu baru buat fitur. Ini disebut dengan TDD

### Alur Testing
- Import fungsi untuk menguji
- Memberikan masukan ke fungsi
- Menentukan apa yang diharapkan sebagai output
- Memeriksa apakah fungsi menghasilkan output yang diharapkan

### TDD (Test Driven Development)
- Circle of life
  - Red zone (test fails): tahap menulis ekspetasi tanpa code
  - Green zone (test passes): tahap membuat code untuk ekspetasi
  - Blue zone (refactor): tahap memperbaharui code tanpa mengubah ekspetasi
![image](https://user-images.githubusercontent.com/85722923/201527021-a0985bf4-4130-4db5-b3b1-22059a9a5975.png)
![image](https://user-images.githubusercontent.com/85722923/201525684-b05abf4f-ddad-4373-b205-2dd8a741c732.png)

### Unit Testing
- Unit test merupakan automated test yang paling sering digunakan
- Unit test merupakan test yang paling murah dan yang paling cepat karena sang developer tinggal mengetest function tanpa perlu hire orang lain
- Unit test baiknya digunakan untuk menguji satu unit saja dari program kita (satu fungsi)
- Unit test memiliki tiga istilah, yaitu arrange-act-assert
- arrange-act-assert merupakan pola untuk mengatur dan memformat code dalam unit test
  - Arrange: mengatur semua persyaratan dan input yang dibutuhkan
  - Act: melakukan pengujian pada object yang ingin diuji
  - Assert: memastikan hasil yang diharapkan telah didapat
```js
  describe('addTwoNumbers', () => {
      test('1 and 2 make 3', () => {
          // Arrange
          const argA = 1;
          const argB = 2;
          const assert = 3;

          // Act
          const result = addTwoNumbers(argA, argB);

          // Assert
          expect(result).toBe(assert);
      });
  });
```
- Pada unit test, hasil yang didapat dari function yang dites akan dibandingkan dengan nilai ekspektasi
- Test akan gagal bila kedua data tidak sama

### Jest
- Jest merupakan library javascript untuk melakukan pengetesan pada unit test
- Jest menggunakan matchers untuk membandingkan nilai, seperti:
  - memeriksa kesetaraan
  - membandingkan dua nomor atau string
  - memverifikasi truthiness ekspresi
- Menginstall package jest `npm install jest --save-dev`

#### Menggunakan Jest
- Kalau mau run jest maka tambahkan script di file package.json. Lalu, masukan perintah `npm run test` ke terminal (bash)
![image](https://user-images.githubusercontent.com/85722923/201525424-5276d3f9-4843-4875-b42a-660747ef92b8.png)
- Jika code tidak sesuai dengan ekspetasi maka akan error
  -	Ekspetasi kita plus tetapi kita buat function minus
  - Pada ekspetasi pertama (0, 0) masih benar tetapi untuk ekspetasi kedua dan seterusnya error
![image](https://user-images.githubusercontent.com/85722923/201525497-bd03a3a2-3249-45c3-827a-6f26e97ae648.png)

### RTL (React Testing Library)
- React Testing Library dibangun di atas DOM Testing Library dengan menambahkan API untuk bekerja dengan komponen React
- Di dalam RTL sudah terdapat jest
- RTL merupakan library unit testing semi end-to-end
- Menginstall library testing `npm install --save-dev @testing-library/react`

### Elemen berdasarkan Accessibility
- Access by everyone
  - getByRole
  - getByLabelText
  - getByPlaceholderText
  - getByText
- Semantic queries
  - getByAllText
  - getByTitle
- Test ID
  - getByTestId

**Catatan**:
- `toBe()` untuk mencocokan value yang didapat dengan value yang diharapkan
- `jest.fn()` untuk membuat function mock jest
- `.toEqual()` method matcher untuk mencocokkan nilai dari dua object, biasa disebut 'deep equal'
- `npm run test` perintah untuk menjalankan testing
