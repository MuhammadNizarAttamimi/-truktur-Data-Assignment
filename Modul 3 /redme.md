# <h1 align="center">Laporan Praktikum Modul Abstract Data Type (ADT)</h1>
<p align="center">Muhammad Nizar Attamimi</p>

## Dasar Teori
ADT adalah TYPE dan sekumpulan PRIMITIF (operasi dasar) terhadap TYPE tersebut. Selain itu, dalam
sebuah ADT yang lengkap, disertakan pula definisi invarian dari TYPE dan aksioma yang berlaku. ADT
merupakan definisi STATIK.

## Guided 

### 1. [Abstract Data Type (ADT)]

```C++
#include <iostream>
using namespace std;

struct mahasiswa{ 
char nim[10]; 
int nilai1,nilai2;
};
void inputMhs(mahasiswa &m); 
float rata2(mahasiswa m);

int main() 
{ 
mahasiswa mhs; 
inputMhs(mhs); 
cout << “rata-rata = “ << rata2(mhs); 
return 0; 
}


void inputMhs(mahasiswa &m){ 
cout << “input nama = “; 
cin >> m.nim; 
cout << “input nilai = “; 
cin >> m.nilai1; 
cout << “input nilai2 = “;
cin >> m.nilai2; 
} 
float rata2(mahasiswa m){ 
return float(m.nilai1+m.nilai2)/2; 
}

mahasiswa.h
#ifndef MAHASISWA_H_INCLUDED 
#define MAHASISWA_H_INCLUDED 
struct mahasiswa{ 
char nim[10]; 
int nilai1, nilai2; 
};
void inputMhs(mahasiswa &m); 
float rata2(mahasiswa m); 
#endif // MAHASISWA_H_INCLUDED

mahasiswa.cpp
#include “mahasiswa.h” 
void inputMhs(mahasiswa &m){ 
cout << “input nama = “; 
cin >> (m).nim; 
cout << “input nilai = “; 
cin >> (m).nilai1; 
cout << “input nilai2 = “; 
cin >> (m).nilai2;
} 
 
float rata2(mahasiswa m){ 
  return float(m.nilai1+m.nilai2)/2; 
}
}
```
Program ini bertujuan untuk.
## Unguided 

### 1. [Soal]

```C++
#include <iostream>
using namespace std;

struct Mahasiswa {
    string nama;
    string nim;
    float nilaiUTS;
    float nilaiUAS;
    float nilaiTugas;
    float totalNilai;
};

float hitungTotalNilai(float uts, float uas, float tugas) {
    return (0.3 * uts) + (0.4 * uas) + (0.3 * tugas);
}

int main() {
    Mahasiswa data[10];
    int jumlah;

    cout << "Masukkan banyaknya mahasiswa (maksimal 10): ";
    cin >> jumlah;

    for (int i = 0; i < jumlah; i++) {
        cout << "\nMahasiswa ke-" << i + 1 << endl;
        cin.ignore();
        cout << "Nama Mahasiswa : ";
        getline(cin, data[i].nama);
        cout << "NIM            : ";
        cin >> data[i].nim;
        cout << "Nilai UTS      : ";
        cin >> data[i].nilaiUTS;
        cout << "Nilai UAS      : ";
        cin >> data[i].nilaiUAS;
        cout << "Nilai Tugas    : ";
        cin >> data[i].nilaiTugas;

        data[i].totalNilai = hitungTotalNilai(data[i].nilaiUTS, data[i].nilaiUAS, data[i].nilaiTugas);
    }

    cout << "\n=== Rekapitulasi Nilai Mahasiswa ===" << endl;
    for (int i = 0; i < jumlah; i++) {
        cout << "\nNama         : " << data[i].nama;
        cout << "\nNIM          : " << data[i].nim;
        cout << "\nNilai Akhir  : " << data[i].totalNilai << endl;
    }

    return 0;
}


```
#### Output:
<img width="1602" height="532" alt="Image" src="https://github.com/user-attachments/assets/632047c0-8310-4d15-a6f9-912066442e2b" />

code ini digunakan untuk.

#### Full code Screenshot:
<img width="1653" height="924" alt="image" src="https://github.com/user-attachments/assets/2636ef21-1bc6-4bbb-b92e-1a91edd9fad4" />


### 2. [Soal]
**(Pelajaran.h)**
```C++
#ifndef MATAKULIAH_H
#define MATAKULIAH_H

#include <string>
using namespace std;

struct MataKuliah {
    string nama;
    string kode;
};

MataKuliah buatMataKuliah(string namaMatkul, string kodeMatkul);

void tampilkanMataKuliah(MataKuliah mk);

#endif
```

