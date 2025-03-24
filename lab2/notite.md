📌 Explicație: Implementarea imaginii integrale și filtrului Lee

**1️⃣ Calculul imaginii integrale (img_integrala)

Această funcție creează o matrice de aceeași dimensiune ca imaginea inițială și calculează suma pixelilor de la colțul stânga-sus până la fiecare poziție  folosind trei metode diferite:

🔹 Metoda 1 (brute force cu for și np.sum)

Pentru fiecare pixel , face suma tuturor pixelilor de la  până la .

Ineficientă pentru imagini mari, deoarece recalculăm de fiecare dată întreaga sumă.

🔹 Metoda 2 (np.cumsum(), adică sumă cumulativă)

Se calculează întâi suma cumulativă pe linii, apoi pe coloane.

Mult mai rapidă, deoarece nu recalculăm sumă pentru fiecare pixel de la 0.

🔹 Metoda 3 (formulă optimizată)

Folosim formula eficientă:



Aceasta reduce complexitatea la  și este cea mai eficientă metodă pentru procesare imagini.

2️⃣ Calculul sumei într-un dreptunghi (suma_dreptunghi)

Folosind imaginea integrală, calculăm suma pixelilor dintr-o zonă dreptunghiulară cu formula:



unde:

 este colțul dreapta-jos al dreptunghiului

 este colțul stânga-sus

 este colțul dreapta-sus

 este colțul stânga-jos

✅ Această metodă permite calcularea instantanee a sumei pixelilor din orice dreptunghi din imagine, indiferent de dimensiune.

3️⃣ Filtrul Lee (filt_LEE)

Acest filtru reduce zgomotul în imagine.

🔹 Pașii algoritmului:

Calculăm media și varianța pixelilor într-o fereastră (ex: ).

Aplicăm formula:



unde:

 este media pixelilor



Dacă zgomotul e mare,  scade, păstrând mai mult din original.

Imaginea filtrată este returnată.

📌 Concluzii

✅ Metoda 2 și 3 pentru imaginea integrală sunt cele mai rapide.✅ Suma într-un dreptunghi se calculează instantaneu datorită imaginii integrale.✅ Filtrul Lee ajustează zgomotul adaptiv, fiind robust pentru imagini reale.

Dacă ai întrebări sau vrei optimizări, spune-mi! 🚀

