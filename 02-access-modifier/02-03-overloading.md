# Overloading Method

Overloading method adalah beberapa method yang memiliki nama method yang sama, namun parameternya berbeda. Overloading method terdiri dari 3 jenis, diantaranya :

* Jumlah parameter berbeda
* Tipe data parameter berbeda
* Urutan tipe data parameter berbeda

Bingung membayangkannya? Kalau bingung, berikut ini contoh potongan kode yang menerapkan overloading

#### Kode 1 ####

```java
import static java.lang.System.out;

// overloading dengan jumlah parameter yang berbeda
class Overloading {

    public void testingOvl(int a, int b, int c) {
        out.println("Memiliki 3 parameter");
    }

    public void testingOvl(int a, int b) {
        out.println("Memiliki 2 parameter");
    }

}

class OverloadingMain {
    public static void main(String[] args) {

        // instansiasi
        Overloading ovlTest = new Overloading();

        // pemanggilan instance method
        ovlTest.testingOvl(1,2,1);
        ovlTest.testingOvl(1,1);

    }
}
```

Kode 1 akan menghasilkan output

```
Memiliki 3 parameter
Memiliki 2 parameter
```

#### Kode 2 ####

```java
import static java.lang.System.out;

// overloading yang berbeda tipe data parameternya
class Overloading {

    public void testingOvl(int x) {
        out.println("Ini dipanggil dengan parameter integer");
    }

    public void testingOvl(String x) {
        out.println("Ini dipanggil dengan parameter string");
    }

    public void testingOvl(float f) {
        out.println("Ini dipanggil dengan parameter float");
    }

}

class OverloadingMain {
    public static void main(String[] args) {

        // instansiasi
        Overloading ovlTest = new Overloading();

        // pemanggilan instance method
        ovlTest.testingOvl(1);
        ovlTest.testingOvl("1101");
        ovlTest.testingOvl(1.01f);


    }
}
```

Kode 2 akan menghasilkan output

```
Ini dipanggil dengan parameter integer
Ini dipanggil dengan parameter string
Ini dipanggil dengan parameter float
```

#### Kode 3 ####

```java
import static java.lang.System.out;

// overloading yang berbeda urutan tipe datanya
class Overloading {

    public void testingOvl(int a, char b, float f) {
        out.println("Memiliki 3 parameter, urutan int char float");
    }

    public void testingOvl(int a, float f, char b) {
        out.println("Memiliki 3 parameter, urutan int float char");
    }

}

class OverloadingMain {
    public static void main(String[] args) {

        // instansiasi
        Overloading ovlTest = new Overloading();

        // pemanggilan instance method
        ovlTest.testingOvl(1,'2',1.0f);
        ovlTest.testingOvl(1,1.0f,'1');

    }
}
```

Kode 3 akan menghasilkan output

```
Memiliki 3 parameter, urutan int char float
Memiliki 3 parameter, urutan int float char
```

## Kasus ##

#### Kasus 1 ####

```java
public int ovlTest(int a, int b, float x)
public int ovlTest(int ax, int bx, float gx)
```

Apakah ini valid?

**Tidak**, karena urutan tipe data argumennya sama. `(int, int, float)`.

#### Kasus 2 ####

```java
int ovlTest(int a, int b)
int ovlTest(float a, float b)
```

Apakah ini valid?

**Ya**, karena tipe data argumennya berbeda.

#### Kasus 3 ####

```java
float ovlTest(int x, int y)
char ovlTest(int x, int y)
```

Apakah ini valid?

**Tidak**, karena meskipun return valuenya berbeda, namun urutan tipe datanya sama.

#### Kasus 4 ####

```java
float ovlTest(int x, int y)
float ovlTest()
```

Apakah ini valid?

**Ya**, karena jumlah parameternya berbeda.
