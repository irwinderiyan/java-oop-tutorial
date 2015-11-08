# Implementasi Interface

Sebenarnya, interface itu hampir mirip dengan class. Namun berbeda.

Interface hanya berisi kerangka method yang siap diimplementasikan di class yang meng-implement interface tersebut. Di dalam interface tidak ada statement sama sekali. Method seperti ini dinamakan abstract method.

Untuk membuat interface caranya cukup mudah, buat saja file `.java`, contoh...

#### Movement.java ####

```java
public interface Movement {

    public void increaseOrDecreaseSpeed(int speed);
    public void setGear(int gear);

}
```

...yang nantinya `Movement` akan diimplement oleh class `Car`...

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

...jika kita meng-implement suatu interface, namun kita lupa untuk mengimplementasikan semua method dari interface tadi, maka akan menimbulkan error.

Interface memungkinkan kita untuk meng-extends lebih dari satu interface lain.

```java
// Interface1, Interface2, Interface3, ... dst.
public interface MyInterface extends Interface1, Interface2, Interface3 {

    // abstract method atau field final yang lain...

}
```

Contoh, membuat interface `EnhancedMovement` yang meng-extends interface `Movement`...

#### EnhancedMovement.java ####

```java
public interface EnhancedMovement extends Movement {

    public final int INCREASE_SPEED_WITH_NITRO = 70;

    public void activateNitro(boolean toggle);

}
```

...yang nantinya akan di-implement oleh class `SportCar`...

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

Jika dijalankan memakai main class...

#### CarMain.java ####

```java
class CarMain {
    public static void main(String[] args) {

        SportCar sc = new SportCar();
        sc.setBrand("BMW");
        sc.setColor("Black");
        sc.initEquipmentCount(3);
        sc.addEquipment("Nitrous System");
        sc.addEquipment("High end audio system");
        sc.addEquipment("Enhanced Radiators");
        sc.increaseOrDecreaseSpeed(40);
        System.out.println(sc.getSpeed());
        sc.activateNitro(true);
        System.out.println(sc.getSpeed());

    }
}
```

...akan menghasilkan [output](http://ideone.com/ZD7icd)

```
40
110
```
