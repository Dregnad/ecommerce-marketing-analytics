# Analiza Sprzedaży i Efektywności Marketingowej w E-Commerce

## 📌 O projekcie
Kompleksowy projekt analityczny typu end-to-end skupiający się na przetwarzaniu, czyszczeniu oraz analizie danych sprzedażowych i marketingowych sklepu internetowego. Zbiór danych obejmuje aż **60 000 rekordów**, co pozwoliło na przeprowadzenie zaawansowanych symulacji biznesowych.

Celem projektu jest dostarczenie kluczowych wniosków biznesowych (actionable insights) w obszarach: regionalnej dystrybucji przychodów, segmentacji klientów według wieku i zachowań zakupowych, rentowności działań marketingowych (ROI) oraz wydajności poszczególnych kategorii produktowych.

Projekt odtwarza pełną ścieżkę pracy analityka danych (Data Analyst / BI Engineer) przy użyciu stosu technologicznego: **PostgreSQL (SQL)**, **MS Excel** oraz **Power BI**.

---

## 🛠️ Stos technologiczny i narzędzia
* **Baza danych i ETL:** PostgreSQL (pgAdmin)
* **Analiza ad-hoc i raportowanie:** MS Excel (Tabele przestawne, Fragmentatory, Formatowanie warunkowe)
* **Analityka BI i Wizualizacja:** Power BI Desktop (Język DAX, Modelowanie danych, Interaktywne pulpity)

---

## 📊 Pulpit Menedżerski (Power BI)
Oto pełny widok interaktywnego dashboardu stworzonego w Power BI:

![Pełny Dashboard](dashboard_preview.png)

### Szczegółowa analiza komponentów:
Poniżej znajdują się kluczowe wykresy przedstawiające szczegółowe metryki biznesowe:

| Przychody według Kategorii | Udział Kanałów Sprzedaży |
|---|---|
| ![Kategorie](chart_categories.png) | ![Kanały](chart_channels.png) |

| Trendy i Sezonowość Sprzedaży |
|---|
| ![Trendy](chart_trends.png) |

---

## 🚀 Kluczowe etapy projektu

### 1. Przygotowanie danych i proces ETL (PostgreSQL)
* Zaprojektowanie struktury tabeli i import surowego pliku CSV (60k wierszy) do bazy danych.
* Przeprowadzenie zaawansowanego czyszczenia danych (Data Cleaning): obsłużenie brakujących wartości (`NULL`) w kolumnie z rabatami za pomocą funkcji `COALESCE`.
* Użycie **funkcji okna (`AVG() OVER(PARTITION BY...)`)** do inteligentnego uzupełnienia braków w ocenach satysfakcji klientów średnią wartością wyliczoną dla danej kategorii produktu.
* Implementacja logiki biznesowej: stworzenie dynamicznej flagi rentowności marketingu (`CASE WHEN`) na podstawie relacji kosztów reklamowych do wygenerowanego przychodu.
* Przygotowanie zaawansowanych zapytań analitycznych, w tym rankingu popularności produktów w regionach przy użyciu funkcji okna `DENSE_RANK()`.

### 2. Taktyczne Raportowanie (MS Excel)
* Agregacja i eksport wyników segmentacji z bazy SQL bezpośrednio do arkusza menedżerskiego.
* Zbudowanie zaawansowanych **Tabel Przestawnych** analizujących przychody generowane przez klientów w zależności od ich wieku (z podziałem na grupy demograficzne).
* Wdrożenie **Fragmentatorów (Slicerów)**, dzięki którym użytkownik końcowy może jednym kliknięciem filtrować wykresy według typu klienta (Corporate / Regular / New).

### 3. Wizualizacja i Modelowanie (Power BI)
* Zaimportowanie danych i zbudowanie miar w języku **DAX** (`Suma Przychodów`, `Suma Budżetu`, `Średnia Satysfakcja`).
* Stworzenie intuicyjnego interfejsu z kartami KPI, ułatwiającego kadrze zarządzającej błyskawiczny przegląd kondycji finansowej firmy.

---

## 📈 Główne wnioski biznesowe
* **Potencjał demograficzny:** Wykazano, które grupy wiekowe generują najwyższą wartość koszyka zakupowego oraz jak stopień przyznawanych rabatów wpływa na ich zadowolenie.
* **Efektywność Omnichannel:** Porównano skuteczność sprzedaży online z tradycyjnymi sklepami stacjonarnymi pod kątem stóp konwersji, co pozwala na optymalizację budżetów reklamowych.
* **Dystrybucja regionalna:** Zidentyfikowano dominujące kategorie produktów w dynamicznie rozwijających się hubach gospodarczych (Dubaj, Rijad, Kair).

---

## 📁 Struktura repozytorium
* `1_data_cleaning_and_analysis.sql` - Pełny skrypt PostgreSQL (tworzenie tabel, transformacje ETL, zapytania).
* `2_customer_segmentation_report.xlsx` - Interaktywny raport Excel z wykresami i filtrami.
* `3_ecommerce_marketing_dashboard.pbix` - Plik źródłowy Power BI zawierający model danych.
* Obrazy graficzne (`dashboard_preview.png`, `chart_categories.png`, `chart_channels.png`, `chart_trends.png`) stanowiące dokumentację wizualną projektu.
