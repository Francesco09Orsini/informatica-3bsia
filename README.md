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


### PROGRAMMA A PAG 86 - Somma.cpp

``` c +Somma.cpp
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
    cout << "La somma è: " << s << endl;

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

#### 5. Make (p. 86)

Scrivo un nuovo programma che calcola il prodotto.

```c assegnazione.cpp
// asssegnazione.cpp
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

### PROGRAMMA A PAG.93 - Tipi.cpp

```c assegnazione.cpp
// asssegnazione.cpp
#include <iostream>
using namespace std;

int main() {
    cout << "Dimensioni di int: " << sizeof(int) << " byte\n";
    cout << "Dimensioni di short int: " << sizeof(short int) << " byte\n";
    cout << "Dimensioni di long int: " << sizeof(long int) << " byte\n";
    cout << "Dimensioni di long long int: " << sizeof(long long int) << " byte\n";
    cout << "Dimensioni di float: " << sizeof(float) << " byte\n";
    cout << "Dimensioni di double: " << sizeof(double) << " byte\n";
    cout << "Dimensioni di long double: " << sizeof(long double) << " byte\n";
    cout << "Dimensioni di char: " << sizeof(char) << " byte\n";
    cout << "Dimensioni di bool: " << sizeof(bool) << " byte\n";

    return 0;
}
```
@LIA.cpp

#### 1. Predict (p. 93)

Il programma stamperà sullo schermo la dimensione in byte dei vari tipi di dato in C++

#### 2. Run (p. 93)

eseguire il codice e osservare le dimensioni in byte dei diversi tipi di dato che vengono visualizzate riga per riga

#### 3. Investigate

<iframe width="800" height="500" frameborder="0" src="https://pythontutor.com/iframe-embed.html#code=%23include%20%3Ciostream%3E%0Ausing%20namespace%20std%3B%0A%0Aint%20main%28%29%20%7B%0A%20%20%20%20cout%20%3C%3C%20%22Dimensioni%20di%20int%3A%20%22%20%3C%3C%20sizeof%28int%29%20%3C%3C%20%22%20byte%5Cn%22%3B%0A%20%20%20%20cout%20%3C%3C%20%22Dimensioni%20di%20short%20int%3A%20%22%20%3C%3C%20sizeof%28short%20int%29%20%3C%3C%20%22%20byte%5Cn%22%3B%0A%20%20%20%20cout%20%3C%3C%20%22Dimensioni%20di%20long%20int%3A%20%22%20%3C%3C%20sizeof%28long%20int%29%20%3C%3C%20%22%20byte%5Cn%22%3B%0A%20%20%20%20cout%20%3C%3C%20%22Dimensioni%20di%20long%20long%20int%3A%20%22%20%3C%3C%20sizeof%28long%20long%20int%29%20%3C%3C%20%22%20byte%5Cn%22%3B%0A%20%20%20%20cout%20%3C%3C%20%22Dimensioni%20di%20float%3A%20%22%20%3C%3C%20sizeof%28float%29%20%3C%3C%20%22%20byte%5Cn%22%3B%0A%20%20%20%20cout%20%3C%3C%20%22Dimensioni%20di%20double%3A%20%22%20%3C%3C%20sizeof%28double%29%20%3C%3C%20%22%20byte%5Cn%22%3B%0A%20%20%20%20cout%20%3C%3C%20%22Dimensioni%20di%20long%20double%3A%20%22%20%3C%3C%20sizeof%28long%20double%29%20%3C%3C%20%22%20byte%5Cn%22%3B%0A%20%20%20%20cout%20%3C%3C%20%22Dimensioni%20di%20char%3A%20%22%20%3C%3C%20sizeof%28char%29%20%3C%3C%20%22%20byte%5Cn%22%3B%0A%20%20%20%20cout%20%3C%3C%20%22Dimensioni%20di%20bool%3A%20%22%20%3C%3C%20sizeof%28bool%29%20%3C%3C%20%22%20byte%5Cn%22%3B%0A%0A%20%20%20%20return%200%3B%0A%7D&codeDivHeight=400&codeDivWidth=350&cumulative=false&curInstr=0&heapPrimitives=nevernest&origin=opt-frontend.js&py=cpp_g%2B%2B9.3.0&rawInputLstJSON=%5B%5D&textReferences=false"> </iframe>

#### 4. Modify

```
#include <iostream>
using namespace std;

int main () {
    cout << "=== Dimensioni dei tipi di dato in C++ ===\n\n";

    cout << "int: " << sizeof(int) << " byte\n";
    cout << "short int: " << sizeof(short int) << " byte\n";
    cout << "long int: " << sizeof(long int) << " byte\n";
    cout << "long long int: " << sizeof(long long int) << " byte\n";
    cout << "float: " << sizeof(float) << " byte\n";
    cout << "double: " << sizeof(double) << " byte\n";
    cout << "long double: " << sizeof(long double) << " byte\n";
    cout << "char: " << sizeof(char) << " byte\n";
    cout << "bool: " << sizeof(bool) << " byte\n";
    cout << "unsigned int: " << sizeof(unsigned int) << " byte\n";

    return 0;
}
```

#### 5. Make

