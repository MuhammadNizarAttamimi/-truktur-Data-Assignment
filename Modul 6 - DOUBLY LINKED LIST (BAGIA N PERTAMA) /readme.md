# <h1 align="center">Laporan Praktikum Modul DOUBLY LINKED LIST (BAGIAN PERTAMA)</h1>
<p align="center">Muhammad Nizar Attamimi</p>

## Dasar Teori

Doubly Linked list adalah linked list yang masing – masing elemen nya memiliki 2 successor, yaitu
successor yang menunjuk pada elemen sebelumnya (prev) dan successor yang menunjuk pada elemen
sesudahnya (next).

## Guided 

### 1. [DOUBLY LINKED LIST (BAGIAN PERTAMA)]

```C++
#include <iostream>
#define Nil NULL
using namespace std;

typedef int infotype; // Definisikan tipe data infotype sebagai integer untuk menyimpan informasi elemen
typedef struct elmlist *address; // Definisikan tipe address sebagai pointer ke struct elmlist

struct elmlist {
    infotype info; // Deklarasikan field info untuk menyimpan data elemen
    address next;
    address prev;
};

struct List { 
    address first; 
    address last; 
}; 

void insertFirst(List &L, address P) { 
    P->next = L.first; // Set pointer next dari P ke elemen pertama saat ini
    P->prev = Nil; // Set pointer prev dari P ke Nil karena menjadi elemen pertama
    if (L.first != Nil) L.first->prev = P; // Jika list tidak kosong, set prev elemen pertama lama ke P
    else L.last = P; // Jika list kosong, set last juga ke P
    L.first = P; // Update first list menjadi P
} 

void insertLast(List &L, address P) { 
    P->prev = L.last; // Set pointer prev dari P ke elemen terakhir saat ini
    P->next = Nil; // Set pointer next dari P ke Nil karena menjadi elemen terakhir
    if (L.last != Nil) L.last->next = P; // Jika list tidak kosong, set next elemen terakhir lama ke P
    else L.first = P; // Jika list kosong, set first juga ke P
    L.last = P; // Update last list menjadi P
} 

void insertAfter(List &L, address P, address R) { // Definisikan fungsi insertAfter untuk menyisipkan elemen setelah R
    P->next = R->next; // Set pointer next dari P ke elemen setelah R
    P->prev = R; // Set pointer prev dari P ke R
    if (R->next != Nil) R->next->prev = P; // Jika ada elemen setelah R, set prev elemen tersebut ke P
    else L.last = P; // Jika R adalah terakhir, update last menjadi P
    R->next = P; // Set next dari R ke P
}

address alokasi(infotype x) { // Definisikan fungsi alokasi untuk membuat elemen baru
    address P = new elmlist; // Alokasikan memori baru untuk elemen
    P->info = x; // Set info elemen dengan nilai x
    P->next = Nil; // Set next elemen ke Nil
    P->prev = Nil; // Set prev elemen ke Nil
    return P; 
} 

void printInfo(List L) { // Definisikan fungsi printInfo untuk mencetak isi list
    address P = L.first; // Set P ke elemen pertama list
    while (P != Nil) { // Loop selama P tidak Nil
        cout << P->info << " "; // Cetak info dari P 
        P = P->next; // Pindah ke elemen berikutnya
    } 
    cout << endl; 
}

int main() { 
    List L; 
    L.first = Nil; 
    L.last = Nil;
    address P1 = alokasi(1); 
    insertFirst(L, P1); 
    address P2 = alokasi(2); 
    insertLast(L, P2); 
    address P3 = alokasi(3); 
    insertAfter(L, P3, P1); 
    printInfo(L); 
    return 0; 
}

```
Program ini nunjukin cara bikin dan ngatur data pakai doubly linked list dengan masukin tiga angka (1, 2, dan 3) di posisi berbeda, sampai akhirnya kebentuk urutan data 1, 3, 2.

## Unguided 

### 1. [Soal]
**[Doublylist.h]**
```C++
#ifndef DOUBLYLIST_H
#define DOUBLYLIST_H

#include <iostream>
#include <string>
using namespace std;

struct Kendaraan {
    string nopol;  
    string warna;   
    int tahun;      
};


typedef struct Node* address;


struct Node {
    Kendaraan data; 
    address next;   
    address prev;   
};

struct List {
    address first;  
    address last;   
};

void createList(List &L);

address newNode(Kendaraan x);

void printList(List L);

void insertLast(List &L, address P);

address find(List L, string nopol);

void deleteByNopol(List &L, string nopol);

#endif

```

