# PinBoard – Fullstack Image Discovery Platform 

## Architektura

- **MVC (Model-View-Controller)**: Separacja logiki biznesowej (PHP), bazy danych (SQL) i interfejsu (HTML/CSS).
- **Monolit z elementami API**: Główny silnik w PHP, dynamiczne akcje (lajki, nieskończony scroll) przez JavaScript Fetch API.
- **Relacyjna Baza Danych (SQL)**: Skomplikowany system powiązań między użytkownikami, pinami a tablicami.
- **REST API**: Endpointy JSON do komunikacji front-endu z backendem.

## Stuck technologiczny (języki, frameworki, biblioteki)

- **Języki**: PHP 8.x, SQL, JavaScript (ES6+), HTML5, CSS3.
- **Backend**: PHP (Vanilla lub Slim Framework), MySQL/MariaDB.
- **Frontend**: Vite (bundler), Masonry.js (układ kafelkowy), marked.js (renderowanie opisu Markdown).
- **Zależności**: Composer (PHP), NPM (JS).
- **Zewnętrzne**: Tokeny API do integracji (np. Cloudinary do hostingu zdjęć lub lokalny system plików).

## Logika biznesowa

- **System Pinowania**: Upload zdjęć przez PHP z walidacją rozmiaru i typu. Przechowywanie ścieżek do plików w bazie SQL.
- **Tablice (Boards)**: Użytkownicy mogą tworzyć kolekcje. Jeden Pin może być przypisany do wielu tablic (tabela łącząca w SQL).
- **Dynamiczny Grid**: JavaScript oblicza pozycje kafelków (Masonry) po załadowaniu zdjęć z bazy danych.
- **Interakcje UX**: 
    - Rejestracja i logowanie (sesje PHP).
    - System polubień i zapisywania pinów u siebie (re-pin).
    - Podgląd Pina w oknie modalnym bez odświeżania strony.

## Grupa docelowa
- **Odbiorca**: Projektanci, hobbyści i osoby szukające inspiracji wizualnych.
- **Potrzeby**: Szybki dostęp do treści wizualnych, łatwe kategoryzowanie zdjęć, estetyczny interfejs "Mobile-First".

## Wymagania techniczne

### Wymagania prawne
- **Prawa autorskie**: System raportowania naruszeń (DMCA).
- **RODO**: Szyfrowanie danych wrażliwych (hasła: `password_hash`), polityka plików cookies.
- **Licencje**: Kod na licencji MIT, biblioteki zewnętrzne zgodnie z ich licencjami (np. Masonry - MIT).

### Standaryzacja
- **SEO**: Dynamiczne generowanie Open Graph tags dla każdego zdjęcia (podgląd w Social Media).
- **WCAG 2.1**: Odpowiednie kontrasty, obsługa klawiatury w modalu, tagi `alt` pobierane z bazy danych.

---
# Standardowe wymagania końcowe projektu
- **Dokumentacja techniczna**: Kompletna dokumentacja bazy danych (diagram ERD) oraz komentarze w kodzie (PHPDoc).
- **Dokumentacja Markdown**: Plik `GUIDE.md` opisujący proces instalacji środowiska (XAMPP/Docker) i konfigurację bazy SQL.