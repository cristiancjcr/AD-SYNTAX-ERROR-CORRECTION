# PA - SYNTAX ERROR CORRECTION

## ENUNȚUL PROBLEMEI :
Avem sarcina de a dezvolta un algoritm pentru un editor de cod avansat care să corecteze automat erorile de sintaxă din limbajele de programare. Se presupune că primim o specificație clară a sintaxei valide a limbajului de programare sub forma unei "reguli" și un fragment de cod care conține erori de sintaxă, adică nu se conformează acelei reguli.
Obiectivul nostru este să construim un algoritm care să determine numărul minim de operații necesare pentru a transforma fragmentul de cod într-unul care respectă regula dată. Aceste operații pot include substituiri de caractere, inserții sau ștergeri.

Să luăm un exemplu concret pentru a ilustra problema: să presupunem că avem următoarea regulă de sintaxă pentru declarațiile de funcții în limbajul de programare:
"Fiecare funcție trebuie să înceapă cu cuvântul cheie „func”, urmat de numele funcției închis între paranteze."

Un exemplu de declarație de funcție validă ar fi „func(myFunction)”. 

Fragmentul de cod dat: „fnuc(myFuncion”

Obiectivul nostru este să găsim numărul minim de operații necesare pentru a corecta fragmentul de cod astfel încât să se potrivească cu modelul definit de regulă. Aceste operații pot include, de exemplu, inversarea caracterelor „n” și „u” pentru a obține „func”, apoi inserția caracterelor lipsă „t” și „)”, astfel încât să obținem „func(myFunction)” conform regulii date.


## DESCRIEREA PROBLEMEI :

În cadrul acestui proiect, trebuie să dezvoltăm un algoritm pentru un editor de cod avansat, având ca scop corectarea automată a erorilor de sintaxă din limbajele de programare. Acest algoritm primește două intrări esențiale: o specificație clară a sintaxei valide a limbajului de programare sub forma unei "reguli" și un fragment de cod care nu respectă această regulă.

Obiectivul nostru este să determinăm numărul minim de operații necesare pentru a transforma fragmentul de cod dat într-unul care să respecte regula specificată. Aceste operații pot include substituiri de caractere, inserții sau ștergeri.
Pentru a realiza acest lucru, algoritmul nostru va trebui să compare fragmentul de cod dat cu regulile de sintaxă specificate și să identifice și să efectueze operațiile necesare pentru a corecta orice discrepanțe. Aceste operații pot include inversarea caracterelor, inserții de caractere lipsă sau ștergeri.

Scopul final este de a ajunge la un fragment de cod care respectă regulile de sintaxă, folosind cel mai mic număr posibil de operații. Acest lucru va asigura că fragmentul de cod corectat este funcțional și poate fi folosit corespunzător în cadrul limbajului de programare dat. Prin abordarea acestei probleme, ne propunem să dezvoltăm un algoritm eficient și precis, care să faciliteze procesul de corectare a erorilor de sintaxă din codul sursă, contribuind astfel la îmbunătățirea calității și eficienței dezvoltării software.


## EXEMPLU, IDEI & SOLUȚII :
Un exemplu clar este chiar cel din enunț, ce prezintă inversarea și apoi inserția unor caractere pentru ca la final să obținem varianta corectă.

Pentru verificarea corectitudinii codului, exemplele ce se pot verifica sunt la alegerea utilizatorului fiind restricționat doar de lungimea cuvintelor, ce trebuie să fie mai mari sau egale cu 2 (ex: eu, tu, up, go ..șamd) putând ca un exemplu să ajungă și la 10 / 11 litere pentru verificare (ex: experiment, decizional, perspective). Dar fi atent ! Orice cuvânt ce are o lungime mai mare devine mai greu de inspectat de utilizator care nu poate verifica în totalitate corectitudinea programului.

Pentru a reusi sa ducem la bun sfarsit un astfel de program am folosit 3 functii principale :

