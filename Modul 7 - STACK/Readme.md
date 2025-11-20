# <h1 align="center">Laporan Praktikum Modul STACK<h1>
<p align="center">Muhammad Nizar Attamimi</p>

## Dasar Teori

Stack merupakan salah satu bentuk struktur data dimana prinsip operasi yang digunakan seperti tumpukan. Seperti halnya tumpukan, elemen yang bisa diambil terlebih dahulu adalah elemen yang paling atas, atau elemen yang pertama kali masuk, prinsip ini biasa disebut LIFO (Last In First Out).

## Guided 

### 1. [STACK]
**[Stack.h]**
```C++
#ifndef STACK_TABLE
#define STACK_TABLE

#include <iostream>
using namespace std;

//ubah kapasitas sesuai kebutuhan
const int MAX = 10;

struct stackTable{
    int data[MAX];
    int top; // -1 = kosong

};

bool isEmpty(stackTable s);
bool isFull(stackTable s);
void createStack(stackTable &s);

void push(stackTable &s, int angka);
void pop(stackTable &s);
void update(stackTable &s, int posisi);
void view(stackTable s);
void searchData(stackTable s, int data);

#endif

```

**[Stack.cpp]**
```C++
#include "stack.h"
#include <iostream>

using namespace std;

bool isEmpty(stackTable s) {
    return s.top == -1;
}

bool isFull(stackTable s){
    return s.top == MAX -1;
}

void createStack(stackTable &s) {
    s.top = -1;
}

void push(stackTable &s, int angka){
    if(isFull(s)){
        cout << "Stack Penuh!" << endl;
    } else {
        s.top++;
        s.data[s.top] = angka;
        cout << "Data " << angka << " berhasil ditambahkan kedalam stack!" << endl;
    }
}

void pop(stackTable &s){
    if(isEmpty(s)){
        cout << "Stack kosong!" << endl;
    } else {
        int val = s.data[s.top];
        s.top--;
        cout << "Data " << val << " Berhasil dihapus dari stack!" << endl;
    }
}

void update(stackTable &s, int posisi){
    if(isEmpty(s)){
        cout << "Stack kosong!" << endl;
        return;
    }
    if(posisi <= 0){
        cout << "Posisi tidak valid!" << endl;
        return;
    }

    //index = top - (posisi -1)
    int idx = s.top - (posisi -1);
    if(idx < 0 || idx > s.top){
        cout << "Posisi " << posisi << " Tidak valid!" << endl;
        return;
    }

    cout << "Update data posisi ke-" << posisi << endl;
    cout << "Masukkan angka: ";
    cin >> s.data[idx];
    cout << "Data berhasil diupdate!" << endl;
    cout << endl;
}

void view(stackTable s){
    if(isEmpty(s)){
        cout << "Stack Kosong!" << endl;
    } else {
        for(int i = s.top; i >= 0; --i){
            cout << s.data[i] << " ";
        }
    }
    cout << endl;
}

void searchData(stackTable s, int data){
    if(isEmpty(s)){
        cout << "Stack Kosong!" << endl;
        return;
    }
    cout << "Mencari data" << data << "..." << endl;
    int posisi = 1;
    bool found = false;

    for(int i = s.top; i >= 0; --i){
        if(s.data[i] == data){
            cout << "Data " << data << " ditemukan pada posisi ke-" << posisi << endl;
            cout << endl;
            found = true;
            break;
        }
        posisi++;
    }

    if(!found){
        cout << "Data " << data << " tidak ditemukan didalam stack!" << endl;
        cout << endl;
    }
}

```

**[Main.cpp]**
```C++
#include "stack.h"
#include <iostream>

using namespace std;

int main(){
    stackTable s;
    createStack(s);

    push(s, 1);
    push(s, 2);
    push(s, 3);
    push(s, 4);
    push(s, 5);
    cout << endl;

    cout << "--- Stack setelah push ---" << endl;
    view(s);
    cout << endl;

    pop(s);
    pop(s);
    cout << endl;

    cout << "--- Stack setelah pop 2 kali ---" << endl;
    view(s);
    cout << endl;

    //Posisi dihitung dari TOP(1-based)
    update(s, 2);
    update(s, 1);
    update(s, 4);
    cout << endl;

    cout << "--- Stack setelah update ---" << endl;
    view(s);
    cout << endl;

    searchData(s, 4);
    searchData(s, 9);

    return 0;
}
```
Program ini pakai struktur data stack yang dibuat dengan array. Di dalamnya ada operasi dasar push (nambah data), pop (nghapus data paling atas), plus fitur tambahan kayak update dan cari data (search).

