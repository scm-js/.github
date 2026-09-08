<p align="center">
  <img src="https://raw.githubusercontent.com/scm-js/.github/main/profile/globe.png" width="880" alt="scmJS">
</p>

# scmJS

A map editor for **StarCraft** and **Brood War** that runs in a browser tab, modelled on
StarEdit, SCMDraft 2 and StarForge. It opens the game's own `.scm` and `.scx` maps (and a
bare `.chk` scenario), draws them with the game's terrain and unit graphics, and saves
archives the game plays. Whatever it does not understand in a file is copied through
untouched, so a map only loses what you deliberately change.

**[Open the editor](https://editor.scmjs.dev)** &nbsp;·&nbsp;
[Downloads and nightlies](https://scmjs.dev) &nbsp;·&nbsp;
[The guide](https://docs.scmjs.dev/guide/) &nbsp;·&nbsp;
[Documentation](https://docs.scmjs.dev)

> **Beta.** Nothing here has shipped a campaign yet. Keep backups of maps you care about,
> and check anything important in-game before you rely on it.

## If you make maps

Terrain in tiles or the game's own ISOM brushes, with blending, symmetry and copy-paste
that carries everything under the selection. Units, sprites, doodads, locations and fog on
their own layers. Triggers three ways: a list editor, SCMDraft's text format, and a
TypeScript-like language that compiles down to them. Strings, WAVs, switches, forces and
every scenario setting, plus the map checks and Test Map before you hand it to anyone.

Nothing is uploaded. The map stays on your disk, and the graphics come out of a StarCraft
installation you already have — the editor asks for it once, keeps it in the browser, and
this project redistributes none of Blizzard's data. There is a desktop build if you would
rather double-click a `.scx`, and a container image for a copy on your own network.

Start with [the guide](https://docs.scmjs.dev/guide/); it goes from opening the editor to
a finished melee map, then through each layer and dialog in turn.

## If you write code

The editor is React, TypeScript and Vite, with the file formats written from the ground up
— MPQ, CHK, the `.dat` tables, the tileset graphics — and a test suite over real maps.
[docs.scmjs.dev/map-files](https://docs.scmjs.dev/map-files/) is the format reference,
[game-data](https://docs.scmjs.dev/game-data/) covers what is read out of the archives, and
[development](https://docs.scmjs.dev/development/) is how to build and run it.

Most of what is interesting sits behind the plugin API. A plugin is a module the editor
fetches from a repository and runs in the page: it can add menu items, dialogs, docked
panels and tools, read and edit the open map in one undoable transaction, and store its own
settings. Everything below is written against that same API — there is no privileged
insider version of it — so
[plugin-hello-world](https://github.com/scm-js/plugin-hello-world) is a working plugin to
copy, [docs.scmjs.dev/plugins](https://docs.scmjs.dev/plugins/) is the guide and
[/api](https://docs.scmjs.dev/api/) the reference. Issues and pull requests are welcome on
any of these repositories.

## The repositories

| | |
| --- | --- |
| [scm-js](https://github.com/scm-js/scm-js) | the editor itself, and the map maker's guide |
| [plugin-api](https://github.com/scm-js/plugin-api) | `@scm-js/plugin-api`, the type definitions a plugin builds against |
| [registry](https://github.com/scm-js/registry) | the index behind **Plugins ▸ Browse Plugins…** |
| [site](https://github.com/scm-js/site) | [scmjs.dev](https://scmjs.dev), the landing page |
| [docs](https://github.com/scm-js/docs) | [docs.scmjs.dev](https://docs.scmjs.dev), built from the editor's own documents |
| [nightly](https://github.com/scm-js/nightly) | last night's build of `main`, served at [nightly.editor.scmjs.dev](https://nightly.editor.scmjs.dev) |

Plugins that ship switched on:

| | |
| --- | --- |
| [scm-scx](https://github.com/scm-js/plugin-scm-scx) | search [scmscx.com](https://scmscx.com) and open a map straight from it |
| [repair](https://github.com/scm-js/plugin-repair) | checks a map as it opens and offers to rebuild what is missing or broken |
| [walkability](https://github.com/scm-js/plugin-walkability) | where ground units can actually go, and how wide the chokes are |
| [image-to-terrain](https://github.com/scm-js/plugin-image-to-terrain) | paints a picture into terrain |
| [paint](https://github.com/scm-js/plugin-paint) | lines, shapes, text and sprays made of units, sprites, doodads, terrain or fog |
| [trigscript](https://github.com/scm-js/plugin-trigscript) | a TypeScript-like language, and its editor, compiled to triggers |
| [stamp-library](https://github.com/scm-js/plugin-stamp-library) | named terrain pieces kept across maps and shared as JSON |

And the rest, a tick away in **Manage Plugins**:

| | |
| --- | --- |
| [trigedit](https://github.com/scm-js/plugin-trigedit) | SCMDraft 2's text trigger editor |
| [scmjs-dev](https://github.com/scm-js/plugin-scmjs-dev) | a scmjs.dev account: maps kept online, and the AI assistant |
| [melee-wizard](https://github.com/scm-js/plugin-melee-wizard) | symmetric start locations and mineral lines for a ladder map |
| [section-explorer](https://github.com/scm-js/plugin-section-explorer) | an annotated hex editor over the map's own sections |
| [hello-world](https://github.com/scm-js/plugin-hello-world) | the smallest plugin there is, to copy |

MIT licensed. StarCraft and Brood War are Blizzard Entertainment's; this project is not
affiliated with Blizzard, and ships none of the game's data.
