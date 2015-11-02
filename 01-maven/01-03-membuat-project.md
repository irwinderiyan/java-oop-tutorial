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

Untuk instruksi selengkapnya, silakan cek [disini](https://maven.apache.org/guides/getting-started/maven-in-five-minutes.html).
