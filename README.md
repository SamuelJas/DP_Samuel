## Analýza rádiových spektrogramov metódami nekontrolovaného učenia

### Rozšírenie článku publikovaného v [Earth and Space Science](https://doi.org/10.1029/2021EA002007) o nové metódy:

### Abstrakt

Bleskové výboje generujú elektromagnetické pulzy, ktoré môžu cestovať atmosférou Zeme na veľké vzdialenosti. Namerané pulzy tiež nazývame atmosferiky a ich analýzou je možné skúmať vzdialené búrky ako aj zemskú ionosféru. Použitím metód strojového učenia je možné uľahčiť analýzu nameraných atmosferikov a metódami nekontrolovaného učenia je navyše možné nájsť v nameraných dátach vzory a súvislosti, ktoré by inak mohli ostať nepovšimnuté. Cieľom diplomovej práce je rozšírenie doterajšieho výskumu detekcie nameraných atmosferikov o nové metódy strojového učenia a oboznámenie sa s metódami nekontrolovaného učenia s ich využitím na zhlukovanie dát.

- Jupyter notebook [Preprocess](/Predspracovanie_dat/tweek_crop.ipynb) obsahuje metódy spracovania výstupu anotačného projektu a extrakcie udalostí zo spektrogramov. Extrahované udalosti ukladá do zložiek podľa počtu disperzií.

- Jupyter notebook [NormalNet](/Kontrolovane_ucenie/Normal_model/Normal_Net.ipynb) obsahuje metódy vytvorenia a trénovania modelu klasifikácie disperzií s predspracovaním dát normalizáciou.

- Jupyter notebook [AugNet](/Kontrolovane_ucenie/Augmentacny_model/Datagen_model.ipynb) obsahuje metódy vytvorenia a trénovania modelu klasifikácie disperzií za použitia augmentovanej dátovej množiny.

- Jupyter notebook [Detection](/Kontrolovane_ucenie/Nasadenie_modelu/detection.ipynb) obsahuje metódy stiahnutia, rozbalenia a spracovania dát. Ďalej obsahuje YOLO model pre detekciu udalostí. Pri veľkom množstve dát je možné spustiť rozbalenie a spracovanie dát paralelne pomocou notebookov v zložke [Spracovanie](/Kontrolovane_ucenie/Nasadenie_modelu/Spracovanie_stiahnutych_dat).

- Jupyter notebook [Prediction](/Kontrolovane_ucenie/Nasadenie_modelu/prediction.ipynb) obsahuje metódy extrakcie stiahnutých dát a vytvárania výstupných tabuliek. Udalosti typu tweek skript klasifikuje podľa počtu disperzií naučeným modelom.

- Jupyter notebook [Visualization](/Kontrolovane_ucenie/Nasadenie_modelu/Frekvencne_grafy.ipynb) obsahuje metódy vizualizácie dát z výstupnej tabuľky.

- Jupyter notebook [k-Means](/Nekontrolovane_ucenie/k-Means/Silny_enkoder/encoder_kmeans_final.ipynb) obsahuje metódy vytvorenia enkóderu a k-Means zhlukovania. Informáciu o zhlukoch skript pridáva do výstupnej tabuľky a vytvorené zhluky vizualizuje.

- Jupyter notebook [k-MeansAnalysis](/Nekontrolovane_ucenie/k-Means/Silny_enkoder/cluster_analysis.ipynb) analyzuje vytvorené zhluky za pomoci informácií obsiahnutých vo výstupnej tabuľke.

- Jupyter notebook [SOM-Optimalization](/Nekontrolovane_ucenie/SOM/SOM_3_3/SOM_3_3.ipynb) obsahuje metódy trénovania, vizualizácie a optimalizácie parametrov SOM mapy.

- Jupyter notebook [SOM](/Nekontrolovane_ucenie/SOM/SOM_3_3/SOM_3_3_clustering_sig_opti.ipynb) obsahuje metódy trénovania a vizualizácie SOM mapy s najlepšími parametrami učenia. Informáciu o zhlukoch skript spája s výstupnou tabuľkou.

- Jupyter notebook [SOM-analysis](/Nekontrolovane_ucenie/SOM/SOM_3_3/som_3_3_cluster_analysis_sig_opti.ipynb) analyzuje vytvorené zhluky za pomoci informácií obsiahnutých vo výstupnej tabuľke.

### Vstupné, výstupné a pracovné súbory

---

### Ako citovať:

Viera Maslej-Krešňaková, Adrián Kundrát, Šimon Mackovjak, Peter Butka, Samuel Jaščur, Ivana Kolmašová, Ondřej Santolík, Automatic Detection of Atmospherics and Tweek Atmospherics in Radio Spectrograms Based on a Deep Learning Approach, Earth and Space Science, Volume 8, Issue 11, e02007, November 2021 https://doi.org/10.1029/2021EA002007

***BibTex:***  
*@article{10.1029/2021EA002007,   
author = {{Maslej-Krešňáková}, Viera and {Kundrát}, Adrián. and {Mackovjak}, Šimon and {Butka}, Peter and {Jaščur}, Samuel and {Kolmašová}, Ivana and {Santolík}, Ondřej},   
title = "{Automatic Detection of Atmospherics and Tweek Atmospherics in Radio Spectrograms Based on a Deep Learning Approach}",   
journal = {Earth and Space Science},   
volume = {8},   
number = {11},   
pages = {e02007},   
year = {2021},   
month = {11},   
doi = {10.1029/2021EA002007},   
url = {https://doi.org/10.1029/2021EA002007}  
}*
