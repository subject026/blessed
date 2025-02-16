# Blessed v0.1.0 - new terminal goodies for node.js

## 0.2.85

### Patch Changes

- 4d86f1f: types

## 0.2.84

### Patch Changes

- c0425a1: added term.js as dependency

## 0.2.83

### Patch Changes

- 00e41b5: fix publish action

## 0.2.82

### Patch Changes

- 4df6ea6: reset changesets due to new pkg name

![blessed](https://raw.githubusercontent.com/chjj/blessed/master/img/v0.1.0-3.gif)

The features demonstrated in the above gif **element transparency/shadow** and
**border docking**.

## New useful options for your typewriter application:

- **`transparent` option** - Lower element opacity to 50%. This will display
  dimmed elements and content behind the foreground element using a naive color
  blending function (good enough for a terminal's limited amount of colors).
  works best with 256color terminals. (see widget-shadow.js)

- **`shadow` option** - Give the element a translucent shadow. Automatically
  darkens the background behind it. (see widget-shadow.js)

- **`dockBorders` option** - Element borders will automatically "dock" to each
  other. Instead of overlapping the borders end up connecting. (see
  widget-dock.js)

- **`autoPadding` default** - Auto padding is now enabled by default, meaning
  blessed will automatically position elements inside their parent's border.

- **`rleft` property** - Relative offsets are now default element properties
  (`left` instead of `rleft`).

- **`draggable` property** - Make any element draggable with the mouse. (see
  widget-shadow.js or widget-dock.js)

- **`Table` and `ListTable` elements** - Tables with a high quality rendering.
  (see widget-table.js and widget-listtable.js)

- **`Log` element** - A top to bottom logger box with scrollback and other
  features. (see widget-log.js)

- **Obscurable borders** - In addition to docking borders, it's possible to
  obscure borders by sliding them off the screen with negative offsets. (see
  widget-dock.js)

- **Percentage expressions** - Like CSS, arithmetic can now be performed on
  percentages. e.g. `width: '50%-1'`. This is useful for overlapping borders on
  elements with a percentage width. (see widget-dock.js)

## Other features that weren't mentioned before:

- **`setHover` option** - Set a hover text box to follow cursor on mouseover,
  similar to how a web browser handles the "title" attribute. (see widget.js)

- **`Terminal` element** - Spin up a pseudo terminal as a blessed element.
  useful for writing a terminal multiplexer. (requires term.js and pty.js as
  optional dependencies). (see example/multiplex.js)

- **`Image` element** - Uses `w3mimgdisplay` to draw real images your terminal.
  this is much easier than calling w3mimgdisplay by hand. Image elements behave
  like any other element, although it is wise to use `width: 'shrink', height:
'shrink'`. (see widget-image.js)

---

The major things that justified the 0.1.0 release were fixes and stabilization
of api (`autoPadding`/`rleft`/`left`). Scrolling boxes were almost completely
revamped to work a bit smarter.

---

## Things yet to come:

- **@secrettriangle's [improvements](https://github.com/slap-editor/slap) for
  textareas** - This allows for real text navigation.

- **Gravity and margin layouts**

This is something that's been in the idea bin for a while. Every element could
potentially have properties like:

```
  gravity: 'bottomleft',
  margin: 5,
``

In other words, just a more complex `float` system than what the CSSOM is used
to.
```
