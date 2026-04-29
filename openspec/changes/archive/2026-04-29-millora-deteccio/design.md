## Context

Actualment, l'aplicació retorna una espècie aleatòria sense cap base d'anàlisi. L'usuari demana una millora en la "intel·ligència" del sistema per fer-lo més realista i útil.

## Goals / Non-Goals

**Goals:**
- Proporcionar resultats d'identificació que incloguin un nivell de confiança (percentatge).
- Incloure una breu descripció de cada espècie detectada en català.
- Millorar la lògica del backend per simular un anàlisi més profund de la imatge carregada.

**Non-Goals:**
- Entrenar un model propi de Deep Learning en aquesta fase (massa pesat pel servidor actual).
- Identificació de múltiples papallones en una sola foto.

## Decisions

- **Backend**: S'actualitzarà la funció `identificarPapallona` per retornar un objecte complex que inclogui: nom, confiança (entre 70% i 99%) i descripció. Es podria utilitzar la mida del fitxer o altres metadades bàsiques per variar el resultat i fer-lo menys aleatori.
- **Frontend**: S'actualitzarà la interfície per mostrar aquestes noves dades. S'utilitzarà un component `v-progress-linear` de Vuetify per representar visualment la confiança de la detecció.
- **Dades**: Es crearà una base de dades local (objecte JSON) amb les descripcions de les espècies més comunes a Catalunya.

## Risks / Trade-offs

- **Falsa precisió**: Encara que el percentatge de confiança sigui alt, el sistema continua sent una simulació millorada. Cal informar a l'usuari que els resultats són orientatius.
- **Manteniment**: Afegir més dades d'espècies augmenta el volum de codi en el backend si no es gestiona en un fitxer separat.
