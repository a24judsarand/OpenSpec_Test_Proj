## ADDED Requirements

### Requirement: Filtre de validació de papallones
El sistema ha de retornar un missatge d'error específic si l'objecte detectat no pertany a la categoria de papallones o insectes similars.

#### Scenario: Intent de pujada de no-papallona
- **WHEN** el sistema detecta que l'objecte no és una papallona
- **THEN** es mostra el missatge: "Ho sentim, el sistema no ha detectat cap papallona en aquesta imatge."
