# <h1 align="center">Laporan Praktikum Modul Pengenalan Bahasa C++ (1)</h1>
<p align="center">Muhammad Nizar Attamimi</p>

## Dasar Teori

penjelasan terkait materi modul ini yaitu memberikan pemahaman dasar tentang cara menulis, menjalankan, dan memahami program sederhana menggunakan C++. mulai dari mengenal tampilan IDE, menulis kode sederhana, menggunakan variabel, hingga membuat logika dasar dengan percabangan dan perulangan.

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
<img width="1444" height="141" alt="Image" src="https://github.com/user-attachments/assets/28e65e77-bf81-4b26-8aad-bb2fee0732cb" />

Kode di atas digunakan untuk mengubah angka dari 0 sampai 100 menjadi bentuk tulisan dalam bahasa Indonesia.

#### Full code Screenshot:
<img width="1600" height="812" alt="Image" src="https://github.com/user-attachments/assets/f1d51f02-f3b5-4da8-80a1-3d3c851f90ea" />

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
<img width="1603" height="226" alt="Image" src="https://github.com/user-attachments/assets/e534e1aa-d89a-425b-ae55-cd4f5bbd12df" />

Kode di atas digunakan untuk mencetak sebuah pola angka secara menurun dengan bentuk simetris yang di mana di tengah setiap baris terdapat tanda bintang (*) sebagai pemisah antara deretan angka menurun dan menaik.

#### Full code Screenshot:
<img width="1598" height="665" alt="Image" src="https://github.com/user-attachments/assets/c1fe6454-eeec-41d5-b624-7f06bb70688b" />

## Kesimpulan
Program di atas menunjukkan penerapan dasar dari bahasa pemrograman C++ yang mencakup penggunaan struktur program dasar (input, proses, output), operator aritmetika, percabangan (if–else), dan perulangan (looping). 

## Referensi
[1] GeeksforGeeks. (2025). Basic Input and Output in C++. Retrieved October 9, 2025, from https://www.geeksforgeeks.org/basic-input-output-cpp/
[2] GeeksforGeeks. (2025). C++ Program to Convert Number to Words. Retrieved October 9, 2025, from https://www.geeksforgeeks.org/cpp-program-to-convert-number-to-words/
[3] W3Schools. (2025). C++ For Loop. Retrieved October 9, 2025, from https://www.w3schools.com/cpp/cpp_for_loop.asp


