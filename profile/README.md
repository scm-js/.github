<p align="center">
  <img src="https://raw.githubusercontent.com/scm-js/.github/main/profile/icon.svg" width="160" alt="scmJS">
</p>

<p align="center">
  <a href="https://github.com/scm-js/scm-js/releases/latest"><img alt="Latest release" src="https://img.shields.io/github/v/release/scm-js/scm-js?style=flat-square&label=release&color=e6b95c&labelColor=12151b"></a>
  <a href="https://github.com/scm-js/scm-js/actions/workflows/build.yml"><img alt="Build status" src="https://img.shields.io/github/actions/workflow/status/scm-js/scm-js/build.yml?branch=main&style=flat-square&label=build&labelColor=12151b"></a>
  <a href="https://www.npmjs.com/package/@scm-js/plugin-api"><img alt="Plugin API on npm" src="https://img.shields.io/npm/v/%40scm-js%2Fplugin-api?style=flat-square&label=plugin%20api&color=4fd1c5&labelColor=12151b"></a>
  <a href="https://github.com/scm-js/scm-js/blob/main/LICENSE"><img alt="MIT licensed" src="https://img.shields.io/github/license/scm-js/scm-js?style=flat-square&label=license&color=4fd1c5&labelColor=12151b"></a>
</p>

# scmJS

scmJS is a powerful, fully featured map editor for **StarCraft** and **Brood War**, written in TypeScript and modelled on
StarEdit, SCMDraft 2 and StarForge. It runs in a native browser tab or as a desktop app.

It comes with a powerful plugin API. See the [plugins page](https://https://scmjs.dev/plugins.html)
for the complete current list of plugins. Install them in the editor by going to **Plugins** → **Browse Plugins**.

#### Supported Languages
English and Korean (AI generated). It should automatically configure locale, but you can override in application preferences. **Currently looking for a native Korean speaker to review the localization!**

### Main Site
https://scmjs.dev

### Releases

| Release | Link |
| :--- | :--- |
| Web Editor (stable) | https://editor.scmjs.dev |
| Web Editor (nightly, latest) | https://nightly.editor.scmjs.dev |
| Desktop Builds | [Windows, Mac, Linux](https://scmjs.dev/index.html#download) |

## Docs
* [User guide and features](https://docs.scmjs.dev/guide/)
* [Docs](https://docs.scmjs.dev)

## Blizzard Assets
The editor ships with no Blizzard assets by default. `stardat.mpq` and `broodat.mpq` are required assets from StarCraft
needed to render tiles, units, and doodads. On first load the editor will prompt you to download them directly
from Blizzard, or you can upload your own files if you have them. The desktop build will attempt to find them
on disk.

## Data Storage
Nothing is uploaded anywhere unless you use the scmjs.dev or scmscx.com plugins. The map stays on your disk, 
and once the Blizzard assets are installed they also remain locally on disk

## Contributing
### Plugins
Consider contributing a plugin. A plugin is a powerful program that allows extensive editing of
the map through a nicely abstracted plugin API. Start with:
* [plugin-hello-world](https://github.com/scm-js/plugin-hello-world) - a working example plugin to
copy
* [docs.scmjs.dev/plugins](https://docs.scmjs.dev/plugins/) - the plugin guide
* [https://docs.scmjs.dev/api](https://docs.scmjs.dev/api) - the plugin API reference

During development you can load your plugin right from your own git repository. Once you have your plugin written and
want to add it to the registry for everyone, [fill out this issue form](https://github.com/scm-js/registry/issues/new?template=submit-plugin.yml).

### The editor
To contribute to the editor itself, see these documents and open a PR against the [scm-js repository](https://github.com/scm-js/scm-js).
* [docs.scmjs.dev/map-files](https://docs.scmjs.dev/map-files/) is the format reference,
* [game-data](https://docs.scmjs.dev/game-data/) covers what is read out of the archives, and
* [development](https://docs.scmjs.dev/development/) is how to build and run it.

## The repositories
### Main
| Repository | Description |
| :--- | :--- |
| [scm-js](https://github.com/scm-js/scm-js) | the editor itself, and the map maker's guide |
| [plugin-api](https://github.com/scm-js/plugin-api) | `@scm-js/plugin-api`, the type definitions a plugin builds against |
| [registry](https://github.com/scm-js/registry) | the index behind **Plugins ▸ Browse Plugins…** |
| [site](https://github.com/scm-js/site) | [scmjs.dev](https://scmjs.dev), the landing page |
| [docs](https://github.com/scm-js/docs) | [docs.scmjs.dev](https://docs.scmjs.dev), built from the editor's own documents |
| [nightly](https://github.com/scm-js/nightly) | last night's build of `main`, served at [nightly.editor.scmjs.dev](https://nightly.editor.scmjs.dev) |

### Plugins
| Plugin | Description |
| :--- | :--- |
| [scm-scx](https://github.com/scm-js/plugin-scm-scx) | search [scmscx.com](https://scmscx.com) and open a map straight from it |
| [repair](https://github.com/scm-js/plugin-repair) | checks a map as it opens and offers to rebuild what is missing or broken |
| [walkability](https://github.com/scm-js/plugin-walkability) | where ground units can actually go, and how wide the chokes are |
| [image-to-terrain](https://github.com/scm-js/plugin-image-to-terrain) | paints a picture into terrain |
| [paint](https://github.com/scm-js/plugin-paint) | lines, shapes, text and sprays made of units, sprites, doodads, terrain or fog |
| [trigscript](https://github.com/scm-js/plugin-trigscript) | a TypeScript-like language, and its editor, compiled to triggers |
| [stamp-library](https://github.com/scm-js/plugin-stamp-library) | named terrain pieces kept across maps and shared as JSON |
| [trigedit](https://github.com/scm-js/plugin-trigedit) | SCMDraft 2's text trigger editor |
| [scmjs-dev](https://github.com/scm-js/plugin-scmjs-dev) | a scmjs.dev account: maps kept online, and the AI assistant |
| [melee-wizard](https://github.com/scm-js/plugin-melee-wizard) | symmetric start locations and mineral lines for a ladder map |
| [section-explorer](https://github.com/scm-js/plugin-section-explorer) | an annotated hex editor over the map's own sections |
| [hello-world](https://github.com/scm-js/plugin-hello-world) | the smallest plugin there is, to copy |

## License
MIT licensed. StarCraft and Brood War are Blizzard Entertainment's; this project is not
affiliated with Blizzard, and ships none of the game's data.

See the [attributions document](https://github.com/scm-js/scm-js/blob/main/ATTRIBUTION.md) for algorithms used in this project.
