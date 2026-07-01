# 📊 E-Commerce Sales & Marketing Analytics Dashboard | SQL + Power BI

## 📌 Project Overview
Projekt przedstawia kompleksową analizę danych sprzedażowych oraz marketingowych sklepu internetowego z wykorzystaniem stosu technologicznego: **PostgreSQL, MS Excel oraz Power BI**.

Celem projektu było przeprowadzenie pełnego procesu analitycznego typu **end-to-end** — od przygotowania surowych danych, przez transformacje SQL, aż po stworzenie interaktywnego, dwustronicowego dashboardu wspierającego podejmowanie strategicznych decyzji biznesowych.

Analiza koncentruje się na czterech głównych obszarach:
* 📈 **Sales Performance** — analiza przychodów, realizacji budżetu oraz wydajności kategorii produktowych.
* 👥 **Customer Segmentation** — analiza zachowań zakupowych oraz wartości poszczególnych grup klientów.
* 📢 **Marketing Effectiveness** — ocena alokacji kosztów marketingowych w kanałach i ich przełożenia na wyniki.
* 🌍 **Regional Sales Analysis** — analiza dystrybucji sprzedaży według lokalizacji geograficznych.

Projekt pokazuje kompletny proces pracy analityka danych (Data Analyst / BI Engineer) — od surowych danych transakcyjnych do gotowych wniosków biznesowych.

---

## 🎯 Business Questions
Analiza została przeprowadzona w celu dostarczenia odpowiedzi na następujące pytania biznesowe:
* Które kategorie produktów generują największy przychód i powinny być traktowane priorytetowo?
* Jak kształtują się trendy sprzedażowe oraz sezonowość w poszczególnych kwartałach?
* Jak wygląda struktura alokacji wydatków marketingowych na poszczególne kanały dotarcia?
* Które kanały sprzedaży odpowiadają za największą wartość biznesową i udział w budżecie?
* Jakie są wskaźniki satysfakcji klientów w odniesieniu do prowadzonych działań?
* Które regiony (huby gospodarcze) generują największy udział w przychodach firmy?

---

