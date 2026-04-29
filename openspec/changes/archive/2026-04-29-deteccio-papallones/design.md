## Context

El projecte neix de la necessitat de facilitar la identificació d'espècies de papallones mitjançant tecnologia mòbil/web. Es construirà des de zero utilitzant un stack modern basat en JavaScript.

## Goals / Non-Goals

**Goals:**
- Implementar un servidor Express que pugui rebre i processar imatges.
- Crear una aplicació web amb Vue 3 i Vuetify que permeti fer fotos o pujar fitxers.
- Retornar l'espècie detectada a l'usuari de manera clara i en català.
- Garantir que tota la comunicació amb l'usuari sigui sense emoticones.

**Non-Goals:**
- Autenticació d'usuaris o perfils personals.
- Emmagatzematge permanent de les fotografies en una base de dades.
- Sistema de classificació per a altres insectes o animals.

## Decisions

- **Backend**: S'utilitzarà Node.js amb Express per la seva lleugeresa i facilitat d'integració. El middleware `multer` gestionarà la recepció de fitxers binaris (imatges).
- **Frontend**: Vue 3 serà el framework de referència per la seva reactivitat. Vuetify s'emprarà per garantir una interfície professional i adaptada a dispositius mòbils sense haver de dedicar gaire temps al CSS personalitzat.
- **Detecció**: Es crearà un mòdul de servei que simularà la detecció (o utilitzarà una IA senzilla) per validar el flux complet des de la captura fins a la visualització.
- **Idioma**: Totes les cadenes de text i missatges d'error estaran definits en català directament en el codi o en fitxers de traducció.

## Risks / Trade-offs

- **Qualitat de la imatge**: Les fotos borroses poden donar resultats erronis. Es mitigarà afegint consells de captura a la interfície.
- **Dependències**: L'ús de Vuetify afegeix pes al bundle, però es considera acceptable pel guany en velocitat de desenvolupament i coherència visual.
- **Simulació de detecció**: En aquesta fase, la precisió dependrà de la lògica implementada, que podria ser limitada inicialment.
