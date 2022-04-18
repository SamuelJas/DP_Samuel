## Analýza rádiových spektrogramov metódami nekontrolovaného učenia

### Rozšírenie článku publikovaného v [Earth and Space Science](https://doi.org/10.1029/2021EA002007) o nové metódy:

### Abstrakt

Bleskové výboje generujú elektromagnetické pulzy, ktoré môžu cestovať atmosférou Zeme na veľké vzdialenosti. Namerané pulzy tiež nazývame atmosferiky a ich analýzou je možné skúmať vzdialené búrky ako aj zemskú ionosféru. Použitím metód strojového učenia je možné uľahčiť analýzu nameraných atmosferikov a metódami nekontrolovaného učenia je navyše možné nájsť v nameraných dátach vzory a súvislosti, ktoré by inak mohli ostať nepovšimnuté. Cieľom diplomovej práce je rozšírenie doterajšieho výskumu detekcie nameraných atmosferikov o nové metódy strojového učenia a oboznámenie sa s metódami nekontrolovaného učenia s ich využitím na zhlukovanie dát.

- Jupyter notebook [Preprocess](/Predspracovanie_dat/tweek_crop.ipynb) obsahuje metódy spracovania výstupu anotačného projektu a extrakcie udalostí zo spektrogramov. Extrahované udalosti ukladá do zložiek podľa počtu disperzií.

- Jupyter notebook [NormalNet](/Kontrolovane_ucenie/Normal_model/Normal_Net.ipynb) obsahuje metódy vytvorenia a trénovania modelu klasifikácie disperzií s predspracovaním dát normalizáciou. V práci je tento model označovaný ako Model 1

- Jupyter notebook [AugNet](/Kontrolovane_ucenie/Augmentacny_model/Datagen_model.ipynb) obsahuje metódy vytvorenia a trénovania modelu klasifikácie disperzií za použitia augmentovanej dátovej množiny. V práci je tento model označovaný ako Model 3

- Jupyter notebook [Detection](/Kontrolovane_ucenie/Nasadenie_modelu/detection.ipynb) obsahuje metódy stiahnutia, rozbalenia a spracovania dát. Ďalej obsahuje YOLO model pre detekciu udalostí. Pri veľkom množstve dát je možné spustiť rozbalenie a spracovanie dát paralelne pomocou notebookov v zložke [Spracovanie](/Kontrolovane_ucenie/Nasadenie_modelu/Spracovanie_stiahnutych_dat).

- Jupyter notebook [Prediction](/Kontrolovane_ucenie/Nasadenie_modelu/prediction.ipynb) obsahuje metódy extrakcie stiahnutých dát a vytvárania výstupných tabuliek. Udalosti typu tweek skript klasifikuje podľa počtu disperzií modelom klasifikácie disperzií.

- Jupyter notebook [Visualization](/Kontrolovane_ucenie/Nasadenie_modelu/Frekvencne_grafy.ipynb) obsahuje metódy vizualizácie dát z výstupnej tabuľky.

- Jupyter notebook [ClusterPreprocess](/Nekontrolovane_ucenie/spracovanie_cluster_dat.ipynb) obsahuje metódy spracovania extrahovaných udalostí do podoby vhodnej pre metódy zhlukovania.

- Jupyter notebook [k-Means](/Nekontrolovane_ucenie/k-Means/Silny_enkoder/encoder_kmeans_final.ipynb) obsahuje metódy vytvorenia enkóderu a k-Means zhlukovania. Informáciu o zhlukoch skript pridáva do výstupnej tabuľky a vytvorené zhluky vizualizuje.

- Jupyter notebook [k-MeansAnalysis](/Nekontrolovane_ucenie/k-Means/Silny_enkoder/cluster_analysis.ipynb) analyzuje vytvorené zhluky za pomoci informácií obsiahnutých vo výstupnej tabuľke.

- Jupyter notebook [SOM-Optimalization](/Nekontrolovane_ucenie/SOM/SOM_3_3/SOM_3_3.ipynb) obsahuje metódy trénovania, vizualizácie a optimalizácie parametrov SOM mapy.

- Jupyter notebook [SOM](/Nekontrolovane_ucenie/SOM/SOM_3_3/SOM_3_3_clustering_sig_opti.ipynb) obsahuje metódy trénovania a vizualizácie SOM mapy s najlepšími parametrami učenia. Informáciu o zhlukoch skript spája s výstupnou tabuľkou.

