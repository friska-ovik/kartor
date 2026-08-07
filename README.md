# Friska Örnsköldsviks kart-repository

Detta repository innehåller georefererade orienteringskartor och guider för Friska Örnsköldsvik.

Även om kartor och guider går att hämta direkt här är detta inte den avsedda ingången för användare.

Den publika och mobilanpassade sidan finns här:

**[friska-ovik.github.io/kartor](https://friska-ovik.github.io/kartor/)**

## För administratörer

### Kartfiler

Kartorna ska publiceras som **GeoTIFF-filer (`.tif`)** med georefereringen inbyggd i filen.

Kontrollera före publicering att:

- filen öppnas på rätt geografisk plats i QGIS
- koordinatsystemet är **SWEREF 99 TM (EPSG:3006)**
- kartan fungerar utan separat `.tfw`-fil
- filen går att importera i QField

En korrekt GeoTIFF behöver alltså ingen separat `.tfw`-fil för publiceringen.

### Filnamn

Kartfiler ska namnges enligt:

`FOÅR_KX_Plats.tif`

där:

- `ÅR` är tvåsiffrigt årtal
- `X` är kartans nummer
- `Plats` är kartområdets namn

Använd helst endast vanliga bokstäver i själva filnamnet, alltså exempelvis `a` i stället för `ä` och `o` i stället för `ö`.

Exempel för karta 5 över Nävertjäl år 2026:

`FO26_K5_Navertjal.tif`

Filnamnsstandarden gör det enklare för användaren att identifiera rätt karta bland nedladdade filer när den ska importeras i QField.

### Publicera en ny karta

1. Kontrollera GeoTIFF-filen i QGIS.
2. Ladda upp `.tif`-filen till repositoryt.
3. Öppna `index.md`.
4. Lägg till eller uppdatera knappen för kartan så att länken pekar på exakt rätt filnamn.
5. Commit:a ändringarna till `main`.
6. GitHub Pages bygger och publicerar därefter automatiskt en ny version av webbplatsen.
7. Kontrollera den publicerade sidan på:
   **[friska-ovik.github.io/kartor](https://friska-ovik.github.io/kartor/)**

Observera att filnamn och sökvägar är skiftlägeskänsliga. Ett felaktigt filnamn i `index.md` leder till **404 Not Found**.

### GitHub Pages

Webbplatsen publiceras från:

- branch: `main`
- katalog: `/(root)`

`index.md` är den publika startsidan.

En commit i repositoryt startar en ny GitHub Pages-publicering. Det innebär att även en ändring i exempelvis `README.md` bygger om webbplatsen utifrån den senaste versionen av hela `main`.

Om en ändring inte syns på webbplatsen, kontrollera **Actions → pages build and deployment** för att se om publiceringen har lyckats.

### Guider och övriga filer

Guider och andra resurser som används på den publika sidan lagras i respektive mapp i repositoryt.

Vid ändring av filnamn eller sökväg måste motsvarande länk i `index.md` också uppdateras.
