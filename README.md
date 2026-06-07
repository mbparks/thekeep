# The Keep

A single-file, browser-based companion for medieval-fantasy tabletop campaigns.

The Keep is a chronicler's tool, not a rules engine. It holds the soft, narrative substance of a long campaign: who your party has met, what they have found, where they have been, what factions favour or hate them today, what dooms are ticking. Built to feel like a hand-bound book opened on a candlelit table rather than a software dashboard.

It works for a group GM and for a solo player. The same rooms that help a Game Master prepare for a session help a solo journaler talk to fate, listen to companions, walk a small adventure, and remember what happened last week.

## At a Glance

- One self-contained HTML file. Open in any modern browser. No install, no build step, no server. The only outside calls are optional YouTube ambience streams in The Hearth.
- Per-chronicle persistence. Run as many campaigns as you want, each kept separate.
- Light and dark themes. Parchment-and-ink for noble adventures, Cult of Shadow for those who play the villains.
- Twenty-three interconnected modules, each a "room" in the keep.
- A session-prep landing page (The Watch) that aggregates current state across rooms.
- Universal search across everything (press `/`).
- Full chronicle backup and restore (JSON).
- Print stylesheet for paper-table use: any room can print, tuned for letter paper.
- GPL-3.0. No telemetry, no accounts.

## Philosophy

Three principles shape every part of the project.

**Documents are objects.** Each room is meant to feel like a thing you hold, not a screen you scroll. Cards have corner brackets and parchment shadows. The Tavern is a posting board. The Augury draws cards by candlelight. Skirmish cards look like an initiative slate, Quest beats like an illuminated manuscript.

**The work weaves itself.** Each module knows about the others. Pin a tavern rumour and it lands in the Almanac. Recruit a patron and they enter the roster. Tag an Archive entry as a Person and it groups in the sidebar. Loot generates items that one-click into the Cabinet and coins that one-click into the Coffer. Quest hands off to Skirmish, Loot, or the Cabinet at its climax. Skirmish writes Fellowship statuses back when allies fall. Universal search jumps you to the exact record, not just the room.

**Words matter more than features.** The room names, the button labels, the placeholder text are all written in the chronicler's voice. The Roll. The Augury. The Cabinet. The Hearth. The Spark. The Skirmish. The Quest. The vocabulary itself is part of the playing surface.

## Solo Play

The Keep was built for chroniclers running games for others, then grew to serve solo players too. Several rooms target the solo experience directly:

- **The Wayfarer** is a character sheet for your own PC (or for multiple PCs in a party game). Lineage, calling, oath, bonds, what you carry, current status from Hale through Fallen.
- **The Fellowship** holds NPC companions who travel with you. Each has an archetype (Stoic, Sage, Scout, Healer, Bard, Scoundrel, Devoted, Reluctant) and a Speak button that gives them a voice line drawn from a pool of seeded utterances. Their bond gauge shifts as you play.
- **The Spark** is a narrative prompt generator. Eight pools of phrases for moments, plus a ninth Thread pool that composes plot hooks from three sub-pools (person, need, complication) for 15,625 possible combinations.
- **Quest** is the solo-play centerpiece. Pick a setting, pick your companions, walk a short atmospheric adventure beat by beat, land on a climax that hands off to Skirmish, Loot, or the Cabinet. The chronicle records what happened.
- **The Skirmish** runs combat without a GM. Generate the foes, roll initiative, track HP and conditions, log the round, pin the outcome.

The pre-existing rooms also serve solo play: the Oracle answers yes-or-no questions when there is no GM to ask, the Augury speaks in cards and runes, the Tavern is a fully populated stop ready to roll, the Almanac becomes a journal of days.

## The Rooms

### Top Level

**The Watch.** The session-prep page. Aggregates the current state of the chronicle: today's Almanac note and weather, the last several days of notes, threats over halfway full, recently-touched NPCs, recent Cabinet finds, companions in trouble, the Wayfarers and their statuses, factions in play, recent Oracle and Augury castings, recent Sparks, recently-edited Archive entries, and a digest of everything pinned this week. The default landing page for new chronicles.

**The Gate.** The original welcome landing, a tile grid of every room in the keep grouped by category. Reachable from The Watch via "Browse Rooms".

**The Roll.** The campaign manager. Found a new chronicle, retire an old one, switch between them, export a single chronicle, or back up the entire Keep. Restore supports both merge (add to existing) and replace (full wipe with a typed confirm).

