# The Keep

A single-file, browser-based companion for medieval-fantasy tabletop campaigns.

The Keep is a chronicler's tool, not a rules engine. It holds the soft, narrative substance of a long campaign: who your party has met, what they have found, where they have been, what factions favour or hate them today, what dooms are ticking. Built to feel like a hand-bound book opened on a candlelit table rather than a software dashboard.

## At a Glance

- One self-contained HTML file. Open in any modern browser. No install, no build step, no server, no network calls.
- Per-chronicle persistence. Run as many campaigns as you want, each kept separate.
- Light and dark themes. Parchment-and-ink for noble adventures, Cult of Shadow for those who play the villains.
- Fourteen interconnected modules, each a "room" in the keep.
- Universal search across everything (press `/`).
- Full chronicle backup and restore (JSON).
- GPL-3.0. No telemetry, no accounts.

## Philosophy

Three principles shape every part of the project.

**Documents are objects.** Each room is meant to feel like a thing you hold, not a screen you scroll. Cards have corner brackets and parchment shadows. The Tavern is a posting board. The Augury draws blood-red tarot cards. The Lists read like an initiative slate.

**The work weaves itself.** Each module knows about the others. Pin a tavern rumour and it lands in the Almanac. Recruit a patron and they enter the roster. Tag an Archive entry as a Person and it groups in the sidebar. Universal search jumps you to the exact record, not just the room.

**Words matter more than features.** The room names, the button labels, the placeholder text are all written in the chronicler's voice. The Roll. The Augury. The Cabinet. The Hearth. The vocabulary itself is part of the playing surface.

## The Rooms

### The Gate

The home tile, a welcome landing with a grid of every room in the keep, grouped by category.

### The Roll

The campaign manager. Found a new chronicle, retire an old one, switch between them, export a single chronicle, or back up the entire Keep. Restore supports both merge (add to existing) and replace (full wipe with a typed confirm).

### Workshop

Where the chronicler builds the world.

**The Scriptorium.** Forge handouts on aged parchment. Five styles: Parchment Letter, Wanted Poster, Journal Page, Ledger Sheet, Royal Edict. Procedural SVG aging seeded for repeatable results. Export as PNG or SVG.

**The Archive.** A markdown wiki for lore. Wikilinks in `[[brackets]]` auto-create entries, and NPC names from the roster turn forest-green when linked. Sidebar search with hit highlighting and body excerpts. Hover any wikilink for a small parchment preview. Entries carry optional type tags (Person, Place, Thing, Event, Faction, Lore) with coloured stripes in the sidebar and grouping headers when more than one type is present.

**Hall of Faces.** NPC conjurer. Rolls a name, culture, role, voice, want, mannerism, appearance, and secret. Three cultures: Northron, Rivenmark, Southern. Persists a roster of inducted NPCs, with backlinks showing the Archive entries that mention them and the Cabinet items they carry.

**The Cabinet.** A catalogue of relics, letters, weapons, and curiosities the party has touched. Each find has a kind (eight glyph categories from Relic to Curiosity), description, current holder, location and date of finding, worth, and status (Held, Lost, Hidden, Given, Destroyed) with colour-coded borders.

**The Tavern.** Roll a tavern. Name, proprietor, atmosphere, menu, three patrons, three rumours with truth tags. Reveal rumours one at a time or all at once. Pin individual rumours to the Almanac. Recruit any patron into the Hall roster with one click.

**Faction Ledger.** Track the powers your party crosses. Sigil, motto, goal, notes, and a party-standing gauge from minus ten to plus ten across seven labels (Blood Enemy through Sworn). Inter-faction relations are directional: House Ashlow can scorn the Greyfern Order while the Order pities them. Cards view for detail, Matrix view for the whole web at once. Shows mentioned-in backlinks from the Archive, plus a count badge when any Threats are linked to the faction.

### Mysteries

Where the unknown is asked of.

**The Oracle.** Yes-or-no consultation in the style of Mythic GME. Likelihood from "almost certainly not" through "almost certainly," modulated by qualifier, with roughly one in three results carrying a complication. History of the last fifty castings. Pin any verdict to the day's note.

**The Augury.** Drawn answers. Three methods: tarot (single, three-card, Celtic cross), runes (Elder Futhark subset), and scrying (mirror, smoke, water, flame). Pin any reading to the Almanac.

**The Almanac.** An editable in-world calendar. Twelve months of thirty days, seven daynames, year 712 of the Long Comet by default, with moon phases. Click a day to write a note, set weather, or advance the campaign-today marker. The Almanac is the spine of the chronicle: every pin from every other room lands here.

**Threats.** Forged in the Dark style countdown clocks. Each clock has 4, 6, 8, or 12 segments. Tick by clicking segments directly, or with plus and minus buttons. Auto-pins to the Almanac on fulfillment. Optionally linked to a faction, in which case the linked faction card shows a count badge of active and fulfilled clocks.

### Table

Where the chronicler plays.

**The Lists.** Initiative tracker. HP bars, conditions (eight types: Prone, Bleed, Stun, Hex, Burn, Mark, Shield, Hidden), critical-HP highlighting, drag-to-reorder via a grip handle, and a From Roster pulldown to pull NPCs from the Hall. Big Mode strips down to large readable text for projecting at the table. Keyboard `n` and right-arrow advance turns.

**The Hearth.** Eight Web Audio layers (rain, wind, fire, drone, bells, tavern, waves, crows) with individual gain. Six presets for common moods (Tavern at Night, Storm-Bound Watch, etc). Audio context cleans up automatically when leaving the room.

## Getting Started

Download `the-keep.html`. Open it in any modern browser. That is the entire install.

