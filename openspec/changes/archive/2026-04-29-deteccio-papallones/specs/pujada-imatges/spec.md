## ADDED Requirements

### Requirement: Captura i pujada d'imatges
El sistema ha de permetre a l'usuari seleccionar una imatge del seu dispositiu o fer una fotografia directament per ser analitzada.

#### Scenario: Pujada amb èxit d'una imatge
- **WHEN** l'usuari selecciona un fitxer d'imatge vàlid (JPG, PNG) i prem el botó d'enviar
- **THEN** el sistema confirma la recepció de la imatge i comença el procés d'identificació

#### Scenario: Intent de pujada de fitxer no vàlid
- **WHEN** l'usuari intenta pujar un fitxer que no és una imatge (ex. PDF)
- **THEN** el sistema mostra un missatge d'error indicant que només s'accepten imatges