## Unguided 

### 1. [Soal]
**[Stack.h]**
```C++
#ifndef STACK_H
#define STACK_H

const int MAX = 20; 

struct Stack {
    int data[MAX]; 
    int top;       
};

void createStack(Stack &S);
void push(Stack &S, int x);
int pop(Stack &S);
void printInfo(Stack S);
void balikStack(Stack &S);
void getInputStream(Stack &S);

#endif

```

**[Stack.cpp]**
```C++
#include <iostream>
#include "stack.h"
using namespace std;

void createStack(Stack &S) {
    S.top = -1; 
}

void push(Stack &S, int x) {
    if (S.top < MAX - 1) {  
        S.top++;
        S.data[S.top] = x;
    } else {

    }
}

int pop(Stack &S) {
    if (S.top >= 0) {              
        int value = S.data[S.top]; 
        S.top--;
        return value;
    }
    return -1;
}

void printInfo(Stack S) {
    cout << "[TOP] ";
    for (int i = S.top; i >= 0; i--) {
        cout << S.data[i] << " ";
    }
    cout << endl;
}

void balikStack(Stack &S) {
    Stack temp;
    createStack(temp);

    while (S.top >= 0) {
        int angka = pop(S);   
        push(temp, angka);    
    }

    S = temp;
}

void getInputStream(Stack &S) {
    string input = "4729601";   
    cout << input << endl;      

    for (char ch : input) {
        int angka = ch - '0'; 
        push(S, angka);
    }
}
```

**[Main.cpp]**
```C++
#include <iostream>
#include "stack.h"
using namespace std;

int main() {
    cout << "Hello world!" << endl;

    Stack S;
    createStack(S);     

    getInputStream(S);  

    printInfo(S);       

    cout << "balik stack" << endl;

    balikStack(S);    

    printInfo(S);      

    return 0;
}
```
#### Output:
<img width="1468" height="163" alt="image" src="https://github.com/user-attachments/assets/229ab54d-746a-41cf-beab-eee30ab6347a" />

Program ini bikin stack, terus otomatis ngisi pakai angka 4729601. Habis itu, isi stack ditampilin dari atas ke bawah. Lalu stack-nya dibalik pakai stack sementara, dan hasil akhirnya ditampilin lagi.

#### Full code Screenshot:
<img width="1604" height="383" alt="image" src="https://github.com/user-attachments/assets/d3d78392-6b79-467b-9e15-1468ecb2c1b7" />
<img width="1656" height="935" alt="image" src="https://github.com/user-attachments/assets/0c44f857-33c8-4c00-ae9b-514038fd2073" />
<img width="1603" height="463" alt="image" src="https://github.com/user-attachments/assets/d4e65fb7-709b-461c-b9c2-0df7f8b168d3" />

## Kesimpulan
Stack itu kerjanya pakai prinsip LIFO, jadi data yang masuk terakhir bakal keluar duluan. Di sini aku nyoba operasi dasar kayak push sama pop, terus bikin fungsi buat nampilin isi stack dan ngebalik urutannya. Dari hasil percobaan, stack-nya jalan sesuai logika dan proses balik datanya berhasil. Praktikum ini bikin aku jadi lebih paham cara pakai stack di program.

## Referensi
[1] GeeksforGeeks. (n.d.). Stack in C++. Retrieved from https://www.geeksforgeeks.org
[2] file:///C:/Users/hp/AppData/Local/Packages/5319275A.WhatsAppDesktop_cv1g1gvanyjgm/LocalState/sessions/FB8C6BF54308E84227E5A00CD9CDDCE2F492A52B/transfers/2025-47/Modul%207%20Stack%20(1).pdf