**(Pelajaran.cpp)**
```C++
#include <iostream>
#include "Pelajaran.h" 
using namespace std;

MataKuliah buatMataKuliah(string namaMatkul, string kodeMatkul) {
    MataKuliah mk;
    mk.nama = namaMatkul;
    mk.kode = kodeMatkul;
    return mk;
}

void tampilkanMataKuliah(MataKuliah mk) {
    cout << "Nama Mata Kuliah : " << mk.nama << endl;
    cout << "Kode Mata Kuliah : " << mk.kode << endl;
}
```

**(Main.cpp)**
```C++
#include <iostream>
#include "Pelajaran.h"  
using namespace std;

int main() {
    string namaMatkul = "Praktikum Struktur Data";
    string kodeMatkul = "STD";

    MataKuliah mk = buatMataKuliah(namaMatkul, kodeMatkul);

    cout << "\n=== Informasi Mata Kuliah ===\n";
    tampilkanMataKuliah(mk);

    return 0;
}

```
#### Output:
<img width="1604" height="172" alt="image" src="https://github.com/user-attachments/assets/18d76be1-aab3-4176-97f6-14b71bc31da2" />

code ini digunakan untuk.

#### Full code Screenshot:
<img width="1600" height="421" alt="image" src="https://github.com/user-attachments/assets/4cbf13bb-579c-4d9f-a0ec-83c2525bab14" />
<img width="1603" height="401" alt="image" src="https://github.com/user-attachments/assets/59ff5472-e645-4cf7-8e88-5e8ba52cabc0" />
<img width="1599" height="400" alt="image" src="https://github.com/user-attachments/assets/ef7994af-3374-46ef-8445-5638473ff36c" />

### 3. [Soal]

```C++
#include <iostream>
using namespace std;

int main() {
    int matriks1[3][3] = { {1, 2, 3}, {4, 5, 6}, {7, 8, 9} };
    int matriks2[3][3] = { {9, 8, 7}, {6, 5, 4}, {3, 2, 1} };

    cout << "Isi Matriks 1 sebelum ditukar:\n";
    for (int baris = 0; baris < 3; baris++) {
        for (int kolom = 0; kolom < 3; kolom++) {
            cout << matriks1[baris][kolom] << " ";
        }
        cout << endl;
    }

    cout << "\nIsi Matriks 2 sebelum ditukar:\n";
    for (int baris = 0; baris < 3; baris++) {
        for (int kolom = 0; kolom < 3; kolom++) {
            cout << matriks2[baris][kolom] << " ";
        }
        cout << endl;
    }

    for (int baris = 0; baris < 3; baris++) {
        for (int kolom = 0; kolom < 3; kolom++) {
            int sementara = matriks1[baris][kolom];
            matriks1[baris][kolom] = matriks2[baris][kolom];
            matriks2[baris][kolom] = sementara;
        }
    }

    cout << "\nSetelah pertukaran elemen matriks:\n";

    cout << "Matriks 1:\n";
    for (int baris = 0; baris < 3; baris++) {
        for (int kolom = 0; kolom < 3; kolom++) {
            cout << matriks1[baris][kolom] << " ";
        }
        cout << endl;
    }

    cout << "\nMatriks 2:\n";
    for (int baris = 0; baris < 3; baris++) {
        for (int kolom = 0; kolom < 3; kolom++) {
            cout << matriks2[baris][kolom] << " ";
        }
        cout << endl;
    }

    return 0;
}
```
#### Output:
<img width="1601" height="441" alt="image" src="https://github.com/user-attachments/assets/99b41ff8-d8e8-470f-8c03-e45bdd6451c6" />

Program ini digunakan untuk.

#### Full code Screenshot:
<img width="1651" height="937" alt="image" src="https://github.com/user-attachments/assets/74a700c8-9e76-43fb-8169-61cbf3cfeda6" />

## Kesimpulan
Ketiga program di atas merupakan contoh penerapan dasar pemrograman dalam bahasa C++, pada pengolahan data menggunakan variabel, array, dan matriks. Secara keseluruhan, ketiga program ini menggambarkan perkembangan logika pemrograman dari sederhana ke kompleks yang dimulai dari manipulasi variabel, pengolahan data linear dengan array, hingga pengolahan data dua dimensi dalam bentuk matriks — yang semuanya menjadi dasar penting dalam memahami konsep algoritma dan struktur data di C++. 

## Referensi
[1] C++ documentation. (2024). cppreference.com: C++ Standard Library reference. Retrieved from https://en.cppreference.com/w/

[2] Deitel, P. J., & Deitel, H. M. (2017). C++ How to Program (10th ed.). Pearson Education.

[3] Schildt, H. (2017). C++: The Complete Reference (4th ed.). McGraw-Hill Education.











