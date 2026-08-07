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

Kartfiler laddas upp direkt i **roten av repot på `main`**, alltså på samma
nivå som `index.md` och `README.md`.

Exempel:

`FO26_K5_Navertjal.tif`

Undermappar behöver inte skapas för kartorna. Detta gör publiceringen enklare
och minskar risken för felaktiga sökvägar.

### Lagring över tid

Kartfilerna är endast avsedda att finnas tillgängliga under den period då de
ska publiceras. Av upphovsrättsliga skäl ska tidigare års kartfiler inte
arkiveras i repositoryt.

När ett nytt års kartor ska publiceras tas därför föregående års GeoTIFF-filer
bort från repot.

Historiska kartfiler ska inte läggas i årsmappar eller på annat sätt sparas
publikt i repositoryt.

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
2. Kontrollera att filnamnet följer namnstandarden.
3. Ladda upp `.tif`-filen direkt i roten av repot på `main`.
4. Öppna `index.md`.
5. Lägg till eller uppdatera knappen för kartan. Länken ska innehålla exakt
   samma filnamn som den uppladdade filen.
6. Commit:a ändringarna.
7. GitHub Pages bygger och publicerar automatiskt den nya versionen.
8. Kontrollera den publicerade sidan och prova kartlänken på en mobiltelefon.

Observera att filnamn och sökvägar är skiftlägeskänsliga. Ett felaktigt
filnamn i `index.md` leder till **404 Not Found**.

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

### Publicering och GitHub Pages

Efter en commit tar det normalt någon minut innan GitHub Pages har byggt om och publicerat webbplatsen.

Om ändringarna inte syns efter några minuter:

1. Kontrollera att den senaste körningen under **Actions → pages build and deployment** har slutförts utan fel.
2. Uppdatera webbläsaren (vid behov med en hård uppdatering eller i ett privat fönster).
3. Om GitHub Actions eller GitHub Pages har driftstörningar kan publiceringen bli fördröjd. Aktuell driftstatus finns på:

https://www.githubstatus.com/

Vid tillfälliga driftstörningar kan det räcka att göra en ny commit när GitHub åter fungerar normalt för att trigga en ny publicering. :contentReference[oaicite:0]{index=0}


> **Tips**
>
> Om en kartlänk ger **404 Not Found** beror det nästan alltid på att
> filnamnet i `index.md` inte exakt överensstämmer med namnet på den
> uppladdade filen. Kontrollera stavning, filändelse (`.tif`) samt
> stora och små bokstäver.