On first open, the Keep seeds a chronicle called "First Chronicle" with example data in several rooms (NPCs, factions, a tavern, threats, cabinet finds, Archive entries) so you can see the shape of things. Edit anything; the seed is not sacred.

To start truly fresh, open The Roll, found a new chronicle, and retire the seeded one. Or just delete or rewrite the seed content as you go.

## Universal Search

Press `/` anywhere outside a text input, or click the magnifying glass in the banner, to open universal search. It queries every persistent surface in the active chronicle:

- Archive entries (title and body)
- NPC roster (all fields including voice, want, secret, mannerism, appearance)
- Faction Ledger (name, motto, goal, notes)
- Cabinet items (name, kind, status, description, holder, place, worth)
- Threats (name, description, fill state)
- Almanac day notes (body and weather)
- Oracle history (last eighty castings)

Results group by source with sticky section headers. Arrow keys navigate, Enter opens the active result. Clicking a result navigates not just to the room but to the specific record, scrolling it into view and (where applicable) flashing a brief gold glow.

## Storage and Backup

The Keep persists everything to your browser's local storage (or to a sandboxed `window.storage` API when running inside an embedding environment that provides one). Each chronicle's data is stored under a per-chronicle key prefix; switching chronicles swaps the active prefix.

**Important.** Local storage is per-browser, per-device, and per-origin. Clearing your browser data wipes it. Always back up before doing anything risky.

Backups are plain JSON files. From The Roll:

- **Export Chronicle** writes the active chronicle to disk.
- **Backup the Keep** writes every chronicle plus global settings (theme, last-active campaign).
- **Restore (Merge)** imports a backup without erasing existing chronicles. Imported chronicles get unique ids to avoid collisions.
- **Restore (Replace)** wipes everything first, then loads the backup. Requires typing the word `RESTORE` to confirm.

## Themes

A button in the banner switches between the parchment-and-ink Light theme and the Cult of Shadow Dark theme. Both are full palettes, not inverted colours; the dark theme has its own atmospheric noise, its own Tavern parchment (dark stained vellum rather than cream), and its own decisions for surfaces where light text sits on heraldic backgrounds.

The choice persists across sessions and applies to every chronicle.

## Keyboard Shortcuts

- `/` opens universal search
- `Esc` closes modals and the search overlay
- Arrow Up and Arrow Down navigate search results
- `Enter` opens the active search result
- `n` or Right Arrow advances the turn in The Lists

## Cross-Module Connections

The rooms know about each other. Some of the connections that compound across a campaign:

- Wikilinks in `[[brackets]]` inside Archive entries become navigable links. NPC names render in forest-green and auto-create entries seeded from the NPC's card content. Hover any wikilink for a preview.
- Tavern patrons can be recruited into the Hall of Faces roster with one button. The patron's tavern is recorded on the resulting NPC.
- Cabinet items track who holds them; the Hall of Faces card for an NPC shows the items they carry.
- Threats can be linked to factions. The faction card shows a count of ticking and fulfilled clocks.
- Pinning any Oracle verdict, Augury reading, Tavern rumour, Threat state, or Cabinet find drops a dated note into the Almanac.
- Archive entries that mention a faction by `[[wikilink]]` show as backlinks on the faction's card, mirroring the existing NPC pattern.
- Universal search opens specific records via per-module transient navigation keys, so a hit in the Cabinet group does not just take you to the Cabinet but to the exact item, scrolled into view and briefly glowing.

## Browser Support

Tested in current Chrome, Firefox, and Safari. Uses Web Audio for the Hearth, SVG for the Threats clocks and Scriptorium handouts, the `window.storage` API when available (or `localStorage` as fallback), and standard ES2020 features. No transpilation, no polyfills, no external dependencies.

## Development

The Keep is one HTML file with embedded CSS and JavaScript, written in vanilla ES2020. About seven thousand lines at this writing. Modular structure: each room is a self-contained object registered via `Keep.register({...})` with `mount(body, actions)` and optional `unmount()`.

Persistence is abstracted through a `Vault` helper with three surfaces:

- `Vault.get`, `Vault.set`, `Vault.list`, `Vault.remove`: per-chronicle, auto-prefixed by the active chronicle's id
- `Vault.global.*`: cross-chronicle data (theme, chronicles list, active chronicle id)
- `Vault.raw.*`: unprefixed access used for migration and management

Cross-module operations go through a `Refs` helper to keep modules from depending on each other directly. See `Refs.pinToToday`, `Refs.openArchiveEntry`, `Refs.openAlmanacAt`, `Refs.backlinks`, `Refs.formatDate`, `Refs.npcRoster`, and others.

To extend the Keep with a new room, register a module:

```js
Keep.register({
  id: 'my-room',
  name: 'My Room',
  category: 'workshop',
  glyph: 'g-quill',
  tagline: 'A short subtitle for the nav.',
  sub: 'Longer description for the room\u2019s header.',
  async mount(body, actions) {
    // body: the main DOM container for this room
    // actions: the right-aligned actions row in the folio head
    body.append(/* your content */);
    actions.append(/* primary actions */);
  },
  unmount() {
    // optional cleanup (close audio contexts, remove global listeners, etc)
  }
});
```

The `category` value places the room in the navigation: `workshop`, `mysteries`, `table`, or null for top-level. `glyph` references an SVG `<symbol id="g-*">` defined at the top of the file.

For cross-module navigation, set a transient Vault key before mounting the target module; the target reads and consumes the key on its next mount. Existing keys: `archive-current`, `almanac-selected`, `faces-show`, `factions-expand`, `cabinet-highlight`, `threats-highlight`.

## Status

In active use and active development. The schema is stable but the seed data and module roster may grow. Backwards-compatible migrations happen automatically on chronicle load.

## License

GPL-3.0
