# Tenemos Problemas Web
Web Client for Tenemos Problemas card game

## Available commands
### Install dependencies
`$ npm install`

### Start the local development server (on port 8080)
`$ npm start`

### Build the production ready code to the /dist folder
`$ npm run build`


All the game code lies inside the **/src/scripts** folder. All assets need to be inside the **/src/assets** folder in order to get copied to /dist while creating the production build. Do not change the name of the index.html and game.ts files.

## Progressive Web App (PWA) Configuration

The ServiceWorker is **disabled by default**. To enable the ServiceWorker the line below should be uncommented.

```html
<script>
  if ('serviceWorker' in navigator) {
    window.addEventListener('load', () => {
      navigator.serviceWorker.register('./sw.js')
    })
  }
</script>
```

The PWA can be personalized with these steps:

- Replace both icons in /pwa/icons
  - One is **512x512** the other **192x192**
- Add a custom **favicon.ico** to /src
- Adjust these parameters in the **manifest.json** file in /pwa
  - **short_name**: Max. 12 characters
  - **name**: The full game name
  - **orientation**: "landscape" or "portrait"
  - **background_color**: color of the splash screen
  - **theme_color**: color of the navbar - has to match the theme-color in the index.html file
- The **sw.js** (serviceWorker) file in /pwa can be left how it is.
- Change the **gameName** in /webpack/webpack.common.js

Read more about PWA on [developers.google.com](https://developers.google.com/web/progressive-web-apps/)


---
This project was generated following this [template](https://github.com/yandeu/phaser-project-template).
