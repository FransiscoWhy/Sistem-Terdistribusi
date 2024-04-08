1. Membuat microservice3 menggunakan Debian

   sudo lxc-create -n microservice3 -t download -- --dist "debian" --release "buster" –arch amd64

![Screenshot 2024-04-08 085144](https://github.com/FransiscoWhy/Sistem-Terdistribusi/assets/141225950/5fc41f2f-7193-4914-8449-071559b14d08)

   sudo lxc-start -n microservice3

   sudo lxc-attach microservice3

   sudo apt update

   sudo apt install nginx nano

![image](https://github.com/FransiscoWhy/Sistem-Terdistribusi/assets/141225950/aaec64e3-18a6-4779-8a1a-8d00d34a29c0)

2. Mengubah konfigurasi microservice3

   sudo nano /etc/hosts

![image](https://github.com/FransiscoWhy/Sistem-Terdistribusi/assets/141225950/6833b4d6-75a3-4bc9-9605-0fb2c3d890af)

3. Membuat microservice4 menggunakan Debian

  sudo lxc-create -n microservice4 -t download -- --dist "debian" --release "buster" –arch amd64

![image](https://github.com/FransiscoWhy/Sistem-Terdistribusi/assets/141225950/108d6f48-bcaf-47d9-89e7-d922d5912f8b)

  sudo lxc-start -n microservice4
  
  sudo lxc-attach microservice4
  
  sudo apt update
  
  sudo apt install nginx nano

![image](https://github.com/FransiscoWhy/Sistem-Terdistribusi/assets/141225950/dc1167aa-5e0f-4f6f-9256-fd3d68d30593)

4. Konfigurasi microservice4

   sudo nano /etc/hosts

![image](https://github.com/FransiscoWhy/Sistem-Terdistribusi/assets/141225950/402bd8b7-e5ff-495b-b217-96c83883d9ca)

5. Membuat microservice4 menggunakan Debian

   sudo lxc-create -n microservice5 -t download -- --dist "debian" --release "buster" –arch amd64

![image](https://github.com/FransiscoWhy/Sistem-Terdistribusi/assets/141225950/1f4d47fe-f43f-4c47-b929-4e455b4a45db)

sudo lxc-start -n microservice5

sudo lxc-attach microservice5

sudo apt update

sudo apt install nginx nano

![image](https://github.com/FransiscoWhy/Sistem-Terdistribusi/assets/141225950/db254008-99db-4c2d-9909-6c5eb398c7f1)

6. Konfigurasi microservice5

sudo nano /etc/hosts

![image](https://github.com/FransiscoWhy/Sistem-Terdistribusi/assets/141225950/e1f8b728-f0cc-4d37-a0a5-55713441fb54)

7. Mengkonfigurasi Host Wsl

   sudo nano /etc/hosts

![image](https://github.com/FransiscoWhy/Sistem-Terdistribusi/assets/141225950/02181172-64da-403b-9f76-20b8570297b1)

8. Mengubah direktori /etc/nginx/sites-enabled/sister.local

   sudo nano /etc/nginx/sites-enabled/sister.local

![image](https://github.com/FransiscoWhy/Sistem-Terdistribusi/assets/141225950/bd266f12-45d5-4f9a-a732-19b439e05bb6)



![image](https://github.com/FransiscoWhy/Sistem-Terdistribusi/assets/141225950/cb37f073-1b09-45a7-9d5b-eedce1889613)

9. Pindah ke direktori /etc/nginx/sites-enabled/

   cd /etc/nginx/sites-enabled

10. Mengetest perubahan konfigurasi dan mereload

    sudo nginx -t

    sudo nginx -s reload  

![image](https://github.com/FransiscoWhy/Sistem-Terdistribusi/assets/141225950/f53cc3e7-a46a-40a4-9507-07f49cd780cd)

11. Review tampilan dengan perintah

    curl -i app.fransisco.local

![image](https://github.com/FransiscoWhy/Sistem-Terdistribusi/assets/141225950/69c9ed73-5981-4653-87c9-6e33aeb1d502)

