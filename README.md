# Mapbox GL Language

Switch the language of your style in Mapbox GL JS.

## Usage

**mapbox-gl-language** is a [Mapbox GL JS plugin](https://www.mapbox.com/blog/build-mapbox-gl-js-plugins/) that you can easily add on top of your map. Check `index.html` for a complete example.

Make sure to include the JS files.

**When using NPM**

Check [how to use Mapbox GL JS in a module bundler](https://www.mapbox.com/mapbox-gl-js/api/).

```bash
npm install --save mapbox-gl @mapbox/mapbox-gl-browser-language
```

```javascript
const mapboxgl = require('mapbox-gl')
const MapboxBrowserLanguage = require('@mapbox/mapbox-gl-language');
const map = new mapboxgl.Map({
    container: 'map',
    style: 'mapbox://styles/mapbox/traffic-night-v2',
    center: [-77.0259, 38.9010],
    zoom: 9
});
map.addControl(new MapboxBrowserLanguage());
```

## API

<!-- Generated by documentation.js. Update this documentation by updating the source code. -->

### MapboxBrowserLanguage

Create a new [Mapbox GL JS plugin](https://www.mapbox.com/blog/build-mapbox-gl-js-plugins/) that
modifies the layers of the map style to use the 'text-field' that matches the browser language.

**Parameters**

-   `options` **[object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)** Options to configure the plugin.
    -   `options.supportedLanguages` **[Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)&lt;[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)>?** List of supported languages
    -   `options.languageTransform` **[Function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function)?** Custom style transformation to apply

#### setLanguage

Explicitly change the language for a style.

**Parameters**

-   `style` **[object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)** Mapbox GL style to modify
-   `language` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** The language iso code

## Supported Styles

You can configure the plugin to support your own very custom style using style transforms and custom language fields.
By default this plugin works best with official Mapbox styles (or styles derived from official Mapbox styles):

- `mapbox://mapbox-streets-v9`
- `mapbox://mapbox-outdoors-v9`
- `mapbox://mapbox-dark-v9`
- `mapbox://mapbox-light-v9`
- `mapbox://mapbox-satellite-streets-v9`
- `mapbox://mapbox-traffic-day-v9`
- `mapbox://mapbox-traffic-night-v9`


## Develop

Run the linter and watch for changes to rebuild with browserify.

    npm install
    npm run test
    npm run watch

Create a minified standalone build.

    npm install
    npm run build
