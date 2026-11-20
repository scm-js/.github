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

scmJS is a map editor and replay viewer for StarCraft, Brood War and StarCraft: Remastered,
modelled on StarEdit, SCMDraft 2 and StarForge. It runs in a browser tab or as a desktop app,
draws maps with the game's own graphics, classic or Remastered, and saves maps the game plays.

Around the editor:

* **Replays** open on the map they were played on, and at scmjs.dev they play back and are
  analysed: fights, economy and tech.
* **The play page** at [scmjs.dev/play](https://scmjs.dev/play/) runs StarCraft 1.16.1's own
  engine in the browser, from your own StarCraft files: test a map, play a mod, or play
  against a bot.
* **Mods** such as Cosmonarchy BW play there with their own code, and the editor makes maps
  for them with their units and tilesets.
* **`scmjs`, the command line**, looks inside maps and replays, checks maps in CI, plays a
  map's triggers in the game, keeps a mod as a folder of text, and runs bots.
* **AI apps** (Claude Desktop, Claude Code, Cursor and others) read and change maps through
  `scmjs mcp`, with each change arriving in the open editor as one undo step.
* **TrigScript** writes triggers in TypeScript, with tests, and builds programs that run
  inside StarCraft: Remastered.
* **Bots** in JavaScript or BWAPI C++ play on the same engine as the play page.

Plugins add to the editor. The [plugins page](https://scmjs.dev/plugins.html) lists the
current ones, and you install them in the editor from **Plugins ▸ Browse Plugins…**.

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
| Play page | https://scmjs.dev/play/ |
| Command line | `brew install scm-js/tap/scmjs`, Scoop, or `npm install -g @scm-js/cli` ([how](https://docs.scmjs.dev/cli/)) |

## Documentation

* [The map maker's guide](https://docs.scmjs.dev/guide/)
* [All documentation](https://docs.scmjs.dev)

## Game data

The editor does not include any of Blizzard's files. The first time you open it, it asks for
your StarCraft folder, classic (1.16) or Remastered, and reads the graphics from there. The
desktop app finds an installed game by itself. Without StarCraft, Blizzard's free map editor
download is enough to edit maps and watch replays; testing a map or playing needs the game.
[Installing](https://docs.scmjs.dev/installing/) has the details.

## Your data

Maps and game data stay on your computer. Nothing is uploaded unless you ask for it: keeping
maps or replays in your scmjs.dev account, sharing one by link, editing a map with others,
using scmscx.com, or using the AI tools, which send what they read of the map to the AI you
chose.

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
| [scm-js](https://github.com/scm-js/scm-js) | the editor itself, the guides, the `scmjs` command line ([`@scm-js/cli`](https://www.npmjs.com/package/@scm-js/cli)), the editor's map code as a library ([`@scm-js/core`](https://www.npmjs.com/package/@scm-js/core)) and the types for JavaScript bots ([`@scm-js/bot`](https://www.npmjs.com/package/@scm-js/bot)) |
| [plugin-api](https://github.com/scm-js/plugin-api) | `@scm-js/plugin-api`, the type definitions a plugin builds against |
| [registry](https://github.com/scm-js/registry) | the list behind **Plugins ▸ Browse Plugins…** |
| [site](https://github.com/scm-js/site) | [scmjs.dev](https://scmjs.dev), the landing page |
| [docs](https://github.com/scm-js/docs) | [docs.scmjs.dev](https://docs.scmjs.dev), built from the editor's own documents |
| [nightly](https://github.com/scm-js/nightly) | last night's build of `main`, served at [scmjs.dev/nightly](https://scmjs.dev/nightly/) |
| [replay](https://github.com/scm-js/replay) | [`@scm-js/replay`](https://www.npmjs.com/package/@scm-js/replay), which reads StarCraft replays from 1.16 to Remastered |
| [mod](https://github.com/scm-js/mod) | [`@scm-js/mod`](https://www.npmjs.com/package/@scm-js/mod), which reads a Brood War mod (a folder, an MPQ, an MPQDraft or FireGraft exe, a zip) without running it |
| [scmbot](https://github.com/scm-js/scmbot) | builds a BWAPI bot into a `.scmbot` file to play against on [scmjs.dev/play](https://scmjs.dev/play/) |
| [ai-engine](https://github.com/scm-js/ai-engine) | the prompt recipes behind scmjs.dev's AI features |
| [homebrew-tap](https://github.com/scm-js/homebrew-tap) | `brew install scm-js/tap/scmjs`, the command line for macOS and Linux |
| [scoop-bucket](https://github.com/scm-js/scoop-bucket) | `scoop install scmjs`, the command line for Windows |

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
| [mods](https://github.com/scm-js/plugin-mods) | the Mod Editor: a mod's tables, strings, pictures, sounds and scripts, with the map drawn from the mod as you change it |
| [scm-sim](https://github.com/scm-js/plugin-scm-sim) | lets other plugins use the game engine behind [scmjs.dev/play](https://scmjs.dev/play/), and adds **Tools ▸ Test in Browser** |
| [api-playground](https://github.com/scm-js/plugin-api-playground) | try the plugin API in a panel without writing a plugin |
| [hello-world](https://github.com/scm-js/plugin-hello-world) | the smallest plugin there is, to copy |

Retired: [eudplib](https://github.com/scm-js/plugin-eudplib), replaced by TrigScript's own
builds, and [ai](https://github.com/scm-js/plugin-ai), whose features moved into scmjs-dev.

## License

MIT. StarCraft and Brood War are trademarks of Blizzard Entertainment. This project is not
affiliated with Blizzard and does not include any of the game's data.

[ATTRIBUTION.md](https://github.com/scm-js/scm-js/blob/main/ATTRIBUTION.md) credits the
algorithms and libraries the editor uses.
