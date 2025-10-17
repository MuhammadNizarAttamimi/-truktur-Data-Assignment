# <h1 align="center">Laporan Praktikum Modul Pengenalan Bahasa C++ (1)</h1>
<p align="center">Muhammad Nizar Attamimi</p>

## Dasar Teori
“Pengenalan Bahasa C++ (Bagian Kedua)” membahas lanjutan dasar-dasar pemrograman C++ dengan fokus pada pemahaman tipe data, operator, percabangan, dan perulangan. Pada bagian awal, dijelaskan berbagai tipe data seperti int, float, double, char, bool, dan string, serta cara melakukan konversi antar tipe data.

## Guided 

### 1. [Pengenalan Bahasa C++ (Bagian Kedua)]

```C++
#include <iostream>
using namespace std;

int main() {
    int arr[5] = {10, 20, 30, 40, 50};
    cout << "Array 1 Dimensi:" << endl;
    for (int i = 0; i < 5; i++) {
        cout << "Element ke-" << i << ": " << arr[i] << endl;
    }
    cout << endl;

    int arr2D[2][3] = {
        {1, 2, 3},
        {4, 5, 6},
    };
    cout << "Array 2 Dimensi:" << endl;
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 3; j++) {
            cout << "arr2D[" << i << "][" << j << "]: " << arr2D[i][j]
            << " ";
        }
        cout << endl;
    }
    int arr3D[2][2][3] = {
        { {1, 2, 3}, {4, 5, 6} },
        { {7, 8, 9}, {10, 11, 12} },
    };
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 2; j++) {
            for (int k = 0; k < 3; k++) {
                cout << "arr3D[" << i << "][" << j << "]["
                << k << "]: " << arr3D[i][j][k] << endl;
            }
        }
    }

    return 0;
}
```
Program ini bertujuan untuk memperkenalkan konsep array,digunakan untuk menyimpan sekumpulan data dengan tipe yang sama dalam satu variabel.
## Unguided 

### 1. [Soal]

```C++
#include <iostream>
using namespace std;

int main() {
    int A[3][3], B[3][3], C[3][3];

    cout << "Input matriks A:" << endl;
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            cin >> A[i][j];
        }
    }

    cout << "Input matriks B:" << endl;
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            cin >> B[i][j];
        }
    }

    cout << "Hasil penjumlahan matriks:" << endl;
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            C[i][j] = A[i][j] + B[i][j];
            cout << C[i][j] << " ";
        }
        cout << endl;
    }

    cout << "Hasil pengurangan matriks:" << endl;
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            C[i][j] = A[i][j] - B[i][j];
            cout << C[i][j] << " ";
        }
        cout << endl;
    }

    cout << "Hasil perkalian matriks:" << endl;
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            C[i][j] = 0;
            for (int k = 0; k < 3; k++) {
                C[i][j] += A[i][k] * B[k][j];
            }
            cout << C[i][j] << " ";
        }
        cout << endl;
    }

    return 0;
}

```
#### Output:
<img width="1602" height="669" alt="Image" src="https://github.com/user-attachments/assets/85c96198-a071-4296-8ba1-d02f2c1f798b" />

code ini digunakan untuk melakukan operasi pada dua buah matriks berukuran 3×3, yaitu:Penjumlahan matriks,Pengurangan matriks,Perkalian matriks, Program ini juga mengajarkan cara menggunakan array dua dimensi (2D array) serta loop bersarang (nested loop) untuk mengakses elemen-elemen dalam matriks.

#### Full code Screenshot:
<img width="1652" height="984" alt="Image" src="https://github.com/user-attachments/assets/8ddd2308-44e6-4ced-995b-083dbb5f05b9" />

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