**[Doublylist.cpp]**
```C++
#include "DoublyList.h"
using namespace std;

void createList(List &L) {
    L.first = NULL; 
    L.last = NULL;  
}

address newNode(Kendaraan x) {
    address P = new Node; 
    P->data = x;          
    P->next = NULL;       
    P->prev = NULL;       
    return P;             
}


void printList(List L) {
    cout << "DATA LIST 1\n\n";
    address P = L.last;       
    while (P != NULL) {       
        cout << "no polisi : " << P->data.nopol << endl;
        cout << "warna     : " << P->data.warna << endl;
        cout << "tahun     : " << P->data.tahun << endl;
        if (P->prev != NULL) cout << endl; 
        P = P->prev;          
    }
}

void insertLast(List &L, address P) {
    if (L.first == NULL) {    
        L.first = L.last = P; 
    } else {
        L.last->next = P;     
        P->prev = L.last;     
        L.last = P;           
    }
}


address find(List L, string nopol) {
    address P = L.first;      
    while (P != NULL) {
        if (P->data.nopol == nopol) 
            return P;         
        P = P->next;         
    }
    return NULL;              
}


void deleteByNopol(List &L, string nopol) {
    address P = find(L, nopol); 
    if (P == NULL) {            
        cout << "Data tidak ditemukan\n";
        return;
    }

    if (P == L.first && P == L.last) {
        L.first = L.last = NULL;
    } 

    else if (P == L.first) {
        L.first = P->next;     
        L.first->prev = NULL;   
    } 
   
    else if (P == L.last) {
        L.last = P->prev;      
        L.last->next = NULL;    
    } 
    
    else {
        P->prev->next = P->next;
        P->next->prev = P->prev; 
    }

    cout << "Data dengan nomor polisi " << nopol << " berhasil dihapus.\n\n";
    delete P; 
}

```

**[Main.cpp]**
```C++
#include <iostream>
#include "DoublyList.h"
using namespace std;

int main() {
    List L;
    createList(L);  

    Kendaraan x;
    string nopol;

    cout << "masukkan nomor polisi: ";
    cin >> x.nopol;
    cout << "masukkan warna kendaraan: ";
    cin >> x.warna;
    cout << "masukkan tahun kendaraan: ";
    cin >> x.tahun;
    insertLast(L, newNode(x));  
    cout << endl;

    cout << "masukkan nomor polisi: ";
    cin >> x.nopol;
    cout << "masukkan warna kendaraan: ";
    cin >> x.warna;
    cout << "masukkan tahun kendaraan: ";
    cin >> x.tahun;
    insertLast(L, newNode(x)); 
    cout << endl;

    cout << "masukkan nomor polisi: ";
    cin >> nopol;
    if (find(L, nopol) != NULL) {
        cout << "nomor polisi sudah terdaftar\n\n";
    }

    cout << "masukkan nomor polisi: ";
    cin >> x.nopol;
    cout << "masukkan warna kendaraan: ";
    cin >> x.warna;
    cout << "masukkan tahun kendaraan: ";
    cin >> x.tahun;
    insertLast(L, newNode(x));  
    cout << endl;

    printList(L);
    cout << endl;

    cout << "Masukkan Nomor Polisi yang dicari  : ";
    cin >> nopol;

    address P = find(L, nopol);
    if (P != NULL) {
        cout << "\nNomor Polisi : " << P->data.nopol << endl;
        cout << "Warna        : " << P->data.warna << endl;
        cout << "Tahun        : " << P->data.tahun << endl;
    }
    cout << endl;

    cout << "Masukkan Nomor Polisi yang akan dihapus  : ";
    cin >> nopol;
    deleteByNopol(L, nopol);

    printList(L);

    return 0;
}
```
#### Output:
<img width="1452" height="901" alt="image" src="https://github.com/user-attachments/assets/a92bf380-de52-441e-a365-b9bcacb54209" />

Doubly linked list itu lebih kuat dari singly linked list karena bisa jalan maju–mundur (dua arah). Jadi, operasi insert dan delete jadi lebih enak dan efisien, apalagi kalau butuh akses ke elemen sebelumnya.

#### Full code Screenshot:
<img width="1603" height="840" alt="image" src="https://github.com/user-attachments/assets/20119844-bcef-4972-b874-4aa2dc3f75e8" />
<img width="1734" height="934" alt="image" src="https://github.com/user-attachments/assets/377224f3-4644-4db6-a4b7-618f63b7ce39" />
<img width="1700" height="931" alt="image" src="https://github.com/user-attachments/assets/a47d7a70-de4b-4890-ba07-7aef9e2e8055" />

## Kesimpulan
Doubly Linked List itu lebih “powerful” daripada Singly Linked List buat kasus yang butuh akses dua arah (bisa maju dan mundur), walaupun makannya memori lebih gede karena ada pointer tambahan. Struktur data ini cocok banget buat aplikasi yang sering ngelakuin operasi insert dan delete di berbagai posisi dalam list.

## Referensi
[1] GeeksforGeeks. (n.d.). Doubly Linked List. Retrieved from https://www.geeksforgeeks.org
[2] file:///C:/Users/hp/AppData/Local/Packages/5319275A.WhatsAppDesktop_cv1g1gvanyjgm/LocalState/sessions/FB8C6BF54308E84227E5A00CD9CDDCE2F492A52B/transfers/2025-47/Modul%206_Doubly%20Linked%20List%20(Bagian%20Pertama).pdf
[3] https://chatgpt.com/
