# TXS - Terminal Stock Analysis Tool

Terminal Stock Analysis Tool to narzędzie command-line do szybkiej analizy finansowej akcji bezpośrednio z terminala.

## Funkcjonalność

- **Kwartalne dane finansowe** - wyświetla kluczowe wskaźniki finansowe z ostatnich 4 kwartałów
- **Zmiany rok-do-roku (YoY)** - pokazuje procentowe zmiany dla każdego wskaźnika
- **Wykresy ASCII** - wizualizuje cenę akcji i wolumen obrotów za ostatni rok
- **Formatowanie danych** - automatyczne formatowanie dużych liczb (K, M, B)
- **Rzymskie miesiące** - oś czasu z miesiącami w cyfrach rzymskich

## Instalacja

```bash
# Klonuj repozytorium
git clone https://github.com/jeziorny/TXS.git
cd TXS

# Zainstaluj zależności
pip install -r requirements.txt

# Zainstaluj globalnie (opcjonalne)
pip install -e .
```

## Użycie

```bash
# Podstawowe użycie
./txs AAPL

# Lub po globalnej instalacji
txs AAPL

# Inne przykłady
txs GOOGL
txs MSFT
txs META
txs TSLA
```

## Przykładowy output

```
Kluczowe wskaźniki finansowe dla: Apple Inc. (AAPL)

┌─────────────────────────┬──────────────┬──────────────┬──────────────┬──────────────┐
│ Wskaźnik (wg istotności) │ 2024-12-31   │ 2024-09-30   │ 2024-06-30   │ 2024-03-31   │
├─────────────────────────┼──────────────┼──────────────┼──────────────┼──────────────┤
│ Total Revenue           │ $124.30B     │ $94.93B      │ $85.78B      │ $90.75B      │
│    └ YoY Change %       │ +6.1%        │ +6.1%        │ +4.9%        │ -4.3%        │
│ Gross Profit            │ $54.51B      │ $42.66B      │ $35.31B      │ $38.04B      │
│    └ YoY Change %       │ +4.4%        │ +4.2%        │ +3.1%        │ -2.5%        │
└─────────────────────────┴──────────────┴──────────────┴──────────────┴──────────────┘

[Wykresy ASCII ceny i wolumenu]
```

## Wymagania

- Python 3.8+
- yfinance >= 0.2.0
- pandas >= 1.5.0
- tabulate >= 0.9.0
- plotext >= 5.0.0

## Obsługa błędów

- **Nieprawidłowy ticker** - aplikacja sprawdza poprawność symbolu
- **Brak internetu** - wyświetla komunikat o problemach z połączeniem
- **Brak danych** - gracefully obsługuje brakujące dane finansowe
- **Timeout API** - retry z informacją o problemie

## Licencja

MIT License