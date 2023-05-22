# ZUM
Zastosowania Uczenia Maszynowego 

## Projekt z NLP

## Projekt zrealizowany w zespole trzy osobowym :
- Maciej Cichanowicz s16691
- Kacper Padarz s18535
- Mateusz Godlewski s19282

## Uruchomienie
Uruchomienie wszystkich komórek z Colaba spowoduje:
1. Pobranie wymaganych bibliotek
2. Zebranie tweetów dotyczących w Ukrainie (po dwa tysiące tweetów z każdego miesiąca wojny)
3. Wyczyszczenie danych
4. Otagowanie danych
5. Uruchomienie klasycznych modeli uczenia maszynowego:
    - Regresja Logistyczna
    - LSVC
    - MNB
6. Wytrenowanie sieci neuronowych:
    - Z wykorzystaniem BLSTM 
    - Z wykorzystaniem LSTM
7. Wytrenowanie modeli językowych:
    - DistilBERT
    - AlBERT

## Omówienie
Przy użyciu biblioteki sntwitter zebrano około 30000 tys. tweetów dotyczących wojny w Ukrainie. Aby tweety dotyczyły ogółu wydarzeń a nie konkretnego okresu zebranych zostało po dwa tysiące tweetów z każdego miesiąca trwania wojny.
Podczas czyszczenia danych usunięto wzmianki(@UserName), hashtagi(#topic), stopwordsy, itd. Dodatkowo w celu dokładniejszego oddania emocji towarzyszących tweetowi zamieniono emotikony na ich tekstowe odpowiedniki. 
Aby lepiej wytrenować modele, klasy zostały odpowiednio zbalansowane tak by rekordów reprezentującą daną klasę było po równo.
Klasyczne modele ML uzyskały wyniki około 80% accuracy.
W celu uzyskania jak najlepszych wyników sieci neuronowych poddano je procesowi fine tuningu. Po wielu iteracjach udało się uzyskać wyniki około 83% dla obu modeli. Aby uniknąć przetrenowania zaimplementowano early stopping i wykorzystano model checkpoint. 
W modelach językowych po dostosowaniu parametrów takich jak `learning_rate`, `num_train_epochs`, `weight_decay` udało się uzyskać wyniki na poziomie 87%.