### Workshop

Where the chronicler builds the world.

**The Scriptorium.** Forge handouts on aged parchment. Five styles: Parchment Letter, Wanted Poster, Journal Page, Ledger Sheet, Royal Edict. Procedural SVG aging seeded for repeatable results. Export as PNG or SVG.

**The Archive.** A markdown wiki for lore. Wikilinks in `[[brackets]]` auto-create entries, and NPC names from the roster turn forest-green when linked. Sidebar search with hit highlighting and body excerpts. Hover any wikilink for a small parchment preview. Entries carry optional type tags (Person, Place, Thing, Event, Faction, Lore) with coloured stripes in the sidebar and grouping headers when more than one type is present.

**The Wayfarer.** Player-character sheets. Name, lineage, calling, description, oath (rendered in accent colour as italic rubric), bonds, carried, notes. Five statuses (Hale, Weary, Wounded, Grievous, Fallen) and eight accent colours. Supports multiple PCs for a party game. Archive backlinks show wikilinks that mention each PC.

**Hall of Faces.** NPC conjurer. Rolls a name, culture, role, voice, want, mannerism, appearance, and secret. Three cultures: Northron, Rivenmark, Southern. Persists a roster of inducted NPCs, with backlinks showing the Archive entries that mention them and the Cabinet items they carry.

**The Fellowship.** Companion NPCs who travel with the party (or with a solo Wayfarer). Eight archetypes, each with a seeded pool of about twenty-five voice lines that the Speak button draws from, avoiding recent repeats. Bond gauge from minus five to plus ten with eight standing labels. Five statuses. Custom voice lines can be added per companion. Any spoken line can be pinned to the Almanac. Comes seeded with two companions (Mira Greycloak, Scout; Brother Halric, Healer) which you can rename, retire, or replace.

