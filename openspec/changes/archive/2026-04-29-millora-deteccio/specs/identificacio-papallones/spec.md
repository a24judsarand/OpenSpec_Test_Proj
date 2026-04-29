## MODIFIED Requirements

### Requirement: Identificació automàtica de l'espècie
El sistema ha d'analitzar la imatge proporcionada i retornar un objecte detallat amb el nom de l'espècie, una descripció i el nivell de confiança.

#### Scenario: Identificació detallada
- **WHEN** el sistema processa una imatge
- **THEN** retorna un JSON amb els camps "especie", "descripcio" i "confiança" (en lloc de només el nom)
