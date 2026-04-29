## ADDED Requirements

### Requirement: Identificació automàtica de l'espècie
El sistema ha d'analitzar la imatge proporcionada i retornar el nom de l'espècie de papallona detectada.

#### Scenario: Identificació positiva d'una espècie coneguda
- **WHEN** el sistema processa una imatge clara d'una papallona (ex. monarca)
- **THEN** el sistema retorna el nom "Papallona Monarca" a la pantalla

#### Scenario: Sistema no pot identificar la papallona
- **WHEN** la imatge és borrosa o no conté cap papallona recognoscible
- **THEN** el sistema informa que no s'ha pogut identificar l'espècie i suggereix fer una nova foto
