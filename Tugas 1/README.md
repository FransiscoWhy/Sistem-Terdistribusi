Sistem Terdistribusi

1. Download wsl

   “wsl —install -d Ubuntu”, perintah untuk mengecek apakah wsl sudah berhasil didownload
   
2. Install Server host

   sudo apt install -y build-essential linux-headers-$(uname -r)
   
![image](https://github.com/FransiscoWhy/Sistem-Terdistribusi/assets/141225950/b3537eea-9737-4216-a0f8-902ca5186856)

3. Mengganti source list ubuntu 22.04
   
![image](https://github.com/FransiscoWhy/Sistem-Terdistribusi/assets/141225950/d5c343ed-492c-4f3d-988a-7de4bc85eb1c)

4. Mengupgrade

   sudo apt upgrade -y
   
![image](https://github.com/FransiscoWhy/Sistem-Terdistribusi/assets/141225950/08870613-ef35-4541-ac14-537052844027)

![image](https://github.com/FransiscoWhy/Sistem-Terdistribusi/assets/141225950/63a4dae3-0234-4a54-b347-1614125e617d)

5. Installasi lxc
   
   sudo apt-get install lxc lxctl lxc-templates net-tools

6.  Menampilkan template container yang tersedia

    sudo ls /usr/share/lxc/templates/
    
![image](https://github.com/FransiscoWhy/Sistem-Terdistribusi/assets/141225950/657e2407-7868-43ce-a819-c254993b7809)

7. Installasi nginx

    sudo apt install nginx nginx-extras
    
![image](https://github.com/FransiscoWhy/Sistem-Terdistribusi/assets/141225950/3caa66d9-c1e5-4978-b9c5-731844506dba)

8. Kemudian pindah ke direktori “sites-enabled”

cd /etc/nginx/

![image](https://github.com/FransiscoWhy/Sistem-Terdistribusi/assets/141225950/22bc1b98-30f2-437d-a859-475491777bb8)

cd /etc/nginx/sites-enabled/

ls -la, untuk menampilkan daftar isi dari sebuah direktori

sudo cp default fransisco.local, untuk membuat salinan dari file “default” dan diberi nama “fransisco.local”.

![image](https://github.com/FransiscoWhy/Sistem-Terdistribusi/assets/141225950/497adbe4-3945-45a2-b661-98d7f349a78a)

9. Lalu masuk direktori

    sudo nano fransisco.local
    
![image](https://github.com/FransiscoWhy/Sistem-Terdistribusi/assets/141225950/aab97164-b48a-46f1-88dc-b478d92f0596)

10. Tes konfigurasi

sudo nginx -t

sudo nginx -s reload

Kemudian masuk ke direktori var/www/html

sudo cp index.nginx-debian.html index.html

lalu masuk ke, sudo nano index.html

![image](https://github.com/FransiscoWhy/Sistem-Terdistribusi/assets/141225950/13c4cbdf-28b3-445f-948e-c327b92d110d)

![image](https://github.com/FransiscoWhy/Sistem-Terdistribusi/assets/141225950/d9de688a-7587-439a-a5f9-71eb674031ec)

11. Kemudian buka file direktori PC ke menu dibawah

    C:\Windows\System32\drivers\etc

    Buka file hosts pada notepad

    Kemudian tambahkan dibagian paling bawah seperti gambar
    
![image](https://github.com/FransiscoWhy/Sistem-Terdistribusi/assets/141225950/b465c726-6526-41fc-8433-a47e323793b9)

12. Masuk ke web browser

    Ketikkan “fransisco.local”, maka akan muncul tampilan
    
![image](https://github.com/FransiscoWhy/Sistem-Terdistribusi/assets/141225950/df98ed06-9ff6-409c-ad4e-df2dce622348)


13. Kemudian install 

    sudo lxc-create -n microservice1 -t download -- --dist ubuntu --release focal --arch amd64 --force-cache --server images.linuxcontainers.org

    sudo lxc-create -n microservice2 -t download -- --dist ubuntu --release bionic --arch amd64 --force-cache --server images.linuxcontainers.org

    Perintah diatas digunakan untuk membuat sebuah kontainer lxc
    
![image](https://github.com/FransiscoWhy/Sistem-Terdistribusi/assets/141225950/d8027a83-b6f0-48be-b453-1fa32117e166)
 
![image](https://github.com/FransiscoWhy/Sistem-Terdistribusi/assets/141225950/7384e5a6-5802-4895-9c99-467d39ad4616)

14. Lalu kita cek status dan menghidupkan microservice

    sudo lxc-start -n microservice2

    sudo lxc-attach -n microservice2

    sudo lxc-ls -f, untuk mengecek status mcsv2 apakah sudah running

    Perintah diatas juga berlaku untuk microservice1
    
![image](https://github.com/FransiscoWhy/Sistem-Terdistribusi/assets/141225950/f3d21608-2233-4e3a-942d-df48ddfc00d7)
 
![image](https://github.com/FransiscoWhy/Sistem-Terdistribusi/assets/141225950/b71d0a1b-46e9-424c-81fe-12032569e44c)

15. Masukkan ip Addres yang sesuai dengan mcsv, cek ip menggunakan perintah

    Ip a

16. Lalu masuk ke direktori untuk mengubah ip

    sudo nano /etc/netplan/10-lxc.yaml

    perintah diatas untuk mcsv1 dan mcsv2

![image](https://github.com/FransiscoWhy/Sistem-Terdistribusi/assets/141225950/f562277f-85e9-44bb-a4fb-4d226f1a1432)
  
![image](https://github.com/FransiscoWhy/Sistem-Terdistribusi/assets/141225950/7963327d-cc4c-47f4-aec2-701ecfc1f2e2)

17. Masuk ke direktori var/www/html

    cd /var/www/html/

    berlaku pada mcsv1 dan mcsv2

18. Lalu cek file HTML dengan perintah

    ls
19. Masuk ke direktori nya untuk mengubah file HTML

    nano index.nginx-debian.html

    pada mcsv1 dan mcsv2

![image](https://github.com/FransiscoWhy/Sistem-Terdistribusi/assets/141225950/aa049c1b-b084-4429-8ab4-487c6ed6f4df)

20. Masuk ke direktori sites-enabled

    cd sites-enabled

    ls

    cp default mcsv1.local

    nano mcsv1.local

    berlaku juga untuk mcsv2

![image](https://github.com/FransiscoWhy/Sistem-Terdistribusi/assets/141225950/bb8bb204-512d-49cb-9d64-8964eab44a2a)

![image](https://github.com/FransiscoWhy/Sistem-Terdistribusi/assets/141225950/86c81a49-6f16-4ec0-a922-81b8214c0575)

21. Masukkan perintah dibawah dan reload
    
    sudo nginx -t

    sudo nginx -s reload
 
![image](https://github.com/FransiscoWhy/Sistem-Terdistribusi/assets/141225950/6474b320-64ed-4010-8b3c-c51ee50486c9)

22. Masuk ke direktori hosts dan tambahkan mcsv didalamnya pada mcsv1 dan mcsv2

   sudo nano /etc/hosts

![image](https://github.com/FransiscoWhy/Sistem-Terdistribusi/assets/141225950/1eaccc6d-7c53-479d-af7a-62e824bd43ac)

23. Masuk ke direktori fransisco.local dan ubah seperti pada gambar

    sudo nano fransisco.local
 
![image](https://github.com/FransiscoWhy/Sistem-Terdistribusi/assets/141225950/e926e182-ba18-4dbc-99f9-c50e5c315756)

24. Jangan lupa untuk mereload

    sudo nginx -t

    sudo nginx -s reload

25. Lalu buka web browser ketik “fransisco.local/blog”, akan muncul tampilan seperti dibawah

![image](https://github.com/FransiscoWhy/Sistem-Terdistribusi/assets/141225950/698d7220-1482-4a79-be5f-b3628ce73aa5)

25. Dan jika ketik “fransisco.local/aboutus”, akan muncul tampilan seperti dibawah

![image](https://github.com/FransiscoWhy/Sistem-Terdistribusi/assets/141225950/65796316-e7cf-41f4-b5ea-aa4f9ee73802)

 

 

 
