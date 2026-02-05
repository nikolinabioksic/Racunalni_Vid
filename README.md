# Racunalni_Vid
Python implementacija K-means algoritma za segmentaciju slike. Uključuje analizu optimalnog broja klastera koristeći WCSS (Elbow metodu) i Silhouette analizu.

# Segmentacija slike koristeći K-means algoritam

Ovaj repozitorij sadrži praktični dio seminarskog rada iz kolegija **Računalni vid**. Projekt demonstrira primjenu **K-means algoritma** (nenadzirano strojno učenje) za segmentaciju digitalnih slika na temelju boja.

Cilj projekta je analizirati kako broj segmenata ($K$) utječe na kvalitetu segmentacije te usporediti matematičke metrike s vizualnom ljudskom percepcijom.

## 📋 Značajke projekta

* **Predobrada slike:** Učitavanje, konverzija u RGB prostor, normalizacija i *flattening* podataka.
* **K-means implementacija:** Korištenje `scikit-learn` biblioteke za klasteriranje piksela.
* **Eksperimentalna analiza:** Testiranje s različitim vrijednostima $K$ (2, 3, 5, 10, 50).
* **Evaluacija:**
    * **Metoda lakta (Elbow Method):** Izračun WCSS (Within-Cluster Sum of Squares).
    * **Silhouette Analysis:** Mjerenje kohezije i separacije klastera.
* **Vizualizacija:** Generiranje usporednih prikaza (Original vs. Segmentirano) i grafova metrika.

## 🛠️ Korištene tehnologije

* **Python 3.x**
* **OpenCV** (`cv2`) - obrada slike
* **Scikit-learn** (`sklearn`) - algoritam strojnog učenja
* **NumPy** - matrične operacije
* **Matplotlib** - vizualizacija grafova i slika

## 🚀 Instalacija i pokretanje

1.  Klonirajte repozitorij:
    ```bash
    git clone [https://github.com/nikolinabioksic/Racunalni_Vid.git]
    ```
2.  Instalirajte potrebne biblioteke:
    ```bash
    pip install numpy matplotlib opencv-python scikit-learn
    ```
3.  Pokrenite Jupyter Notebook ili Python skriptu:
    ```bash
    jupyter notebook
    # ili
    python main.py
    ```

## 📊 Primjeri rezultata

Eksperiment je proveden na tri tipa slika: objekt visokog kontrasta (jabuka), pejzaž i složena scena (voće).

### 1. Segmentacija objekta (Jabuka)
Ovdje se vidi kako algoritam već pri **K=2** savršeno odvaja objekt od pozadine.

https://github.com/nikolinabioksic/Racunalni_Vid/blob/main/rezultati/slika1_segmentacija.png

### 2. Analiza metrika (Metoda lakta)
Prikaz pada WCSS greške i Silhouette Score-a. Jasno je vidljiv "lakat" pri K=2.

https://github.com/nikolinabioksic/Racunalni_Vid/blob/main/rezultati/slika1_metrike.png

### 3. Fenomen pre-segmentacije (K=50)
Primjer kako prevelik broj klastera dovodi do modeliranja šuma umjesto korisne segmentacije.

https://github.com/nikolinabioksic/Racunalni_Vid/blob/main/rezultati/slika1_K50_usporedba.png

## 📂 Struktura repozitorija

* `main.py` (ili `.ipynb`) - Glavni kod za pokretanje segmentacije.
* `images/` - Ulazne slike korištene za testiranje.
* `results/` - Generirane segmentirane slike i grafovi.
* `README.md` - Dokumentacija projekta.

## 📝 Zaključak

Analiza je pokazala da matematičke metrike (poput Silhouette Score) nisu uvijek u korelaciji s ljudskom percepcijom, posebno kod vizualno složenih scena (npr. zdjela s voćem), gdje je potreban veći broj segmenata ($K=10$) za prepoznavanje objekata unatoč nižim statističkim ocjenama.

---
**Autor:** Nikolina Biokšić
**Kolegij:** Računalni vid
