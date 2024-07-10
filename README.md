# ajengpratiwi-215610047-ResponsiAjeng

# Langkah-langkah Membangun Website Data Diri.

## Langkah 1: Persiapan Direktori dan File.
#### 1. Buat dua direktori: website-utama dan website-profil.


```
$ mkdir website-utama
$ cd website-utama
```

#### Penjelasan :
Perintah di atas digunakan untuk membuat dan berpindah ke sebuah direktori baru. Pertama, dengan perintah mkdir website-utama, pengguna membuat sebuah direktori baru yang diberi nama website-utama. Perintah ini singkatan dari "make directory" yang artinya membuat direktori baru. Setelah direktori ini dibuat, pengguna kemudian menggunakan perintah cd website-utama untuk masuk ke dalam direktori tersebut.

#### 2. Buat file index.html di dalam direktori website-utama.

```
$ nano index.html
``` 
#### Penjelasan :
Perintah nano index.html digunakan untuk membuat atau membuka file bernama index.html menggunakan editor teks bernama Nano. Setelah memasukkan perintah ini di killercoda ubuntu, editor Nano akan terbuka dan menampilkan isi dari file index.html jika file tersebut sudah ada.
 
#### 3. Buat file index.html di dalam direktori website-utama.
#### Penjelasan :
Perintah nano index.html digunakan untuk membuka editor teks Nano dan membuat atau mengedit file index.html. Di dalam editor Nano, pengguna menuliskan kode HTML yang membentuk struktur dasar sebuah halaman web. Halaman ini dirancang untuk menampilkan informasi pribadi dengan tampilan yang rapi dan terstruktur, termasuk nama, NIM, program studi, dan hobi, serta sebuah tautan menuju halaman profil.

#### 4. Gunakan perintah wget untuk mengunduh file foto.jpg dalam drive.


```
$ wget ~O ~/website-profil/foto.jpg
"https://docs.google.com/uc?export=download&id=1hdbKeGv0-RFcMbNMmZxL0UE5GWEP8uW2"
```

#### Penjelasan :
Perintah wget adalah perintah yang digunakan untuk mengunduh konten dari web. Dalam perintah ini, pengguna meminta wget untuk mengunduh file gambar dari URL yang disediakan. Argumen -O diikuti oleh jalur -/website-profil/foto.jpg menunjukkan bahwa file yang diunduh akan disimpan dengan nama foto.jpg di dalam direktori website-profil yang berada di direktori home pengguna (~). URL yang diikuti menunjukkan lokasi file gambar di Google Drive, dengan parameter
export=download&id=1hdbKeGv0-RFcMbNMmZxL0UE5GWEP8uW2
yang memastikan file diunduh langsung. Setelah perintah ini dieksekusi, maka akan memiliki file gambar foto.jpg yang tersimpan di dalam direktori website-profil, siap digunakan atau diakses sesuai kebutuhan.

#### 4. Buat file index.html di dalam direktori website-profil.

```
$ mkdir website-profil
$ cd website-profil
```

#### Penjelasan :
Perintah di atas digunakan untuk membuat direktori baru dan kemudian berpindah ke dalamnya. Pertama, perintah mkdir website-profil dijalankan untuk membuat direktori baru bernama website-profil. Setelah direktori ini berhasil dibuat, perintah cd website-profil dijalankan untuk masuk ke dalam direktori tersebut. 

#### 5. Isi file index.html dengan konten berikut :
 
#### Penjelasan :
perintah nano index.html digunakan untuk membuka atau membuat file index.html dengan editor teks Nano, di mana pengguna menulis kode HTML yang mendefinisikan struktur dasar halaman web sederhana. Kode tersebut mencakup deklarasi HTML5, pengaturan karakter set dan viewport, serta konten utama berupa judul "Profil" dan sebuah gambar profil berukuran 200 piksel. Setelah menyimpan file tersebut, pengguna memiliki sebuah halaman web dasar yang siap digunakan.


