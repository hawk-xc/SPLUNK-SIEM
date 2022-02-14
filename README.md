# SPLUNK-SIEM
saat kita bekerja pada SOC, kita akan memerlukan implementasi Splunk dalam Membangun Security Information and Event Management, disini saya akan memaparkan cara installasi pada server Debian 10 (Buster). 

### Prasyarat
- OS Linux Debian 10 (buster)
- root account + password

### installasi
pada tahap awal silakan teman-teman masuk ke mode super user (sudo), dengan perintah

```bash
sudo su
```

silakan masukkan password, jika sudah sekarang silakan ketikkan perintah update repository
```bash
apt-get update
```

tahap selanjutnya silakan teman-teman unduh package splunk pada website resminya.
- Masuk ke situs web Splunk untuk mengunduh paket Splunk versi terbaru.
- Klik logo `Free Splunk` di situs web mereka.
- Lengkapi formulir pendaftaran singkat untuk membuat akun.

setelah download selesai, silakan teman-teman masuk ke path download file splunk tadi, dan lakukan eksekusi dengan perintah

```bash
dpkg -i 
