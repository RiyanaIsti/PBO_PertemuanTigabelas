## Form Login dengan Java Persistence API (JPA)
Project ini merupakan implementasi form login pada aplikasi berbasis Java dengan menggunakan Java Persistence API (JPA) sebagai pengelola data pengguna. Fitur login ini digunakan untuk melakukan proses autentikasi dan otorisasi sebelum pengguna dapat mengakses sistem utama.

## Fitur Utama
- Login menggunakan username dan password
- Validasi data ke database menggunakan EntityManager
- Pesan hasil login: ✔ Berhasil → diarahkan ke halaman utama (Dashboard), ❌ Gagal → pesan kesalahan (username/password salah)

## Mekanisme Login Menggunakan JPA
Berikut adalah alur proses login:
- Pengguna memasukkan username dan password.
- Aplikasi mengirim permintaan query ke database melalui EntityManager.
- JPA melakukan pencarian data dengan JPQL (Java Persistence Query Language).
- Jika data cocok → Akses diberikan.
- Jika tidak ditemukan → Pesan error ditampilkan.

## jFrame Loginn
•	Desain frame Loginn, untuk label “Lupa password?” dan Label “Daftar” klik kanan – event – mouse – mouseClicked digunakan untuk menambahkan event handler yang akan dijalankan ketika label diklik dengan mouse. Dengan cara ini, kita bisa menulis kode program yang menentukan tindakan atau respon yang terjadi setiap kali komponen tersebut diklik.

<img width="397" height="248" alt="image" src="https://github.com/user-attachments/assets/95fd0f0d-4d32-465f-bc96-0bea0a463b1e" />

•	Code Button Masuk berfungsi sebagai proses login menggunakan JPA. Saat tombol Masuk ditekan, program memeriksa apakah username dan password terisi, lalu mencari data pengguna di database. Jika username tidak ditemukan, muncul pesan “Data tidak ditemukan”; jika password sesuai, tampil pesan “Selamat datang, [username]” dan form Dashboard dibuka; namun jika salah, muncul pesan “Password salah”. Setelah itu, transaksi diselesaikan dan koneksi database ditutup.

<img width="482" height="348" alt="image" src="https://github.com/user-attachments/assets/4145b6a3-fc70-414b-add6-0ff2599cf0c6" />

•	Code Label Lupa password berfungsi untuk membuka form ResetPassword saat label “Lupa Password” diklik. Program akan menampilkan form reset password (r.setVisible(true)) dan menutup form login yang sedang aktif (this.dispose()).

<img width="574" height="109" alt="image" src="https://github.com/user-attachments/assets/a32ca3a1-e73f-468c-a1d5-9f21cd5f65a0" />

•	Code Label Daftar berfungsi untuk membuka form Daftar ketika label “Daftar” dikli. Program akan membuat objek form Daftar, menampilkannya di layar, lalu menutup form yang sedang aktif agar dapat langsung melakukan proses pendaftaran akun baru.

<img width="520" height="100" alt="image" src="https://github.com/user-attachments/assets/43fd8147-5dfa-4ddc-b738-1d2301cc18d0" />

## jFrame ResetPassword
•	Desain frame ResetPassword, untuk label “Back” klik kanan – event – mouse – mouseClicked digunakan untuk menambahkan event handler yang akan dijalankan ketika label diklik dengan mouse. Dengan cara ini, kita bisa menulis kode program yang menentukan tindakan atau respon yang terjadi setiap kali komponen tersebut diklik.

<img width="392" height="231" alt="image" src="https://github.com/user-attachments/assets/ab6d644d-0dc7-4bf6-b16c-944e21acecfc" />
 
•	Code Button Cari berfungsi untuk mencari data pengguna berdasarkan username saat tombol Cari ditekan. Program terlebih dahulu memeriksa apakah kolom username sudah diisi. Jika belum, muncul pesan peringatan. Jika sudah, program menggunakan JPA untuk mencari data pengguna di database. Jika data tidak ditemukan, muncul pesan “Data tidak ditemukan”. Namun jika ditemukan, form akan menampilkan kolom dan tombol untuk mengganti password, mengunci input username agar tidak diubah, dan memfokuskan kursor ke kolom password baru. Setelah itu, transaksi diselesaikan dan koneksi database ditutup.

<img width="621" height="380" alt="image" src="https://github.com/user-attachments/assets/b3ae4151-4f3a-4957-9e79-a6b6b9ead58d" />

•	Code Button Simpan berfungsi untuk menyimpan perubahan password saat tombol Simpan ditekan. Program terlebih dahulu memeriksa apakah kolom password sudah diisi. Jika belum, muncul pesan peringatan. Jika sudah, program menggunakan JPA untuk mengambil data pengguna berdasarkan username, kemudian memperbarui password di database dengan nilai baru. Setelah transaksi disimpan (commit), sistem menampilkan pesan “Berhasil diubah”, menutup form saat ini, dan membuka kembali form Login agar pengguna dapat masuk menggunakan password yang baru diperbarui.

<img width="606" height="392" alt="image" src="https://github.com/user-attachments/assets/d26a83cf-1e49-4557-8f55-a8b4858bbf72" />

•	Code Label Back berfungsi untuk kembali ke form Login saat label “Back” diklik. Program membuka objek form Login, menampilkannya di layar, lalu menutup form yang sedang aktif agar dapat kembali ke halaman login dengan mudah.

<img width="554" height="106" alt="image" src="https://github.com/user-attachments/assets/ea387aef-5843-4620-b4a8-365680e83f61" />

## jFrame Daftar
•	Desain frame Daftar, untuk label “Back” klik kanan – event – mouse – mouseClicked digunakan untuk menambahkan event handler yang akan dijalankan ketika label diklik dengan mouse. Dengan cara ini, kita bisa menulis kode program yang menentukan tindakan atau respon yang terjadi setiap kali komponen tersebut diklik.

<img width="393" height="250" alt="image" src="https://github.com/user-attachments/assets/5131f304-12dc-4a81-9b72-4d133d583bf8" />

•	Code Daftar berfungsi berfungsi untuk membuat akun baru saat tombol Daftar ditekan. Program memeriksa apakah kolom username dan password telah diisi; jika belum, muncul pesan peringatan. Jika sudah, sistem menggunakan JPA untuk mengecek apakah username tersebut sudah terdaftar di database. Jika sudah ada, muncul pesan bahwa username harus diganti. Jika belum, data baru disimpan ke database, transaksi dikonfirmasi, dan pesan “Sukses dibuat” ditampilkan. Setelah itu, form pendaftaran ditutup dan form Login dibuka agar akun baru bisa langsung digunakan untuk masuk.

<img width="710" height="555" alt="image" src="https://github.com/user-attachments/assets/4fe3c28e-7d1f-4ebd-a826-67bf1ee7bf22" />
 
•	Code Back berfungsi untuk kembali ke form Login saat label “Back” diklik. Program membuat objek form Login, menampilkannya di layar, lalu menutup form yang sedang aktif agar dapat berpindah kembali ke halaman login.

<img width="577" height="115" alt="image" src="https://github.com/user-attachments/assets/2184de0a-4561-4a9d-9792-d86d5ae50489" />



