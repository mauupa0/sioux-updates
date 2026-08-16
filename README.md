# sioux-updates

Kanał aktualizacji apki **Sioux Local** (zgłaszanie bułek między bułkownią a grillem po lokalnej sieci).

To repo trzyma wyłącznie **zbudowany interfejs** apki (HTML/CSS/JS/fonty) i plik `manifest.json`
z informacją, która wersja jest aktualna. Kod źródłowy siedzi w prywatnym repo `sioux-local`.
Nie ma tu żadnych haseł, kluczy ani danych restauracji.

## Kanały

| Kanał | Apka na telefonie | Do czego |
|---|---|---|
| `beta` | **Sioux Nowa** | nowości do sprawdzenia na zmianie |
| `stable` | **Sioux** | wersja, która ma po prostu działać |

## Jak wysłać aktualizację

W katalogu `sioux-local/sioux-local-app`:

```bash
node tools/wyslij-update.mjs --kanal beta --opis "Co się zmieniło"
```

Skrypt buduje apkę, pakuje ją, liczy sumę kontrolną, wpisuje wszystko do `manifest.json`
i wypycha tutaj. Telefony widzą zmianę w zakładce **⬆️ Aktualizacje**.

Aplikacja sprawdza sumę kontrolną każdej paczki, a nowa wersja musi zameldować, że wstała —
jeśli tego nie zrobi, telefon sam wraca do poprzedniej.