```
#include <iostream>
using namespace std;

int main () {
    cout << "Dimensioni dei tipi signed:\n";
    cout << "int: " << sizeof(int) << " byte\n";
    cout << "short int: " << sizeof(short int) << " byte\n";
    cout << "long int: " << sizeof(long int) << " byte\n";
    cout << "long long int: " << sizeof(long long int) << " byte\n";
    cout << "float: " << sizeof(float) << " byte\n";
    cout << "double: " << sizeof(double) << " byte\n";
    cout << "long double: " << sizeof(long double) << " byte\n";
    cout << "char: " << sizeof(char) << " byte\n";
    cout << "bool: " << sizeof(bool) << " byte\n\n";

    cout << "Dimensioni dei tipi unsigned:\n";
    cout << "unsigned int: " << sizeof(unsigned int) << " byte\n";
    cout << "unsigned short int: " << sizeof(unsigned short int) << " byte\n";
    cout << "unsigned long int: " << sizeof(unsigned long int) << " byte\n";

    return 0;

}
```
@LIA.cpp

### PROGRAMAAZIONE - pag. 94


```c assegnazione.cpp
// asssegnazione.cpp
#include <iostream>
using namespace std;

int main () {
    double raggio= 10;
    double area = raggio * raggio * 3.14;
    int tempo_in_sec = 900;
    int durata_in_minuti = tempo_in_sec / 60;
    double spazio = 1000; // 1 km
    double tempo = 6 * 60; // 6 minuti
    double velocita= spazio / tempo;
    string nome = "Rossi";

return 0;
}
```
@LIA.cpp

#### 1. Predict (p. 94)

Il programma dichiara di avere alcuni variabili e costamti con tipi primitivi e definiti dalla libreria standard ( string )

#### 2. Run 
l'esecuzione conferma quanto scritto del predict

#### 3. Investigate

Per usare PythonTutor devo impostare dei valori alle variabili di input.

<iframe width="800" height="500" frameborder="0" src="https://pythontutor.com/iframe-embed.html#code=//%20asssegnazione.cpp%0A%23include%20%3Ciostream%3E%0Ausing%20namespace%20std%3B%0Aint%20main%20%28%29%20%7B%0A%20%20%20%20double%20raggio%3D%2010%3B%0A%20%20%20%20double%20area%20%3D%20raggio%20*%20raggio%20*%203.14%3B%0A%20%20%20%20int%20tempo_in_sec%20%3D%20900%3B%0A%20%20%20%20int%20durata_in_minuti%20%3D%20tempo_in_sec%20/%2060%3B%0A%20%20%20%20double%20spazio%20%3D%201000%3B%20//%201%20km%0A%20%20%20%20double%20tempo%20%3D%206%20*%2060%3B%20//%206%20minuti%0A%20%20%20%20double%20velocita%20%3D%20spazio%20/%20tempo%3B%0A%20%20%20%20string%20nome%20%3D%20%22Rossi%22%3B%0A%0Areturn%200%3B%0A%7D&codeDivHeight=400&codeDivWidth=350&cumulative=false&curInstr=0&heapPrimitives=nevernest&origin=opt-frontend.js&py=cpp_g%2B%2B9.3.0&rawInputLstJSON=%5B%5D&textReferences=false"> </iframe>

#### 4. Modify

```c assegnazione.cpp
// asssegnazione.cpp
#include <iostream>
using namespace std;
// Calcolo dell'età
    int anno_nascita = 2005;
    int anno_corrente = 2025;
    int eta = anno_corrente - anno_nascita;

    cout << "Nome: " << nome << endl;
    cout << "Età: " << eta << " anni" << endl;
}
```
@LIA.cpp

#### 5. Make

```c assegnazione.cpp
// asssegnazione.cpp
#include <iostream>
using namespace std;

int main () {
    string nome = "Rossi";
    double altezza = 1.75; // metri
    double peso = 70;       // kg

    double imc = peso / (altezza * altezza);

    int anno_nascita = 2005;
    int anno_corrente = 2025;
    int eta = anno_corrente - anno_nascita;

    cout << "Nome: " << nome << endl;
    cout << "Età: " << eta << " anni" << endl;
    cout << "IMC: " << imc << endl;
}
```
@LIA.cpp


### PROGRAMMAZIONE PAG. 98 - Tipi.cpp

```c assegnazione.cpp
// asssegnazione.cpp
#include <iostream>
using namespace std;


int main () 
{
    int a= 5;
    float b = 3.56;
    b = a;
    cout << b;

return 0;
}
```
@LIA.cpp

#### 1. Predict (p.98)
a è un intero con valore 5, b è un float inizialmente 3.56, ma poi diventa uguale a a (b = a) , quindi b diventerà 5.

#### 2. Run
Il programma stamperà il numero 5

#### 3. Investigate 

<iframe width="800" height="500" frameborder="0" src="https://pythontutor.com/iframe-embed.html#code=%23include%20%3Ciostream%3E%0Ausing%20namespace%20std%3B%0A%0A%0Aint%20main%20%28%29%20%0A%7B%0A%20%20%20%20int%20a%3D%205%3B%0A%20%20%20%20float%20b%20%3D%203.56%3B%0A%20%20%20%20b%20%3D%20a%3B%0A%20%20%20%20cout%20%3C%3C%20b%3B%0A%0Areturn%200%3B%0A%7D&codeDivHeight=400&codeDivWidth=350&cumulative=false&curInstr=6&heapPrimitives=nevernest&origin=opt-frontend.js&py=cpp_g%2B%2B9.3.0&rawInputLstJSON=%5B%5D&textReferences=false"> </iframe>

#### 4. Modify

```c assegnazione.cpp
// asssegnazione.cpp
#include <iostream>
using namespace std;

int main () 
{
    int a = 5;
    float b = 3.56;
    b = a;

    float somma = a + b;
    cout << "b = " << b << endl;
    cout << "Somma a+b = " << somma << endl;

    return 0;
}
```
@LIA.cpp

