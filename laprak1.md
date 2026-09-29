# <h1 align="center">Laporan Praktikum Modul 1 - Codeblocks IDE & Pengenalan Bahas C++ (Bagian Pertama)</h1>
<p align="center">Ignatius Steven Manurung - 109082500089</p>

## Dasar Teori
Pemrograman C++ berakar pada pemrosesan input dan output menggunakan pustaka <iostream> melalui fungsi cin dan cout. Dalam mengolah data numerik, pemilihan tipe data seperti float digunakan untuk menjaga presisi bilangan desimal pada operasi aritmatika dasar, sedangkan int digunakan untuk bilangan bulat. Evaluasi logika melalui struktur kontrol percabangan (if-else) diterapkan untuk mengambil keputusan dalam program, sekaligus memvalidasi batas input dan mencegah kesalahan runtime (seperti pembagian dengan angka nol).

Untuk pemrosesan logika yang lebih kompleks, percabangan multi-kondisi dikombinasikan dengan struktur data array yang berfungsi sebagai lookup table (tabel acuan). Manipulasi nilai numerik memanfaatkan operator pembagian bulat (/) untuk mengekstrak digit utama (seperti puluhan) dan operator modulo (%) untuk mendapatkan sisa hasil bagi (seperti satuan).

Sementara itu, pembentukan pola visual pada layar memanfaatkan konsep perulangan bersarang (nested loop). Perulangan terluar (outer loop) bertugas mengendalikan alur perpindahan baris secara vertikal, sedangkan perulangan di dalamnya (inner loop) mengatur pencetakan karakter (spasi, angka, atau simbol) secara horizontal. Kombinasi iterasi menaik (++) dan menurun (--) memungkinkan program membangun tata letak yang simetris dan teratur.

## Unguided 

### 1. Program menerima input dua buah bilangan bertipe float, kemudian memberikan output hasil penjumlahan, pengurangan, perkalian dan pembagian dari dua bilangan tersebut.

```C++
#include <iostream>
using namespace std;

int main() {
    float a, b;
    cout << "Masukkan bilangan pertama: ";
    cin >> a;
    cout << "Masukkan bilangan kedua: ";
    cin >> b;

    cout << "Hasil Penjumlahan: " << a + b << endl;
    cout << "Hasil Pengurangan: " << a - b << endl;
    cout << "Hasil Perkalian: " << a * b << endl;
    
    if (b != 0) {
        cout << "Hasil Pembagian: " << a / b << endl;
    } else {
        cout << "Hasil Pembagian: Tidak terdefinisi (pembagi nol)" << endl;
    }

    return 0;
}
```
### Output Unguided 1 :

##### Output 1
![Screenshot Output Unguided 1_1](https://github.com/ignatiussteven/Laprak-1/blob/main/Screenshot%20(346).png)

Program ini menerima dua input bilangan float, lalu menghitung dan menampilkan hasil penjumlahan, pengurangan, perkalian, serta pembagian dengan menyertakan validasi kondisi untuk mencegah kesalahan pembagian dengan angka nol.

### 2. Program menerima masukan angka dan pengeluaran output nilai angka tersebut dalam bentuk tulisan (bilangan bulat positif 0 s.d 100)

```C++
#include <iostream>
#include <string>
using namespace std;

int main() {
    int angka;
    cout << "Masukkan angka (0 s.d 100): ";
    cin >> angka;

    if (angka < 0 || angka > 100) {
        cout << "Input di luar jangkauan (harus 0 - 100)." << endl;
        return 0;
    }

    string satuan[] = {"nol", "satu", "dua", "tiga", "empat", "lima", "enam", "tujuh", "delapan", "sembilan", "sepuluh", "sebelas"};

    cout << angka << " : ";
    
    if (angka <= 11) {
        cout << satuan[angka] << endl;
    } else if (angka < 20) {
        cout << satuan[angka - 10] << " belas" << endl;
    } else if (angka < 100) {
        int puluhan = angka / 10;
        int sisa = angka % 10;
        cout << satuan[puluhan] << " puluh";
        if (sisa != 0) {
            cout << " " << satuan[sisa];
        }
        cout << endl;
    } else if (angka == 100) {
        cout << "seratus" << endl;
    }

    return 0;
}
```
### Output Unguided 2 :

##### Output 1
![Screenshot Output Unguided 2_1](https://github.com/ignatiussteven/Laprak-1/blob/main/Screenshot%20(347).png)

Program ini mengonversi angka bulat rentang 0 hingga 100 menjadi ejaan teks bahasa Indonesia dengan memanfaatkan array sebagai tabel acuan kata serta operasi pembagian dan modulo untuk memisahkan digit puluhan dan satuan.

### 3. Program dapat memberikan input dan output pola mirror
```C++
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "input: ";
    cin >> n;
    cout << "output:" << endl;

    for (int i = n; i >= 0; i--) {
        for (int s = 0; s < n - i; s++) {
            cout << "  "; 
        }
        
        for (int j = i; j >= 1; j--) {
            cout << j << " ";
        }
        
        cout << "*";
        
        for (int j = 1; j <= i; j++) {
            cout << " " << j;
        }
        
        cout << endl;
    }

    return 0;
}
```
### Output Unguided 3 :

##### Output 1
![Screenshot Output Unguided 3_1](https://github.com/ignatiussteven/Laprak-1/blob/main/Screenshot%20(348).png)

Program ini memanfaatkan perulangan bersarang (nested loop) untuk mengatur pencetakan spasi, deret angka menurun di kiri, karakter bintang di tengah, dan deret angka menaik di kanan guna membentuk pola segitiga terbalik yang simetris.

## Kesimpulan
Secara keseluruhan, ketiga soal latihan ini menyajikan fondasi penting dalam pemrograman C++ yang dirancang untuk mengasah kemampuan pemecahan masalah secara bertahap dan terstruktur. Melalui soal pertama, kita dilatih memahami penggunaan tipe data float dan alur input-output, sekaligus menerapkan penanganan kondisi (defensive programming) guna mencegah terjadinya kesalahan runtime akibat pembagian dengan angka nol. Pada soal kedua, pemahaman ditingkatkan dengan mengombinasikan percabangan bertingkat, manipulasi matematika menggunakan operator pembagian bulat dan modulo, serta pemanfaatan struktur array sebagai tabel acuan untuk mengubah nilai numerik menjadi teks. Sementara pada soal ketiga, logika berpikir abstrak diuji secara mendalam melalui penggunaan perulangan bersarang (nested loop) untuk mengatur alur pencetakan spasi, simbol, dan deret angka hingga menghasilkan pola visual yang simetris.   Dengan menguasai seluruh konsep ini, Kita tidak hanya memahami sintaks dasar dari bahasa C++, tetapi juga telah membangun pola pikir logis yang sistematis sebagai modal utama dalam merancang serta memecahkan masalah pemrograman yang lebih kompleks.

## Referensi
Deitel, P., & Deitel, H. (2017). C++ How to Program (10th ed.). Boston: Pearson Education. (Membahas konsep iostream, kontrol alur if-else, array, dan perulangan bersarang).

Stroustrup, B. (2014). Programming: Principles and Practice Using C++ (2nd ed.). Upper Saddle River: Addison-Wesley. (Buku acuan resmi dari pencipta bahasa pemrograman C++).

Prata, S. (2011). C++ Primer Plus (6th ed.). Indianapolis: Addison-Wesley Professional. (Membahas logika manipulasi angka, operator modulo, dan pembentukan pola loop).
