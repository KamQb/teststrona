# Migracja strony do WordPress (Astra + Elementor)

Ten katalog zawiera pakiet migracyjny strony **VoltEdge Electrical** do WordPressa.

> ⚠️ **Ważne:** WordPress nie działa na GitHub Pages (wymaga PHP + MySQL).
> Strona statyczna pozostaje na https://kamqb.github.io/teststrona/ —
> wersja WordPress działa na dowolnym hostingu WP (patrz pkt 1).

## Zawartość pakietu

| Plik | Do czego służy |
|---|---|
| `elementor-template-voltedge-home.json` | Cała strona główna jako szablon Elementora (hero, karty usług, baner oferty, o firmie, kontakt, stopka — 1:1 z wersji statycznej) |
| `images/` | Zdjęcia + favicon do wgrania do biblioteki mediów |
| `custom-css.css` | Dodatkowy CSS (efekt powiększania menu, płynne przewijanie) |

## Instrukcja krok po kroku

### 1. Zainstaluj WordPress

Potrzebujesz hostingu z PHP 8+ i MySQL, np.:

- **Lokalnie (do testów):** [Local](https://localwp.com/) (darmowy, najprostszy) albo `docker run -e ... wordpress`
- **Hosting:** dowolny hosting WP (np. host w Polsce: home.pl, cyber_Folks, cyberly, OVH)

### 2. Zainstaluj motyw i wtyczki

1. **Wygląd → Motywy → Dodaj nowy** → wyszukaj i aktywuj **Astra**
2. **Wtyczki → Dodaj nową** → zainstaluj i aktywuj **Elementor** (darmowa wersja wystarczy)

### 3. Ustaw typografię (Inter)

**Wygląd → Dostosuj → Global → Typografia** → w polach *Base Typography* i *Headings Typography* wybierz font **Inter**.

### 4. Zaimportuj stronę

1. **Strony → Dodaj nową** → tytuł `Home` → kliknij **Edit with Elementor**
2. W edytorze kliknij ikonę **folderu** (szablony) → zakładka **My Templates** → **Import Templates**
3. Wgraj plik `elementor-template-voltedge-home.json` → kliknij **Insert**
4. Zapisz stronę (**Update/Publish**)

> Alternatywnie: **Szablony → Zapisane szablony → Importuj** — potem wstaw szablon
> na nowej stronie przez ikonę folderu.

### 5. Ustawienia strony (Astra + Elementor)

Na stronie `Home` (edycja w WordPressie, zakładka **Astra Settings** / ustawienia strony):

- **Template (Elementor):** `Elementor Full Width` — treść na całą szerokość
- **Sidebar:** `No Sidebar`
- **Disable Elements:** odznacz **Title** (tytuł strony) — strona ma własny nagłówek

### 6. Strona główna

**Ustawienia → Czytanie (Reading)** → *Your homepage displays* → **A static page** → wybierz `Home`.

### 7. Menu nagłówka

**Wygląd → Menu** → utwórz menu `Main` z **własnymi linkami** (Custom Links, URL + etykieta):

| URL | Etykieta |
|---|---|
| `#home` | Home |
| `#services` | Services |
| `#offer` | Special Offer |
| `#about` | About |
| `#contact` | Contact Us |

Przypisz lokalizację **Primary Menu**.

> Logo: **Wygląd → Dostosuj → Header Builder → Site Title & Logo**.
> Favicon: **Ustawienia → Ogólne → Ikona witryny** (`images/favicon.svg`).

### 8. Stopka

Stopka jest częścią szablonu Elementora. Wyłącz domyślną stopkę Astry:
**Strony → Home → Edytuj → Astra Settings → Disable Elements → Footer**
(tytuł *Footer Widget Area*). Jeśli tej opcji nie ma w darmowej Astrze —
usuń sekcję stopki z szablonu i zbuduj stopkę w **Wygląd → Dostosuj → Footer Builder**.

### 9. Obrazy

Szablon tymczasowo ładuje zdjęcia z GitHub Pages (`https://kamqb.github.io/teststrona/...`),
więc działa od razu po imporcie. Żeby hostować lokalnie:

1. **Media → Dodaj nowy** → wgraj pliki z `images/`
2. W edytorze Elementora kliknij każde zdjęcie → **Choose Image** → wybierz z biblioteki

### 10. Formularz kontaktowy

Sekcja formularza w szablonie to **demo (statyczne)**. Podłącz prawdziwy formularz:

- **WPForms Lite** lub **Contact Form 7** (darmowe) → utwórz formularz → w edytorze
  usuń widżet HTML z demo-formularzem → wstaw wtyczkę **Shortcode** z shortcode’em formularza
- albo **Elementor Pro** → widżet **Form**

### 11. Efekt powiększania menu

Skopiuj zawartość `custom-css.css` do **Wygląd → Dostosuj → Dodatkowy CSS**.

## Różnice względem wersji statycznej

- Menu nagłówka obsługuje WordPress (Astra), nie hamburger JS
- Formularz wymaga wtyczki (na statycznej stronie też był tylko demo)
- Licznik „4.9 Average rating" w sekcji About → zamieniony na „10+ Years"
  (widżet Counter nie obsługuje ułamków)
