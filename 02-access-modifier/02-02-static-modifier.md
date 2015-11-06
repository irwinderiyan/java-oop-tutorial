# Static Modifier

`static` modifier biasanya digunakan untuk mendefinisikan atribut/method yang dimiliki oleh class, bukan milik instance (objek) dari suatu class. Jadi semua obyek yang dibuat dari class tersebut akan memiliki atribut dengan nilai yang sama.

Ambil contoh potongan kode berikut

```java
class TestStatic {

    // atribut static
    private static int x = 4;

    // mengembalikan nilai dari x
    public int getX () { return x; }

}

public class TestStaticMain {
    public static void main(String[] args) {

        // instansiasi obyek
        TestStatic t = new TestStatic();
        TestStatic y = new TestStatic();

        // cetak nilai dari getX()
        System.out.println(t.getX());
        System.out.println(y.getX());

    }
}
```

Akan menghasilkan output, bisa dilihat [disini](http://ideone.com/JDJbeX)

```
4
4
```

Jadi kesimpulannya, atribut static akan dimiliki oleh semua obyek yang diinstansiasi dari class tersebut dengan nilai yang sama.

Itu tadi atribut, sekarang bagaimana kita memanggil method static? Dengan cara...

```
NamaClass.namaMethod();
```

Contoh code

```java
public class Hitung {

    // method hitung pangkat pow(x,y)
    public static int pangkat(int x, int y) {
        if (y == 1) return x;
        else return x * pangkat(x, --y);
    }

    // method-method lainnya

}

public class HitungMain {
    public static void main(String[] args) {

        // cetak nilai 2 pangkat 4
        System.out.println(Hitung.pangkat(2,4));

    }
}
```

Akan menghasilkan output, bisa dilihat [disini](http://ideone.com/FLxEzW)

```
16
```

**PERLU DIINGAT!** Atribut/method non `static` tidak bisa dipanggil dari `static`. 
