    Explicatii rezolvari tema 2

    Taskul 1

Verificarea imparitatii elementului prin operatia and 1.
Daca elementul este impar, ultimul bit va fi 1, astfel
element & 1 va da mereu 1. Daca un element este o putere
de a lui 2, echivalentul sau in baza 2 va fi un singur 1
urmat de 0, deci daca scadem 1, echivalentul se va
transforma intr-o insiruire de 1, aplicand and va da 1.

    Taskul 2

2.1 Mai intai se testeaza validitatea anului, care e cel
mai simplu de obtinut, apoi cea a lunii. Dupa ce obtinem
luna, luam caz special lunile cu 30 de zile si verificam
ziua. Luna februarie are si ea caz special. Daca a trecut
de toate aceste teste trebuie verificata doar ca ziua sa
fie intre 1 si 31.

2.2 Se face mai intai o ordonare dupa flagul de validitate,
iar celelalte sortari se fac doar in cazul in care flagurile
sunt egale. Mai intai se testeaza an, luna, zi si daca even
sunt in aceasi zi se testeaza numele printr-o implementare
a functiei strcmp, o comparatie byte by byte.
 Swapul se face byte by byte.

    Taskul 3

Cea mai mare problema a taskului 3 a fost operarea cu bytes,
de aceea am folosit adesea comanda movzx pentru a asigura
mutarea unui byte intr-un registru de 32. Codul e structu-
rat ca un for loop pentru a trece pe la fiecare 3 litere, 
urmand consecutiv pasii transformarii in base64. Pentru
transformarea in litere a fost pus la dispozitie alphabet
in sectiunea data. Pentru taierea registrelor in grupe de
6 biti am folosit adeasea and [registru], 63 deoarece 63 este
o insiruire de 6 biti de 1, in rest 0, reusind astfel sa taie
orice era inaintea celor 6 biti necesari.

    Taskul 4

Aici nu stiu de ce imi pica si pierd 5 puncte. Am incercat
2 abordari diferite la fiecare functie but alas.

Functia check row: verifica mai intai daca sunt gunoaie,
adica numere mai mari decat 9 sau mai mici decat 1.
Dupa aceea prin 2 for uri, al doilea incepand de la indexul 
primului verifica dubluri.

Functia check column: abordarea anterioara e prea dificila
de implementat pe coloane asa ca am decis sa incerc ordonarea
elementelor de pe coloana in ordine crescatoare prin bubble
sort. In cazul unor dubluri acestea ar fi pozitionate una dupa
alta, deci usor de gasit printr-o simpla iteratie finala.

Functia check box: mai intai folosim indexul dat pentru a afla
unde incepe cutia si mutam edi acolo. Avem un loop pentru 
un garbage check, iar apoi am modificat abordarea de la check 
row in cazul cutiei, mutarea de la o linie la alta facandu-se
mereu cand iteratorul ajungea la 2, sf primei linii, sau 5, sf 
celei de a doua. Pentru a muta se face operatiea add edi, 6
deoarece stim ca tabelul de sudoku este de 9x9. Cele doua foruri
au un edx unde este tinuta valoaea testata si un eax care va
creste de fiecare data cand gaseste edx. Cand eax e mai mare
decat 2 inseamna dublura.



