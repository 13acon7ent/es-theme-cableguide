# es-theme-cableguide

Retro TV Guide – Classic 2000s Cable Menu Theme for Batocera

A 2010-era cable TV listings look for Batocera (built for v44, 1920×1080 / 16:9).

- **System view:** systems are listed as "channels" (system code | full name | manufacturer). The top-left panel shows system info and the right panel shows a photo of the system (or a generated channel card if there's no photo).
- **Favorites:** a lock badge appears next to the system code in the info panel.
- **Gamelist view (detailed):** the header shows the system's logo (or its name if there's no logo), and games are listed as "channels" (release year / system code | title | genre). The top-left panel shows the selected game's details and the right panel shows its screenshot (configurable, see Preview style).
- **Genre colors:** a game's cells turn green when its genre contains "sports", "fishing" or "hunting" anywhere (any case, e.g. `Sports`, `Fishing`, `Sports / Hunting`) purple when it's exactly `Platform`, and light blue when it contains "adventure". If a genre matches more than one, green or purple wins over light blue. Everything else is navy.
- **Menus:** restyled to match the guide (blue window, pale-yellow selection).

## Screenshots

| System view | Game list |
|---|---|
| ![System view](screenshots/system.png) | ![Game list](screenshots/gamelist.png) |

![Menu](screenshots/menu.png)

## Install

1. Copy the `es-theme-cableguide` folder to `/userdata/themes/` (over the network share it's `\\BATOCERA\share\themes\`).
2. Main Menu → User Interface Settings → Theme Set → **es-theme-cableguide**.
3. For the header clock: User Interface Settings → **Show clock** → on.
4. Leave Gamelist View Style (under Theme Configuration) on **automatic** or **detailed**.

## Transitions

The button legend, clock and controller icons are drawn by Batocera on a fixed layer above the theme, so they don't move with the screen during transitions. To keep things clean:

- **Switching between systems and game lists:** the theme defaults to **instant** (used when User Interface Settings → **List Transition** is on *auto*).
- **Launching a game:** themes can't set this one. For the cleanest look, set User Interface Settings → **Game Launch Transition** to **instant**.

## Preview style

Choose what the preview window shows:

- **For every system:** User Interface Settings → Theme Configuration → **Preview style**
- **For one system:** in that system's game list, open View Options → **View Customization** → **Preview style** (overrides the global choice)

| Option | Shows | Falls back to |
|---|---|---|
| Screenshot (default) | Screenshot (`image`) | Box art, then NO SIGNAL |
| Box art | Box (`thumbnail`) | Screenshot, then NO SIGNAL |
| Video | Video (`video`) | Box art, then NO SIGNAL |
| Mix image | Mix (`mix`) | Screenshot, then NO SIGNAL |
| Title screen | Title screen (`titleshot`) | Screenshot, then NO SIGNAL |
| Fan art | Fan art (`fanart`) | Screenshot, then NO SIGNAL |
| Logo | Logo (`marquee`) | Box art, then NO SIGNAL |
| Box back | Box back (`boxback`) | Box art, then NO SIGNAL |

Each option only shows media your scraper downloaded or that you set yourself (Edit game → Image, Box, and so on). Media is scaled to fill as much of the window as possible without cropping.

## Custom system images (optional)

Put a JPG named after the system's folder in `art/systems/` (for example `snes.jpg` or `megadrive.jpg`; about 960×540 works best). It replaces the built-in photo or channel card for that system.

## Customize

Colors and the two genre names are variables at the top of `theme.xml` (`cgHighlight`, `cgSports`, `cgSportsGenre`, and so on).

## License

CC BY-NC-SA 4.0: free to use, share and modify, with credit, not for commercial use, and modified versions must use the same license. See `LICENSE`.

## Credits

- Controller icons in `art/controllers/`, system logos in `art/logos/` (white versions where available; large SVGs converted to PNG) and system photos in `art/background/` come from [es-theme-carbon](https://github.com/fabricecaruso/es-theme-carbon) by Fabrice Caruso (based on "Carbon" by Eric Hettervik and "simple" by Nils Bonenberger), licensed CC-BY-NC-SA. Resized for this theme. System logos are trademarks of their respective owners.
- Batocera logo (`art/batocera_logo.svg`): from [batocera-emulationstation](https://github.com/batocera-linux/batocera-emulationstation) (MIT license), recolored. The Batocera name and logo belong to the Batocera project.
- Font: Roboto Condensed, SIL Open Font License 1.1 (`fonts/OFL.txt`).