#### 5. Make 

```c assegnazione.cpp
// asssegnazione.cpp
#include <iostream>
using namespace std;

int main()
{
    float a = 7.5;
    float b = 2.5;

    float risultato = a / b;

    cout << "Risultato della divisione: " << risultato << endl;

    return 0;
}
```
@LIA.cpp

### PROGRAMMA A PAG. 98 - Tipi.cpp

```c assegnazione.cpp
// asssegnazione.cpp
#include <iostream>
using namespace std;

int main ()
{
    int a = 5;
    float b = 3.56; 
    a = b;
    cout << a;

    return 0;
}
```
@LIA.cpp

#### 1. Predict (p.98)
a è un intero con valore 5, b è un float inizialmente 3.56, ma poi diventa uguale a b (a = b) , quindi b sarà troncato ad 3.

#### 2. Run
Il programma stamperà il numero 3

#### 3. Investigate

<iframe width="800" height="500" frameborder="0" src="https://pythontutor.com/iframe-embed.html#code=%23include%20%3Ciostream%3E%0Ausing%20namespace%20std%3B%0A%0Aint%20main%20%28%29%0A%7B%0A%20%20%20%20int%20a%20%3D%205%3B%0A%20%20%20%20float%20b%20%3D%203.56%3B%20%0A%20%20%20%20a%20%3D%20b%3B%0A%20%20%20%20cout%20%3C%3C%20a%3B%0A%0A%20%20%20%20return%200%3B%0A%7D&codeDivHeight=400&codeDivWidth=350&cumulative=false&curInstr=6&heapPrimitives=nevernest&origin=opt-frontend.js&py=cpp_g%2B%2B9.3.0&rawInputLstJSON=%5B%5D&textReferences=false"> </iframe>

#### 4. Modify
```c assegnazione.cpp
// assegnazione.cpp
#include <iostream>
using namespace std;

int main ()
{
    int a = 5;
    float b = 3.56;

    a = b; // assegnazione float -> int (troncamento)
    float somma = a + b; // somma tra int troncato e float

    cout << "a (troncato) = " << a << endl;
    cout << "b = " << b << endl;
    cout << "Somma a+b = " << somma << endl;

    return 0;
}
```
@LIA.cpp

#### 5. Make

```c assegnazione.cpp
// asssegnazione.cpp
#include <iostream>
using namespace std;

int main ()
{
    int a = 7;
    float b;

    b = a; // int -> float (conversione automatica)
    float prodotto = a * b;

    cout << "a = " << a << endl;
    cout << "b (convertito in float) = " << b << endl;
    cout << "Prodotto a*b = " << prodotto << endl;

    return 0;
}
```
@LIA.cpp

### PROGRAMMA A PAG. 99 - Tipi.cpp

```c assegnazione.cpp
// asssegnazione.cpp
#include <iostream>
using namespace std;

int main() 
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

#### 1. Predict
 la divisione a/b dovrà essere 2 e la somma porterà 5.56

#### 2. Run
 il programma stamperà il numero 5.56

#### 3. Investigate

<iframe width="800" height="500" frameborder="0" src="https://pythontutor.com/iframe-embed.html#code=%23include%20%3Ciostream%3E%0Ausing%20namespace%20std%3B%0A%0Aint%20main%28%29%20%0A%7B%0A%20%20int%20a%20%3D%205%3B%0A%20%20int%20b%20%3D%202%3B%0A%20%20float%20c%20%3D%203.56%3B%0A%20%20float%20p%3B%0A%20%20p%20%3D%20a/b%20%2B%20c%3B%0A%20%20cout%20%3C%3C%20p%3B%0A%0A%20%20return%200%3B%0A%7D&codeDivHeight=400&codeDivWidth=350&cumulative=false&curInstr=7&heapPrimitives=nevernest&origin=opt-frontend.js&py=cpp_g%2B%2B9.3.0&rawInputLstJSON=%5B%5D&textReferences=false"> </iframe>

#### 4. Modify

```c assegnazione.cpp
// asssegnazione.cpp
#include <iostream>
using namespace std;

int main() 
{
    int a = 5;
    int b = 2;
    float c = 3.56;
    float p;

    p = float(a)/b + c;  // divisione reale
    cout << "a/b = " << float(a)/b << endl;
    cout << "c = " << c << endl;
    cout << "p = " << p << endl;

    return 0;
} 
```
@LIA.cpp

#### 5. Make

```c assegnazione.cpp
// asssegnazione.cpp
#include <iostream>
using namespace std;

int main() 
{
    int a = 5;
    int b = 2;
    float c = 3.56;
    float p;

    p = (float(a)/b) * c;  
    cout << p;

    return 0;
}
```
@LIA.cpp

### PROGRAMMA A PAG. 103 - Tipi.cpp

```c assegnazione.cpp
// asssegnazione.cpp
// Parcogiochi.cpp: divisione dei biglietti
#include <iostream>
using namespace std;

