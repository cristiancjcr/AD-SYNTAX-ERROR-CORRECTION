# PA-Syntax-Error-Correction

## Enunțul problemei
Avem sarcina de a dezvolta un algoritm pentru un editor de cod avansat care să corecteze automat erorile de sintaxă din limbajele de programare. Se presupune că primim o specificație clară a sintaxei valide a limbajului de programare sub forma unei "reguli" și un fragment de cod care conține erori de sintaxă, adică nu se conformează acelei reguli.
Obiectivul nostru este să construim un algoritm care să determine numărul minim de operații necesare pentru a transforma fragmentul de cod într-unul care respectă regula dată. Aceste operații pot include substituiri de caractere, inserții sau ștergeri.

Să luăm un exemplu concret pentru a ilustra problema: să presupunem că avem următoarea regulă de sintaxă pentru declarațiile de funcții în limbajul de programare:
"Fiecare funcție trebuie să înceapă cu cuvântul cheie „func”, urmat de numele funcției închis între paranteze."
Un exemplu de declarație de funcție validă ar fi „func(myFunction)”.
Fragmentul de cod dat: „fnuc(myFuncion”

Obiectivul nostru este să găsim numărul minim de operații necesare pentru a corecta fragmentul de cod astfel încât să se potrivească cu modelul definit de regulă. Aceste operații pot include, de exemplu, inversarea caracterelor „n” și „u” pentru a obține „func”, apoi inserția caracterelor lipsă „t” și „)”, astfel încât să obținem „func(myFunction)” conform regulii date.

## Descrierea problemei

În cadrul acestui proiect, trebuie să dezvoltăm un algoritm pentru un editor de cod avansat, având ca scop corectarea automată a erorilor de sintaxă din limbajele de programare. Acest algoritm primește două intrări esențiale: o specificație clară a sintaxei valide a limbajului de programare sub forma unei "reguli" și un fragment de cod care nu respectă această regulă.

Obiectivul nostru este să determinăm numărul minim de operații necesare pentru a transforma fragmentul de cod dat într-unul care să respecte regula specificată. Aceste operații pot include substituiri de caractere, inserții sau ștergeri.

Pentru a ilustra această problemă, să considerăm un exemplu concret: presupunem că avem o regulă de sintaxă pentru declarațiile de funcții într-un limbaj de programare, conform căreia fiecare funcție trebuie să înceapă cu cuvântul cheie "func", urmat de numele funcției închis între paranteze. Dacă avem un fragment de cod care nu respectă această regulă, cum ar fi "fnuc(myFuncion", obiectivul nostru este să determinăm numărul minim de operații necesare pentru a-l corecta conform regulii date.
Pentru a realiza acest lucru, algoritmul nostru va trebui să compare fragmentul de cod dat cu regulile de sintaxă specificate și să identifice și să efectueze operațiile necesare pentru a corecta orice discrepanțe. Aceste operații pot include inversarea caracterelor, inserții de caractere lipsă sau ștergeri.

Scopul final este de a ajunge la un fragment de cod care respectă regulile de sintaxă, folosind cel mai mic număr posibil de operații. Acest lucru va asigura că fragmentul de cod corectat este funcțional și poate fi folosit corespunzător în cadrul limbajului de programare dat. Prin abordarea acestei probleme, ne propunem să dezvoltăm un algoritm eficient și precis, care să faciliteze procesul de corectare a erorilor de sintaxă din codul sursă, contribuind astfel la îmbunătățirea calității și eficienței dezvoltării software.
