## ADDED Requirements

### Requirement: Localització íntegra en català
Tota la interfície d'usuari, missatges del servidor i avisos han d'estar redactats exclusivament en català.

#### Scenario: Visualització de la interfície principal
- **WHEN** l'usuari carrega l'aplicació
- **THEN** tots els botons, títols i etiquetes es mostren en català (ex. "Puja una foto", "Identificant...")

#### Scenario: Missatges d'error en català
- **WHEN** es produeix un error en el servidor
- **THEN** el missatge d'error retornat a l'usuari està escrit en català i no conté cap emoticona