int main () 
{
  // input
  int biglietti, ragazzi;
  // output
  int quota, avanzo;

  cout << "Numero di biglietti e di ragazzi: ";
  cin >> biglietti >> ragazzi;
  quota = biglietti / ragazzi;
  avanzo = biglietti % ragazzi;
  cout << "Ad ogni ragazzo spettano " << quota << " biglietti " << endl;
  cout << "e ne avanzano " << avanzo << endl;

  return 0;
}
```
@LIA.cpp
 
#### 1. Predict 
con quota si troverranno i numeri di biglietti che ha una persona e con l'avanzo è quello che rimane dolo pa divisione dei blieglietti / ragazzi

#### 2. Run
Il programma farà vedere il risultato trovato

#### 3. Investigate

<iframe width="800" height="500" frameborder="0" src="https://pythontutor.com/iframe-embed.html#code=%23include%20%3Ciostream%3E%0Ausing%20namespace%20std%3B%0A%0Aint%20main%20%28%29%20%0A%7B%0A%20%20//%20input%0A%20%20int%20biglietti%20%3D%2010,%20ragazzi%20%3D%203%3B%0A%20%20//%20output%0A%20%20int%20quota,%20avanzo%3B%0A%0A%20%20quota%20%3D%20biglietti%20/%20ragazzi%3B%0A%20%20avanzo%20%3D%20biglietti%20%25%20ragazzi%3B%0A%20%20cout%20%3C%3C%20%22Ad%20ogni%20ragazzo%20spettano%20%22%20%3C%3C%20quota%20%3C%3C%20%22%20biglietti%20%22%20%3C%3C%20endl%3B%0A%20%20cout%20%3C%3C%20%22e%20ne%20avanzano%20%22%20%3C%3C%20avanzo%20%3C%3C%20endl%3B%0A%0A%20%20return%200%3B%0A%7D&codeDivHeight=400&codeDivWidth=350&cumulative=false&curInstr=4&heapPrimitives=nevernest&origin=opt-frontend.js&py=cpp_g%2B%2B9.3.0&rawInputLstJSON=%5B%5D&textReferences=false"> </iframe>

#### 4. Modify

```c assegnazione.cpp
// asssegnazione.cpp
#include <iostream>
using namespace std;

int main () 
{
  int biglietti, ragazzi;
  int quota, avanzo;

  cout << "Numero di biglietti e di ragazzi: ";
  cin >> biglietti >> ragazzi;

  quota = biglietti / ragazzi;
  avanzo = biglietti % ragazzi;

  int distribuiti = quota * ragazzi;

  cout << "Ad ogni ragazzo spettano " << quota << " biglietti " << endl;
  cout << "e ne avanzano " << avanzo << endl;
  cout << "Totale biglietti distribuiti: " << distribuiti << endl;

  return 0;
}
```
@LIA.cpp


#### 5. Make 

```c assegnazione.cpp
// asssegnazione.cpp
#include <iostream>
using namespace std;

int main () 
{
  int biglietti, ragazzi;
  int quota, avanzo;

  cout << "Numero di biglietti e di ragazzi: ";
  cin >> biglietti >> ragazzi;

  // Calcolo per gruppi di 2 ragazzi
  quota = biglietti / (2 * ragazzi);
  avanzo = biglietti % (2 * ragazzi);

  cout << "Ad ogni coppia di ragazzi spettano " << quota << " biglietti " << endl;
  cout << "e ne avanzano " << avanzo << endl;

  return 0;
}
```
@LIA.cpp

### PROGRAMMA A PAG. 103 - Tipi.cpp

```c assegnazione.cpp
// asssegnazione.cpp
// Quoziente.cpp : divisione di due numeri
#include <iostream>
using namespace std;

int main () 
{
 int a, b, q;
 cin >> a >> b;
 q = a / b;
 cout << q;

 return 0;
}
```
@LIA.cpp

#### 1. Predict
a, b, avranno due numeri interi e la quota mi darà la divisione dei due numeri

#### 2. Run
il programma stamperà il valore della quota

#### 3. Investigate 

<iframe width="800" height="500" frameborder="0" src="https://pythontutor.com/iframe-embed.html#code=//%20Quoziente.cpp%20%3A%20divisione%20di%20due%20numeri%0A%23include%20%3Ciostream%3E%0Ausing%20namespace%20std%3B%0A%0Aint%20main%20%28%29%20%0A%7B%0A%20int%20a%20%3D%20300%3B%0A%20int%20b%20%3D%205%3B%20%0A%20int%20q%20%3D%2060%3B%0A%0A%20return%200%3B%0A%7D&codeDivHeight=400&codeDivWidth=350&cumulative=false&curInstr=4&heapPrimitives=nevernest&origin=opt-frontend.js&py=cpp_g%2B%2B9.3.0&rawInputLstJSON=%5B%5D&textReferences=false"> </iframe>

#### 4. Modify

```c assegnazione.cpp
// asssegnazione.cpp
#include <iostream>
using namespace std;

int main () 
{
    int a, b, q, resto;
    cin >> a >> b;
    q = a / b;
    resto = a % b;

    cout << q <<;
    cout << resto;

    return 0;
}
```
@LIA.cpp

#### 5. Make 

```c assegnazione.cpp
// asssegnazione.cpp
#include <iostream>
using namespace std;

int main () 
{
    float a, b, q;
    cin >> a >> b;
    q = a / b;
    cout <<  q;

    return 0;
}
```
@LIA.cpp

### PROGRAMMA A PAG. 106 - Tipi.cpp

```c assegnazione.cpp
// asssegnazione.cpp
// Differenza.cpp: differenza tra due numeri 
#include <iostream>
using namespace std;
int main () 
{
int num1, num2, differenza 
cout << "Due numeri: "; 
cin >> num1 >> num2; 
differenza = num1 - num2;
cout << "Risultato = " << differenza << endl return 0;

return 0
}
```
@LIA.cpp

#### 1. Predict
quando verranno dati i valori a num1, num2, si torverà il valore della differenza

#### 2. Run
Il programma scirverà l'equivalente della differenza

#### 3. Investigate

#### 4. Modify

```c assegnazione.cpp
// asssegnazione.cpp
#include <iostream>
using namespace std;

