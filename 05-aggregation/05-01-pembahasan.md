# Pembahasan

Seperti yang kita tahu, obyek dapat memiliki obyek yang lain. Misalkan obyek Warga. Warga akan memiliki alamat yang dapat kita buat classnya. Asumsikan code yang dibuat seperti ini...

```java
public class Alamat {

    private String alamat;
    private int rt;
    private int rw;
    private String kelurahan;
    private String kecamatan;
    private String kota;
    private int kodePos;

    /*
    berisi getter dan setter dari masing-masing atribut....
    */

}

public class Warga {

    private String nama;
    private String jenisKelamin;
    private String kotaLahir;
    private int tahunLahir, bulanLahir, tanggalLahir;
    private Alamat alamat;

    /*
    berisi getter dan setter dari masing-masing atribut....
    */

}
```

Terlihat dalam kode diatas, pada class `Warga` memiliki atribut bertipe `Alamat`. Nah, relasi yang tepat menggambarkan kondisi diatas adalah, `Warga memiliki Alamat`. Relasi agregasi biasa disebut sebagai relasi `has a`.

Namun dalam contoh diatas, class `Alamat` tidak memiliki relasi dengan `Warga`. Dengan kata lain, `Warga` memiliki `Alamat`, dan `Alamat` bisa saja tidak memiliki `Warga`.
