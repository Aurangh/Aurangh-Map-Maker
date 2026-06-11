# Grid Combat Tracker — User Guide

A single-file battle map and combat tracker for D&D 3.5, built for play-by-post games. Paint terrain like a spreadsheet, drop tokens, run initiative, and export images and logs straight into your forum or Discord posts. Everything lives in one HTML file: open it in any modern browser, locally or hosted, and it works. Your data is saved automatically in the browser itself.

## Quick start

Open the file and you'll see a dark grid. Pick the Paint tool, choose a color swatch in the left panel, and drag across the map to draw terrain — that's the whole drawing model. Add a combatant in the bottom-right form, press its 📍 button, click a map cell, and it appears as a token. Press "Next turn ▶" to start cycling initiative. When the round is done, hit "PNG ⬇" to download an image of the map and "copy" on the combat log to grab the round summary, then paste both into your post.

## The interface

The screen has three zones. The **left panel** holds the drawing tools, the terrain palette, and the legend. The **center** is the map canvas, with spreadsheet-style coordinates (columns A, B, C… and numbered rows) so players can call moves like "I move to F7". The **right panel** is the combat side: the initiative list, the combat log, the add-combatant form, and the token library. The **top bar** handles the map title, grid size, zoom, mode switching, file management, and exports.

## Drawing the map

The map is a grid of colored cells, exactly like a Sheets template. Select a swatch in the **terrain palette** and draw with one of three tools: **Paint** (B) brushes cell by cell as you drag, **Rectangle** (R) fills a dragged box, and **Fill** (G) flood-fills a connected region of the same color — the equivalent of selecting a range and applying a fill. **Erase** (E) returns a cell to the default terrain and also removes any label or fog on it.

Swatches are fully editable. Click one to select it, then change its color or name with the controls below the palette; the **legend** updates automatically, so "rock", "water", and "open deck" mean whatever you decide they mean. Add new swatches with "+ add swatch"; removing one converts its cells to the default terrain.

**Labels** (T) place short text directly on a cell — room numbers, "p2"-style markers, anything. Click a cell with the tool active, type, and press Enter. Entering empty text deletes an existing label.

**Fog of war** (F) paints a hidden layer over cells; **Unfog** (U) reveals them. As GM you see fog as a translucent hatched overlay so you always know what's underneath. In player mode, fog is fully opaque and hides everything beneath it, including tokens and labels.

## Tokens and combatants

There are two kinds of tokens, and the distinction matters.

**Combatants** are full participants: they have a name, initiative, AC, hit points, size (Medium through Gargantuan), conditions, and an optional portrait. Create one with the form at the bottom right, then press its **📍** button and click the map to place it. Move placed tokens by dragging with the **Move** tool (V); while dragging, a floating readout shows the distance traveled in feet using the 3.5 diagonal rule. Clicking a token selects it (blue ring) and links it to its card in the sidebar; arrow keys nudge a selected token one square. Hovering over a token shows its name, and its current HP in GM mode.

To give a combatant a portrait, press **🖼** on its card and choose an image file. The image is automatically cropped to a circle and downscaled, so any JPG or PNG works — monster art, a player's avatar, a photo of your cat.

**Stamps** (♟, shortcut S) are the second kind: disposable markers that never enter the initiative list. Set a base letter, color, and size in the options under the tool, then every map click drops an auto-numbered marker — G1, G2, G3 and so on. Use them for mooks, summons, objects, or anything you'll track narratively. Remove them with Erase or undo; reposition them with Move.

## The token library

Any combatant can be saved as a reusable template with the **📚** button on its card. The library, at the bottom of the right panel, stores the name, portrait, color, size, AC, and maximum HP — and it persists independently of any map, so your recurring PCs and favorite monsters follow you across every encounter and campaign. Click a library entry's name to drop a fresh copy into the current encounter (then 📍 to place it); press ✕ to remove the template.

## Running combat

The initiative list sorts itself by initiative score, highest first. **Next turn ▶** advances through the order, marking the active combatant with a gold ring on the map and a highlight in the sidebar; when the order wraps, the round counter increments. **Reset** returns to round 1 with no active turn.

Each combatant card exposes its numbers directly: initiative, AC, current and maximum HP. For damage and healing, type the amount in the small ± field and press **Dmg** or **Heal** — this also writes the result to the log. Conditions come from a dropdown of the standard 3.5 list (prone, shaken, nauseated, and the rest); they appear as tags on the card, and clicking a tag removes it.

