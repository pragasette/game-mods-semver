# Semantic Versioning for End-User Game Mods

> :information_source: **This is currently a draft:** depending on the
feedback, it may be updated into a more formal specification.

This document aims to apply the concepts of [semantic versioning] to game save
compatibility: the purpose is to let users look at the version number to
determine whether they can update without breaking an existing game save.

## Guidelines

- A mod which refers to this document must declare a version for each public
  release using three numbers separated by dots, called respectively _major_,
  _minor_ and _patch_ versions.

- The mod can be safely updated mid-game to a newer release which has the same
  _major_ version: the mod author expresses the intention to keep the new
  release compatible with a game save created using a previous release of the
  mod having the same _major_ version.

- A change in the _major_ version means compatibility with a previous version
  is not guaranteed: a game save created using a previous release of the mod
  will not work as expected with the newer version; a new game is required to
  use the newer version.

- A change in the _minor_ version means new features are added in a compatible
  fashion: it's safe to update mid-game.

- A change in the _patch_ version means only bugs are fixed, no new feature is
  added and compatibility is preserved: it's safe to update mid-game.

- Downgrading is not supported, unless specifically stated by the mod author.

> :warning: **Warning**  
A mod coming with a versioning scheme which looks like semantic versioning is
to be assumed **NOT** to follow any specification, unless it explicitly refers
to this document.

## Examples

You can safely update mid-game in these cases:

- :heavy_check_mark: 1.2.9 → 1.2.10;
- :heavy_check_mark: 1.2.9 → 1.3.0.

You shouldn't update mid-game in the following cases, things will break and
your game won't work as expected, start a new game instead:

- :x: 1.2.9 → 2.3.0;
- :x: 1.2.9 → 1.2.8.

## What is semantic versioning?

Semantic versioning is a convention used in the software development industry
and is designed to make it easier to tell whether upgrading a piece of software
will keep or break the compatibility with other software.

It revolves around the definition of an [application programming interface]
(API), which can be thought as a set of rules given by the software author to
describe how other pieces of software can interact with it.

## What is the API of a game mod?

A mod can be designed as a library, a modders resource which defines a
traditional API for other mods to interact with.

In most cases, however, a mod meant for direct use by the players doesn't need
to define any API.

When a documented API is missing, the mod version can be linked to game save
compatibility to tell if updating is supported.

## Can things break?

Despite of the author's intention, things break all the time: a release meant
only to fix a bug, may not preserve compatibility as intended.

As a good measure, always keep a backup of your save files before any update.

If you notice any unexpected behavior after updating, test again using the
original version you saved the game with.

In case the issue appears only with the newer version, inform the author in a
polite way and following their instructions to file a bug report.

## License

![Creative Commons License](https://i.creativecommons.org/l/by-sa/4.0/88x31.png)

This work is licensed under a [Creative Commons Attribution-ShareAlike 4.0
International License][CC BY-SA 4.0].


[Semantic versioning]: https://semver.org/
[Application programming interface]: https://en.wikipedia.org/wiki/Application_programming_interface
[CC BY-SA 4.0]: https://creativecommons.org/licenses/by-sa/4.0/
