# Mengimplementasikan Konsep Inheritance

Untuk mewariskan class, maka kita akan menggunakan keyword `extends`. Contoh dibawah adalah bagaimana kita membuat class `SportCar` yang merupakan turunan dari class `Car`. `SportCar` akan memiliki atribut tambahan berupa array yang akan memuat daftar equipment yang dipasang didalamnya.

#### Car.java ####

```java
public class Car {

    private String brand;
    private String color;

    public void setBrand(String brand) { this.brand = brand; }
    public void setColor(String color) { this.color = color; }
    public String getBrand() { return this.brand; }
    public String getColor() { return this.color; }

}
```

#### SportCar.java ####

```java
public class SportCar extends Car {

    private String[] equipmentList;
    private int lastIndex = -1;

    public void initEquipmentCount(int x) {
        equipmentList = new String[x];
    }

    public void addEquipment(String equipment) {
        // jika equipmentList penuh, maka tidak akan menambahkan equipment
        if (lastIndex == equipmentList.length - 1) {
            return;
        }

        // menambahkan equipment ke array equipmentList
        equipmentList[++lastIndex] = equipment;
    }

    public void listEquipment() {
        for (int i = 0 ; i < lastIndex ; i++) {
            System.out.println(equipmentList[i]);
        }
    }

    public String toString() {
        return String.format(
            "Brand : %s\nColor : %s\nEquipment List : %s",
            super.getBrand(), super.getColor(), java.util.Arrays.toString(equipmentList)
        );
    }

}
```

Untuk menerapkannya, maka kita akan membuat main class...

#### CarMain.java ####

```java
public class CarMain {
    public static void main(String[] args) {

        SportCar sc = new SportCar();
        sc.setBrand("BMW");
        sc.setColor("Black");
        sc.initEquipmentCount(3);
        sc.addEquipment("Nitrous System");
        sc.addEquipment("High end audio system");
        sc.addEquipment("Enhanced Radiators");
        System.out.println(sc);

    }
}
```

Terlihat di class `CarMain`, `sc` memanggil method `setBrand()` dan `setColor()` yang tidak dituliskan langsung di class `SportCar`, disitulah konsep inheritance bekerja. Bahwa class `SportCar` mewarisi segala `public` atau `protected` method/atribut dari class `Car`.

Dan jika dijalankan, maka akan menghasilkan [output](http://ideone.com/KHy1YR)

```
Brand : BMW
Color : Black
Equipment List : [Nitrous System, High end audio system, Enhanced Radiators]
```

Mudah, bukan? Persis seperti pewarisan sifat orang tua kepada anaknya.
