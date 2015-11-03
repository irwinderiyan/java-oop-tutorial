# Class

Setelah kita mengetahui OOP itu nanti seperti apa, satu hal yang memegang kunci penting dalam OOP adalah penggunaan class. Class adalah blueprint/cetakan dari suatu obyek. Jadi sebelum objek diinstansiasi, maka yang dibutuhkan ialah membuat class yang sesuai dengan karakteristik objek tersebut agar bisa diinstansiasi.

Ambil contoh obyek Mobil pada contoh di perkenalan OOP sebelumnya. Mobil pasti memiliki merek, nomor polisi, warna dan mobil pastinya bisa bergerak maju, mundur, belok. Jika kita tulis dalam bentuk `class`, kira-kira akan seperti ini

```java
public class Mobil {

    public String merek;
    public String noPol;
    public String warna;

    public void maju() {
        // instruksi
    }

    public void mundur() {
        // instruksi
    }

    public void belok() {
        // instruksi
    }

}
```

Setelah kita membuat classnya, baru kita bisa menginstansiasinya, contoh

```java
Mobil sedan = new Mobil(); // instansiasi obyek sedan
```

Bingung dengan penulisan class? Mari kita jabarkan kode diatas.

Bagian...

```java
public String merek;
public String noPol;
public String warna;
```

...adalah bagian atribut dari obyek. Obyek itu punya apa saja? Di tulis seperti itu dan sesuaikan dengan tipe data yang sesuai.

Sedangkan bagian...

```java
public void maju() {
    // instruksi
}

public void mundur() {
    // instruksi
}

public void belok() {
    // instruksi
}
```

...adalah bagian aksi dari obyek. Obyek tersebut bisa melakukan apa saja? Maka dari itu kita perlu method supaya obyek dapat melakukan aksi yang diinginkan. Method-method ini biasa disebut sebagai **instance method**.

Bingung cara membuat class? Silakan belajar kembali materi-materi Pemrograman Dasar, karena membuat file class baru sudah diajarkan di Progdas.

## Constructor ##

Constructor adalah method khusus yang digunakan untuk menginisialisasi nilai dari atribut-atribut dalam class. Ciri khususnya adalah menggunakan nama yang sama seperti nama classnya (untuk Java). Penulisan constructor sama seperti method pada umumnya, dan tanpa tipe return value.

Dari class Mobil diatas bisa ditambahkan constructor seperti ini

```java
public class Mobil {

    public String merek;
    public String noPol;
    public String warna;

    // blok constructor
    public Mobil(String merek, String noPol, String warna) {
        this.merek = merek;
        this.noPol = noPol;
        this.warna = warna;

        /* kata kunci this digunakan untuk memanggil
           atribut/method dalam class tersebut */
    }

    public void maju() {
        // instruksi
    }

    public void mundur() {
        // instruksi
    }

    public void belok() {
        // instruksi
    }

}
```

Cara instansiasinya seperti ini

```java
Mobil sedan = new Mobil("Mercedes-Benz", "N 1901 LX", "Hitam");
```

Ketika instansiasi akan selalu memanggil constructor dari class tersebut. Jika tidak ada constructor dalam class tersebut, maka akan memanggil constructor default yang akan menginisialisasikan nilai default dari atribut. (0 untuk numerik, `null` untuk obyek).

Kita juga bisa membuat overloaded constructor yang aturan overloadingnya sama seperti overloading method.
