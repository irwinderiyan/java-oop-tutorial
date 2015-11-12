# Instalasi

## Untuk UNIX-based OS (Linux, Solaris, Mac OS X) ##

Pastikan file binary `java` dikenali oleh shell. Cara mengetesnya dengan mengetikkan perintah `which java`. Jika dikenali, lanjut ketahap selanjutnya. Jika tidak, silakan kenalkan path JDK yang telah terinstall kepada `$PATH`, atau membuat symbolic link ke `/usr/bin`. Cara tersebut lazim saya gunakan untuk menginstall JDK di Linux, biasanya saya letakkan di `/opt`.

Download [disini](https://maven.apache.org/download.cgi), lalu pilih dengan format `.zip` atau `.tar.gz`. Bebas.

Setelah didownload, maka harus dilakukan pengekstrakan, biasanya saya letakkan hasil ekstrakan ke `/opt`. Contoh nama file nya `apache-maven-3.3.3-bin.zip`

Untuk format `.zip`

```
sudo unzip apache-maven-3.3.3-bin.zip -d /opt
```

Untuk format `.tar.gz`

```
sudo tar xvzf apache-maven-3.3.3-bin.tar.gz -C /opt
```

Silakan sesuaikan nama filenya dengan file yang telah didownload. Lalu kenalkan path Mavennya ke `$PATH` atau binary `mvn` nya dibuatkan symbolic link ke `/usr/bin`

## Untuk Windows ##

Silakan lihat [disini](https://maven.apache.org/install.html).
