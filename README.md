<!--
author:   Francesco Orsini

email:    francesco.orsini@savoiabenincasa.it

version:  0.0.1

language: it

narrator: IT Italian Male

comment:  Quaderno elettronico di Informatica. Classe 3za. Capitolo 4. Il linguaggio C++.

import: https://raw.githubusercontent.com/LiaScript/CodeRunner/master/README.md

import: https://raw.githubusercontent.com/liascript-templates/plantUML/master/README.md

-->

# Il linguaggio C++

[Visualizza su LiaScript](https://liascript.github.io/course/?https://raw.githubusercontent.com/Francesco09Orsini/informatica-3bsia/refs/heads/main/README.md#1)

Appunti del capitolo 4 del libro di testo pp. 86--121.

Per ogni programma presentato nel testo (pp. 86, 93, 98, 99, 103, 105, 106, 107, 109, 110, 112, 115, 118, 119, 121):

1. **Predict** Esamina il programma e cerca di capire cosa farà;
2. Copia il programma in modo da poterlo eseguire sul computer; eseguilo per verificare la previsione; 
3. **Investigate** Copia il programma su PythonTutor/linguaggio C++ ed esegui passo passo il programma per comprendere come evolve il processo generato dal programma. Controlla l'evoluzione della memoria ad ogni operazione di assegnamento; Copia il link dell'esecuzione del programma (Generate embed code).
4. **Modify** Modifica il codice cambiando prima qualcosa di semplice, quindi apportate sempre più modifiche per appropriarti poco alla volta del codice sorgente. Ad esempio, se il programma usa dati scritti nel codice sorgente, modifica il programma per chiedere i dati tramite un'istruzione di input; se un programma usa valori di tipo intero, prova a sostituirli con numeri in virgola mobile...
5. **Make** Scrivi un nuovo programma, in cui puoi prendere in prestito frammenti di codice dal programma originale, che realizza una funzione diversa, oppure la stessa funzione applicata in un contesto, o problema, diverso.

## Le basi del linguaggio

Es. pag 86

### Programma a pag. 86 - Somma.cpp

``` c +Somma.cpp
// Somma.cpp
#include <iostream>
using namespace std;

int main() {
    int a, b, s;
    cin >> a;
    cin >> b;
    s = a + b;
    cout << s;

    return 0;
}
```
@LIA.cpp

#### 1. Predict (p. 86)

Il programma dichiara tre variabili intere, `a`, `b` e `s`.
Legge due numeri interi dati in ingresso memorizzandoli nelle variabili `a` e `b`, calcola la somma di queste due variabili memorizzandola in `s` e ne stampa il valore.

#### 2. Run (p. 86)

Il programma conferma la previsione

#### 3. Investigate (p. 86)

``` cpp +Somma.cpp
// Somma.cpp
#include <iostream>
using namespace std;

int main() {
    int a, b, s;
    cin >> a;
    cin >> b;
    s = a + b;
    cout << s;

    return 0;
}
```
@LIA.evalWithDebug(`["Somma.cpp"]`, `g++ -g -Wall Somma.cpp -o a.out`, `./a.out`)


Per usare PythonTutor devo impostare dei valori alle variabili di input.
Uso 1 e 2.

<iframe width="800" height="500" frameborder="0" src="https://pythontutor.com/iframe-embed.html#code=%23include%20%3Ciostream%3E%0Ausing%20namespace%20std%3B%0A%0Aint%20main%28%29%20%7B%0A%20%20%20%20int%20a,%20b,%20s%3B%0A%20%20%20%20//cin%20%3E%3E%20a%3B%0A%20%20%20%20a%20%3D%201%3B%0A%20%20%20%20//cin%20%3E%3E%20b%3B%0A%20%20%20%20b%20%3D%202%3B%0A%20%20%20%20s%20%3D%20a%20%2B%20b%3B%0A%20%20%20%20cout%20%3C%3C%20s%3B%0A%0A%20%20%20%20return%200%3B%0A%7D&codeDivHeight=400&codeDivWidth=350&cumulative=false&curInstr=6&heapPrimitives=nevernest&origin=opt-frontend.js&py=cpp_g%2B%2B9.3.0&rawInputLstJSON=%5B%5D&textReferences=false"> </iframe>


#### 4. Modify  (p. 86)

Voglio aggiungere informazioni all'utente per comunicare di immettere i numeri intero, voglio essere più descrittivo e andare a capo nell'output.

``` cpp +Somma.cpp
// Somma.cpp
#include <iostream>
using namespace std;

int main() {
    int a, b, s;
    cout << "Immetti un addendo intero: ";
    cin >> a;
    cout << "Immetti un altro addendo intero: ";
    cin >> b;
    s = a + b;
    cout << "La somma di " << a << " e " << b << " e' pari a " << s << "." << endl;

    return 0;
}
```
@LIA.cpp

#### 5. Make (p. 86)

Scrivo un nuovo programma che calcola il prodotto.

``` cpp +Prodotto.cpp
// Prodotto.cpp
#include <iostream>
using namespace std;

int main() {
    int a, b, p;
    cout << "Immetti un moltiplicando intero: ";
    cin >> a;
    cout << "Immetti un altro moltiplicando intero: ";
    cin >> b;
    p = a * b;
    cout << "Il prodotto di " << a << " e " << b << " e' pari a " << p << "." << endl;

    return 0;
}
```
@LIA.cpp


### Programma a pag. 93 - tipi.cpp
#Il linguaggio C++
##Le basi del linguaggio
###Programma a pag. 93 - Tipi.cpp

``` cpp
// Tipi.cpp:dimensioni     dei tipi
#include <iostream>
using namespace std;

int main () {
    cout << "Dimensioni di int: " << sizeof(int) << " byte\n";
    cout << "Dimensioni di short int: " << sizeof(short int) << " byte\n;
    cout << "Dimensioni di long int: " << sizeof(long int) << " byte\n; 
    cout << "Dimensioni di long long int: " << sizeof(long long int) << " byte\n;
    cout << "Dimensioni di float: " << sizeof(float) << " byte\n; 
    cout << "Dimensioni di double: " << sizeof(double) << " byte\n;
    cout << "Dimensioni di long double " << sizeof(long double) << " byte\n;
    cout << "Dimensioni di char " << sizeof(chair) << " byte\n;
    cout << "Dimensioni di bool " << sizeof(bool) << " byte\n;
    return 0;

}
```
@LIA.cpp



@LIA.cpp


### Programma a pag. 98 - tipi.cpp
#Il linguaggio C++
## Il casting per la conversazione tipo
###Programma a pag. 98 - Tipi.cpp


``` cpp
// Tipi.cpp:dimensioni     dei tipi

#include <iostream>
using namespace std;

int main () 
{
    int a =5;
    float b = 3.56;
    a = b;
    cout << a;

    return 0;
}
```
@LIA.cpp


@LIA.cpp


### Programma a pag. 98 - tipi.cpp
#Il linguaggio C++
## Il casting per la conversazione tipo
###Programma a pag. 98 - Tipi.cpp

``` cpp
// Tipi.cpp:dimensioni     dei tipi

#include <iostream>
using namespace std;

int main () 
{
    int a =5;
    float b = 3.56;
    b = a;
    cout << b;

    return 0;
}
```
@LIA.cpp


@LIA.cpp


### Programma a pag. 99 - tipi.cpp
#Il linguaggio C++
## Il casting per la conversazione tipo
###Programma a pag. 99 - Tipi.cpp

``` cpp
// Tipi.cpp:dimensioni     dei tipi

#include <iostream>
using namespace std;

int main () 
{
    int a = 5;
    int b = 2;
    float c = 3.56;
    float p;
    p = a/b + c;
    cout << p;

    return 0;
}
```
@LIA.cpp


### Programma a pag. 99 - tipi.cpp
#Il linguaggio C++
## Il casting per la conversazione tipo
###Programma a pag. 99 - Tipi.cpp

``` cpp
// Tipi.cpp:dimensioni     dei tipi

#include <iostream>
using namespace std;

int main () 
{
    int a = 5;
    int b = 2;
    float c = 3.56;
    float p;
    p = static_cast<float>(a)/b + c;
    cout << p;

    return 0;
}
```
@LIA.cpp


@LIA.cpp


### Programma a pag. 103 - tipi.cpp
#Il linguaggio C++
## Le istruzioni di ingresso e di uscita
###Programma a pag. 103 - Tipi.cpp

``` cpp
// Parcogiochi.cpp: divisione dei biglietti
#include <iostream>
using namespace std;

int main () 
{
   // input
   int biglietti, ragazzi;
   // output
   int quota, avanzo;

   cout << "Numero di biglietti e di ragazzi:";
   cin >> biglietti/ ragazzi;
   quota = biglietti / ragazzi;
   avanzo = biglietti % ragazzi;
   cout << "Ad ogni ragazzo spettano" << quota << "biglietti" << endl;
   cout << "e ne avanzano" << avanzo << endl;

   return 0;
}
```
@LIA.cpp

@LIA.cpp


### Programma a pag. 105 - tipi.cpp
#Il linguaggio C++
## Gli errori nella programmazione 
###Programma a pag. 105 - Tipi.cpp

``` cpp
// Quoziente.cpp: divisione di due numeri
#include <iostream>
using namespace std;

int main () 
{
    int a, b, q;
    cin >> a >> b;
    q = a / b
    cout << q;

    return 0;
}
```
@LIA.cpp


@LIA.cpp


### Programma a pag. 106 - tipi.cpp
#Il linguaggio C++
## Gli errori nella programmazione 
###Programma a pag. 106 - Tipi.cpp

``` cpp
// Differenza.cpp: differenza tra due numeri
#include <iostream>
using namespace std;

int main () 
{
    int num1, num2, differenza;
    cout << "Due numeri"
    cin >> num1 >> num2;
    differenza = num1 - num2
    cout << "Risultato = " << differenza << endl

    return 0;
}
```
@LIA.cpp


@LIA.cpp


### Programma a pag. 107 - tipi.cpp
#Il linguaggio C++
## Gli errori nella programmazione 
###Programma a pag. 107 - Tipi.cpp

``` cpp
// CalcoloSconto.cpp: calcolo del prezzo socntato
#include <iostream>
using <string>

using namespace std;
const int PERC = 20;     // percentuale di sconto
int main () 
{
    // variabili di input-output
    string descrizione;
    float prezzo;
    // variabili di lavoro
    float sconto;

    cout << "Descrizione e prezzo: ";
    cin >> descrizione >> prezzo;
    sconto = prezzo * PERC / 100;
    prezzo = prezzo - sconto;
    cout << descrizione << ": " << prezzo << endl;

    return 0;
}
```
@LIA.cpp


### Programma a pag. 109 - tipi.cpp
#Il linguaggio C++
## La struttura di alternativa  
###Programma a pag. 109 - Tipi.cpp

``` cpp
// Ordina.cpp: due numeri in onridne crescente
#include <iostream>

int main () 
{
    // input
    int a, b;

    cout << "Due numeri: ";
    cin >> a >> b;
    if (a < b) {
       cout << a << endl; 
       cout << b << endl; 
}
 else {
      cout << b << endl; 
      cout << a << endl;
}
return 0;
}
```
@LIA.cpp 







