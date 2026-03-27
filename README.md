# 🔬 Cyfrowa Korelacja Obrazów (DIC) - Pomiar Odkształceń

Projekt badawczo-analityczny z dziedziny wizji maszynowej (Computer Vision) i inżynierii materiałowej. Skrypt napisany w środowisku **Scilab** służy do bezkontaktowego wyznaczania wydłużenia próbki materiałowej na podstawie serii zdjęć wykonanych podczas próby rozciągania.

## 🎯 Cel projektu
Zbudowanie algorytmu śledzącego wybrane wzorce (punkty referencyjne) na serii obrazów odkształcającej się próbki. Na podstawie zmiany odległości między wzorcami program oblicza względne wydłużenie materiału, analizując równomierność rozkładu naprężeń.

## 🛠 Wykorzystane technologie
* **Język / Środowisko:** Scilab (przetwarzanie macierzy, obliczenia numeryczne, wizualizacja wyników).
* **Pre-processing obrazu:** ImageJ (konwersja map bitowych BMP na macierze tekstowe TXT w skali szarości).
* **Computer Vision:** Algorytmy śledzenia obiektów (Template Matching), korelacja krzyżowa obrazów, interpolacja subpikselowa.

## ⚙️ Wdrożone funkcjonalności
* **Korelacja obrazów:** Implementacja autorskiej funkcji korelacji znormalizowanej do odnajdywania położenia wzorca (Template) na odkształconym obrazie.
* **Estymacja subpikselowa:** Zastosowanie zaawansowanej interpolacji matematycznej w celu określenia przemieszczenia z dokładnością wyższą niż pojedynczy piksel, co drastycznie zwiększa precyzję pomiarów.
* **Parametryzacja analizy:** Możliwość płynnej zmiany wielkości wzorca (`Tsize`), obszaru poszukiwań (`Area`) oraz współrzędnych startowych punktów pomiarowych.
* **Wizualizacja:** Automatyczne generowanie map korelacji (heatmaps) oraz nakładanie graficznych znaczników (prostokątów) na analizowane obrazy.

## 📊 Główne wnioski z analizy badawczej
W ramach projektu przeprowadzono szereg testów, które wykazały:
* **Wpływ wielkości wzorca:** Wzorzec o rozmiarze 50x50 px okazał się najbardziej stabilny. Zbyt małe wzorce (25 px) były wrażliwe na szum, a zbyt duże (75 px) rozmywały lokalne przesunięcia.
* **Dokładność algorytmu:** Estymacja subpikselowa znacząco poprawiła dokładność wyników (szczególnie przy dużych odkształceniach dochodzących do **2.28%**).
* **Fizyka materiału:** Badanie różnych współrzędnych pionowych (`t1y`, `t2y`) udowodniło, że próbka rozciągała się nierównomiernie (większe odkształcenia w górnej partii materiału).

## 📷 Wizualizacja działania

### Zaznaczenie obszarów śledzenia na obrazie wzorcowym
<img width="830" height="620" alt="image" src="https://github.com/user-attachments/assets/6c03343f-0f0b-4da6-a896-429fe54c918c" />

### Template1 (wzorzec 1)
<img width="790" height="609" alt="image" src="https://github.com/user-attachments/assets/a9a6b52f-44a0-4bfc-82fa-61c30152157f" />

### Punkt 1 (100, 1800); Punkt 2 (150, 850)
<img width="820" height="609" alt="image" src="https://github.com/user-attachments/assets/e0269144-6033-4bfb-b3b1-d66c21e5b8d1" />

---
*Projekt zrealizowany w ramach zajęć na Politechnice Warszawskiej (Kierunek: Automatyzacja i Robotyzacja Procesów Produkcyjnych).*
