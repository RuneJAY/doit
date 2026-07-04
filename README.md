# Min dag (2 børn)

En rutine-app til børn, lavet til iPad. Viser **morgen**, **eftermiddag** og **aften**
med klokkeslæt, skifter automatisk efter ugedag, og nulstiller krydsene hver ny dag.
Ingen konto, ingen server, ingen reklamer — alt bliver på enheden.

Hele appen ligger i `index.html` (styling + kode indbygget), så den virker, uanset
hvordan den åbnes.

## Kør den som installerbar app

1. Læg alle filerne i roden af et GitHub-repo.
2. **Settings → Pages** → branch `main`, mappe `/ (root)`.
3. Åbn `https://DITNAVN.github.io/REPO/` i Safari på iPad →
   Del-knappen → **Føj til hjemmeskærm**.

## Redigér opgaverne

Al data ligger øverst i `<script>` i `index.html`:
- `MORNING` – morgenrutinen (samme hver skoledag, med klokkeslæt)
- `afternoonFor(day)` – eftermiddag pr. ugedag
- `EVENING` – aften pr. ugedag (0=søndag … 6=lørdag)

Hvert punkt er `{x:"tekst", e:"emoji", t:"KL" (valgfrit)}`.

## Model

- Morgen + eftermiddag vises kun man–fre (skoledage)
- Aften vises alle syv dage
- Krydsene gemmes i `localStorage` (`min-dag:v1`) og nulstilles ved dagsskift

**Husk:** hæv `CACHE`-versionen i `sw.js` hver gang du ændrer `index.html`.

## To børn

Øverst vælges hvilket barn der er aktivt. Hvert barn har **egne kryds og egen
stjernebank**; rutinerne er fælles. Navnene ændres under ⚙️ → "Børnenes navne".
Gamle data fra én-barns-versionen migreres automatisk til barn 1.
