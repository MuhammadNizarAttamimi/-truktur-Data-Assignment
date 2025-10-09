# <h1 align="center">Laporan Praktikum Modul Pengenalan Bahasa C++ (1)</h1>
<p align="center">Muhammad Nizar Attamimi</p>

## Dasar Teori

Berikan penjelasan teori terkait materi modul ini dengan bahasa anda sendiri serta susunan yang terstruktur per topiknya.

## Guided 

### 1. [Code Blocks Ide dan Pengenalan Bahasa C++]

```C++
#include <iostream>
using namespace std;

void tulis (int x){
    for (int i = 0; 1 < x; i++ ){
        cout << "Baris ke -: " << i+1 << endl;
    }
}

int main () {
    int jum;
    cout << "Jumlah baris kata: ";
    cin >> jum;
    tulis(jum);
    
    return 0;
}
```
Program ini berfungsi untuk menampilkan tulisan berulang sebanyak jumlah yang dimasukkan oleh pengguna.
## Unguided 

### 1. [Soal]

```C++
#include <iostream>
using namespace std;

int main() {
    float a, b;

    cout << "Masukkan dua bilangan float: ";
    cin >> a >> b;

    cout << "Hasil penjumlahan: " << a + b << endl;
    cout << "Hasil pengurangan: " << a - b << endl;
    cout << "Hasil perkalian: " << a * b << endl;

    if (b != 0)
        cout << "Hasil pembagian: " << a / b << endl;
    else
        cout << "Tidak bisa membagi dengan nol!" << endl;

    return 0;
}

```
#### Output:
<img width="1228" height="138" alt="Image" src="https://github.com/user-attachments/assets/b616e8ee-cb44-41e3-9272-cd40c3e947d2" />

Kode di atas digunakan untuk operasi aritmatika dua bilangan bertipe float. Jadi Pengguna  memasukkan dua angka , lalu menampilkan hasil penjumlahan, pengurangan, perkalian, dan pembagian dari kedua angka tersebut..

#### Full code Screenshot:
<img width="1598" height="698" alt="Image" src="https://github.com/user-attachments/assets/b188a1eb-a70d-48ea-a85e-efacf950444e" />

### 2. [Soal]

```C++
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Masukkan angka (0-100): ";
    cin >> n;

    string satuan[] = {"nol", "satu", "dua", "tiga", "empat", "lima", "enam",
                       "tujuh", "delapan", "sembilan", "sepuluh", "sebelas"};

    string hasil;

    if (n < 0 || n > 100) {
        hasil = "Angka di luar jangkauan";
    } else if (n < 12) {
        hasil = satuan[n];
    } else if (n < 20) {
        hasil = satuan[n - 10] + " belas";
    } else if (n < 100) {
        int puluh = n / 10;
        int sisa = n % 10;
        hasil = satuan[puluh] + " puluh";
        if (sisa != 0) hasil += " " + satuan[sisa];
    } else if (n == 100) {
        hasil = "seratus";
    }

    cout << n << " : " << hasil << endl;

    return 0;
}
```
#### Output:
<img width="1444" height="141" alt="Image" src="https://github.com/user-attachments/assets/28e65e77-bf81-4b26-8aad-bb2fee0732cb" />

Kode di atas digunakan untuk mengubah angka dari 0 sampai 100 menjadi bentuk tulisan dalam bahasa Indonesia.

#### Full code Screenshot:
<img width="1600" height="812" alt="Image" src="https://github.com/user-attachments/assets/f1d51f02-f3b5-4da8-80a1-3d3c851f90ea" />

### 3. [Soal]

```C++
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Input: ";
    cin >> n;
    cout << "Output:\n";

    for (int i = n; i >= 1; i--) {
    
        for (int s = 0; s < (n - i) * 2; s++)
            cout << " ";


        for (int j = i; j >= 1; j--)
            cout << j << " ";

        cout << "* ";

        for (int j = 1; j <= i; j++)
            cout << j << " ";

        cout << endl;
    }

    return 0;
}
```
#### Output:
<img width="1603" height="226" alt="Image" src="https://github.com/user-attachments/assets/e534e1aa-d89a-425b-ae55-cd4f5bbd12df" />

Kode di atas digunakan untuk mencetak teks "ini adalah file code guided praktikan" ke layar menggunakan function cout untuk mengeksekusi nya.

#### Full code Screenshot:
<img width="1598" height="665" alt="Image" src="https://github.com/user-attachments/assets/c1fe6454-eeec-41d5-b624-7f06bb70688b" />

## Kesimpulan
Ringkasan dan interpretasi pandangan kalia dari hasil praktikum dan pembelajaran yang didapat[1].

## Referensi
[1] I. Holm, Narrator, and J. Fullerton-Smith, Producer, How to Build a Human [DVD]. London: BBC; 2002.
