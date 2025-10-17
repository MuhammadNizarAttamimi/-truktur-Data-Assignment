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

```C++
#include <iostream>
using namespace std;

int main(){
    int a, b, c, t;
    cout << "Masukkan tiga bilangan: ";
    cin >> a >> b >> c;
    cout<<"Sebelum: "<<a<<" "<<b<<" "<<c<<endl;
    t=a; a=b; b=c; c=t;
    cout<<"Sesudah: "<<a<<" "<<b<<" "<<c<<endl;
}
```
#### Output:
<img width="1604" height="143" alt="Image" src="https://github.com/user-attachments/assets/7117239c-d76d-40f8-907e-21b324683c23" />

code ini digunakan untuk menukar posisi (menggeser) tiga buah bilangan yang dimasukkan oleh pengguna. program melakukan pertukaran nilai secara melingkar antara variabel a, b, dan c menggunakan variabel sementara t.

#### Full code Screenshot:
<img width="1595" height="340" alt="Image" src="https://github.com/user-attachments/assets/35e2bd68-ae1c-432e-9b72-a3ab75c12fb9" />

### 3. [Soal]

```C++
#include <iostream>
using namespace std;

int cariMin(int a[], int n);
int cariMaks(int a[], int n);
void hitungRata(int a[], int n);

int main() {
    int arr[10] = {11,8,5,7,12,26,3,54,33,55};
    int pilih, n = 10;

    do {
        cout << "\n--- Menu Program Array ---\n";
        cout << "1. Tampilkan isi array\n";
        cout << "2. Cari nilai maksimum\n";
        cout << "3. Cari nilai minimum\n";
        cout << "4. Hitung nilai rata-rata\n";
        cout << "5. Keluar\n";
        cout << "Pilih: ";
        cin >> pilih;

        switch(pilih) {
            case 1:
                for(int i=0;i<n;i++)
                    cout << arr[i] << " ";
                cout << endl;
                break;
            case 2:
                cout << "Nilai maksimum: " << cariMaks(arr,n) << endl;
                break;
            case 3:
                cout << "Nilai minimum: " << cariMin(arr,n) << endl;
                break;
            case 4:
                hitungRata(arr,n);
                break;
            case 5:
                cout << "Terima kasih!\n";
                break;
            default:
                cout << "Pilihan tidak valid!\n";
        }
    } while(pilih != 5);

    return 0;
}

int cariMin(int a[], int n){
    int min = a[0];
    for(int i=1;i<n;i++)
        if(a[i]<min) min = a[i];
    return min;
}

int cariMaks(int a[], int n){
    int maks = a[0];
    for(int i=1;i<n;i++)
        if(a[i]>maks) maks = a[i];
    return maks;
}

void hitungRata(int a[], int n){
    int total=0;
    for(int i=0;i<n;i++) total += a[i];
    cout << "Nilai rata-rata: " << (float)total/n << endl;
}
```
#### Output:
<img width="1652" height="755" alt="Image" src="https://github.com/user-attachments/assets/c790110a-95c5-4be0-b1fd-c13d4a8caa74" />

Program ini digunakan untuk mengolah data array dengan berbagai fungsi, seperti: Menampilkan isi array,Mencari nilai maksimum,Mencari nilai minimum,Menghitung rata-rata nilai.

#### Full code Screenshot:
<img width="1700" height="999" alt="Image" src="https://github.com/user-attachments/assets/a99439a4-3dd3-4ebd-9d38-a039b3bd59e6" />

## Kesimpulan
Ketiga program di atas merupakan contoh penerapan dasar pemrograman dalam bahasa C++, pada pengolahan data menggunakan variabel, array, dan matriks. Secara keseluruhan, ketiga program ini menggambarkan perkembangan logika pemrograman dari sederhana ke kompleks yang dimulai dari manipulasi variabel, pengolahan data linear dengan array, hingga pengolahan data dua dimensi dalam bentuk matriks — yang semuanya menjadi dasar penting dalam memahami konsep algoritma dan struktur data di C++. 

## Referensi
[1] C++ documentation. (2024). cppreference.com: C++ Standard Library reference. Retrieved from https://en.cppreference.com/w/

[2] Deitel, P. J., & Deitel, H. M. (2017). C++ How to Program (10th ed.). Pearson Education.

[3] Schildt, H. (2017). C++: The Complete Reference (4th ed.). McGraw-Hill Education.











