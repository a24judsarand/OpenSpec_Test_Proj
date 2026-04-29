# Detector de Papallones

Aquesta és una aplicació web dissenyada per a la identificació d'espècies de papallones mitjançant Intel·ligència Artificial. L'usuari pot pujar una fotografia i el sistema validarà si es tracta d'una papallona abans de proporcionar-ne el nom, una descripció detallada i el nivell de confiança de la detecció.

## Característiques

- **Validació amb IA **: Utilitza TensorFlow.js i el model MobileNet per assegurar que la imatge conté una papallona i filtrar altres objectes o animals.
- **Identificació d'Espècies**: Proporciona informació sobre espècies comunes com la Monarca, la Blanqueta de la col, la Papallona de la reina, el Paó de dia i la Vulcana.
- **Interfície Moderna**: Desenvolupada amb Vue 3 i Vuetify per a una experiència d'usuari fluida i adaptada a dispositius mòbils.
- **Localització**: Tota l'aplicació està redactada exclusivament en català.

## Requisits Previs

- Node.js (versió 18 o superior)
- npm (gestor de paquets)

## Instal·lació

1. Cloneu el repositori o descarregueu el codi font.
2. Accediu a la carpeta del projecte:
   ```bash
   cd deteccio-papallones-app
   ```
3. Instal·leu totes les dependències (arrel, backend i frontend):
   ```bash
   npm install
   npm install --prefix backend
   npm install --prefix frontend
   ```

## Ús

Per iniciar tant el servidor backend com l'aplicació frontend simultàniament, executeu la següent comanda des de la carpeta `deteccio-papallones-app`:

```bash
npm run dev
```

- L'aplicació web estarà disponible a: `http://localhost:5173`
- L'API del backend estarà disponible a: `http://localhost:3000`

## Estructura del Projecte

- `backend/`: Servidor Express amb la lògica de detecció i validació d'IA.
- `frontend/`: Aplicació Vue 3 amb els components d'interfície d'usuari.
- `uploads/`: Carpeta on s'emmagatzemen temporalment les imatges pujades per a la seva anàlisi.

## Metodologia

Aquest projecte ha estat desenvolupat seguint la metodologia **OpenSpec**, garantint una traçabilitat completa des de l'especificació fins a la implementació final.
