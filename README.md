# Klasifikacija antimikrobnih peptida

## Opis projekta

Cilj ovog projekta je razvoj sustava strojnog učenja za klasifikaciju antimikrobnih peptida (AMP) i neantimikrobnih peptida.

Antimikrobni peptidi predstavljaju važan dio prirodnog obrambenog sustava organizama te imaju sposobnost uništavanja ili inhibiranja rasta različitih mikroorganizama. Zbog njihove potencijalne primjene u medicini i farmaciji, važno je razviti metode koje mogu automatski prepoznati takve peptide.

Projekt obuhvaća cijeli proces analize podataka, od prikupljanja i pripreme sekvenci, preko ekstrakcije značajki, do treniranja i evaluacije modela strojnog učenja.

## Izvor podataka

Podaci su preuzeti iz DBAASP baze podataka (Database of Antimicrobial Activity and Structure of Peptides).

Korištene su dvije klase podataka:

* pozitivna klasa – antimikrobni peptidi (AMP),
* negativna klasa – neantimikrobni peptidi.

Nakon čišćenja podataka, uklanjanja neispravnih sekvenci i balansiranja klasa formiran je uravnotežen skup podataka za treniranje i testiranje modela.

## Tijek projekta

### 1. Priprema podataka

U ovoj fazi provedeno je:

* učitavanje peptidnih sekvenci,
* čišćenje podataka,
* uklanjanje duplikata,
* provjera valjanosti sekvenci,
* formiranje uravnoteženog skupa podataka.

### 2. Ekstrakcija značajki

Iz svake sekvence izračunate su različite bioinformatičke značajke:

* duljina sekvence,
* neto naboj,
* hidrofobnost,
* molekularna masa,
* aromatičnost,
* izoelektrična točka,
* aminokiselinski sastav (AAC).

Dobivene značajke pretvorene su u numeričku matricu pogodnu za primjenu algoritama strojnog učenja.

### 3. Modeliranje

Trenirani su sljedeći modeli:

* Random Forest
* Support Vector Machine (SVM)

Podaci su podijeljeni na skup za treniranje i testiranje u omjeru 80:20.


### 4. Evaluacija modela

Performanse modela analizirane su pomoću:

* Accuracy
* Precision
* Recall
* F1-score
* Confusion Matrix prikaza

Također je provedena usporedba modela kako bi se odredio model s najboljim rezultatima klasifikacije.


## Rezultati

Oba modela ostvarila su vrlo dobre rezultate klasifikacije.

Najbolje rezultate ostvario je SVM model s točnošću od približno 96 %, dok je Random Forest ostvario točnost od približno 95 %.

Analiza važnosti značajki pokazala je da najveći doprinos klasifikaciji imaju:

* duljina sekvence,
* neto naboj,
* hidrofobnost,
* aminokiselinski sastav peptida.

Dobiveni rezultati potvrđuju da odabrane značajke sadrže dovoljno informacija za uspješno razlikovanje antimikrobnih i neantimikrobnih peptida.


## Instalacija

Instalacija potrebnih biblioteka:

```bash
pip install -r requirements.txt
```
## Pokretanje projekta

Notebookovi se izvršavaju redoslijedom:

1. 01_data_preparation.ipynb
2. 02_feature_engineering.ipynb
3. 03_modeling.ipynb
4. 04_evaluation.ipynb

Svaki notebook generira podatke koji se koriste u sljedećem koraku analize.


