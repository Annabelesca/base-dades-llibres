# Base de dades de llibres · Institut Escola Enric Granados

Catàleg de llibres infantils del centre. Permet consultar, cercar i filtrar els llibres, i afegir-ne, editar-ne o esborrar-ne (només les persones amb el codi d'edició).

## Com funciona

La informació es reparteix en tres llocs:

| Part | On és | Què fa |
|---|---|---|
| **Dades** | Full de càlcul de Google (pestanya **Llibres**), al Drive del compte @egranados.cat | Guarda tots els llibres. És l'única font de dades. |
| **Script** | Apps Script, dins del mateix full (*Extensions → Apps Script*) | Llegeix i escriu files al full quan la pàgina li ho demana. |
| **Pàgina** | Aquest repositori (GitHub Pages), fitxer `index.html` | Mostra la taula, el formulari i els filtres. No guarda cap dada. |

Les dades d'Open Library (portades, pàgines, títol, autor i suggeriments de temàtica) es consulten en temps real a partir de l'ISBN.

## Fitxers del repositori

- **`index.html`**: la pàgina completa (HTML, CSS i JavaScript en un sol fitxer).
- **`logo.png`**: logo de l'Institut Escola, que es mostra al header. Ha d'estar a la mateixa carpeta que `index.html`.
- **`README.md`**: aquest document.

## Ús habitual

- **Consultar:** qualsevol persona amb l'enllaç pot veure els llibres i fer servir els filtres i el buscador.
- **Afegir un llibre:** escriu l'ISBN i surt del camp (o pulsa **Buscar dades per ISBN**). Es completen automàticament el títol, l'autor, les pàgines i les suggeriments de temàtica. Revisa-les i completa la tapa, el tipus de lletra i la temàtica.
- **Editar o esborrar:** usa els botons de cada fila. Els canvis apareixen a tothom en uns segons.
- **Codi d'edició:** la primera vegada que guardes, esborres o importes, la pàgina et demana el codi. Es guarda en aquell navegador. Si l'ordinador és compartit, prem **Oblidar el codi d'edició** al final.

## Altres funcions

- **Completar tots els buits per ISBN:** busca dades per a tots els llibres amb ISBN que tinguin camps buits. Triga uns minuts.
- **Exportar a CSV (Excel):** descarrega la llista per obrir-la amb Excel o LibreOffice.
- **Fer còpia (JSON):** descarrega una còpia de seguretat de tota la base de dades.
- **Importar còpia:** afegeix a la base de dades els llibres d'un fitxer JSON. Els que ja existeixen (mateix identificador) no es dupliquen.

## Com actualitzar la pàgina

1. Puja el nou `index.html` a l'arrel del repositori amb **Add file → Upload files**, amb el mateix nom. Substituirà l'anterior.
2. Espera uns minuts perquè GitHub Pages el publiqui.
3. Recarrega la pàgina amb **Ctrl + F5** (o obre-la en una finestra d'incògnit) per veure els canvis.

Les dades no es modifiquen en actualitzar la pàgina: estan al full de càlcul.

## Manteniment

- **Canviar el codi d'edició:** edita la línia `const TOKEN = ...` del script (Apps Script), després ves a *Implementar → Gestionar implementacions → Editar → Nova versió → Implementar*. La URL no canvia. Les persones que editen hauran de fer servir **Oblidar el codi d'edició** i escriure el codi nou.
- **Canviar la URL de l'script:** si mai es torna a implementar com a nova aplicació web, cal actualitzar la constant `API` dins de `index.html`.
- **Còpia de seguretat:** al full de càlcul, *Fitxer → Historial de versions*, o descarrega una còpia JSON des de la pàgina.

## Limitacions conegudes

- Les dades d'Open Library estan en anglès en els suggeriments de temàtica i no sempre hi són. Per això la temàtica es revisa a mà.
- Open Library no té totes les edicions en català; alguns llibres necessitaran introducció manual de pàgines.
- La URL de l'aplicació web de l'script és pública: qualsevol pot llegir la base de dades. Només es pot modificar amb el codi d'edició.
- No hi ha identificació d'usuaris: el control d'escriptura és únicament el codi.

## Requisits

- Compte de Google del centre (@egranados.cat) per al full de càlcul i l'script.
- Navegador actualitzat (Chrome, Edge, Firefox o Safari).
