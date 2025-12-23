# <h1 align="center">Laporan Praktikum Modul MULTI LINKED LIST<h1>
<p align="center">Muhammad Nizar Attamimi</p>

## Dasar Teori

Multi List merupakan sekumpulan list yang berbeda yang memiliki suatu keterhubungan satu sama lain. Tiap elemen dalam multi link list dapat membentuk listsendiri.Biasanya ada yang bersifat sebagai list induk dan list anak.

## Guided 

### 1. [MULTI LINKED LIST]
**[Bst.h]**
```C++
#include <iostream>
using namespace std;

int main() {
    cout << "ini adalah file code guided praktikan" << endl;
    return 0;
}
```

Program ini berfungsi untuk menampilkan teks "ini adalah file code guided praktikan" ke layar dengan memanfaatkan fungsi cout sebagai perintah eksekusi output.
## Unguided 

### 1. [Soal]
**[multilinkedlist.h]**
```C++
#ifndef LINKEDLIST_MHS_H
#define LINKEDLIST_MHS_H

#include <iostream>
using namespace std;

struct DataMhs {
    string NamaLengkap;
    string NomorInduk;
    char JenisKelamin;
    float NilaiIPK;
};

struct Elemen {
    DataMhs data;
    Elemen *nextNode;
};

struct LinkedList {
    Elemen *head;
};

void initList(LinkedList &L);
Elemen* buatNode(DataMhs dataBaru);
void tambahDepan(LinkedList &L, Elemen *nodeBaru);
void tambahBelakang(LinkedList &L, Elemen *nodeBaru);
void tambahSetelah(Elemen *sebelum, Elemen *nodeBaru);
void tampilkanList(LinkedList L);

#endif

```

**[multilinkedlist.cpp]**
```C++
#include "multilinkedlist.h"

void initList(LinkedList &L) {
    L.head = nullptr;
}

Elemen* buatNode(DataMhs dataBaru) {
    Elemen *node = new Elemen;
    node->data = dataBaru;
    node->nextNode = nullptr;
    return node;
}

void tambahDepan(LinkedList &L, Elemen *nodeBaru) {
    nodeBaru->nextNode = L.head;
    L.head = nodeBaru;
}

void tambahBelakang(LinkedList &L, Elemen *nodeBaru) {
    if (L.head == nullptr) {
        L.head = nodeBaru;
    } else {
        Elemen *temp = L.head;
        while (temp->nextNode != nullptr) {
            temp = temp->nextNode;
        }
        temp->nextNode = nodeBaru;
    }
}

void tambahSetelah(Elemen *sebelum, Elemen *nodeBaru) {
    nodeBaru->nextNode = sebelum->nextNode;
    sebelum->nextNode = nodeBaru;
}

void tampilkanList(LinkedList L) {
    Elemen *current = L.head;

    while (current != nullptr) {
        cout << "Nama : " << current->data.NamaLengkap << endl;
        cout << "NIM  : " << current->data.NomorInduk << endl;
        cout << "L/P  : " << current->data.JenisKelamin << endl;
        cout << "IPK  : " << current->data.NilaiIPK << endl << endl;
        current = current->nextNode;
    }
}

```

**[main.cpp]**
```C++
#include "multilinkedlist.h"

int main() {
    LinkedList daftar;
    initList(daftar);

    cout << "Percobaan penambahan data (depan, belakang, dan setelah node tertentu)" << endl;

    DataMhs a = {"Ali", "01", 'L', 3.30};
    tambahDepan(daftar, buatNode(a));

    DataMhs b = {"Bobi", "02", 'L', 3.71};
    tambahBelakang(daftar, buatNode(b));

    DataMhs c = {"Cindi", "03", 'P', 3.50};
    tambahBelakang(daftar, buatNode(c));

    DataMhs d = {"Danu", "04", 'L', 4.00};
    Elemen *ptr = daftar.head;
    while (ptr->data.NamaLengkap != "Cindi") {
        ptr = ptr->nextNode;
    }
    tambahSetelah(ptr, buatNode(d));

    tambahBelakang(daftar, buatNode({"Eli", "05", 'P', 3.40}));
    tambahBelakang(daftar, buatNode({"Fahmi", "06", 'L', 3.45}));
    tambahBelakang(daftar, buatNode({"Gita", "07", 'P', 3.75}));
    tambahBelakang(daftar, buatNode({"Hilmi", "08", 'L', 3.30}));

    tampilkanList(daftar);

    return 0;
}

```
#### Output:
<img width="1531" height="689" alt="image" src="https://github.com/user-attachments/assets/d82b2a5f-ecb5-40c8-b11b-4bd5843b0001" />

Program ini digunakan untuk menunjukkan cara menambahkan data mahasiswa ke dalam single linked list lalu menampilkannya dari awal sampai akhir.

#### Full code Screenshot:
<img width="1597" height="629" alt="image" src="https://github.com/user-attachments/assets/b3fad6e8-a001-4704-83fb-a668adab0fc9" />
<img width="1653" height="789" alt="image" src="https://github.com/user-attachments/assets/cb5a2b26-cc2d-49be-8bfc-088afd77986a" />
<img width="1655" height="522" alt="image" src="https://github.com/user-attachments/assets/043c5df9-234f-476e-9702-7571c7dbe2e3" />


## Kesimpulan
Program ini menunjukkan sebuah implementasi Single Linked List sederhana untuk menyimpan dan mengelola data mahasiswa. Program ini mendukung operasi dasar seperti inisialisasi list, alokasi node, penyisipan di berbagai posisi, dan penampilan data, sehingga sangat cocok digunakan sebagai latihan praktikum struktur data.

## Referensi
[1] 
[2] 
[3] 
[4] AI




