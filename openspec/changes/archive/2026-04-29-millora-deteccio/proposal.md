## Why

El model actual de detecció de papallones és purament aleatori i no realitza cap anàlisi real de la imatge. Això provoca una mala experiència d'usuari i falta de fiabilitat en les identificacions.

## What Changes

- Substitució de la lògica de selecció aleatòria per un sistema d'anàlisi de fitxers més avançat.
- Integració d'un servei o llibreria que permeti una classificació més acurada de les espècies.
- Millora de la interfície frontend per mostrar el percentatge de confiança de la detecció.
- Inclusió de missatges informatius sobre les característiques de l'espècie detectada.

## Capabilities

### New Capabilities
- `analisi-real-imatges`: Capacitat per analitzar les propietats de la imatge i extreure'n informació rellevant per a la identificació.
- `nivell-confiança`: Informar a l'usuari sobre la probabilitat d'encert de la detecció.

### Modified Capabilities
- `identificacio-papallones`: Es modificarà el requisit per deixar de ser una simulació i passar a ser un procés d'identificació real.

## Impact

- Backend: Actualització de `index.js` i possible incorporació de noves dependències de visió per computador.
- Frontend: Actualització de `App.vue` per mostrar els nous camps de confiança i descripció.
