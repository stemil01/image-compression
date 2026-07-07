# Kompresija slika

Projekat implementira, analizira i poredi različite algoritme za kompresiju
slika.
Zasnovan je na [radu][hybrid-paper].


## Opis projekta

U Jupyter svesci [`image_compression.ipynb`](image_compression.ipynb) implementirane su četiri metode kompresije:

* **JPEG-DCT** - diskretna kosinusna transformacija
* **SVD**: - kompresija slike zasnovana na singularnoj dekompoziciji,
* **DWT**: dekompozicija zasnovana na talasićima
* **SVD+DWT hibrid**: SVD aproksimacija praćena DWT kompresijom, po uzoru na rad iz literature.

Kvalitet rekonstrukcije meri se metrikama PSNR i SSIM, a metode se porede krivama zavisnosti kvaliteta od faktora kompresije na slikama različitih karakteristika.

Grafici poređenja čuvaju se u direktorijumu `rezultati/`.

## Skup podataka

Korišćene su standardne test slike iz modula `skimage.data` biblioteke
*scikit-image*.
Konkretno, korišćene su:
- *camera* (uz original, korišćena je i zamućena verzija)
- *page*
- *brick*
- *checkerboard*
- *grass*
- *astronaut* (prevedena u crno-belu verziju)
- *moon*
* `data/tiger.jpg` - korišćena za ilustraciju pojedinačnih metoda.

## Podešavanje okruženja

Potreban je Python 3.10 ili noviji. Korišćeni su paketi:
- *NumPy*
- *OpenCV*
- *PyWavelets*
- *scikit-image*
- *Matplotlib*
- *Pandas*
- *Jupyter*

Paketi se mogu instalirati korišćenjem menadžera paketa *pip* sledećom komandom:
```sh
pip install numpy matplotlib pandas opencv-python PyWavelets scikit-image jupyter
```

Preporučuje se rad u virtuelnom okruženju.

## Pokretanje i testiranje

```bash
jupyter notebook image_compression.ipynb
```

Pokretanje automatski kreira direktorijum `rezultati/` sa graficima poređenja za
svaku test sliku. Šum je fiksiran semenom, pa su svi rezultati reproduktivni.

## Literatura

* Y. Vijaywargiya, R. K. Pandey, *Hybrid Image Compression Algorithm based on Singular Value Decomposition and Discrete Wavelet Transform*, Procedia Computer Science 260 (2025). [doi:10.1016/j.procs.2025.03.289][hybrid-paper]

## Članovi tima

* Anđela Mlađenović, 1019/2025 ([andja11](https://github.com/andja11))
* Stefan Milenković, 1076/2024 ([stemil01](https://github.com/stemil01))

[hybrid-paper]: https://doi.org/10.1016/j.procs.2025.03.289