**select_words(num_letters)** <-> **levenshtein_distance(s1, s2)** <-> **main( )**. 

Funcția 'select_words(num_letters)' afișează utilizatorului o listă de cuvinte din care acesta poate alege, acele cuvinte având o anumită lungime specificată de 'num_letters'. Cu toate că funcția nu întoarce nimic, ea afișează lista de cuvinte care corespund criteriului de lungime.

Funcția 'levenshtein_distance(s1, s2)' implementează algoritmul de distanță Levenshtein între două șiruri de caractere s1 și s2. Această distanță reprezintă numărul minim de operații (inserare, ștergere sau înlocuire a unui singur caracter) necesare pentru a transforma un șir în celălalt. Algoritmul funcționează prin utilizarea unei matrice pentru a calcula costurile transformărilor și găsirea căii cu cel mai mic cost.

Funcția 'main()' este punctul de intrare în program și gestionează interacțiunea cu utilizatorul. În primul rând, solicită utilizatorului să introducă numărul dorit de litere pentru cuvânt. Apoi, afișează cuvintele disponibile de acea lungime. Utilizatorul este rugat să introducă cuvântul ales și o versiune incorectă a acelui cuvânt. Apoi, calculează și afișează distanța Levenshtein dintre cele două cuvinte introduse.

În esență, acest cod permite utilizatorului să exploreze conceptul de distanță Levenshtein, care este util în diverse domenii, cum ar fi corectarea ortografică, recunoașterea vocală și bioinformatică.

> [!NOTE]
Un exemplu testat de mine ar fi pentru lungimea 4, selectând apoi opțiunea 'corectă': **func(book)**. Testând această opțiune 'corectă' cu opțiunea pusă de utilizator la tastatură **"func(bocker)"**. În urma verificării s-a afișat **3**, s-a înlocuit *'c-ul'* cu *'o'*, iar *'e'* & *'r'* au fost eliminate pentru a ajunge la varianta inițială (corectă).


## UTILIZARE :
Pentru a utiliza acest program, rog descărcarea într-un folder a fișierelor cu numele: **"TEMA_PA.cbp", "TEMA_PA.depend", "TEMA_PA.layout", "main.c", "word_selector.c", "word_selector.h"** (pentru limbaj C). 

Pentru rularea corectă a programului, trebuie deschis fișierul cu numele **"TEMA_PA.cbp"** ce va deschide întregul program gata de rulat/testat. În caz contrar, deschideți mai întâi **"main.c"**, apoi **"word_selector.c"** urmat de **"word_selector.h"**. 

Programul va solicita mai întâi introducerea lungimii dorite pentru cuvintele pe care doriți să le testați. Programul va afișa o listă generată ce îndeplinește cerința (lungimea N / ex: 5). 

O să fiți rugat să alegeți una din opțiunile afișate, prin scrierea la tastatură a opțiunii alese (ex: *'func(lemon)'*). Programul va cere apoi să introduceți la tastatură o variantă 'greșită' a opțiunii alese anterior (ex: *'func(lebron'*). După introducerea datelor, programul va afișa numărul minim de operații pentru a transforma varianta 'greșită' în varianta 'corectă' (ex: *3*).

> [!IMPORTANT]
Pentru utilizarea programului în limbaj **Python**, rog descărcarea fișierului: **"main.py"** . Utilizarea programului în **Python** este identică cu cea din **'C'**.


## CONTRIBUȚII
Proiect realizat de **Cristian Florin Cojocaru** (student **CR.1** - **Universitatea din Craiova / Facultatea de Automatică, Calculatoare şi Electronică**). Contribuțiile sunt binevenite ! Dacă aveți sugestii de îmbunătățire a codului sau a documentației, vă rog să trimiteți un pull request.


## LICENȚĂ
Acest proiect este licențiat sub [MIT License](LICENSE).
