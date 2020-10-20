V2Ray didasarkan pada skrip instalasi satu-klik vmess + ws + tls Nginx
Terima kasih kepada JetBrains yang telah memberikan otorisasi pengembangan perangkat lunak sumber terbuka non-komersial

Terima kasih atas otorisasi pengembangan sumber terbuka non-komersial oleh JetBrains

Grup Telegram
grup pertukaran telegram: https://t.me/wulabing_v2ray
Saluran pengumuman pembaruan Telegram: https://t.me/wulabing_channel
Siap bekerja
Siapkan nama domain dan tambahkan rekam A.
Petunjuk resmi V2ray , pahami informasi terkait TLS WebSocket dan V2ray
Instal wget
#Metode instalasi / pembaruan (versi h2 dan ws telah digabungkan)
Vmess + websocket + TLS + Nginx + Situs Web

  ```html
wget -N --no-check-certificate -q -O install.sh "https://raw.githubusercontent.com/gugun09/V2Ray_ws-tls_bash_onekey/master/install.sh" && chmod +x install.sh && bash install.sh
  ```
  
Tindakan pencegahan
Jika Anda tidak memahami arti spesifik dari setiap pengaturan dalam skrip, kecuali untuk nama domain, gunakan nilai default yang disediakan oleh skrip
Untuk menggunakan skrip ini, Anda harus memiliki dasar dan pengalaman Linux, memahami beberapa pengetahuan tentang jaringan komputer, dan pengoperasian komputer dasar
Saat ini Debian 9+ / Ubuntu 18.04+ / Centos7 + didukung. Beberapa template Centos mungkin mengalami kesulitan untuk menangani masalah kompilasi. Direkomendasikan bahwa ketika Anda mengalami masalah kompilasi, harap ubah ke template sistem lain
Pemilik grup hanya memberikan dukungan yang sangat terbatas, jika Anda memiliki pertanyaan, Anda dapat bertanya kepada teman grup
Setiap hari Minggu pukul 3 pagi, Nginx akan otomatis restart untuk berkoordinasi dengan penerbitan sertifikat. Selama periode ini node tidak bisa terkoneksi secara normal, dan perkiraan durasi beberapa detik hingga dua menit.
Perbarui log
Silakan periksa CHANGELOG.md untuk pembaruan

Terima kasih
Versi cabang lain dari skrip ini (Gunakan Host) alamat: https://github.com/dylanbai8/V2Ray_ws-tls_Website_onekey Silakan pilih sesuai dengan kebutuhan Anda Penulis mungkin telah menghentikan pemeliharaan
Proyek versi TLS MTProxy-go dalam skrip ini mengacu pada https://github.com/whunt1/onekeymakemtg, terima kasih whunt1
Dalam skrip ini, proyek asli skrip Rui Speed ​​4 in 1 dikutip https://www.94ish.me/1635.html Terima kasih di sini
Dalam skrip ini, proyek versi modifikasi skrip Ruispeed 4-in-1 dikutip dari https://github.com/ylx2016/Linux-NetSpeed, terima kasih ylx2016
sertifikat
Jika Anda sudah memiliki file sertifikat dari nama domain yang Anda gunakan, Anda dapat menamai file crt dan key sebagai v2ray.crt v2ray.key dan menempatkannya di direktori / data (jika direktori tidak ada, buat direktori terlebih dahulu). Harap perhatikan izin file sertifikat dan Masa berlaku sertifikat, mohon perbarui setelah masa berlaku sertifikat khusus berakhir

Skrip mendukung pembuatan otomatis sertifikat yang dienkripsi dengan masa berlaku 3 bulan. Secara teori, sertifikat yang dibuat secara otomatis mendukung pembaruan otomatis

Lihat konfigurasi klien
cat ~/v2ray_info.txt

Pengantar V2ray
V2Ray adalah alat proxy jaringan sumber terbuka luar biasa yang dapat membantu Anda menikmati internet dengan lancar. Saat ini, semua platform mendukung penggunaan Windows, Mac, Android, IOS, Linux, dan sistem operasi lain.
Script ini adalah script konfigurasi lengkap satu kunci. Setelah semua proses berjalan normal, Anda dapat langsung mengatur klien sesuai dengan hasil keluaran yang akan digunakan
Harap diperhatikan: Kami masih sangat menyarankan Anda untuk memiliki pemahaman penuh tentang alur kerja dan prinsip-prinsip dari keseluruhan program
Direkomendasikan bahwa satu server hanya membuat satu agen
Skrip ini menginstal versi terbaru inti V2ray secara default
Versi terbaru inti V2ray adalah 4.22.1 (Pada saat yang sama, harap perhatikan pembaruan sinkronisasi inti klien, Anda perlu memastikan bahwa versi inti klien> = versi inti server)
Direkomendasikan untuk menggunakan port default 443 sebagai port koneksi
Konten yang disamarkan bisa diganti sendiri.
Tindakan pencegahan
Direkomendasikan untuk menggunakan script ini di lingkungan yang murni.Jika Anda seorang pemula, jangan gunakan sistem Centos.
Harap jangan menerapkan program ini di lingkungan produksi hingga skrip ini benar-benar tersedia.
Program ini mengandalkan Nginx untuk mengimplementasikan fungsi terkait. Harap gunakan LNMP atau skrip Nginx serupa lainnya untuk menginstal Nginx. Pengguna yang telah menginstal Nginx harus memberikan perhatian khusus. Menggunakan skrip ini dapat menyebabkan kesalahan yang tidak dapat diprediksi (belum teruji, jika ada, versi berikutnya dapat menangani masalah ini) .
Beberapa fungsi V2Ray bergantung pada waktu sistem. Harap pastikan bahwa kesalahan waktu sistem UTC dari program V2RAY adalah dalam tiga menit, terlepas dari zona waktunya.
Bash ini mengandalkan skrip instalasi V2ray resmi dan acme.sh agar berfungsi.
Untuk pengguna sistem Centos, izinkan terlebih dahulu port yang relevan dari program di firewall (default: 80, 443)
Mulai metode
Mulai V2ray:systemctl start v2ray

Hentikan V2ray:systemctl stop v2ray

Mulai Nginx:systemctl start nginx

Hentikan Nginx:systemctl stop nginx

Katalog terkait
Direktori web:/home/wwwroot/3DCEList

Konfigurasi server V2ray:/etc/v2ray/config.json

Konfigurasi klien V2ray: ~/v2ray_info.inf

Direktori Nginx: /etc/nginx

File sertifikat: /data/v2ray.key 和 /data/v2ray.crtHarap perhatikan pengaturan otoritas sertifikat