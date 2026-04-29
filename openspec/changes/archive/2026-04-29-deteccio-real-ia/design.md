## Context

L'usuari ha demostrat que el sistema actual és fàcilment enganyable (exemple de l'ànec). Cal un pas de validació d'IA real per garantir la integritat de les dades.

## Goals / Non-Goals

**Goals:**
- Detectar si l'objecte de la imatge és realment una papallona o un insecte similar.
- Rebutjar imatges d'altres animals, objectes o persones.
- Mantenir la interfície en català i sense emoticones.

**Non-Goals:**
- Identificar l'espècie exacta de la papallona mitjançant IA (seguirem usant la nostra base de dades local per a les 5 espècies per ara, però validant que l'objecte és una papallona).

## Decisions

- **Tecnologia**: S'instal·laran `@tensorflow/tfjs-node`, `@tensorflow-models/mobilenet` i `canvas` o `jimp` per processar els buffers d'imatge en Node.js.
- **Flux de treball**:
  1. El servidor rep la imatge.
  2. MobileNet classifica la imatge.
  3. Es revisen les 3 primeres categories. Si cap d'elles conté "butterfly", "moth" o paraules clau relacionades, es retorna un error: "Això no sembla una papallona".
  4. Si es valida com a papallona, es procedeix a la identificació de l'espècie amb la lògica existent.
- **Model**: Es carregarà el model en memòria quan s'iniciï el servidor per minimitzar el temps de latència en les peticions.

## Risks / Trade-offs

- **Consum de memòria**: TensorFlow.js pot consumir molta RAM. Cal vigilar els recursos del servidor.
- **Falsos negatius**: Algunes papallones molt rares podrien no ser detectades correctament per un model generalista com MobileNet.
