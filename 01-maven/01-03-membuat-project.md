# Membuat Project

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

## Struktur Direktori ##

Setelah project dibuat, struktur direktorinya kira-kira seperti ini

```
my-app
|-- pom.xml
`-- src
    |-- main
    |   `-- java
    |       `-- com
    |           `-- mycompany
    |               `-- app
    |                   `-- App.java
    `-- test
        `-- java
            `-- com
                `-- mycompany
                    `-- app
                        `-- AppTest.java
```

## Compile dan eksekusi ##

Untuk meng-compile project yang selesai dibuat, bisa menggunakan perintah

```
mvn package
```

Dan untuk menjalankan main class, dalam contoh diatas packagenya `com.mycompany.app`, seperti ini

```
java -cp target/my-app-1.0-SNAPSHOT.jar com.mycompany.app.App
```

Untuk instruksi selengkapnya, silakan cek [disini](https://maven.apache.org/guides/getting-started/maven-in-five-minutes.html).

> PS : Silakan sesuaikan sendiri parameter-parameter diatas sesuai kebutuhan.