The **combat log** records all of this automatically: damage, healing, conditions gained and lost, whose turn it is, and round transitions. The note field beneath it accepts free text — type and press Enter to append anything else worth remembering. The **copy** button puts the entire log on your clipboard, formatted to paste directly into a forum or Discord post.

## Measuring and areas of effect

The **Measure** tool (M) draws a line between two cells as you drag and reports the distance in feet and squares, counting diagonals as 1-2-1-2 per the 3.5 rules.

The **AoE** tool (A) overlays spell templates. Choose a shape — burst/spread, cone, or line — and a size, then click the map: the origin snaps to the nearest grid intersection, as the rules require. For cones and lines, drag to set the direction (cones quantize to the eight compass directions). On release, a message lists every token caught in the area, markers included — exactly what you need before rolling a fireball's worth of saves. The orange overlay stays visible until you switch tools, so it appears in PNG exports if you want players to see the blast zone.

## Importing maps from images

Press **🖼 Import map** in the top bar and choose an image. A calibration view opens: set the number of columns and rows, then drag the two red corner handles onto the corners of the image's grid until the red overlay lines up with it. From there you have two paths.

**Convert to terrain** suits maps drawn with flat cell colors — exports from a Sheets template, for instance. The tool samples the interior of every cell, detects the distinct colors, and rebuilds the map as native terrain with an auto-generated palette (up to 14 swatches). You then rename the swatches to match your legend. If the original had fog tiles drawn as a color, they arrive as a terrain swatch; flood-erase those regions and repaint them with the actual Fog tool.

**Use as background** suits scanned or published maps with textures and artwork. The calibrated region is placed under the grid as an image; terrain cells start transparent, and any painting you do appears as a translucent overlay on top — useful for marking difficult terrain or other cells with mechanical meaning without obscuring the art. A "Remove bg" button appears in the top bar while a background is set.

## Managing multiple maps and campaigns

The **🗂 Maps** button opens the file manager. Give the current map a name and a campaign tag, then **Save**; the list groups saved maps by campaign and sorts them by last update. Click a name to load it, **⧉** to duplicate (handy for "same dungeon, next room"), **✕** to delete, **Save as new** to fork the current state, and **New map** for a blank grid. Once a map has been saved, the quick **Save** button in the top bar overwrites it directly.

The current working state also autosaves continuously, so closing the browser mid-encounter loses nothing.

## GM mode and player mode

The tracker opens in **GM mode** with everything available. Pressing the mode button switches to **player mode**: editing tools disappear, fog becomes opaque, hidden tokens and labels vanish, NPC health bars are hidden, and the sidebar becomes a read-only **Party panel** showing each PC's portrait, AC, initiative, current HP, and conditions. Players can move tokens marked as PC, and they can measure — nothing else. The "⬅ back to GM" button returns to full control.

Player mode serves two purposes: previewing exactly what your players are entitled to see before you export, and handing the file (or a hosted URL plus a state JSON) to players for them to consult.

## Saving, exporting, and sharing

Three export formats cover the play-by-post loop. **PNG ⬇** downloads an image of the current map, stamped with the title and round number — the thing you paste into the thread. The combat log's **copy** button provides the textual round summary. **JSON ⬇** exports the complete map state to a file, and **JSON ⬆** imports one; this is how you archive encounters, move between devices, or hand players an interactive copy of the battle.

All persistent data — current map, saved maps, token library — lives in the browser's IndexedDB storage. It survives reloads and restarts but is tied to that browser on that device. Export JSON copies of anything important; browser storage is sturdy, not sacred.

## Keyboard shortcuts

| Key | Action | | Key | Action |
|---|---|---|---|---|
| V | Move/select | | F | Fog |
| M | Measure | | U | Unfog |
| B | Paint | | T | Label |
| R | Rectangle | | E | Erase |
| G | Fill | | A | AoE template |
| S | Stamp | | Arrows | Nudge selected token |
| Ctrl+Z | Undo | | Ctrl+Shift+Z / Ctrl+Y | Redo |

## A typical play-by-post round

Load the encounter map, or duplicate a saved template. Place the party from the token library and the opposition from the form or stamps. As players post their actions, move their tokens (the drag readout confirms movement is legal), apply damage and conditions through the cards, and let the log accumulate. When the round resolves, export the PNG, copy the log, paste both into the thread, and save. The next round picks up exactly where the autosave left it.
