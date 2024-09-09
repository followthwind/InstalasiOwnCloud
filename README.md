# InstalasiOwnCloud

Tata Cara Instalasi Owncloud di Ubuntu yang berjalan di Virtual Machine untuk Pemula

Pastikan sudah menginstall ubuntu di komputer atau di Virtual Machine, kita membutuhkan banyak package dan module untuk dapat menginstal ownCloud di ubuntu, namun dengan bantuan script ini kita dapat menginstalnya hanya dengan me-running 1 command.

link script: https://raw.githubusercontent.com/linuxsyr/owncloud/main/owncloud.bash.

1. Buka Terminal dengan menekan Ctrl + Alt + T, lalu menggunakan wget kita mendownload script diatas.
 ![image](https://github.com/user-attachments/assets/06fd5ac3-4a46-483e-8892-3639df8bee9e)


2. Ubah Script yang kita download menjadi executable.
 ![image](https://github.com/user-attachments/assets/619fb957-dcee-4de2-956d-00ebb1481cf7)


3. Run Scriptnya.
 ![image](https://github.com/user-attachments/assets/dd75360d-0005-4f26-aead-ac40caebfd23)


4. Akan ada beberapa konfimasi yang harus dilakukan, ikuti saja dengan menekan Enter atau masukan huruf y dan Enter, dan jika diminta password silahkan masukan password ubuntu Anda.
 ![image](https://github.com/user-attachments/assets/f10bc3a7-54b0-47ac-b95e-3b20510e57d5)


5. Setelah selesai kita bisa langsung membuka Owncloud di browser untuk mengetest apakah sudah bisa berjalan dengan baik dengan membuka localhost: https://localhost.
![image](https://github.com/user-attachments/assets/c62219d3-ff35-40ad-8d3b-6307fa5e2bb8)


6. Masukan Username: root, dan Password: 1234 (Username dan Password ini mengikuti di Script yang kita download, jika ingin berbeda bisa di edit di dalam Script atau mengubahnya setelah Login di dalam Owncloud).
![image](https://github.com/user-attachments/assets/8e5172ab-29e2-4f86-810d-715e9516ed4a)


7. Dan seperti gambar di bawah kita sudah berhasil menginstall owncloud dan berjalan dengan baik secara local.
![image](https://github.com/user-attachments/assets/a3e985d2-93a0-43ad-b654-39988ab6f988)


8. Setelah itu semua, kita nyalakan firewall kita agar Owncloud bisa diakses oleh pengguna di jaringan yang sama (satu koneksi wifi) dengan command berikut.
 ![image](https://github.com/user-attachments/assets/9752424a-3cbe-4540-a2d9-085d8ef1ff47)


9. Jika ubuntu berjalan di Virtual Box, buka Virtual Box, klik Machine>Settings>Network, lalu ubah Attached to menjadi Bridged Adapter lalu klik OK.
![image](https://github.com/user-attachments/assets/5fbfa800-c506-490f-94fd-556f481a0563)

10. Lalu setup Ngrok agar bisa diakses diluar jaringan, buka laman ngrok di website, login menggunakan google kemudian di terminal copy paste command untuk menambah repository ngrok dan menginstall nya serta masukan tokennya.
 ![image](https://github.com/user-attachments/assets/d601d93a-cdda-462b-b60e-947ed4b2c314)

Lalu nyalakan ngrok di port 80 dengan command di bawah.
 ![image](https://github.com/user-attachments/assets/09da3bbf-5e02-411a-be07-db3c22506fac)

Maka kita akan mendapatkan domain yang dapat diakses diluar jaringan server.
![image](https://github.com/user-attachments/assets/664d6bd1-dbcb-41d5-bf29-5760bfd5caab)

Untuk mengaksesnya kita masukan 127.0.0.1:4040 di browser dan kita mendapatkan link ownCloud kita yaitu: https://15de-2404-8000-1027-d0bf-e975-8402-e738-85cc.ngrok-free.app
Perlu diingat domain gratis dari ngrok akan selalu berubah setiap kali direstart, maka dari itu jika domain berubah kita harus mengupdate config.php ownCloud agar bisa diakses dari domain luar
![image](https://github.com/user-attachments/assets/29c89c1b-4a58-4209-a507-cb6c419e2373)
 
11. Jangan lupa untuk mengubah config.php di ownCloud agar bisa mengakses ownCloud dari domain luar, lokasi config berada di /var/www/owncloud/config/config.php buka config lalu run as Administrator, ubah yang nomor 2 seperti gambar di bawah, isi dengan ip address linux ubuntu yang bisa didapatkan di settings , Network, Network Option, Ipv4 Address, biasanya ip berbentuk 192.168.0.1, lalu ubah yang nomor 3 dengan domain yang kita dapat dari ngrok, kemudia save.
 ![image](https://github.com/user-attachments/assets/3a1dc3a7-3d10-4df5-9843-d26c2c9ac41d)


Untuk jaringan local juga bisa mengakses ownCloud dengan memasukan ip server.
