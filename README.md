# Web Hangman Game (Flask)

## O projekcie
Klasyczna gra w Wisielca (Hangman) zrealizowana w formie dynamicznej aplikacji webowej. Projekt wykracza poza zwykłą grę – posiada wbudowany system kont użytkowników, dzięki któremu gracze mogą śledzić swoje postępy, zdobywać punkty i przeglądać historię odgadniętych haseł.

Aplikacja losuje hasła z różnych kategorii (plików tekstowych) i dynamicznie aktualizuje stan gry oraz grafiki za pomocą sesji przeglądarki.

## Technologie
* **Backend:** Python, Flask
* **Baza danych:** SQLite, Flask-SQLAlchemy (ORM)
* **Zarządzanie sesją i autoryzacja:** Flask-Login, Werkzeug Security (hashowanie haseł algorytmem pbkdf2:sha256)
* **Frontend:** HTML, CSS (szablony renderowane przez Jinja2)

## Kluczowe funkcjonalności
* **System autoryzacji:** Rejestracja, bezpieczne logowanie oraz wylogowywanie użytkowników. Hasła nie są przechowywane otwartym tekstem.
* **Zarządzanie stanem (Session state):** Aplikacja śledzi na bieżąco liczbę prób, wpisywane litery oraz status wygranej/przegranej w ramach sesji Flask.
* **Statystyki graczy:** Dedykowany widok statystyk (`/stats`), pokazujący łączny wynik (długość odgadniętych słów) oraz historię słów przypisaną do konkretnego użytkownika w bazie danych.
* **Dynamiczne kategorie:** Słowa losowane są z plików w folderze `static/words/`. Kategoria zależy od nazwy pliku.

## Jak uruchomić projekt lokalnie

1. Sklonuj repozytorium:
   ```bash
   git clone https://github.com/FranusCode/hangman.git

2. Zainstaluj wymagane biblioteki z pliku requirements.txt:
   ```bash
   pip install -r requirements.txt
4. Uruchom serwer aplikacyjny:
   ```bash
   python wsgi.py
6. Otwórz przeglądarkę i przejdź pod adres podany w konsoli (domyślnie http://0.0.0.0:4000/). Baza      danych SQLite (users.db) zostanie wygenerowana automatycznie przy pierwszym uruchomieniu.
