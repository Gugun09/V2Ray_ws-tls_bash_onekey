## V2Ray didasarkan pada skrip instalasi satu-klik vmess + ws + tls Nginx

> Terima kasih kepada JetBrains yang telah memberikan otorisasi pengembangan perangkat lunak sumber terbuka non-komersial

> Terima kasih atas otorisasi pengembangan sumber terbuka non-komersial oleh JetBrains

### Siap bekerja
* Siapkan nama domain dan tambahkan rekam A.
* Petunjuk resmi V2ray , pahami informasi terkait TLS WebSocket dan V2ray
* Instal wget

### Metode instalasi / pembaruan (versi h2 dan ws telah digabungkan)
Vmess+websocket+TLS+Nginx+Website
```
wget -N --no-check-certificate -q -O install.sh "https://raw.githubusercontent.com/gugun09/V2Ray_ws-tls_bash_onekey/master/install.sh" && chmod +x install.sh && bash install.sh
```

### Tindakan pencegahan
* Jika Anda tidak memahami arti spesifik dari setiap pengaturan dalam skrip, kecuali untuk nama domain, gunakan nilai default yang disediakan oleh skrip
* Untuk menggunakan skrip ini, Anda harus memiliki dasar dan pengalaman Linux, memahami beberapa pengetahuan tentang jaringan komputer, dan pengoperasian komputer dasar
* Saat ini Debian 9+ / Ubuntu 18.04+ / Centos7 + didukung. Beberapa template Centos mungkin mengalami kesulitan untuk menangani masalah kompilasi. Direkomendasikan bahwa ketika Anda mengalami masalah kompilasi, harap ubah ke template sistem lain
* Pemilik grup hanya memberikan dukungan yang sangat terbatas, jika Anda memiliki pertanyaan, Anda dapat bertanya kepada teman grup
* Setiap hari Minggu pukul 3 pagi, Nginx akan otomatis restart untuk berkoordinasi dengan penerbitan sertifikat. Selama periode ini node tidak bisa terkoneksi secara normal, dan perkiraan durasi beberapa detik hingga dua menit.

### Lihat konfigurasi klien
`cat ~/v2ray_info.txt`

### Mulai metode

Mulai V2ray：`systemctl start v2ray`

Hentikan V2ray：`systemctl stop v2ray`

Mulai Nginx：`systemctl start nginx`

Hentikan Nginx：`systemctl stop nginx`

### 相关目录

Web 目录：`/home/wwwroot/3DCEList`

V2ray 服务端配置：`/etc/v2ray/config.json`

V2ray 客户端配置: `~/v2ray_info.inf`

Nginx 目录： `/etc/nginx`

证书文件: `/data/v2ray.key 和 /data/v2ray.crt` Harap perhatikan pengaturan otoritas sertifikat