## 📂 Dataset
* **Źródło danych:** Platforma Kaggle – [Marketing & Sales Dataset by Abdelfattah Ibrahim](https://www.kaggle.com/datasets/abdelfattahibrahim/marketing-sales-dataset)
* **Wolumen:** Zbiór danych zawiera około **60 000 rekordów**, co pozwoliło na przeprowadzenie zaawansowanych symulacji biznesowych.
* **Zakres danych:** Dane obejmują m.in. profile klientów, kategorie produktowe, kanały dystrybucji, koszty marketingowe, przychody, oceny satysfakcji oraz lokalizacje klientów (m.in. Alexandria, Amman, Cairo, Casablanca, Dubai, Riyadh).

---

## 🛠️ Tools & Technologies

| Narzędzie | Zastosowanie w projekcie |
| :--- | :--- |
| **PostgreSQL** | Import danych, proces ETL, czyszczenie danych (Data Cleaning), zaawansowana analiza SQL |
| **MS Excel** | Analiza ad-hoc, wstępna segmentacja klientów, weryfikacja danych za pomocą tabel przestawnych |
| **Power BI Desktop** | Modelowanie danych, zaawansowane miary DAX, projektowanie interaktywnego interfejsu (UI/UX) |

---

## 🔄 Data Preparation & SQL Analysis

Pierwszy etap projektu obejmował przygotowanie, czyszczenie oraz transformację danych bezpośrednio w bazie PostgreSQL.

### Data Cleaning
* Zaprojektowanie struktury tabeli i import surowego pliku CSV (60k wierszy) do bazy danych.
* Obsługa brakujących wartości (`NULL`) w kolumnach z rabatami przy użyciu funkcji `COALESCE()`.
* Standaryzacja typów danych i przygotowanie czystych relacji pod modelowanie BI.

### Data Transformation & Business Logic
W procesie transformacji wykorzystano zaawansowane zapytania i funkcje SQL:
* **Funkcje okna (`AVG() OVER(PARTITION BY...)`)** — wykorzystane do inteligentnego uzupełnienia brakujących ocen satysfakcji klientów średnią wartością wyliczoną dla danej kategorii produktu.
* **Funkcje okna (`DENSE_RANK()`)** — zastosowane do stworzenia rankingu popularności produktów i wolumenu sprzedaży w poszczególnych regionach.
* **Logika warunkowa (`CASE WHEN`)** — wdrożenie dodatkowych flag biznesowych umożliwiających automatyczną klasyfikację efektywności finansowej i ocenę rentowności działań marketingowych.

---

## 📊 Power BI Dashboard
Raport został celowo rozbity na dwie dedykowane strony. Pozwoliło to na optymalne zagospodarowanie przestrzeni (brak uciętych etykiet danych), zachowanie wysokiej estetyki (zastosowanie nowoczesnej, głębokiej palety granatów) oraz logiczny podział na widok czysto sprzedażowy i marketingowy.

---

### 📄 Strona 1: Dashboard Sprzedażowy (Sales Performance)
Ta strona służy kadrze zarządzającej do błyskawicznego monitorowania ogólnej kondycji finansowej firmy, porównania przychodów z założonym budżetem oraz analizy asortymentu.

![Dashboard Sprzedażowy](dashboard_page_1.png)

#### 🔎 Key Insights
* **Wysoka realizacja finansowa:** Firma wygenerowała 355 mln zł przychodu przy całkowitym budżecie wynoszącym 602 mln zł.
* **Silna sezonowość:** Wykres trendów jednoznacznie wskazuje na skokowy wzrost sprzedaży w ujęciu kwartalnym – od 71 mln zł w Q1 do aż 113 mln zł w Q4.
* **Dominacja kategorii:** Kategoria *Electronics* jest kluczowym motorem napędowym biznesu, generując najwyższy jednostkowy przychód na poziomie 105 mln zł. Tuż za nią plasują się *Home Appliances* (74 mln zł) oraz *Food & Beverage* (70 mln zł).

#### 💡 Business Recommendation
> Rekomenduje się intensyfikację zatowarowania i zabezpieczenie łańcuchów dostaw dla kategorii *Electronics* oraz *Home Appliances* przed wejściem w drugą połowę roku (Q3/Q4). Pozwoli to w pełni obsłużyć zidentyfikowany, naturalny pik sezonowy i uniknąć strat związanych z brakiem asortymentu (stockout).

---

### 📄 Strona 2: Struktura Wydatków Marketingowych (Marketing & Customer Insights)
Druga strona raportu koncentruje się na efektywności alokacji kapitału reklamowego w poszczególnych kanałach oraz monitorowaniu poziomu zadowolenia konsumentów.

![Struktura wydatków marketingowych](dashboard_page_2.png)

#### 🔎 Key Insights
* **Kluczowy kanał Online:** Sprzedaż internetowa (*Online*) odpowiada za największy udział w budżecie marketingowym (31,03% / 110,04 mln zł) i generuje najwyższe zwroty finansowe (179 mln zł).
* **Stabilna satysfakcja:** Średnia satysfakcja klientów utrzymuje się na stałym, zdrowym poziomie 3,50/5, co świadczy o dobrej powtarzalności procesów obsługi.
* **Niska efektywność Social Media:** Kanał *Social Media* zanotował najniższe nakłady budżetowe (84,14 mln zł), przekładając się równocześnie na najsłabszy wynik sprzedażowy (56 mln zł).

#### 💡 Business Recommendation
> Wysokie budżety na kanały *Online* oraz *Retail Store* przynoszą stabilne i zamierzone efekty. Należy natomiast zrewidować strategię dla kanału *Social Media* — zamiast ciągłego obniżania budżetu, warto wdrożyć dedykowane, bardziej precyzyjne kampanie targetowane na zaangażowanie (np. influencer marketing), aby podnieść współczynnik konwersji w tym kanale.

---

## 📈 Key Business Insights Summary

### 1. Sales Optimization
Identyfikacja kategorii *Electronics* jako lidera przychodów pozwala na lepsze zarządzanie przestrzenią magazynową i optymalizację marżowości produktów.

### 2. Marketing Effectiveness
Dzięki zestawieniu struktury wydatków z przychodami w kanałach, firma zyskała twarde dane do optymalizacji budżetów promocyjnych i relokacji środków z kanałów mniej efektywnych.

### 3. Customer Understanding
Stabilny wskaźnik satysfakcji (3,50) stanowi solidny punkt odniesienia (benchmark) do testowania nowych akcji lojalnościowych i mierzenia ich wpływu na zadowolenie klientów.

### 4. Data-Driven Decisions
Rozbity na dwa ekrany dashboard Power BI dostarcza pełnej i przejrzystej informacji zarządczej, skracając czas potrzebny na podjęcie kluczowych decyzji biznesowych.

---

## 📁 Repository Structure
```text
📂 ecommerce-sales-marketing-analysis
│
├── 1_data_cleaning_and_analysis.sql    # Pełny skrypt PostgreSQL (ETL, czyszczenie, funkcje okna)
├── 2_customer_segmentation_report.xlsx # Raport menedżerski Excel (Tabele przestawne, segmentacja)
├── 3_ecommerce_marketing_dashboard.pbix# Plik źródłowy modelu danych i dashboardu Power BI
│
├── dashboard_page_1.png                # Rzut ekranu strony 1: Analiza Sprzedaży
└── dashboard_page_2.png                # Rzut ekranu strony 2: Struktura Marketingowa
