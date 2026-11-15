# Base de dades de llibres · Institut Escola Enric Granados

Catàleg de llibres infantils del centre. Qualsevol persona amb l'enllaç pot consultar els llibres i fer-ne cerques. Només les persones amb el **codi d'edició** poden afegir, editar o esborrar llibres.

Guia d'ús per a l'equip docent: **`Guia_d'us_Base_de_dades_de_llibres.pdf`**.

## Com funciona

| Part | On és | Funció |
|---|---|---|
| **Dades** | Full de càlcul de Google, pestanya **Llibres**, al Drive del compte @egranados.cat | Guarda tots els llibres. És l'única font de dades. |
| **Script** | Apps Script, dins del mateix full (*Extensions → Apps Script*) | Llegeix i escriu files al full quan la pàgina li ho demana. |
| **Pàgina** | Repositori de GitHub (GitHub Pages), fitxer `index.html` | Mostra la taula, el formulari, els filtres i la cerca. No guarda dades. |

Les dades de portades, pàgines, títol, autor i temàtica sugerida es busquen en serveis externs (Open Library i Google Books) a partir de l'ISBN o del títol i l'autor.

## Fitxers del repositori

| Fitxer | Ús |
|---|---|
| `index.html` | La pàgina completa (HTML, CSS i JavaScript en un sol fitxer). |
| `logo.png` | Logo de l'Institut Escola, al header. |
| `favicon.png` | Icona de la pestanya del navegador. |
| `icon-192.png`, `icon-512.png`, `apple-touch-icon.png` | Icones per instal·lar la pàgina com a aplicació. |
| `manifest.json` | Configuració de la instal·lació (nom, icona, color). |
| `README.md` | Aquest document. |

Tots els fitxers han d'estar a l'arrel del repositori, a la mateixa carpeta.

## Funcions

- **Cerca:** un únic camp que busca per títol, autor, ISBN o temàtica.
- **Filtres:** Tapa, Tipus de lletra, Temàtica i rang de Nº pàgines (com el de preus d'Amazon). Es poden combinar entre ells i amb la cerca.
- **Afegir un llibre:**
  - Escriu l'ISBN i surt del camp: es completen títol, autor, pàgines i suggeriments de temàtica.
  - O bé, si el número no és clar, prem **Buscar per títol i autor**, tria el llibre correcte de la llista i prem **Usar aquest**.
  - Revisa la tapa, el tipus de lletra i la temàtica abans de guardar.
- **Editar i esborrar:** icones ✏️ i 🗑️ a cada fila.
- **Codi d'edició:** la primera vegada que guardes, esborres o importes, la pàgina el demana. Queda guardat en aquell navegador. A un ordinador compartit, prem **Oblidar el codi d'edició** en acabar.
- **Completar tots els buits per ISBN:** busca dades per a tots els llibres que tinguin camps buits. Triga uns minuts.
- **Exportar a CSV (Excel)** i **Fer còpia (JSON)**: descàrregues per a Excel o per a còpies de seguretat.
- **Importar còpia:** afegeix llibres des d'un fitxer JSON. Els que ja existeixen no es dupliquen.
- **Instal·lació:** la pàgina es pot instal·lar com a aplicació a l'ordinador, al mòbil o a la tauleta.

## Actualitzar la pàgina

1. Ves al repositori a GitHub i pulsa **Add file → Upload files**.
2. Arrossega el nou `index.html`. Ha de tenir exactament aquest nom.
3. Pulsa **Commit changes** i espera uns minuts.
4. Recarrega la pàgina amb **Ctrl + F5**, o obre-la en una finestra d'incògnit.

Les dades no es modifiquen en actualitzar la pàgina: estan al full de càlcul.

## Manteniment

- **Canviar el codi d'edició:** edita la línia `const TOKEN = ...` a l'script. Després ves a *Implementar → Gestionar implementacions → Editar → Nova versió → Implementar*. La URL no canvia. Cal oblidar el codi antic a cada ordinador i escriure el nou.
- **Canviar la URL de l'script:** només cal si es torna a implementar com a nova aplicació web. Aleshores s'ha d'actualitzar la constant `API` dins de `index.html`.
- **Còpia de seguretat:** al full de càlcul, *Fitxer → Historial de versions*, o descarrega una còpia JSON des de la pàgina.
- **Propietari del full:** recomanable que sigui una cuenta institucional del centre, no una cuenta personal.

## Limitacions conegudes

- Els ISBN mal escrits no es poden trobar. Usa **Buscar per títol i autor** per corregir-los.
- Algunes portades no existeixen a les bases de dades externes, sobretot en edicions antigues o en català.
- Les temàtiques suggerides arriben en anglès i sovint són genèriques. Cal revisar-les a mà.
- Qualsevol persona amb l'enllaç pot veure la base de dades. Només es pot modificar amb el codi d'edició.
- No hi ha identificació d'usuaris: el control d'escriptura és únicament el codi.

## Requisits

- Compte de Google del centre (@egranados.cat) per al full de càlcul i l'script.
- Navegador actualitzat: Chrome, Edge, Firefox o Safari.
- Connexió a internet.
