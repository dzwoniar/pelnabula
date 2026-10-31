# Pełna Buła Burger — demo strony burgerowni

Statyczny prototyp strony restauracji z prezentacją menu, oferty zestawów, sposobu zamawiania i odpowiedziami na częste pytania. Głównym działaniem użytkownika jest przejście do kontaktu telefonicznego.

**Status:** demo witryny informacyjnej. Repozytorium nie zawiera systemu zamówień, koszyka ani integracji płatności.

## Co jest zaimplementowane

- Responsywny układ z menu, opisem oferty, opiniami i sekcją Burger Box Party.
- Odnośniki `tel:` w kilku sekcjach oraz przyklejony do dołu ekranu przycisk kontaktu na urządzeniach mobilnych.
- FAQ, w którym otwarcie kolejnej odpowiedzi zamyka poprzednią.
- Wyświetlanie godzin dla bieżącego dnia na podstawie lokalnej daty urządzenia i tabeli zapisanej w JavaScript.
- Animacje CSS w sekcji otwierającej oraz odnośniki do zewnętrznej wizytówki, opinii, Facebooka i mapy.

## Stos i architektura

HTML, CSS i JavaScript bez frameworka, bundlera oraz zależności npm. Cała aplikacja znajduje się w [index.html](index.html): style w `<style>`, zawartość strony w HTML i dwa fragmenty logiki na końcu dokumentu — `toggleFaq()` oraz funkcja wyświetlająca godziny.

Projekt nie ma backendu, bazy danych ani zmiennych środowiskowych. Fonty DM Serif Display i DM Sans są pobierane z Google Fonts. Zewnętrzne serwisy są dostępne przez odnośniki, bez integracji API.

## Uruchomienie lokalne

Wymagania: Git, Python 3 i współczesna przeglądarka.

```sh
git clone https://github.com/dzwoniar/pelnabula.git
cd pelnabula
python -m http.server 8000 --bind 127.0.0.1
```

Otwórz [http://127.0.0.1:8000](http://127.0.0.1:8000). Zatrzymanie serwera: `Ctrl+C`. Nie trzeba instalować zależności ani budować projektu.

## Struktura i miejsca zmian

```text
.
├── index.html   # menu, oferta, FAQ, CSS i JavaScript
└── README.md    # dokumentacja projektu
```

Menu, ceny i adresy odnośników są wpisane bezpośrednio w HTML. Paletę kolorów i typografię zmienisz w CSS. Godziny dla poszczególnych dni są w obiekcie `hours` w końcowym skrypcie.

## Granice demo

Wybór produktu nie tworzy zamówienia; przyciski jedynie otwierają obsługę telefonu na urządzeniu. Wskaźnik godzin nie sprawdza aktualnej dostępności lokalu, świąt ani wyjątków w grafiku i nie pobiera danych z serwera.

Ceny, opinie, opisy produktów i warunki dostawy są treścią prototypu. Przed wykorzystaniem strony do realnej obsługi klientów wymagają potwierdzenia i aktualizacji u właściciela oferty.

## Sprawdzenie po zmianach

W repozytorium nie ma testów automatycznych. Sprawdź lokalnie układ na telefonie i komputerze, rozwijanie FAQ, widoczność mobilnego CTA i zgodność tabeli godzin z wyświetlaną informacją. Weryfikacja odnośników `tel:` w kodzie nie wymaga wykonywania połączeń.
