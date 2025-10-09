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
    // --- Array 1 Dimensi ---
    int arr[5] = {10, 20, 30, 40, 50};
    cout << "Array 1 Dimensi:" << endl;
    for (int i = 0; i < 5; i++) {
        cout << "Element ke-" << i << ": " << arr[i] << endl;
    }
    cout << endl;

    // --- Array 2 Dimensi ---
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
    // --- Array Multi Dimensi (3D) ---
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
Program ini berfungsi untuk menampilkan tulisan berulang sebanyak jumlah yang dimasukkan oleh pengguna.
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

Kode di atas digunakan untuk operasi aritmatika dua bilangan bertipe float. Jadi Pengguna  memasukkan dua angka , lalu menampilkan hasil penjumlahan, pengurangan, perkalian, dan pembagian dari kedua angka tersebut..

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

Kode di atas digunakan untuk mengubah angka dari 0 sampai 100 menjadi bentuk tulisan dalam bahasa Indonesia.

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

Kode di atas digunakan untuk mencetak sebuah pola angka secara menurun dengan bentuk simetris yang di mana di tengah setiap baris terdapat tanda bintang (*) sebagai pemisah antara deretan angka menurun dan menaik.

#### Full code Screenshot:
<img width="1700" height="999" alt="Image" src="https://github.com/user-attachments/assets/a99439a4-3dd3-4ebd-9d38-a039b3bd59e6" />

## Kesimpulan
Program di atas menunjukkan penerapan dasar dari bahasa pemrograman C++ yang mencakup penggunaan struktur program dasar (input, proses, output), operator aritmetika, percabangan (if–else), dan perulangan (looping). 

## Referensi
[1] GeeksforGeeks. (2025). Basic Input and Output in C++. Retrieved October 9, 2025, from https://www.geeksforgeeks.org/basic-input-output-cpp/
[2] GeeksforGeeks. (2025). C++ Program to Convert Number to Words. Retrieved October 9, 2025, from https://www.geeksforgeeks.org/cpp-program-to-convert-number-to-words/
[3] W3Schools. (2025). C++ For Loop. Retrieved October 9, 2025, from https://www.w3schools.com/cpp/cpp_for_loop.asp








