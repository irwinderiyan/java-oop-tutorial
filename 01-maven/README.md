# Bab 2, Pengenalan Apache Maven

## Maven? Apa itu? ##

Berdasarkan penjelasan dari [websitenya](https://maven.apache.org/) Maven,

> Apache Maven is a software project management and comprehension tool. Based on the concept of a project object model (POM), Maven can manage a project's build, reporting and documentation from a central piece of information.

Jadi Apache Maven (atau selanjutnya bisa disebut sebagai Maven) adalah software untuk memanajemen project, membuat report dan dokumentasi dari project yang kita buat nantinya.

Mengapa harus menggunakan Maven? Dalam OOP, kita akan melakukan coding dengan banyak class. Otomatis source file yang akan kita buat akan bertambah banyak kan? Untuk mengakomodasi itu, maka diperlukan tool seperti Maven dan sebangsanya untuk mengelola project yang akan dibuat. Dan biasanya dalam OOP akan melibatkan `package` untuk mengelompokkan source code yang kita buat agar lebih tertata. Dan tanpa build tools tersebut, akan sulit untuk mengelompokkan source code tersebut ke dalam `package`.

Bagi yang telah menggunakan IDE (Netbeans, Eclipse, atau IntelliJ IDEA) boleh melewati bagian ini. Bagi yang menggunakan text editor, silakan melanjutkan.

## Instalasi ##

#### Untuk UNIX-based OS (Linux, Solaris, Mac OS X) ####

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

## Membuat Project ##

Untuk membuat project, silakan menggunakan perintah...

```
mvn archetype:generate -DgroupId=com.mycompany.app -DartifactId=my-app -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false
```

`groupId` isikan dengan package namenya, contoh diatas `com.mycompany.app`
`artifactId` isikan dengan nama projectnya, contoh diatas `my-app`

Jadi silakan disesuaikan sendiri. Atau bisa menggunakan interactive mode.

```
mvn archetype:generate
```

Untuk eksekusi pertama kali, memang sedikit lama karena Maven akan mendownload dependency yang dibutuhkan. Untuk selanjutnya tidak akan lama karena tersimpan dalam cache.

Untuk instruksi selengkapnya, silakan cek [disini](https://maven.apache.org/guides/getting-started/maven-in-five-minutes.html).
