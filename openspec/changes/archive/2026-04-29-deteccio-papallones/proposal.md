## Why

Proporcionar una eina accessible per a l'estudi i la identificació de papallones en l'entorn natural. Aquesta aplicació permetrà als usuaris conèixer les espècies que observen de manera instantània mitjançant una fotografia, fomentant així l'interès per la biodiversitat i la ciència ciutadana.

## What Changes

- Creació d'un servei backend robust amb Node.js i Express per gestionar la pujada d'imatges i la comunicació amb el motor de detecció.
- Desenvolupament d'una interfície d'usuari moderna i intuïtiva amb Vue 3 i Vuetify.
- Implementació d'un sistema de càrrega d'imatges des del dispositiu de l'usuari.
- Integració d'un motor de detecció que identifiqui l'espècie de papallona a partir de la imatge proporcionada.
- Tota l'aplicació estarà disponible exclusivament en català.

## Capabilities

### New Capabilities
- `pujada-imatges`: Permet als usuaris carregar o fer fotos de papallones directament des de l'aplicació.
- `identificacio-papallones`: Analitza la imatge i retorna el nom de l'espècie detectada.
- `interficie-catala`: Interfície d'usuari completament localitzada en català.

### Modified Capabilities
- Cap: Es tracta d'una aplicació nova.

## Impact

- Creació de noves rutes API per a la detecció d'imatges.
- Dependències noves: express, multer (per a imatges), vue, vuetify, axios.
- Impacte en el sistema d'arxius per a l'emmagatzematge temporal d'imatges si és necessari.
