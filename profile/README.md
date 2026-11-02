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

scmJS is a map editor for StarCraft and Brood War, written in TypeScript and modelled on
StarEdit, SCMDraft 2 and StarForge. It runs in a browser tab or as a desktop app.

Plugins add to it. The [plugins page](https://scmjs.dev/plugins.html) lists the current ones,
and you install them in the editor from **Plugins ▸ Browse Plugins…**.

The editor is in English and Korean. The Korean translation was machine-generated, and we are
looking for a native speaker to review it. The editor picks the language from your browser, and
you can change it in Preferences.

## Where to find it

The main site is [scmjs.dev](https://scmjs.dev).

| Release | Link |
| :--- | :--- |
| Web editor (stable) | https://scmjs.dev/editor/ |
| Web editor (nightly) | https://scmjs.dev/nightly/ |
| Desktop app | [Windows, Mac, Linux](https://scmjs.dev/index.html#download) |

## Documentation

* [The map maker's guide](https://docs.scmjs.dev/guide/)
* [All documentation](https://docs.scmjs.dev)

## Game data

The editor does not include any of Blizzard's files. It needs `StarDat.mpq` and `BrooDat.mpq`
from StarCraft to draw tiles, units and doodads. The first time you open it, it offers to
download them from Blizzard, or you can give it your own copies. The desktop app also looks
for them in the usual StarCraft install folders.

## Your data

Maps and game data stay on your computer. Nothing is uploaded unless you use the scmjs.dev or
scmscx.com plugins.

## Contributing

### Writing a plugin

A plugin is a JavaScript module that reads and edits the open map through the plugin API.
To start:

* [plugin-hello-world](https://github.com/scm-js/plugin-hello-world) is a working example to copy.
* [The plugin guide](https://docs.scmjs.dev/plugins/) explains how plugins load and what they can do.
* [The API reference](https://docs.scmjs.dev/api) lists every call.

While you work on it, the editor can load your plugin straight from your git repository. When
it is ready for others, [submit it to the registry](https://github.com/scm-js/registry/issues/new?template=submit-plugin.yml).

### Working on the editor

Open a pull request against [scm-js](https://github.com/scm-js/scm-js). These help:

* [Map files](https://docs.scmjs.dev/map-files/), the format reference.
* [Game data](https://docs.scmjs.dev/game-data/), what the editor reads from the game's archives.
* [Development](https://docs.scmjs.dev/development/), how to build and run it.

## The repositories

### Main

| Repository | Description |
| :--- | :--- |
| [scm-js](https://github.com/scm-js/scm-js) | the editor itself, and the map maker's guide |
| [plugin-api](https://github.com/scm-js/plugin-api) | `@scm-js/plugin-api`, the type definitions a plugin builds against |
| [registry](https://github.com/scm-js/registry) | the list behind **Plugins ▸ Browse Plugins…** |
| [site](https://github.com/scm-js/site) | [scmjs.dev](https://scmjs.dev), the landing page |
| [docs](https://github.com/scm-js/docs) | [docs.scmjs.dev](https://docs.scmjs.dev), built from the editor's own documents |
| [nightly](https://github.com/scm-js/nightly) | last night's build of `main`, served at [scmjs.dev/nightly](https://scmjs.dev/nightly/) |

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
| [scmjs-dev](https://github.com/scm-js/plugin-scmjs-dev) | a scmjs.dev account: maps kept online, shared editing, and the AI assistant |
| [melee-wizard](https://github.com/scm-js/plugin-melee-wizard) | symmetric start locations and mineral lines for a ladder map |
| [section-explorer](https://github.com/scm-js/plugin-section-explorer) | an annotated hex editor over the map's own sections |
| [trigger-map](https://github.com/scm-js/plugin-trigger-map) | the map's triggers as a graph: who sets and who reads each switch, counter and location |
| [timelapse](https://github.com/scm-js/plugin-timelapse) | records the map as you build it and exports the recording as a GIF or video |
| [aftermath](https://github.com/scm-js/plugin-aftermath) | plays a replay back over its map: heat maps, build orders, APM |
| [magenta](https://github.com/scm-js/plugin-magenta) | a trigger editor where each trigger reads as a sentence, with Remastered EUD conditions and actions |
| [scm-sim](https://github.com/scm-js/plugin-scm-sim) | lets other plugins use the game engine behind [scmjs.dev/play](https://scmjs.dev/play/), and adds **Tools ▸ Test Map in Browser** |
| [api-playground](https://github.com/scm-js/plugin-api-playground) | try the plugin API in a panel without writing a plugin |
| [hello-world](https://github.com/scm-js/plugin-hello-world) | the smallest plugin there is, to copy |

## License

MIT. StarCraft and Brood War are trademarks of Blizzard Entertainment. This project is not
affiliated with Blizzard and does not include any of the game's data.

[ATTRIBUTION.md](https://github.com/scm-js/scm-js/blob/main/ATTRIBUTION.md) credits the
algorithms and libraries the editor uses.
