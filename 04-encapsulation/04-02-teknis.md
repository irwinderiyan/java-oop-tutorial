# Teknik Enkapsulasi

Dalam mengimplementasikan prinsip enkapsulasi, lazimnya kita menggunakan access modifier `private` yang digunakan untuk melindungi atribut dan method di dalam class tersebut. Supaya method yang hanya bisa digunakan di class tersebut tidak bisa diakses dari class lain.

Ambil contoh class `Pegawai`. Class ini mempunyai method yang akan menghitung gaji total yang diperoleh oleh pegawai berdasarkan kondisi tertentu.

```java
public class Pegawai {

    // set atribut private
    private String nama;
    private String nik;
    private int lamaKerja;
    private double gajiPokok;

    // method accessor & mutator
    public void setNama(String nama) { this.nama = nama; }
    public void setNik(String nik) { this.nik = nik; }
    public void setLamaKerja(int lamaKerja) { this.lamaKerja = lamaKerja; }
    public void setGajiPokok(double gajiPokok) { this.gajiPokok = gajiPokok; }
    public String getNama() { return this.nama; }
    public String getNik() { return this.nik; }
    public int getLamaKerja() { return this.lamaKerja; }

    // method untuk menghitung gaji total.
    public double getGajiTotal() {
        return this.gajiPokok + getBonus();
    }

    // method yang dienkapsulasi untuk menghitung bonus
    // bonus berbeda tergantung lama kerja
    private double getBonus() {
        if (getLamaKerja() <= 2) {
            return this.gajiPokok * 10 / 100;
        } else if (getLamaKerja > 2 && getLamaKerja <= 5) {
            return this.gajiPokok * 20 / 100;
        } else {
            return this.gajiPokok * 30 / 100;
        }
    }

}
```

Untuk menghitung gaji total, maka kita cukup memanggil saja method `getGajiTotal()` tanpa kita tahu proses dibalik penghitungan bonus dan penghitungan gaji total itu sendiri. Nah, disitulah proses enkapsulasi bekerja dalam suatu kasus.

## Method Accessor & Mutator ##

Dalam kode diatas, method yang berfungsi sebagai mutator adalah `setNik()`, `setNama()`, `setLamaKerja()`, dan `setGajiPokok()`. Method mutator adalah method yang akan mengubah nilai dari private attribut (atribut yang dienkapsulasi). Sedangkan method accessor adalah method yang akan mengakses atribut dan method yang dienkapsulasi dan juga mengembalikannya. `getBonus()`, `getGajiTotal()`, `getNik()`, `getNama()`, `getLamaKerja()` adalah method accessor.

Method accessor biasa dipanggil sebagai getter method, sedangkan method mutator biasa dipanggil sebagai setter method.
