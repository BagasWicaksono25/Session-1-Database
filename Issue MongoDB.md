Awalnya saya memakai Linux Debian 13, tetapi setelah banyak percobaan dalam menginstall dan menjalankan mongodb dari mulai versi terbaru hingga terlama (4.4) masalahnya masih tidak berhasil. Setelah itu saya coba beralih dengan menginstal Linux Mint Cinnamon versi 21.3
Saya memulai dengan mendownload Linux Mint di Flashdisk yang sesuai dengan laptop saya yaitu "MBR". Setelah itu saya masuk ke mode BIOS dan mulai memindahkan flashdisk ke paling atas pada boot priority kemudian save and exit
Disini terjadi masalah kembali dimana saya lupa merufus flashdisk yang saya gunakan dan mengubah partition scheme ke "MBR"
Selanjutnya saya merufus flashdisk dan mengubah partition scheme ke "MBR"
Pada akhirnya saya berhasil masuk dan memulai tahapan install. Pertama saya disuruh memilih bahasa, saya lalu memilih bahasa inggris
Lalu saya memilih "English US"
Saya juga tidak menyambungkan koneksi internet dan langsung next
Kemudian saya centang "Install multimedia codes"
Disini saya disuruh memilih installation type. Saya memilih "something else"
Selanjutnya saya pilih partisi "Free space" dan klik tanda plus di kiri
Disini saya atur size, type, location, dan use as saya ganti menjadi "swap area"
Selanjutnya saya atur size, type, location, dan use as saya ganti menjadi "Ext4" dengan mount point "/"
Terakhir saya atur size, type, location, dan use as saya ganti menjadi "Ext4" dengan mount point "/home"
Lalu saya centang ketiga partisi tersebut dan klik "install now"
klik "continue"
klik "continue" lagi
Selanjutnya saya pilih set lokasi yaitu Indonesia dan klik "continue"
Step terakhir saya membuat username dan password pada Linux Mint lalu klik "continue"
Tinggal menunggu instalasi
Linux Mint siap digunakan!
Setelh Linux Mint dapat terinstall, saya coba masuk ke terminal dan ketik "sudo su" dan memasukkan passord untuk masuk ke dalam mode root. Selanjutnya saya coba install mongodb di Linux Mint ini dengan melihat situs resmi mongodb, pertama saya ketik prompt "sudo apt-get install gnupg curl"
Kemudian muncul prompt seperti di gambar 22
Lanjut saya ketik "curl -fsSL https://www.mongodb.org/static/pgp/server-8.0.asc | \ sudo gpg -o /usr//share/keyrings/mongodb-server-8.0.gpg \ --dearmor"
Selanjutnya saya ikuti prompt yang ada di web resmi mongodb sebagai berikut "echo "deb [ arch=amd64,arm64 signed by=usr/share/keyrings/mongodb-server-8.2.gpg ] https://repo.mongodb.org/apt/ubuntu jammy/mongodb-org/8.2 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-8.2.list"
Lalu saya salin dan tempel promptnya pada terminal
Kemudian muncul prompt seperti di gambar 26
Saya lalu mengikuti prompt di web resmi mongodb lagi yaitu "sudo apt-get update"
Lalu saya salin dan tempel promptnya pada terminal
Saya lalu mengikuti prompt di web resmi mongodb lagi yaitu "sudo apt-get install -y mongodb-org"
Lalu saya salin dan tempel promptnya pada terminal
Saya lalu mengikuti prompt di web resmi mongodb lagi yaitu "sudo systemctl start mongod"
Lalu saya salin dan tempel promptnya pada terminal. Karena tertulis "Unit mongod.service not found"
Saya lalu mengikuti prompt di web resmi mongodb lagi yaitu "sudo systemctl daemon-reload"
Lalu saya salin dan tempel promptnya pada terminal
Saya lalu coba lagi prompt "sudo systemctl start mongod"
Namun hasilnya masih tertulis "Unit mongod.service not found"
Terakhir saya coba cek status mongodb saya dengan mengetik prompt "systemctl status mongod". Tetapi hasilnya failed, dan terdapat masalah yang hampir mirip saat saya coba install mongodb di debbian 13, yaitu code:dumped dan signal ILL. Yang saat saya cari tahu ternyata CPU laptop saya tidak kompatible dengan system terbaru dari mongodb versi terbaru. Bukan hanya itu, saya juga telah mencoba hapus dan download ulang mongodb dengan berbagai versi di Linux Mint ini, namun hasilnya status yang ditunjukkan masih sama, yaitu code=dumped, signak:ILL
