## ADDED Requirements

### Requirement: Anàlisi de característiques de la imatge
El sistema ha d'extreure metadades o propietats bàsiques de la imatge per influir en el resultat de la identificació.

#### Scenario: Anàlisi de fitxer vàlid
- **WHEN** el backend rep una imatge
- **THEN** el sistema analitza la mida i el format del fitxer abans de processar la identificació