## Langkah 2: Docker Network.
#### 1. Buat jaringan Docker dengan nama my-ajeng-pratiwi-network.


```
$ docker network create my-ajeng-pratiwi-network
```

#### Penjelasan :
Penjelasan di atas adalah bahwa perintah docker network create my-ajeng-pratiwi-network digunakan untuk membuat sebuah jaringan virtual baru dalam lingkungan Docker. Jaringan ini memungkinkan container-container Docker untuk berkomunikasi satu sama lain dengan cara yang terisolasi dan terkontrol. Dengan membuat jaringan seperti ini, pengguna dapat mengelola hubungan antar kontainer secara efisien, menjaga keamanan, dan memfasilitasi komunikasi yang diperlukan antar aplikasi atau layanan yang berjalan di dalam container Docker.

## Langkah 3: Dockerfile dan Image.
### Dockerfile untuk Website Utama.
#### 1. Buat file Dockerfile di dalam direktori website-utama.

```
$ nano Dockerfile
```

#### Penjelasan :
Perintah nano Dockerfile digunakan untuk membuat atau mengedit file bernama Dockerfile menggunakan editor teks Nano di dalam terminal. Dockerfile ini berisi instruksi-instruksi yang digunakan oleh Docker Engine untuk membangun sebuah image Docker. Image ini nantinya akan digunakan untuk menjalankan aplikasi dalam lingkungan container Docker.  

#### 2. Isi dengan konten berikut:

```
FROM nginx:latest
COPY . /usr/share/nginx/html
EXPOSE 80
```

#### Penjelasan :
Dockerfile tersebut diawali dengan instruksi FROM nginx:latest, yang menandakan bahwa basis image yang digunakan adalah image NGINX versi terbaru. Selanjutnya, perintah COPY . /usr/share/nginx/html digunakan untuk menyalin semua file dari direktori saat ini ke dalam direktori /usr/share/nginx/html di dalam container. Direktori ini adalah lokasi default tempat NGINX mencari file HTML untuk dilayani. Terakhir, instruksi EXPOSE 80 memberitahukan bahwa container akan menggunakan port 80 untuk melayani konten web, yang merupakan port standar untuk HTTP.

### Dockerfile untuk Website Profil.
#### 1. Buat file Dockerfile di dalam direktori website-profil.

```
$ nano Dockerfile.
```

#### Penjelasan :
Perintah nano Dockerfile digunakan untuk membuat atau mengedit file bernama Dockerfile menggunakan editor teks Nano di dalam terminal. Dockerfile ini berisi instruksi-instruksi yang digunakan oleh Docker Engine untuk membangun sebuah image Docker. Image ini nantinya akan digunakan untuk menjalankan aplikasi dalam lingkungan container Docker. 

#### 2. Isi dengan konten berikut:

```
FROM nginx:latest
COPY . /usr/share/nginx/html
EXPOSE 80
```

#### Penjelasan :
Dockerfile tersebut diawali dengan instruksi FROM nginx:latest, yang menandakan bahwa basis image yang digunakan adalah image NGINX versi terbaru. Selanjutnya, perintah COPY . /usr/share/nginx/html digunakan untuk menyalin semua file dari direktori saat ini ke dalam direktori /usr/share/nginx/html di dalam container. Direktori ini adalah lokasi default tempat NGINX mencari file HTML untuk dilayani. Terakhir, instruksi EXPOSE 80 memberitahukan bahwa container akan menggunakan port 80 untuk melayani konten web, yang merupakan port standar untuk HTTP.


## Langkah 4: Build Image.
### Bangun dua image Docker dari Dockerfile yang sudah dibuat.
#### 1. Build image untuk website utama:

```
$ docker build -t website-utama .
```

