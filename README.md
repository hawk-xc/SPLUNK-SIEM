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

![Screenshot from 2022-02-14 10-15-04](https://user-images.githubusercontent.com/92193431/153794253-63a18352-3db6-4933-a833-f51238aa4ce9.png)

silakan teman-teman melakukan download, baik melalui browser, ftp dan lainnya. setelah download selesai, silakan teman-teman masuk ke path download file splunk tadi, dan lakukan eksekusi dengan perintah

```bash
dpkg -i splunk-8.2.4-87e2dda940d1-linux-2.6-amd64.deb
```
```
Selecting previously unselected package splunk.
(Reading database ... 148753 files and directories currently installed.)
Preparing to unpack splunk-8.2.4-87e2dda940d1-linux-2.6-amd64.deb ...
Unpacking splunk (8.2.4) ...
Setting up splunk (8.2.4) ...
complete
```
setelah splunk berhasil terinstall sekarang kita akan buat splunk berjalan saat komputer booting alias `daemon` procces dengan perintah

```bash
/opt/splunk/bin/splunk enable boot-start
```

akan ada lisensi pada saat penginstallan, tekan enter sampai lisensi berakhir. input `y` untuk menyetujui lisensi dan ketentuan pengguna.

```
"Statement of Work" means the statements of work and/or any and all applicable
Orders, that describe the specific services to be performed by Splunk,
including any materials and deliverables to be delivered by Splunk.
Do you agree with this license? [y/n]: y
```

setelah itu inputkan username dan password yang akan temen-temen gunakan untuk login ke splunk dashboard.

```
Splunk software must create an administrator account during startup. Otherwise, you cannot log in.
Create credentials for the administrator account.
Characters do not appear on the screen when you type in credentials.

Please enter an administrator username: hawk

Please enter a new password: 
Please confirm new password: 
Copying '/opt/splunk/etc/openldap/ldap.conf.default' to '/opt/splunk/etc/openldap/ldap.conf'.
```

disini saya menginputkan username hawk dengan password, minimal password yang dapat diinputkan adalah 8 karakter, gunakan alphanumeric.

```
e is 65537 (0x10001)
writing RSA key

Generating RSA private key, 2048 bit long modulus
......................+++++
................................+++++
e is 65537 (0x10001)
writing RSA key

Moving '/opt/splunk/share/splunk/search_mrsparkle/modules.new' to '/opt/splunk/share/splunk/search_mrsparkle/modules'.
Init script installed at /etc/init.d/splunk.
Init script is configured to run at boot.
```

maka sekarang teman-teman telah sukses menjalankan splunk secara daemon process. sekarang silakan teman-teman aktifkan service splunk dengan perintah

```bash
systemctl start splunk
```

check status

```bash
systemctl status splunk
```
