## 1. Configuració de l'entorn d'IA

- [x] 1.1 Instal·lar les llibreries de TensorFlow i MobileNet
- [x] 1.2 Instal·lar `jimp` per al processament d'imatges des de buffer

## 2. Desenvolupament de la validació d'IA

- [x] 2.1 Implementar la càrrega del model MobileNet a l'inici del servidor
- [x] 2.2 Crear una funció per convertir el buffer d'imatge a tensor
- [x] 2.3 Desenvolupar la lògica que valida si el resultat de la IA conté paraules clau de papallona

## 3. Integració en el Backend

- [x] 3.1 Afegir el pas de validació d'IA abans de la identificació de l'espècie
- [x] 3.2 Gestionar les respostes d'error en català per a imatges no vàlides

## 4. Proves de camp

- [x] 4.1 Verificar que el sistema rebutja correctament imatges d'altres animals (ànecs, gossos)
- [x] 4.2 Confirmar que les papallones reals segueixen sent identificades correctament