- Jupyter notebook [SOM-analysis](/Nekontrolovane_ucenie/SOM/SOM_3_3/som_3_3_cluster_analysis_sig_opti.ipynb) analyzuje vytvorené zhluky za pomoci informácií obsiahnutých vo výstupnej tabuľke.

### Vstupné, výstupné a pracovné súbory

#### Predspracovanie dát
Súbory sú uložené v zložke [Predspracovanie](/Predspracovanie_dat/csv)

- jjmarkers-classifications2.csv - výstupný súbor anotačného projektu
- annot_output.csv, anot_data_all.csv, anot_data_tweek.csv - čiastkové súbory predspracovania
- tweek1.csv, tweek2.csv, tweek3.csv, tweekMoreThan4.csv - konečné csv súbory, obsahujúce informácie pre extrakciu udalostí

#### Kontrolované učenie

##### [Augmentačný model](/Kontrolovane_ucenie/Augmentacny_model)
- X_test.pkl - testovacia dátová množina
- y_test.pkl - label testovacej dátovej množiny
- X_train_norm.pkl - trénovacia dátová množina
- y_train_norm.pkl - label trénovacej dátovej množiny
- images.pkl - súbor obsahujúci názvy udalostí uložených v zložke
- model_datagen_RBG.h5 - natrénovaný model s najlepošími parametrami
- predictions_datagen.csv - výstup predikcie modelu na testovacej zložke dát
- ch1_20150902_231933_448_s61_2831.jpg - náhľad extrahovanej udalosti

##### [Nasadenie modelu](/Kontrolovane_ucenie/Nasadenie_modelu/csv_spracovane_roky/2014)
- output_S_2014_11.csv, output_T_2014_11.csv, vyst_tab_2014_11.csv - čiastkové výstupné tabuľky
- result_2014_11_cleared.csv - konečná výstupná tabuľka
- [vizualizácia](/Kontrolovane_ucenie/Nasadenie_modelu/Grafy) - png výstupy vizualizácie udalostí

#### Nekontrolované učenie

##### k-Means s enkóderom

- [data](/Nekontrolovane_ucenie/k-Means/Silny_enkoder/data)
- X_train.pkl - trénovacia zložka dát (trénovanie enkódera)
- y_train.pkl - label trénovacej zložky (trénovanie enkódera)
- X_valid.pkl - validačná zložka dát (trénovanie enkódera)
- y_valid.pkl - label v alidačnej zložky (trénovanie enkódera)
- data_2014_11.pkl - spracované dáta pre zhlukovanie (dáta obsahujú len vzorku spracovaných záznamom z kapacitných dôvodov)
- label_2014_11.pkl - label spracovaných dát
- img_name.pkl - názov spracovaných udalostí pre potreby spojenia v výstupnou tabuľkou

- [csv](/Nekontrolovane_ucenie/k-Means/Silny_enkoder/csv)
- result_2014_11_cleared.csv - výstupná tabuľka vytvorená procesom nasadenia modelov
- K2_2014_11.csv až K9_2014_11.csv - výstupné tabuľky metódy zhlukovania k-Means, kde K je počet zhlukov

- [img](/Nekontrolovane_ucenie/k-Means/Silny_enkoder/img)
- kmeans_2clusters.png až kmeans_9clusters.png - vizualizované zhluky k-Means zhlukovania, kde číslo vyjadruje počet zhlukov

##### SOM

[data](/Nekontrolovane_ucenie/SOM/SOM_3_3/data)

- data_2014_11.pkl - spracované dáta pre zhlukovanie (dáta obsahujú len vzorku spracovaných záznamom z kapacitných dôvodov)
- label_2014_11.pkl - label spracovaných dát
- img_name.pkl - názov spracovaných udalostí pre potreby spojenia v výstupnou tabuľkou

[csv](/Nekontrolovane_ucenie/SOM/SOM_3_3/csv)

- result_2014_11_cleared.csv - výstupná tabuľka vytvorená procesom nasadenia modelov
- som3_3_sig_opti_2014_11.csv - výstupná tabuľka metódy SOM s informáciou o príslušnosti udalostí do zhlukov

[img](/Nekontrolovane_ucenie/SOM/SOM_3_3/img)

- som_3_3_cluster_sig_opti.png - vizualizovaná SOM mapa

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