#### Penjelasan :
Perintah docker build -t website-utama . digunakan untuk membangun (build) sebuah image Docker yang diberi tag (-t) dengan nama website-utama. Proses ini dilakukan berdasarkan Dockerfile yang ada di direktori saat ini (.). Dockerfile ini berisi instruksi-instruksi yang mendefinisikan bagaimana image Docker harus dibangun, termasuk langkah-langkah seperti menentukan base image, menyalin file-file yang diperlukan, dan menjalankan perintah-perintah tertentu untuk menyiapkan lingkungan kerja yang diinginkan. Setelah perintah docker build selesai dieksekusi, akan dihasilkan sebuah image Docker yang siap untuk digunakan atau didistribusikan.

#### 2.	Build image untuk website profil:

```
$ docker build -t website-profil .
```
#### Penjelasan :
Perintah docker build -t website-profil . digunakan untuk membangun (build) sebuah image Docker baru yang diberi nama website-profil. Proses ini dilakukan berdasarkan Dockerfile yang terdapat di direktori saat ini (.), yang berisi serangkaian instruksi untuk mengkonfigurasi dan mempersiapkan lingkungan aplikasi. Saat perintah ini dijalankan, Docker akan mengikuti langkah-langkah yang ditentukan dalam Dockerfile untuk menyiapkan semua yang diperlukan, seperti menginstal dependensi, menyalin file-file aplikasi, dan mengatur konfigurasi yang diperlukan. Setelah selesai, image Docker dengan nama website-profil akan tersedia untuk digunakan atau didistribusikan sesuai kebutuhan. Perintah -t digunakan untuk memberi tag (nama) pada image yang dibangun agar mudah diidentifikasi dan dikelola di dalam lingkungan Docker.

## Langkah 5: Docker Volume (Opsional)
#### 1.	Buat volume bernama profile-images.

```
$ docker volume create profil-images
```

#### Penjelasan :
Perintah docker volume create profil-images digunakan untuk membuat sebuah volume baru dalam Docker dengan nama profil-images. Volume ini bertindak sebagai penyimpanan data yang persisten dan terisolasi di dalam lingkungan Docker. Ketika perintah ini dieksekusi, Docker akan membuat sebuah direktori khusus di dalam sistem file host yang digunakan untuk menyimpan data yang terkait dengan volume tersebut.

## Langkah 6: Menjalankan Container.
#### 1.	Jalankan container untuk website utama:

```
$ docker run -d --name website-utama --network my-ajeng-pratiwi-network -p 8080:80 website-utama
```
#### Penjelasan :
Perintah docker run -d --name website-utama --network my-ajeng-pratiwi-network -p 8080:80 website-utama digunakan untuk membuat dan menjalankan sebuah container Docker dari image website-utama. Container ini berjalan di latar belakang (-d), diberi nama website-utama (--name website-utama), terhubung ke jaringan Docker my-ajeng-pratiwi-network (--network my-ajeng-pratiwi-network), dan memetakan port 8080 dari host ke port 80 di dalam container (-p 8080:80). Hal ini memungkinkan akses ke aplikasi yang berjalan di dalam container melalui port 8080 dari host.

#### 2.	Jalankan container untuk website profil:

```
$ docker run -d --name website-profil --network my-ajeng-pratiwi-network -p 8081:80 website-profil
```

Penjelasan: Perintah docker run -d --name website-profil --network my-ajeng-pratiwi-network -p 8081:80 website-profil digunakan untuk membuat dan menjalankan sebuah container Docker dari image website-profil. Container ini berjalan di latar belakang (-d), diberi nama website-profil (--name website-profil), terhubung ke jaringan Docker my-ajeng-pratiwi-network (--network my-ajeng-pratiwi-network), dan memetakan port 8081 dari host ke port 80 di dalam container (-p 8081:80). Ini memungkinkan akses ke aplikasi yang berjalan di dalam container melalui port 8081 dari host.


## Mengakses Website.
#### 1.	Membuka traffic port accessor pada killercoda ubuntu.
#### 2.	Akses halaman utama di: http://localhost:8080. maka akan menampilkan website data diri.
#### 3.	Klik halaman profil untuk bernavigasi “ke Halaman Profil”.
#### 4. Akan tampak halaman profil.