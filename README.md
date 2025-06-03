# # 🎾 TennisApp – Aplikacja do zarządzania zawodnikami tenisa

## 📋 Opis aplikacji

**TennisApp** to prosta aplikacja okienkowa stworzona w języku **C# (.NET Windows Forms)**, umożliwiająca:

- dodawanie zawodników do bazy danych PostgreSQL,
- przeglądanie listy zawodników,
- edytowanie i usuwanie zawodników z listy,
- Funkcje walidacyjne: (Imię i nazwisko nie mogą zawierać cyfr, Ranking musi być unikalny, Wymagane pola: imię, nazwisko, data urodzenia, kraj, ranking.)

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

## Pliki Aplikacji
| Plik                | Opis                                         |
| ------------------- | -------------------------------------------- |
| `MainForm.cs`       | Formularz do dodawania zawodnika             |
| `MenuForm.cs`       | Główne menu aplikacji                        |
| `PlayerListForm.cs` | Lista zawodników z opcją edycji/usuwania     |
| `EditPlayerForm.cs` | formularz edycji zawodnika |
| `README.md`         | Dokumentacja aplikacji                       |
| `Plik do bazy danych.txt`         | plik do stworzenia bazy danych                      |


## ⚙️ Konfiguracja i uruchomienie

### 1. Wymagania

-.NET Framework lub .NET 6+
- Visual Studio lub inny edytor C#
- PostgreSQL
- Biblioteka Npgsql (do komunikacji z bazą PostgreSQL)

## 2.Tworzenie bazy danych
- zaloguj się do PostreSQL i utwórz baze danych przy użyciu zalączonego pliku

## 3.Zainstaluj NpgSql
- W visual studio przejdz do Tools > NuGet Package Manager > Package Manager Console i zainstaluj NpgSql

