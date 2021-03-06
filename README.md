  "name": "@webextension-toolbox/webpack-webextension-plugin",
  "version": "2.1.3",
  "description": "Webpack plugin that compiles web-extension manifest.json files and adds smart auto reload",
  "main": "./dist/index.js",
  "types": "./dist/index.d.ts",
  "repository": "git@github.com:webextension-toolbox/webpack-webextension-plugin.git",
  "author": "Henrik Wenz <HaNdTriX@gmail.com> (https://github.com/HaNdTriX)",
  "contributors": [
    {
      "name": "Dávid Balatoni",
      "email": "balcsida@gmail.com",
      "url": "https://github.com/balcsida"
    },
    {
      "name": "Andrew Nagy",
      "url": "https://github.com/tm1000"
    }
  ],
  "license": "MIT",
  "private": false,
  "scripts": {
    "lint": "eslint --ignore-path .eslintignore --ext .js,.ts ./src",
    "build-plugin": "tsc -p ./src/plugin/tsconfig.json",
    "build-client": "webpack-cli --config ./src/client/webpack.config.js --mode=production",
    "build": "concurrently \"npm:build-plugin\" \"npm:build-client\"",
    "dev-plugin": "tsc -p ./src/plugin/tsconfig.json --watch",
    "dev-client": "webpack-cli --config ./src/client/webpack.config.js --watch --mode=development",
    "dev": "concurrently \"npm:dev-plugin\" \"npm:dev-client\"",
    "generate-manifest-schema": "typescript-json-schema ./src/plugin/tsconfig.json browser._manifest.WebExtensionManifest > ./src/plugin/manifest.schema.json"
  },
  "dependencies": {
    "@types/chrome": "^0.0.188",
    "ajv": "^6.12.6",
    "mustache": "^4.2.0",
    "webpack-sources": "^3.2.3",
    "ws": "8.7.0"
  },
  "devDependencies": {
    "@tsconfig/node12": "^1.0.9",
    "@types/firefox-webext-browser": "^94.0.1",
    "@types/mustache": "^4.1.3",
    "@types/webpack": "^5.28.0",
    "@types/webpack-sources": "^3.2.0",
    "@types/ws": "^8.5.3",
    "@typescript-eslint/eslint-plugin": "^5.27.0",
    "@typescript-eslint/parser": "^5.27.0",
    "concurrently": "^7.2.1",
    "eslint": "^8.16.0",
    "eslint-config-airbnb-base": "^15.0.0",
    "eslint-config-prettier": "^8.5.0",
    "eslint-plugin-import": "^2.26.0",
    "prettier": "^2.6.2",
    "ts-loader": "^9.3.0",
    "typescript": "^4.7.2",
    "typescript-json-schema": "^0.53.1",
    "webpack": "^5.73.0",
    "webpack-cli": "^4.9.2"
  },
  "engines": {
    "node": ">=12"
  }
}
