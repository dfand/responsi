Responsi_TEK_CLOUD
Website Data Diri
Deskripsi
Website ini terdiri dari dua halaman yang di-hosting di container terpisah menggunakan Docker.

Cara Menjalankan di Killercoda Ubuntu Playground
Langkah-langkah
Buat direktori website-profil dan file index.html juga file foto di dalamnya dengan isi seperti berikut:

mkdir website-profil
Buat file index.html Mengunggah foto Profil dalam bentuk png foto.png

Buat jaringan Docker dengan nama my-evita-ishtar-dewi-network:

docker network create my-evita-ishtar-dewi-network
Buat Dockerfile untuk website-profil

Build image Docker untuk website-profil

cd website-profil
docker build -t website-profil .
Jalankan container website-profil:

docker run -d --name website-profil --network my-evita-ishtar-dewi-network -p 8081:80 website-profil
Buat direktori website-utama dan file index.html di dalamnya dengan isi seperti berikut:

mkdir website-utama
Buat file index.html

Buat Dockerfile untuk website-utama

Build image Docker untuk website-utama:

cd website-utama
docker build -t website-utama .
Jalankan container website-utama:

docker run -d --name website-utama --network my-evita-ishtar-dewi-network -p 8080:80 website-utama
Pengujian
Akses website utama di http://localhost:8080.
Klik link "Profil Saya" dan pastikan link tersebut mengarah dan menampilkan halaman profil.
