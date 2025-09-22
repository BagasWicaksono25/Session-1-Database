langkah pertama masuk ke terminal linux lalu ketik prompt "sudo su" untuk masuk ke mode root, setelah itu masukkan password kalian. Selanjutnya ketik "apt update" dan "apt upgrade" untuk memastikan sistem linux yang digunakan sudah terupdate ke versi yang paling terbaru
Kemudian ketik prompt "apt install mariadb-server"
Pilih "Y"
Ketik prompt "systemctl start mariadb" untuk memulai mariadb
Ketik prompt "systemctl enable mariadb" untuk mengiinkan mariadb
Ketik prompt "systemctl status mariadb" untuk mengecek apakah mariadb sudah running atau belum
Lalu ketik prompt "mysql_secure_installation" untuk meningkatkan keamanan instalasi server pada mariadb. jika terdapat pilihan, pilih "n"
Lanjut pilih "n" lagi, Terakhir pilih "Y" sebanyak 4x
Mariadb siap dijalankan!
