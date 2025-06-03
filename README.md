# # 🎾 TennisApp – Aplikacja do zarządzania zawodnikami tenisa

## 📋 Opis aplikacji

**TennisApp** to prosta aplikacja okienkowa stworzona w języku **C# (.NET Windows Forms)**, umożliwiająca:

- dodawanie zawodników do bazy danych PostgreSQL,
- przeglądanie listy zawodników,
- edytowanie i usuwanie zawodników z listy,
- walidację danych wejściowych (np. brak cyfr w imieniu/nazwisku, unikalny ranking).

Aplikacja wspiera podstawową obsługę GUI i łączy się z bazą danych PostgreSQL przy użyciu biblioteki **Npgsql**.

---

## 🗃️ Struktura bazy danych

Baza danych **`tennisdb`** zawiera dwie tabele:

### `countries`
| Kolumna     | Typ danych | Uwagi                     |
|-------------|-------------|---------------------------|
| `id`        | SERIAL      | Klucz główny             |
| `name`      | TEXT        | Nazwa kraju              |

### `players`
| Kolumna       | Typ danych | Uwagi                                        |
|---------------|------------|----------------------------------------------|
| `id`          | SERIAL     | Klucz główny                                 |
| `first_name`  | TEXT       | Imię zawodnika                               |
| `last_name`   | TEXT       | Nazwisko zawodnika                           |
| `birth_date`  | DATE       | Data urodzenia                               |
| `country_id`  | INT        | Klucz obcy do `countries(id)`                |
| `ranking`     | INT        | Ranking zawodnika (unikalny)                 |
| `is_active`   | BOOLEAN    | Czy zawodnik jest aktywny                    |

---

## ⚙️ Konfiguracja i uruchomienie

### 1. Wymagania

- .NET Framework lub .NET 6+
- Visual Studio lub inny edytor C#
- PostgreSQL
- Biblioteka Npgsql (do komunikacji z bazą PostgreSQL)