int main () 
{
    int num1, num2, differenza;
    cout << "Due numeri: ";
    cin >> num1 >> num2;
    differenza = num1 - num2;

    cout << "Differenza = " << differenza << endl;
    cout << "Differenza assoluta = " << abs(differenza) << endl;

    return 0;
} 
```
@LIA.cpp
        
#### 5. Make

```c assegnazione.cpp
// asssegnazione.cpp
#include <iostream>
using namespace std;

int main () 
{
    int num1, num2, somma, differenza;
    cout << "Due numeri: ";
    cin >> num1 >> num2;

    somma = num1 + num2;
    differenza = num1 - num2;

    cout <<  somma ;
    cout <<differenza;

    return 0;
} 
```
@LIA.cpp

### PROGRAMMA A PAG. 107 - Tipi.cpp

```c assegnazione.cpp
// asssegnazione.cpp
// CalcoloSconto.cpp calcolo del prezzo scontato
 #include <iostream>
 #include <string>

using  namespace std;
const int PERC = 20;

int main() 
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
  cout << descrizione << ":" << prezzo << endl;

  return 0;
}
```
@LIA.cpp

#### 1. Predict
gli verrà dato la descrizione dell'oggetto e il prezzo
    
#### 2. Run
il programma stamperà la descrizione e il suo valore
    
#### 3. Investigate

<iframe width="800" height="500" frameborder="0" src="https://pythontutor.com/iframe-embed.html#code=%20%23include%20%3Ciostream%3E%0A%20%23include%20%3Cstring%3E%0A%0Ausing%20%20namespace%20std%3B%0Aconst%20int%20PERC%20%3D%2020%3B%0A%0Aint%20main%28%29%20%0A%7B%0A%20%20//%20variabili%20di%20input-output%0A%20%20string%20descrizione%3B%0A%20%20float%20prezzo%20%3D%20125%3B%0A%20%20//%20variabili%20di%20lavoro%20%0A%20%20float%20sconto%3B%0A%0A%20%20%0A%20%20sconto%20%3D%20prezzo%20*%20PERC%20/%20100%3B%0A%20%20prezzo%20%3D%20prezzo%20-%20sconto%3B%0A%20%0A%0A%20%20return%200%3B%0A%7D&codeDivHeight=400&codeDivWidth=350&cumulative=false&curInstr=6&heapPrimitives=nevernest&origin=opt-frontend.js&py=cpp_g%2B%2B9.3.0&rawInputLstJSON=%5B%5D&textReferences=false"> </iframe>

#### 4. Modify

```c assegnazione.cpp
// asssegnazione.cpp
#include <iostream>
#include <string>
using namespace std;

const int PERC = 20;

int main() 
{
    string descrizione;
    float prezzo;
    float sconto;

    cout << "Descrizione e prezzo: ";
    cin >> descrizione >> prezzo;

    sconto = prezzo * PERC / 100;
    prezzo = prezzo - sconto;

    cout << descrizione << ":" << prezzo << endl;
    cout << "Sconto applicato: " << sconto << endl;

    return 0;
}
```
@LIA.cpp
     
#### 5. Make

```c assegnazione.cpp
// asssegnazione.cpp
#include <iostream>
#include <string>
using namespace std;

int main() 
{
    string descrizione;
    float prezzo, scontoPerc, sconto;

    cout << "Descrizione, prezzo e percentuale di sconto: ";
    cin >> descrizione >> prezzo >> scontoPerc;

    sconto = prezzo * sconto Perc / 100;
    prezzo = prezzo - sconto;

    cout << descrizione << ":" << prezzo << endl;
    cout << "Sconto applicato: " << sconto << endl;

    return 0;
}
```
@LIA.cpp

### PROGRAMMA A PAG. 109 - Tipi.cpp

```c assegnazione.cpp
// asssegnazione.cpp
// Ordina.cpp: due numeri in ordine crescente

#include<iostream>
using namespace std;

