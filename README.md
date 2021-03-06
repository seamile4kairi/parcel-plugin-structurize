# parcel-plugin-structurize

[![npm badge](https://img.shields.io/npm/v/parcel-plugin-structurize.svg)](https://www.npmjs.com/package/parcel-plugin-structurize)
[![Codacy Badge](https://api.codacy.com/project/badge/Grade/d17ed96821dc491b81ae0de1ebb1ce8e)](https://app.codacy.com/app/samrith/parcel-plugin-structurize?utm_source=github.com&utm_medium=referral&utm_content=samrith-s/parcel-plugin-structurize&utm_campaign=Badge_Grade_Dashboard)
[![Say Thanks!](https://img.shields.io/badge/Say%20Thanks-!-1EAEDB.svg)](https://saythanks.io/to/samrith-s)
[![Donations Badge](https://yourdonation.rocks/images/badge.svg)](https://www.patreon.com/samrith)

A [Parcel][parcel] plugin that lets you organize your build directory into any structure.

## Why?

Currently, Parcel builds everything for production in a flat structure. Sometimes, we might need a particular structure or might just prefer having a structure in the build folder.

This plugin runs only in `build` and let's you organize your scripts, styles and assets into folders.

## Getting Started

Via NPM

```
npm i -D parcel-plugin-structurize
```

Via Yarn

```
yarn add --dev parcel-plugin-structurize
```

## Configuration

To configure the plugin, add `parcel-plugin-structurize` as a key to your `package.json` file:

```json
{
    "name": "my-parcel-project",
    "parcel-plugin-structurize": {
        "scripts": {
            "match": "*.{js,js.map}",
            "folder": "js"
        },
        "styles": {
            "match": "*.{css,css.map}",
            "folder": "css"
        },
        "assets": {
            "match": "*.{png,svg,jpg,jpg2,jpeg,gif,bmp,webm}",
            "folder": "assets"
        }
    }
}
```

Right now, the plugin only supports `scripts`, `styles` and `assets`. Please feel free to raise a PR to add support for other types (example: `fonts`)!

For the supported keys, you can pass a custom folder and a custom glob:

-   `assets`: Denotes ONLY images. Updates every `img` tag in all your HTML files.
-   `scripts`: Denotes ONLY JavaScript files. Updates every `script` tag in all your HTML files.
-   `styles`: Denotes ONLY stylesheets. Updates every `style` and `link` tag in all your HTML files.

Additionally, the plugin also updates paths of source-maps to match the updated folder structure.

To turn the plugin off, you can also set `"parcel-plugin-structurize": false` in your `package.json`.

[parcel]: https://parceljs.org
