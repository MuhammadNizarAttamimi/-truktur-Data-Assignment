# <h1 align="center">Laporan Praktikum Modul GRAPH<h1>
<p align="center">Muhammad Nizar Attamimi</p>

## Dasar Teori
Graph merupakan himpunan tidak kosong dari node (vertec) dan garis penghubung (edge). Contoh sederhana tentang graph, yaitu antara Tempat Kost Anda dengan Common Lab. Tempat Kost Anda dan Common Lab merupakan node (vertec). Jalan yang menghubungkan tempat Kost dan Common Lab merupakan garis penghubung antara keduanya (edge)
## Guided 

### 1. [GRAPH]
**[GRAP.h]**
```C++
#ifndef GRAPH_H_INCLUDE
#define GRAPH_H_INCLUDE
typedefintinfoGraph;
typedefstruct ElmNode*adrNode;
typedefstruct ElmEdge*adrEdge;

structElmNode{
    infoGraph info;
    intVisited;
    intPred;
    adrEdgefirstEdge;
    adrNode Next;
};
    structElmEdge{
    adrNode Node;
    adrEdge Next;
};

struct Graph {
    adrNode First;
};

adrNode AllocateNode(infoGraphX);
adrEdgeAllocateEdge(adrNodeN);
void CreateGraph(Graph &G);
void InsertNode(Graph &G,infoGraphX);
void DeleteNode(Graph &G,infoGraphX);
void ConnectNode(adrNodeN1,adrNode N2);
void DisconnectNode (adrNodeN1, adrNodeN2);
adrNodeFindNode(Graph G,infoGraphX);
adrEdgeFindEdge(adrNodeN,adrNodeNFind);
void PrintInfoGraph (Graph G);
void PrintTopologicalSort(Graph G);

#endif

#ifndef GRAPH_H_INCLUDE
#define GRAPH_H_INCLUDE

typedefintinfoGraph;
typedefstruct ElmNode*adrNode;
typedefstruct ElmEdge*adrEdge;

structElmNode{
    infoGraph info;
    intVisited;
    adrEdgefirstEdge;
    adrNode Next;
};

struct ElmEdge{
    adrNode Node;
    adrEdge Next;
};
struct Graph {
    adrNode First;
};

//Adds Node
ElmNode addNode(infoGrapha,intb, adrEdgec,adrNoded){
    ElmNodenewNode;
    newNode.Info= a;
    newNode.Visited=b ;
    newNode.firstEdge= c;
    newNode.Next = d;
returnnewNode;
}
//Addsanedgetoa graph
void addEdge(ElmNodenewNode){
    ElmEdgenewEdge;
    newEdge.Node = newNode.Next;
    newEdge.Next = newNode.firstEdge;
}
```

## Unguided 

### 1. [Soal]
**[multilinkedlist.h]**
```C++


```

**[multilinkedlist.cpp]**
```C++

```

**[main.cpp]**
```C++

```
#### Output:
<img width="1457" height="292" alt="image" src="https://github.com/user-attachments/assets/f0be3531-33ef-4167-8f74-464ad6cb5f3e" />

Program ini bertujuan untuk memahami ADT Graph tidak berarah dalam merepresentasikan hubungan antar simpul menggunakan adjacency list. Operasi penambahan simpul, penghubungan edge, serta penelusuran DFS dan BFS menunjukkan bagaimana simpul-simpul saling terhubung melalui pointer. Penggunaan atribut visited membantu mencegah kunjungan berulang sehingga proses penelusuran berjalan lebih efisien dan teratur.

#### Full code Screenshot:
<img width="1606" height="749" alt="image" src="https://github.com/user-attachments/assets/180e87d9-e3f3-4998-82a2-3c965147bacc" />
<img width="1765" height="820" alt="image" src="https://github.com/user-attachments/assets/a759c80c-233a-44be-b5fa-c934799687fb" />
<img width="1600" height="783" alt="image" src="https://github.com/user-attachments/assets/ff184623-7788-45b8-ad3b-fc53062e2254" />

## Kesimpulan
Program ini dibuat untuk mengimplementasikan struktur data Graph tak berarah (undirected graph) menggunakan bahasa pemrograman C++. Graph direpresentasikan dalam bentuk adjacency list, di mana setiap simpul (vertex) memiliki daftar sisi (edge) yang terhubung dengannya.
## Referensi
[1] GeeksforGeeks. (n.d.). Graph data structure. Diakses dari https://www.geeksforgeeks.org/graph-data-structure/
[2] Modul 14 Graph
[3] AI





