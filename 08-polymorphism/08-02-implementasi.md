# Implementasi Dasar dari Polimorfisme

Asumsikan terdapat sebuah class dengan nama `Car`, yang akan menjadi induk dari semua class turunannya, kita pakai kode yang telah ditulis di bab sebelumnya.

#### Movement.java ####

```java
public interface Movement {

    public void increaseOrDecreaseSpeed(int speed);
    public void setGear(int gear);

}
```

#### EnhancedMovement.java ####

```java
public interface EnhancedMovement extends Movement {

    public final int INCREASE_SPEED_WITH_NITRO = 70;

    public void activateNitro(boolean toggle);

}
```

#### Car.java ####

```java
public class Car implements Movement {

    private String brand;
    private String color;
    private int speed, gear;

    public void setBrand(String brand) { this.brand = brand; }
    public void setColor(String color) { this.color = color; }
    public String getBrand() { return this.brand; }
    public String getColor() { return this.color; }
    public int getSpeed() { return this.speed; }

    // jangan lupa untuk mengimplementasikan SEMUA method dari interface.
    public void increaseOrDecreaseSpeed(int speed) { this.speed += speed; }
    public void setGear(int gear) { this.gear = gear; }
}
```

#### SportCar.java ####

```java
public class SportCar extends Car implements EnhancedMovement {

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

    // jangan lupa untuk mengimplementasikan SEMUA method dari interface.
    public void activateNitro(boolean toggle) {
        if (!toggle) {
            // kata kunci super digunakan untuk mengakses properti dari superclass.
            super.increaseOrDecreaseSpeed(-1 * SportCar.INCREASE_SPEED_WITH_NITRO);
        } else {
            super.increaseOrDecreaseSpeed(SportCar.INCREASE_SPEED_WITH_NITRO);
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

Setelah kita merancang class diatas, kita akan membuat main classnya...

#### CarMain.java ####

```java
class CarMain {
    public static void main(String[] args) {

        Car sc = new SportCar(); // Polimorfisme
        sc.setBrand("BMW");
        sc.setColor("Black");
        ((SportCar)sc).initEquipmentCount(3);
        ((SportCar)sc).addEquipment("Nitrous System");
        ((SportCar)sc).addEquipment("High end audio system");
        ((SportCar)sc).addEquipment("Enhanced Radiators");
        sc.increaseOrDecreaseSpeed(40);
        System.out.println(sc.getSpeed());
        ((SportCar)sc).activateNitro(true);
        System.out.println(sc.getSpeed());

    }
}
```

Hasilnya akan [sama](http://ideone.com/FfagrR) seperti di pembahasan sebelumnya

```
40
110
```

Muncul pertanyaan, mengapa dibaris tertentu harus ada casting seperti `(SportCar)sc`?

Karena, obyek `sc`, yang sebenarnya adalah `SportCar` dianggap sebagai bentuk umum dari `SportCar`, yaitu `Car`. Obyek yang diinstansiasi dari class `Car` tidak memiliki method `initEquipmentCount()`, `addEquipment()`, dan `activateNitro()`. Untuk dapat mengakses `initEquipmentCount()`, `addEquipment()`, dan `activateNitro()` maka obyek yang bertipe `Car` tadi harus dicasting ke `SportCar`. Disitulah polimorfisme bekerja.