int main() 
{
  //input
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


#### 1. Predict
Chiede due numeri, controlla quale dei due è più piccolo e li stampa in ordine crescente.
    
#### 2. Run
Il programma scriverà i numeri naturali in ordine crescente

#### 3. Investigate 
#### 4. Modifiy

```c assegnazione.cpp
// asssegnazione.cpp
#include<iostream>
using namespace std;

int main() 
{
    int a, b;

    cout << "Due numeri: ";
    cin >> a >> b;

    if (a < b) {
        cout << a << endl;
        cout << b << endl;
    }
    else if (a > b) {
        cout << b << endl;
        cout << a << endl;
    }
    else {
        cout << "I due numeri sono uguali: " << a << endl;
    }

    return 0;
}
```
@LIA.cpp
       
#### 5. Make

```c assegnazione.cpp
// asssegnazione.cpp
 #include <iostream>
using namespace std;

int main() 
{
    int a, b, c;

    cout << "Tre numeri: ";
    cin >> a >> b >> c;

    // Ordine crescente
    if (a > b) swap(a, b);
    if (a > c) swap(a, c);
    if (b > c) swap(b, c);

    cout << a << endl;
    cout << b << endl;
    cout << c << endl;

    return 0;
}
```
@LIA.cpp


### PROGRAMMA A PAG. 110 - Tipi.cpp

```c assegnazione.cpp
// asssegnazione.cpp
// TreXDue.cpp: offerta 3 x 2

#include<iostream>
using namespace std;

int main() 
{
  // input
  float prezzo;
  int qta;
  // output
  float importo;

  cout << "Prezzo e quantità': ";
  cin >> prezzo >> qta;
  if (qta == 3) qta = 2;
  importo = prezzo * qta;
  cout << "Importo da pagare = " << importo << endl;

  return 0;
}
```
@LIA.cpp

#### 1. Predict
Il programma applica l’offerta 3×2,quindi se compri 3 pezzi, ne paghi solo 2.
    
#### 2. Run
il programma produce il risultato previsto.
   
####  3. Investigate

<iframe width="800" height="500" frameborder="0" src="https://pythontutor.com/iframe-embed.html#code=%23include%3Ciostream%3E%0Ausing%20namespace%20std%3B%0A%0Aint%20main%28%29%20%0A%7B%0A%20%20//%20input%0A%20%20float%20prezzo%20%3D%204.50%3B%0A%20%20int%20qta%20%3D%2015%3B%0A%20%20//%20output%0A%20%20float%20importo%3B%0A%0A%20%0A%20%20importo%20%3D%20prezzo%20*%20qta%3B%0A%20%20cout%20%3C%3C%20%22Importo%20da%20pagare%20%3D%20%22%20%3C%3C%20importo%20%3C%3C%20endl%3B%0A%0A%20%20return%200%3B%0A%7D&codeDivHeight=400&codeDivWidth=350&cumulative=false&curInstr=4&heapPrimitives=nevernest&origin=opt-frontend.js&py=cpp_g%2B%2B9.3.0&rawInputLstJSON=%5B%5D&textReferences=false"> </iframe>
   
#### 4. Modify

```c assegnazione.cpp
// asssegnazione.cpp
#include<iostream>
using namespace std;

int main() 
{
    float prezzo;
    int qta;
    float importo;

    cout << "Prezzo e quantita': ";
    cin >> prezzo >> qta;

    if (qta == 3) {
        cout << "Offerta 3x2 applicata!" << endl;
        qta = 2;
    }

    importo = prezzo * qta;
    cout << "Importo da pagare = " << importo << endl;

    return 0;
}
```
@LIA.cpp
   
#### 5. Make

```c assegnazione.cpp
// asssegnazione.cpp
#include<iostream>
using namespace std;

int main()
{
    float prezzo;
    int qta;
    float importo;

    cout << "Prezzo e quantita': ";
    cin >> prezzo >> qta;

    // Offerta 3x2
    if (qta == 3) 
        qta = 2;

    importo = prezzo * qta;

    // Sconto aggiuntivo
    if (importo > 20) {
        importo = importo * 0.90; // 10% di sconto
    }

    cout << "Importo finale = " << importo << endl;

    return 0;
}
```
@LIA.cpp

### PROGRAMMA A PAG. 112 - Tipi.cpp

```c assegnazione.cpp
// asssegnazione.cpp
// Prodotto.cpp: prodotto di due numeri

#include<iostream>
using namespace std;

int main () 
{
  // input 
  int a, b;
  // output
  int prod = 0;

  cout << "Due numeri: ";
  cin >> a >> b;
  do {
     prod += a;
     b--;
  } while (b > 0 );

  cout << "Prodotto = " << prood << endl;

  return 0;
}
```
@LIA.cpp

#### 1. Predict
Il programma calcola il prodotto
    
#### 2. Run
Il programma stamperà il risultato
#### 3. Investigate
   
#### 4. Modify

 ```c assegnazione.cpp
// asssegnazione.cpp   
#include<iostream>
using namespace std;

int main () 
{
    int a, b;
    int prod = 0;

    cout << "Due numeri: ";
    cin >> a >> b;

    if (b <= 0) {
        cout << "La quantità deve essere maggiore di 0!" << endl;
        return 0;
    }

    do {
        prod += a;
        b--;
    } while (b > 0);

    cout << "Prodotto = " << prod << endl;

    return 0;
}
```
@LIA.cpp
    
#### 5. Make

```c assegnazione.cpp
// asssegnazione.cpp
#include<iostream>
using namespace std;

int main()
{
    int a, b, quoziente = 0;

    cout << "Due numeri: ";
    cin >> a >> b;

    while (a >= b) {
        a -= b;
        quoziente++;
    }

    cout << "Quoziente = " << quoziente << endl;

    return 0;
}
```
@LIA.cpp

### PROGRAMMA A PAG.. 115 - Tipi.cpp

```c assegnazione.cpp
// asssegnazione.cpp
// Divisione.cpp: divisione tra interi con sottrazioni succesive

#include<iostream>
using namespace std;

int main() 
{
  // input
  int a, b;
  // output
  int quoz = 0;  // quoziente della divisione tra interi

  cout << "Due numeri (dividendo e divisore): ";
  cin >> a >> b;
  while (a >= b) {
     a -=b;
     quoz++;
}

cout << "Quoziente = " << quoz << endl;
cout << "Resto     = " << a << endl;

return 0;
  
}
```
@LIA.cpp

#### 1. Predict
divisione tra interi usando sottrazioni successive
    
#### 2. Run
Il programma esegue il calcolo

#### 3. Investigate

<iframe width="800" height="500" frameborder="0" src="https://pythontutor.com/iframe-embed.html#code=%0A%23include%3Ciostream%3E%0Ausing%20namespace%20std%3B%0A%0Aint%20main%28%29%20%0A%7B%0A%20%20//%20input%0A%20%20int%20a%20%3D%2030%3B%20%0A%20%20int%20b%20%3D%2010%3B%0A%20%20//%20output%0A%20%20int%20quoz%20%3D%203%3B%20%20//%20quoziente%20della%20divisione%20tra%20interi%0A%0A%20%20cout%20%3C%3C%20%22Due%20numeri%20%28dividendo%20e%20divisore%29%3A%20%22%3B%0A%20%20cin%20%3E%3E%20a%20%3E%3E%20b%3B%0A%20%20while%20%28a%20%3E%3D%20b%29%20%7B%0A%20%20%20%20%20a%20-%3Db%3B%0A%20%20%20%20%20quoz%2B%2B%3B%0A%7D%0A%0Acout%20%3C%3C%20%22Quoziente%20%3D%20%22%20%3C%3C%20quoz%20%3C%3C%20endl%3B%0Acout%20%3C%3C%20%22Resto%20%20%20%20%20%3D%20%22%20%3C%3C%20a%20%3C%3C%20endl%3B%0A%0Areturn%200%3B%0A%20%20%0A%7D&codeDivHeight=400&codeDivWidth=350&cumulative=false&curInstr=11&heapPrimitives=nevernest&origin=opt-frontend.js&py=cpp_g%2B%2B9.3.0&rawInputLstJSON=%5B%5D&textReferences=false"> </iframe>
   
#### 4. Modify

```c assegnazione.cpp
// asssegnazione.cpp
#include<iostream>
using namespace std;

int main() 
{
    int a, b;
    int quoz = 0;

    cout << "Due numeri (dividendo e divisore): ";
    cin >> a >> b;

    if (b == 0) {
        cout << "Errore: divisione per zero!" << endl;
        return 0;
    }

    while (a >= b) {
        a -= b;
        quoz++;
    }

    cout << quoz << endl;
    cout << a << endl;

    return 0;
}
```
@LIA.cpp
    
#### 5. Make

```c assegnazione.cpp
// asssegnazione.cpp
#include<iostream>
using namespace std;

int main()
{
    int a, b, prod = 0;

    cout << "Due numeri: ";
    cin >> a >> b;

    while (b > 0) {
        prod += a;
        b--;
    }

    cout << "Prodotto = " << prod << endl;

    return 0;
}
```
@LIA.cpp


### PROGRAMMA A PAG. 118 - Tipi.cpp

```c assegnazione.cpp
// asssegnazione.cpp
// Doppio.cpp: doppio dei primi 30 numeri naturali
#include <iostream>
using namespace std;

int main()
{
  for (int i=1; i<=30; i++) {
      cout << i*2 << endl;
    
}

return 0;

}
```
@LIA.cpp


#### 1. Predict
Il programma dichiara una variabile. Legge il numero e lo moltiplica
    
#### 2. Run
Il programma deve stampare il doppio dei numeri naturali da 1 a 30.
    
#### 3. Investigate

<iframe width="800" height="500" frameborder="0" src="https://pythontutor.com/iframe-embed.html#code=%23include%20%3Ciostream%3E%0Ausing%20namespace%20std%3B%0A%0Aint%20main%28%29%0A%7B%0A%20%20for%20%28int%20i%3D1%3B%20i%3C%3D30%3B%20i%2B%2B%29%20%7B%0A%20%20%20%20%20%20cout%20%3C%3C%20i*2%20%3C%3C%20endl%3B%0A%20%20%20%20%0A%7D%0A%0Areturn%200%3B%0A%0A%7D&codeDivHeight=400&codeDivWidth=350&cumulative=false&curInstr=63&heapPrimitives=nevernest&origin=opt-frontend.js&py=cpp_g%2B%2B9.3.0&rawInputLstJSON=%5B%5D&textReferences=false"> </iframe>
    
#### 4. Modify

```c assegnazione.cpp
// asssegnazione.cpp
// Doppio.cpp: doppio dei primi 30 numeri naturali
#include <iostream>
    using namespace std;

int main()
{
    for (int i = 1; i <= 30; i++) 
    cout << i << " -> " << i*2 << endl;
}
```
@LIA.cpp
  
#### 5. Make

```c assegnazione.cpp
// asssegnazione.cpp
#include <iostream>
using namespace std;

int main()
{
    for (int i = 1; i <= 20; i++) {
        cout << i * 3 << endl;
    }

    return 0;
}
```
@LIA.cpp

### PROGRAMMA A PAG. 118 - Tipi.cpp

```c assegnazione.cpp
// asssegnazione.cpp
// TavolaPitagorica.cpp
#include <iostream>
#include <iomanip>
using namespace std;
int main()
{
  for (int r=1; r<=10; r++) {
     for (int c=1; c<=10; c++) {
        cout << setw(5) << r*c;
     }
     cout << endl;
}

return 0;
}
```
@LIA.cpp


#### 1. Predict
Il programma deve stampare la tavola pitagorica da 1×1 a 10×10

#### 2. Run
Esegue il programma, quindi svolge le moltiplicazioni

#### 3. Investigate

#### 4. Modify

```c assegnazione.cpp
// asssegnazione.cpp
// TavolaPitagorica.cpp
#include <iostream>
#include <iomanip>
using namespace std;

int main()
{
    for (int r = 1; r <= 20; r++) {
        for (int c = 1; c <= 20; c++) {
            cout << setw(5) << r * c;
        }
        cout << endl;
    }

    return 0;
}
    cout << "     ";
for (int c = 1; c <= 10; c++) {
    cout << setw(5) << c;
}
cout << endl;

for (int r=1; r<=10; r++) {
    cout << setw(3) << r << " | ";
    for (int c=1; c<=10; c++) {
        cout << setw(5) << r*c;
    }
    cout << endl;
}
```
@LIA.cpp

#### 5. Make

```c assegnazione.cpp
// asssegnazione.cpp
#include <iostream>
#include <iomanip>
using namespace std;

int main()
{
    int n;
    cout << "Fino a che numero vuoi la tavola pitagorica? ";
    cin >> n;

    for (int r = 1; r <= n; r++) {
        for (int c = 1; c <= n; c++) {
            cout << setw(5) << r*c;
        }
        cout << endl;
    }

    return 0;
}
```
@LIA.cpp

### PROGRAMMA A PAG. 119 - Tipi.cpp

```c assegnazione.cpp
// asssegnazione.cpp
// Massimo.ccp: massimo di n numeri

#include <iostream>
using namespace std;

int main()
{
  // input 
  int n;                 // numero dei dati inseriti
  int dato;              // dato inserito
  // output
  int max;               // massimo

  cout << " Quanti sono i dati? ";
  cin >> n;
  for (int i=1; i<=n; i++) {
     cout << "Inserisci il "<< i << ". dato: ";
     cin >> dato;
     if (i == 1) max = dato;
     if (dato > max) max = dato;
}

cout << "Il massimo valore e' " << max << endl;

return 0;

}
```
@LIA.cpp

#### 1. Predict
Il programma deve: chiedere quanti numeri inserire (n),leggere n numeri uno alla volta, confrontarli e tenere il massimo e stampare il numero più grande

#### 2. Run
a goni n viene assegnato un valore e trovare il valore massimo

#### 3. Investigate 
    
#### 4. Modify

```c assegnazione.cpp
// asssegnazione.cpp
/ Massimo_Minimo_Modify.cpp
#include <iostream>
using namespace std;

int main()
{
    int n, dato;
    int max, min;

    cout << "Quanti sono i dati? ";
    cin >> n;

    for (int i = 1; i <= n; i++) {
        cout << "Inserisci il " << i << ". dato: ";
        cin >> dato;

        if (i == 1) {
            max = dato;
            min = dato;
        }

        if (dato > max) max = dato;
        if (dato < min) min = dato;
    }

    cout << "Massimo = " << max << endl;
    cout << "Minimo  = " << min << endl;

    return 0;
}
```
@LIA.cpp


#### 5. Make

```c assegnazione.cpp
// asssegnazione.cpp
// Media.cpp: calcola la media di n numeri

#include <iostream>
using namespace std;

int main()
{
    int n, dato;
    int somma = 0;

    cout << "Quanti numeri vuoi inserire? ";
    cin >> n;

    for (int i = 1; i <= n; i++) {
        cout << "Inserisci il " << i << ". numero: ";
        cin >> dato;
        somma += dato;
    }

    cout << "La media è: " << (somma / (float)n) << endl;

    return 0;
}
```
@LIA.cpp

### PROGRAMMA A PAG. 121 - Tipi.cpp

```c assegnazione.cpp
// asssegnazione.cpp
// ScontoProgressivo.cpp: sconto progressivo sui prodotti

#include <iostream>
using namespace std;

int main()
{
    // input
    float prezzo;                 // prezzo del prodotto 
    int pezzi;                    // pezzi acquistati 
    // output
    float importo;                // importo da pagare 
    // lavoro
    int sconto;                   // percentuale di sconto

    cout << "Pezzi acquistati: ";
    cin >> pezzi;
    cout << "Prezzo del prodotto: ";
    cin >> prezzo;
    switch(pezzi) {
    case 1:
    case 2:
    case 3:
       sconto = 5;
       break;
case 4:
case 5:
       sconto = 10;
       break;
case 6:
case 7:
case 8:
case 9:
case 10:
       sconto = 20;
       break;
default:
       sconto = 30;
}
importo = pezzi * prezzo * (100.0-sconto)/100.0;
cout << "Importo da pagare = " << importo << endl;
return 0;
}
```
@LIA.cpp


#### 1. Predict
Il programma,leggerà quanti pezzi vengono acquistati poi legge il prezzo di un singolo prodotto e in base al numero di pezzi, assegna una percentuale di sconto:
    
#### 2. Run 
il programma esegue il codice e troverà l'importo da pagare
    
#### 3. Inevstigate
    
#### 4. Modify

```c assegnazione.cpp
// asssegnazione.cpp
    // ScontoProgressivo_Modify.cpp
#include <iostream>
using namespace std;

int main()
{
    float prezzo;
    int pezzi;
    float importo;
    int sconto;

    cout << "Pezzi acquistati: ";
    cin >> pezzi;
    cout << "Prezzo del prodotto: ";
    cin >> prezzo;

    switch(pezzi) {
        case 1:
        case 2:
        case 3: sconto = 5;  break;
        case 4:
        case 5: sconto = 10; break;
        case 6:
        case 7:
        case 8:
        case 9:
        case 10: sconto = 20; break;
        default: sconto = 30;
    }

    importo = pezzi * prezzo * (100.0 - sconto) / 100.0;

    cout << sconto << endl;
    cout << importo << endl;

    return 0;
}
```
@LIA.cpp
    
#### 5. Make

```c assegnazione.cpp
// asssegnazione.cpp
// ScontoImporto.cpp
#include <iostream>
using namespace std;

int main()
{
    float importo;
    int sconto;

    cout << "Totale spesa: ";
    cin >> importo;

    if (importo < 50)        sconto = 5;
    else if (importo < 100)  sconto = 10;
    else if (importo < 200)  sconto = 15;
    else                     sconto = 25;

    float finale = importo * (100 - sconto) / 100.0;

    cout << "Sconto applicato = " << sconto << "%" << endl;
    cout << "Importo finale = " << finale << endl;

    return 0;
}
```
@LIA.cpp


