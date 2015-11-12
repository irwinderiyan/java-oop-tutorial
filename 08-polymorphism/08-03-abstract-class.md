# Penggunaan Abstract Class

Seperti yang kita tahu, abstract class adalah class yang abstrak, alias class tersebut tidak dapat diinstansiasi sebagai obyek. Pada teknik polimorfisme, abstract class sering dipakai untuk melakukan teknik ini. Dalam pembuatan classnya akan melibatkan keyword `abstract`.

Kita beri contoh yang mudah dulu saja, anggap aja ada class `Hewan`...

```java
public abstract class Hewan {
    public abstract int getJumlahKaki();
}
```

...yang akan diextends oleh class `Sapi`, `Ayam`, dan `Ular`

```java
public class Sapi extends Hewan {
    public int getJumlahKaki() {
        return 4;
    }
}

public class Ayam extends Hewan {
    public int getJumlahKaki() {
        return 2;
    }
}

public class Ular extends Hewan {
    public int getJumlahKaki() {
        return 0;
    }
}
```

**PERLU DIINGAT** Ketika kita meng-extends abstract class, maka subclass harus meng-override method-method abstraknya.

Sekarang, kita buat main classnya

```java
public class HewanMain {
    public static void main(String[] args) {
        Hewan[] arrayHewan = {new Sapi(), new Ayam(), new Ular()};
        for (Hewan hewan : arrayHewan) {
            System.out.println(hewan.getJumlahKaki());
        }
    }
}
```

Jika di run, akan menghasilkan [output](http://ideone.com/ronqQj)

```
4
2
0
```

Terlihat di class `HewanMain`, sapi, ayam dan ular akan dianggap sebagai hewan pada umumnya. Jika kita menginstansiasi obyek dari `Hewan`, apa yang terjadi?

```java
public class HewanMain {
    public static void main(String[] args) {
        Hewan hewan = new Hewan();
    }
}
```

Akan menghasilkan [output](http://ideone.com/8WwHUO)

```
Main.java:25: error: Hewan is abstract; cannot be instantiated
        Hewan hewan = new Hewan();
                      ^
```
