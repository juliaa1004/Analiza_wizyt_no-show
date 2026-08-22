# Analiza wizyt typu "no-show"

Projekt zajmuje się analizą danych dotyczących wizyt lekarskich oraz próbą zrozumienia i przewidzenia zachowań pacjentów, którzy nie stawiają się na umówione spotkania (tzw. *no-show*). W analizie zostały połączone **trzy niezależne źródła danych**, aby sprawdzić wpływ demografii, warunków pogodowych oraz uroczystości na realizację umówionych wizyt.

## Dane
Główny zbiór danych zawiera informacje o wizytach medycznych, wzbogacone o kontekst pogodowy i kalendarzowy.

⚠️ **Ważne:** Ze względu na duży rozmiar pliku z danymi, nie został on umieszczony bezpośrednio w repozytorium GitHub.
* [Pobierz pełny plik z danymi z platformy Kaggle](https://www.kaggle.com/datasets/saraivaufc/conventional-weather-stations-brazil)

## Cele i etapy projektu
1. **Integracja danych:** Połączenie trzech odrębnych źródeł danych (demografia, pogoda, wydarzenia/uroczystości) w jeden spójny zestaw analizowany za pomocą biblioteki `pandas`.
2. **Eksploracyjna analiza danych (EDA) & Metody statystyczne:** Wykorzystanie testów statystycznych (m.in. testu istotności **Chi-kwadrat** - `chi2_contingency`) do weryfikacji hipotez i sprawdzenia, które zmienne korelują z nieobecnością pacjentów w sposób istotny statystycznie.
3. **Inżynieria cech (Feature Engineering):** Manipulacja czasem i datami (za pomocą `datetime` i `timedelta`) w celu określenia np. czasu oczekiwania na wizytę lub wpływu konkretnych dni świątecznych.
4. **Modelowanie predykcyjne (Uczenie maszynowe):** Budowa i ocena klasyfikatora opartego na algorytmie **Lasu Losowego (Random Forest)**, służącego do przewidywania prawdopodobieństwa niestawienia się pacjenta na wizytę.

## Wykorzystane technologie i biblioteki
Projekt został napisany w języku **Python**. Wykorzystano następujące pakiety:

* **Manipulacja i analiza danych:**
  * `pandas` - podstawowa biblioteka do pracy z strukturami DataFrame.
  * `numpy` - operacje macierzowe i obliczenia matematyczne.
  * `datetime` (`timedelta`) - zaawansowana manipulacja czasem i datami.
* **Wizualizacja danych:**
  * `matplotlib.pyplot` - tworzenie podstawowych wykresów.
  * `seaborn` - budowa estetycznych wykresów statystycznych.
* **Metody statystyczne:**
  * `scipy.stats` (`chi2_contingency`, `stats`) - przeprowadzenie testów statystycznych i weryfikacja hipotez.
* **Uczenie maszynowe (Machine Learning):**
  * `sklearn.model_selection` (`train_test_split`) - podział danych na zbiór treningowy i testowy.
  * `sklearn.ensemble` (`RandomForestClassifier`) - budowa modelu lasu losowego.
  * `sklearn.metrics` (`classification_report`, `accuracy_score`) - ewaluacja modelu (metryki dokładności, precyzji i pełności).