**Loot.** A tiered treasure generator. Pick a tier (Paltry, Modest, Rich, Royal) and roll a haul. Coins come by per-tier dice formulas across four denominations (copper, silver, gold, platinum). Oddments come from a thirty-entry mundane-finds table (a worn dagger, a half-melted candle, a child's drawing weighted with a stone). A Wonder occasionally rolls (5% Paltry, 65% Royal), drawn from thirty named magical items with brief flavor properties: The Whispering Mirror, Ironwood Ring of Vance, The Salt-Eaten Compass. Each item has a "+ Cabinet" button; coins have a "+ Coffer" button; the whole haul pins to the Almanac.

**The Cabinet.** A catalogue of relics, letters, weapons, and curiosities the party has touched. Each find has a kind (eight glyph categories from Relic to Curiosity), description, current holder, location and date of finding, worth, and status (Held, Lost, Hidden, Given, Destroyed) with colour-coded borders.

**The Coffer.** Party wealth tracker. Current balance in four denominations rendered as tiles (dim when zero) with a worth-in-gold conversion below. Deposit and withdraw form with a free-text note. A split-among-shares utility divides current wealth by an arbitrary party size. Transaction ledger persists the last two hundred entries, displays the latest twenty-five. Pin current balance to the Almanac, or empty the purse entirely with a confirm.

**The Tavern.** Roll a tavern. Name, proprietor, atmosphere, menu, three patrons, three rumours with truth tags. Reveal rumours one at a time or all at once. Pin individual rumours to the Almanac. Recruit any patron into the Hall roster with one click.

**Faction Ledger.** Track the powers your party crosses. Sigil, motto, goal, notes, and a party-standing gauge from minus ten to plus ten across seven labels (Blood Enemy through Sworn). Inter-faction relations are directional: House Ashlow can scorn the Greyfern Order while the Order pities them. Cards view for detail, Matrix view for the whole web at once. Shows mentioned-in backlinks from the Archive, plus a count badge when any Threats are linked to the faction.

### Mysteries

Where the unknown is asked of.

**The Oracle.** Yes-or-no consultation in the style of Mythic GME. Likelihood from "almost certainly not" through "almost certainly," modulated by qualifier, with roughly one in three results carrying a complication. History of the last fifty castings. Pin any verdict to the day's note.

**The Augury.** Drawn answers. Three methods: tarot (three of the old arcana, in "What Was / What Is / What Shall Come"), runes (three from a small futhark cast in sequence), and scrying (an evocative four-line vision from the water). Each casting persists to history for review in The Watch. Pin any reading to the Almanac.

**The Spark.** A narrative prompt generator. Eight pools of twenty-five phrases each (image, complication, mood, presence, omen, overheard fragment, token, scene turn) plus a ninth Thread category that composes plot hooks. Thread draws one entry from each of three sub-pools (twenty-five persons, twenty-five needs, twenty-five complications) and stitches them into a single sentence: *"An aging knight seeks word of a missing sister, but her father's killer wears your face."* That's 15,625 unique compositions, on top of the 200 single-phrase sparks. Strike to draw. Pin any spark to the day.

**The Almanac.** An editable in-world calendar. Twelve months of thirty days, seven daynames, year 712 of the Long Comet by default, with moon phases. Click a day to write a note, set weather, or advance the campaign-today marker. The Almanac is the spine of the chronicle: every pin from every other room lands here.

**Threats.** Forged in the Dark style countdown clocks. Each clock has 4, 6, 8, or 12 segments. Tick by clicking segments directly, or with plus and minus buttons. Auto-pins to the Almanac on fulfillment. Optionally linked to a faction, in which case the linked faction card shows a count badge of active and fulfilled clocks.

### Table

Where the chronicler plays.

**Quest.** A short procedural exploration adventure. Choose a setting (dungeon, castle, abandoned farmhouse, haunted graveyard, shipwreck, enemy hideout), the companions from your Fellowship who go with you, a beat count (3 quick, 5 standard, 7 extended), and a climax type (Skirmish, Loot, Find, Coda, or Surprise Me). Each regular beat is procedurally composed from setting-specific pools (twelve features, twelve details, twelve hooks, yielding 1,728 unique combinations per setting). Roughly half of beats feature one of your companions with a voice line drawn from a shared twenty-five-line pool. The final beat is the climax, hand-written for the chosen setting and climax type, and offers a handoff: Launch Skirmish (prefills allies from your chosen Fellowship and foes from setting-mapped archetypes), Roll Loot (opens with the setting's preset tier), Add to Cabinet (writes a thematic named find with description and date), or Walk Away. The Almanac records the day either way.

**The Skirmish.** A combat dashboard, not a combat simulator. Pulls allies from the Fellowship (hale by default, optionally include wounded) and the Hall of Faces. Generates foes as Quick Foes (one of eight anonymous archetypes across four tiers, with counts) or Epic Foes (thirty named bosses with kind, HP, init modifier, and flavor lines like "Carrack the Black-Tongued, a bandit lord with three scars he refuses to explain"), or accepts custom combatants. Roll initiative, begin the encounter, and the active turn highlights with a chevron and gold border. HP bars (forest for allies, wine for foes, dim grey when down), quick-adjust buttons (-5, -1, +1, +5) plus a custom-amount input with separate damage and heal buttons. Thirteen toggleable conditions with colour-coded badges (poisoned, stunned, prone, bleeding, frightened, charmed, restrained, blinded, burning, silenced, inspired, blessed, hidden). Per-combatant d20+mod quick roll with crit/fumble highlighting. An auto-action log records every HP change, condition toggle, KO, and round transition in reverse chronological order. An inline stripped-down Bones widget allows ad-hoc dice in the middle of the fight. End Encounter prompts for a summary line, writes Fellowship statuses for any allies who went down (wounded by default, override to lost or fallen), pins to the Almanac, clears state.

**The Lists.** A lightweight initiative tracker for non-combat scenes (debates, races, ritual sequences) and quick combats that do not warrant the full Skirmish dashboard. HP bars, conditions (eight types: Prone, Bleed, Stun, Hex, Burn, Mark, Shield, Hidden), critical-HP highlighting, drag-to-reorder via a grip handle, and a From Roster pulldown to pull NPCs from the Hall. Big Mode strips down to large readable text for projecting at the table. Keyboard `n` and right-arrow advance turns.

**The Bones.** A dice roller. Tap d4, d6, d8, d10, d12, d20, or d100 to add to a pool. Tap pool chips to remove. Adjust modifier with plus and minus controls. Cast the Bones rolls everything; each die animates in with a tumble. Maximum rolls (a 6 on a d6, a 20 on a d20) get gold "boon" highlighting; natural 1s on d20 and d100 get wine "fumble" highlighting. History persists per chronicle, last twelve casts shown, fifty stored. Pin any cast to the Almanac; the pin format records the full expression, the total, and the individual rolls.

**The Hearth.** A web-audio soundscape mixer. Eleven layers (Rain on Stone, Cold Wind, Hearthfire, Cavern Drone, Distant Bell, Tavern Murmur, Slow Surf, Crow Cry, Wolves at Night, Market Day, Stone Grinding), each with individual gain. Nine presets for common moods (Storm Vigil, The Tavern, Crypt, Cliffside, Hearthside, Lonely Wood, Wolves at Door, Market Square, Forge Depths). Most layers carry occasional ambient events: rain spawns distant thunder, wind spawns far bells, fire spawns log collapses, drone spawns cave drips, waves spawn gulls, tavern spawns laughter and chair scrapes, market spawns vendor calls and hammer strikes. **From Afar** plays external YouTube and audio streams in addition to the synth layers; comes seeded with eight curated atmospheric streams (medieval tavern, market square, crackling fireplace, cave dungeon, heavy thunderstorm, forest at night, coast and sea, castle in snow), and lets you save your own URLs. **Pop Out** opens the Hearth in a separate browser window with an independent AudioContext, so the audio survives any navigation, refresh, or chronicle switch you do in the main window; close the popup to silence everything.

## Getting Started

Download `the-keep.html`. Open it in any modern browser. That is the entire install.

On first open, the Keep seeds a chronicle called "First Chronicle" with example data in several rooms (NPCs, factions, a tavern, threats, cabinet finds, Archive entries, two Fellowship companions) so you can see the shape of things. Edit anything; the seed is not sacred.

To start truly fresh, open The Roll, found a new chronicle, and retire the seeded one. Or just delete or rewrite the seed content as you go.

## Universal Search

Press `/` anywhere outside a text input, or click the magnifying glass in the banner, to open universal search. It queries every persistent surface in the active chronicle:

- Archive entries (title and body)
- NPC roster (all fields including voice, want, secret, mannerism, appearance)
- The Wayfarer (PC sheets)
- The Fellowship (companions, including voice lines and recent speech)
- Faction Ledger (name, motto, goal, notes)
- Cabinet items (name, kind, status, description, holder, place, worth)
- Threats (name, description, fill state)
- Almanac day notes (body and weather)
- Oracle history

Results group by source with sticky section headers. Arrow keys navigate, Enter opens the active result. Clicking a result navigates not just to the room but to the specific record, scrolling it into view and (where applicable) flashing a brief gold glow.

## Storage and Backup

The Keep persists everything to your browser's local storage (or to a sandboxed `window.storage` API when running inside an embedding environment that provides one). Each chronicle's data is stored under a per-chronicle key prefix; switching chronicles swaps the active prefix.

**Important.** Local storage is per-browser, per-device, and per-origin. Clearing your browser data wipes it. Always back up before doing anything risky.

Backups are plain JSON files. From The Roll:

- **Export Chronicle** writes the active chronicle to disk.
- **Backup the Keep** writes every chronicle plus global settings (theme, last-active campaign).
- **Restore (Merge)** imports a backup without erasing existing chronicles. Imported chronicles get unique ids to avoid collisions.
- **Restore (Replace)** wipes everything first, then loads the backup. Requires typing the word `RESTORE` to confirm.

Per-chronicle keys cover both persistent data (factions, NPCs, archive, fellowship, cabinet, coffer, almanac notes) and active session state (lists-state, skirmish-active, quest-active, bones-history, augury-history, oracle-history, spark-history, loot-tier). Active session state is included in chronicle exports, so you can resume an interrupted quest or skirmish on another device.

## Themes

A button in the banner switches between the parchment-and-ink Light theme and the Cult of Shadow Dark theme. Both are full palettes, not inverted colours; the dark theme has its own atmospheric noise, its own Tavern parchment (dark stained vellum rather than cream), and its own decisions for surfaces where light text sits on heraldic backgrounds.

The choice persists across sessions and applies to every chronicle.

## Printing

Every room can be printed for paper-table use. A print stylesheet hides the application chrome (banner, navigation, theme toggle, search, all action buttons, modals, tooltips) and lays the current room out for letter paper.

Each room is tuned for its likely printed artifact:

- **The Scriptorium** prints the current handout as the whole page, with the forge panel hidden and the SVG sized to fill.
- **The Almanac** prints the calendar grid, with the day-note panel stacked below if open.
- **The Watch** prints as a session-briefing sheet.
- **The Cabinet** prints as a two-column inventory the party can pass around.
- **The Faction Ledger** prints with all factions open by default; matrix relations and ribbon colours preserved via `print-color-adjust: exact`.
- **The Lists** prints as a clean initiative slate, no controls.
- **The Tavern** prints the posting parchment as a clean handout.
- **Threats** prints the SVG clock fills so the segments are visible on paper.
- **The Hearth** is the one room with nothing useful to print; only its title shows.

Dark mode is overridden to a light palette in print regardless of theme, so the page does not waste ink.

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
- Threats can be linked to factions. The faction card shows a count of ticking and fulfilled clocks. The Watch's Standing With section flags factions whose clocks are active.
- Pinning any Oracle verdict, Augury reading, Spark phrase, Fellowship voice line, Tavern rumour, Threat state, Cabinet find, Bones cast, Loot haul, Coffer balance, Skirmish summary, or Quest summary drops a dated note into the Almanac.
- Archive entries that mention a faction, NPC, companion, or Wayfarer by `[[wikilink]]` show as backlinks on the respective card.
- Augury castings persist to history, so The Watch can show recent draws alongside Oracle results.
- Universal search opens specific records via per-module transient navigation keys, so a hit in the Cabinet group does not just take you to the Cabinet but to the exact item, scrolled into view and briefly glowing. The Watch uses the same navigation contract.
- **Loot** generates oddments and named wonders that one-click into the Cabinet (with the correct kind, description, holder, and date prefilled) and coins that one-click into the Coffer (with an auto-generated ledger note).
- **The Skirmish** pulls allies from the Fellowship (with default HP and initiative modifier by archetype) and the Hall of Faces, generates foes from archetype pools, and on encounter end writes Fellowship statuses back for any allies who went down (wounded by default; user can override to lost or fallen before confirming).
- **Quest** is the orchestrator. It pulls companions from the Fellowship as your party, runs procedural beats with companion voice moments, and at climax hands off into one of the other rooms: Skirmish (prefills the encounter with both your chosen allies and setting-appropriate foes), Loot (preselects the right tier), or the Cabinet (writes a setting-themed named find with description and date). The Almanac records the day regardless of which path the climax takes.

## Browser Support

Tested in current Chrome, Firefox, and Safari. Uses Web Audio for the Hearth, SVG for the Threats clocks and Scriptorium handouts, the `window.storage` API when available (or `localStorage` as fallback), and standard ES2020 features. No transpilation, no polyfills, no external dependencies. The Hearth's From Afar feature lazy-loads the YouTube IFrame Player API only when a YouTube stream is played; without that feature, the Keep makes zero outside network calls.

## Development

The Keep is one HTML file with embedded CSS and JavaScript, written in vanilla ES2020. About sixteen thousand lines at this writing. Modular structure: each room is a self-contained object registered via `Keep.register({...})` with `mount(body, actions)` and optional `unmount()`.

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

For cross-module navigation, set a transient Vault key before mounting the target module; the target reads and consumes the key on its next mount. Existing keys: `archive-current`, `almanac-selected`, `faces-show`, `factions-expand`, `cabinet-highlight`, `threats-highlight`, `fellowship-highlight`, `wayfarer-highlight`.

For richer cross-module handoffs, write directly to the target module's primary state key before mounting it. Quest does this when handing off to Skirmish: it writes a fully-formed encounter (with allies populated from the chosen Fellowship members and foes generated from setting-mapped archetypes) to `skirmish-active` in building status, then `Keep.mount('skirmish')`. The Skirmish renders the prefilled roster and the user picks up from there.

The Hearth's synthesis engine is built on three primitives: `noiseSource` for continuous looping noise, `noiseOneShot` for finite-duration noise events, and `schedule(minMs, maxMs, fn)` which returns a cancel function for attaching occasional event sounds to active layers. New layer builders should return `{gain, stop()}` where `stop()` calls every relevant cancel function so the layer leaks no resources when silenced. The Hearth's popout mode is opened via `window.open(window.location.pathname + '#hearth-popout', ...)`; the same file detects the hash on init, applies a `popout-mode` body class that hides chrome, and force-mounts the Hearth, running an independent AudioContext.

## Status

In active use and active development. The schema is stable but the seed data and module roster may grow. Backwards-compatible migrations happen automatically on chronicle load.

## License

GPL-3.0
