Backup config squid lama:

```
cp -Rf /etc/squid /etc/squid-jadul
```

Remove Package:
```
apt-get purge lusca lusca-common lusca-cgi
apt-get purge squid squid-common squid-cgi
```
Atau jika pc sudah pernah terinstall squid/lusca dari sources
```
rm -rf /etc/squid
rm -f /usr/sbin/squid
```
Download Package Debian:
```
cd /tmp
```
32bit:

```
wget https://shufiardhabilly.googlecode.com/files/deb-htproxy_14942_i386.tar.bz2
```

64bit:
```
wget https://shufiardhabilly.googlecode.com/files/deb-htproxy_14942_x86-64.tar.bz2
```
Install Packetnya:
```
tar xvf deb-htproxy_14942_i386.tar.bz2 && dpkg -i *.deb
tar xvf deb-htproxy_14942_x86-64.tar.bz2 && dpkg -i *.deb
```

Stop Squidnya:
```
/etc/init.d/squid stop
```

Edit squid.conf
Sesuaikan cache\_dir & cache\_mem

```
# install package dependencies "apt-get install libfile-readbackwards-perl"
```

Buat cache swap:
```
chown proxy:proxy /cache*
chmod 777 /cache*
squid -z
```
Jalankan squid:
```
/etc/init.d/squid start
```
Cek apakah squid sudah jalan:
```
netstat -pln
```
Cek service apakah sudah jalan:
```
netstat -pln | grep squid
```