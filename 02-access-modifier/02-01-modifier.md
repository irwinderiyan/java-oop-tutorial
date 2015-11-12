# Access Modifier

Access modifier adalah penentu akses suatu atribut atau method dari suatu class. Dalam Java, kita akan mengenal 4 access modifier, diantaranya :

```
+-----------------------------------------------------------+
|            |        Visibility / Scope                    |
|  Modifier  |----------------------------------------------|
|            |  class   | package  |   subclass  |   world  |
|-----------------------------------------------------------|
| private        v                                          |
| <default>      v          v                               |
| protected      v          v              v                |
| public         v          v              v           v    |
+-----------------------------------------------------------+
```

Bingung?

Begini. Segala atribut/method yang diberi modifier `private` hanya bisa diakses dari class yang mempunyai atribut/method itu sendiri. Tidak bisa diakses dari mana saja. Sedangkan `<default>` atau di Java tidak ditulis access modifiernya, segala sesuatunya bisa diakses dari class itu sendiri dan class lain di `package` yang sama. Modifier `protected` lebih luas lagi. Ia sama seperti `<default>` hanya saja bisa diakses dari class yang lain di package yang berbeda, namun harus merupakan subclass dari class yang mempunyai atribut/method `protected`. Sedangkan `public` bisa diakses dari mana saja.

Masih bingung? Dibawah ini ada visualisasi yang menggambarkan hal tersebut

![class-access](https://docs.oracle.com/javase/tutorial/figures/java/classes-access.gif)

Gambar diambil dari [sini](https://docs.oracle.com/javase/tutorial/java/javaOO/accesscontrol.html)

Asumsikan apakah atribut dari Alpha bisa terlihat dari class mana saja berdasarkan modifiernya

```
+-----------------------------------------------------------+
|            |        Visibility / Scope                    |
|  Modifier  |----------------------------------------------|
|            |  alpha   |  beta   |   alphaSub  |   gamma   |
|-----------------------------------------------------------|
| private        v                                          |
| <default>      v          v                               |
| protected      v          v              v                |
| public         v          v              v           v    |
+-----------------------------------------------------------+
```
