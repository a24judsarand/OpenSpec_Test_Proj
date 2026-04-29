## Why

L'aplicació actual encara no té la capacitat real de distingir entre una papallona i altres objectes o animals (com un ànec). Cal una integració amb un model d'Intel·ligència Artificial real per validar que la imatge conté efectivament una papallona.

## What Changes

- Integració de la llibreria TensorFlow.js i el model pre-entrenat MobileNet en el backend.
- Validació de la categoria de la imatge abans de procedir a la identificació de l'espècie.
- Implementació d'un filtre que rebutgi imatges que no siguin insectes o papallones.
- Millora de la resposta del servidor per informar si l'objecte detectat no és una papallona.

## Capabilities

### New Capabilities
- `classificacio-objectes-ia`: Utilitzar IA per classificar l'objecte principal de la imatge.
- `filtre-no-papallona`: Detectar i informar quan la imatge no conté una papallona.

### Modified Capabilities
- `identificacio-papallones`: Es modificarà per incloure un pas previ de validació d'objecte.

## Impact

- Backend: Noves dependències pesades (`@tensorflow/tfjs-node`, `@tensorflow-models/mobilenet`).
- Temps de resposta: La primera petició podria ser més lenta mentre es carrega el model.
