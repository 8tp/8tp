<p align="center">
  <img src="./assets/banner.webp" alt="8tp.dev - games, self-hosted tools, and native apps" width="100%" />
</p>

<p align="center">
  <a href="https://github.com/8tp">
    <img src="https://img.shields.io/badge/GitHub-8tp-090909?style=for-the-badge&logo=github&logoColor=090909&labelColor=fffdf7" alt="GitHub 8tp" />
  </a>
  <a href="https://8tp.dev">
    <img src="https://img.shields.io/website?down_message=offline&label=8tp.dev&style=for-the-badge&up_message=online&url=https%3A%2F%2F8tp.dev&color=090909&labelColor=fffdf7" alt="8tp.dev status" />
  </a>
  <img src="https://komarev.com/ghpvc/?username=8tp&style=for-the-badge&color=090909&label=views&labelColor=fffdf7" alt="Profile views" />
</p>

<table>
<tr>
<td width="178" align="center" valign="top">
  <img src="https://github.com/8tp.png" width="154" alt="Hunter / 8tp avatar" />
  <br>
  <sub><samp>@8tp</samp></sub>
</td>
<td valign="top">
  <h1>Hunter / 8tp</h1>
  <p><samp><strong>games, self-hosted tools, and native apps</strong></samp></p>
  <p>
    I build small, fast software solo: real-time multiplayer browser games,
    self-hosted server tools, terminal apps, and native macOS utilities. Most
    of it started as something I wanted to exist, then shipped once it earned it.
  </p>
  <p>
    <samp>
      TypeScript / React / Next.js / Three.js / Node / WebSocket /
      Go / Rust / Ratatui / Swift / SwiftUI / AppKit / Docker
    </samp>
  </p>
</td>
</tr>
</table>

<p align="center">
  <samp>
    <a href="#featured">featured</a>
    /
    <a href="#browser-games">browser games</a>
    /
    <a href="#terminal-apps">terminal apps</a>
    /
    <a href="#macos-apps">macOS apps</a>
  </samp>
</p>

---

<a id="featured"></a>

## <samp>Featured</samp>

<table>
<tr>
<td width="290" align="center" valign="top">
  <a href="https://palhelm.com"><img src="./assets/projects/palhelm.webp" width="268" alt="Palhelm thumbnail" /></a>
</td>
<td valign="top">
  <h3><a href="https://github.com/8tp/palhelm">Palhelm</a> / <a href="https://palhelm.com">palhelm.com</a></h3>
  <p>
    Self-hosted web admin panel for Palworld dedicated servers. One Docker
    image with no external database. It talks to the server three ways: the
    official REST API, RCON, and the world save file, which it parses directly
    in pure Go. You get a live dashboard, player and Pal data, a world map, an
    RCON console, and scheduled backups with dry-run restores.
  </p>
  <p><samp>[Go] [Svelte] [Docker] [RCON]</samp></p>
</td>
</tr>
<tr>
<td width="290" align="center" valign="top">
  <a href="https://github.com/8tp/palhelm-bot"><img src="./assets/projects/palhelm-bot.webp" width="268" alt="Palhelm Bot thumbnail" /></a>
</td>
<td valign="top">
  <h3><a href="https://github.com/8tp/palhelm-bot">Palhelm Bot</a> / <a href="https://docs.palhelm.com">docs.palhelm.com</a></h3>
  <p>
    Discord companion for Palhelm. It posts live server events into a channel
    and answers more than 30 slash commands for players, guilds, Pal ownership,
    breeding, and records, with rendered world-map and Pal images. Reads run
    through the panel's read-only integration API, which redacts platform IDs,
    live positions, and ban state so replies are safe in a public channel.
  </p>
  <p><samp>[TypeScript] [discord.js] [Node.js]</samp></p>
</td>
</tr>
<tr>
<td width="290" align="center" valign="top">
  <a href="https://instagib.win"><img src="./assets/projects/instagib-arena.webp" width="268" alt="Instagib Arena thumbnail" /></a>
</td>
<td valign="top">
  <h3><a href="https://github.com/8tp/instagib-arena">Instagib Arena</a> / <a href="https://instagib.win">instagib.win</a></h3>
  <p>
    Quake-style instagib FPS in the browser. One-shot railgun, strafe-jump
    movement, and server-authoritative 64 Hz binary netcode with lag
    compensation. Ranked duels, weekly replay challenges, and offline bots.
    Free, no download.
  </p>
  <p><samp>[Three.js] [React 19] [Node/ws] [SQLite]</samp></p>
</td>
</tr>
</table>

---

<a id="browser-games"></a>

## <samp>Browser games</samp>

<table>
<tr>
<td width="290" align="center" valign="top">
  <a href="https://coup.8tp.dev"><img src="./assets/projects/coup.webp" width="268" alt="Coup thumbnail" /></a>
</td>
<td valign="top">
  <h3><a href="https://github.com/8tp/Coup">Coup</a> / <a href="https://coup.8tp.dev">coup.8tp.dev</a></h3>
  <p>
    Real-time multiplayer bluffing card game with bots, room codes, and
    mobile-friendly play. No install, no accounts.
  </p>
  <p><samp>[Next.js] [TypeScript] [Socket.io] [Zustand]</samp></p>
</td>
</tr>
<tr>
<td width="290" align="center" valign="top">
  <a href="https://aim.8tp.dev"><img src="./assets/projects/hudaim.webp" width="268" alt="HudAim thumbnail" /></a>
</td>
<td valign="top">
  <h3><a href="https://github.com/8tp/hudaim">HudAim</a> / <a href="https://aim.8tp.dev">aim.8tp.dev</a></h3>
  <p>
    Browser aim trainer with six game modes, 60 FPS replay capture, LAN
    leaderboards, and HMAC-SHA256 anti-cheat.
  </p>
  <p><samp>[React 19] [Tailwind] [Node/Express] [IndexedDB]</samp></p>
</td>
</tr>
<tr>
<td width="290" align="center" valign="top">
  <a href="https://ant.8tp.dev"><img src="./assets/projects/antmaze.webp" width="268" alt="AntMaze thumbnail" /></a>
</td>
<td valign="top">
  <h3><a href="https://github.com/8tp/AntMaze">AntMaze</a> / <a href="https://ant.8tp.dev">ant.8tp.dev</a></h3>
  <p>
    Perpetual-motion maze game where the ant never stops moving. Procedural
    7x7 to 21x21 mazes, an LBP-inspired Web Audio soundtrack, and a 10 KB
    gzipped payload.
  </p>
  <p><samp>[TypeScript] [Vite] [Canvas 2D] [Web Audio]</samp></p>
</td>
</tr>
<tr>
<td width="290" align="center" valign="top">
  <a href="https://duel.8tp.dev"><img src="./assets/projects/typeduel.webp" width="268" alt="TypeDuel thumbnail" /></a>
</td>
<td valign="top">
  <h3><a href="https://github.com/8tp/typeduel">TypeDuel</a> / <a href="https://duel.8tp.dev">duel.8tp.dev</a></h3>
  <p>
    Real-time multiplayer typing combat. Type fast, deal damage, trigger
    abilities, and win the duel in the browser.
  </p>
  <p><samp>[TypeScript] [React] [WebSocket] [Zustand]</samp></p>
</td>
</tr>
</table>

<sub><samp>Also: <a href="https://8tp.github.io/iq-test/">iq-test</a>, an open-source 35-question cognitive assessment. [HTML] [CSS] [JS]</samp></sub>

---

<a id="terminal-apps"></a>

## <samp>Terminal apps</samp>

<table>
<tr>
<td width="290" align="center" valign="top">
  <a href="https://github.com/8tp/ghgarden"><img src="./assets/projects/ghgarden.webp" width="268" alt="ghgarden thumbnail" /></a>
</td>
<td valign="top">
  <h3><a href="https://github.com/8tp/ghgarden">ghgarden</a></h3>
  <p>
    GitHub contribution visualizer for the terminal, with heatmaps, streak
    stats, language breakdowns, and six themes.
  </p>
  <p><samp>[Rust] [Ratatui]</samp></p>
</td>
</tr>
<tr>
<td width="290" align="center" valign="top">
  <a href="https://github.com/8tp/netmap"><img src="./assets/projects/netmap.webp" width="268" alt="netmap thumbnail" /></a>
</td>
<td valign="top">
  <h3><a href="https://github.com/8tp/netmap">netmap</a></h3>
  <p>
    Visual network topology mapper and scanner. Discover devices, scan ports,
    and measure latency from a terminal UI.
  </p>
  <p><samp>[Go] [Bubble Tea]</samp></p>
</td>
</tr>
<tr>
<td width="290" align="center" valign="top">
  <a href="https://github.com/8tp/tidewatcher"><img src="./assets/projects/tidewatcher.webp" width="268" alt="TideWatcher thumbnail" /></a>
</td>
<td valign="top">
  <h3><a href="https://github.com/8tp/tidewatcher">TideWatcher</a></h3>
  <p>
    System monitor TUI with tide-inspired live charts, process views, and
    theme-aware ASCII scenes.
  </p>
  <p><samp>[Rust] [Ratatui]</samp></p>
</td>
</tr>
</table>

---

<a id="macos-apps"></a>

## <samp>macOS apps</samp>

<table>
<tr>
<td width="290" align="center" valign="top">
  <a href="https://github.com/8tp/ScreenCap"><img src="./assets/projects/screencap.webp" width="268" alt="ScreenCap thumbnail" /></a>
</td>
<td valign="top">
  <h3><a href="https://github.com/8tp/ScreenCap">ScreenCap</a></h3>
  <p>
    Native screenshot and annotation app for macOS. Area, window, and scrolling
    capture, screen recording, OCR, color picker, and GIF export.
  </p>
  <p><samp>[Swift] [SwiftUI] [AppKit] [ScreenCaptureKit]</samp></p>
</td>
</tr>
<tr>
<td width="290" align="center" valign="top">
  <a href="https://github.com/8tp/Recopy"><img src="./assets/projects/recopy.webp" width="268" alt="Recopy thumbnail" /></a>
</td>
<td valign="top">
  <h3><a href="https://github.com/8tp/Recopy">Recopy</a></h3>
  <p>
    Native menu bar clipboard manager. Zero dependencies, fully offline, built
    with SwiftData.
  </p>
  <p><samp>[Swift] [SwiftUI] [SwiftData]</samp></p>
</td>
</tr>
<tr>
<td width="290" align="center" valign="top">
  <a href="https://github.com/8tp/LiteStats"><img src="./assets/projects/litestats.webp" width="268" alt="LiteStats thumbnail" /></a>
</td>
<td valign="top">
  <h3><a href="https://github.com/8tp/LiteStats">LiteStats</a></h3>
  <p>
    Lightweight menu bar system monitor for CPU, RAM, storage, battery, and
    thermals.
  </p>
  <p><samp>[Swift] [SwiftUI] [IOKit]</samp></p>
</td>
</tr>
</table>

<sub><samp>Also: <a href="https://github.com/8tp/AppMixer">AppMixer</a>, per-app volume from the menu bar via a HAL virtual audio driver. [Swift] [AppKit] [CoreAudio]</samp></sub>

---

<table>
<tr>
<td valign="top" width="50%">
  <h3>8tp.dev</h3>
  <p>
    Portfolio site for the projects above. It collects the playable apps, repo
    links, thumbnails, and build notes in one place.
  </p>
  <p>
    <a href="https://8tp.dev">8tp.dev</a>
    /
    <a href="https://github.com/8tp/8tp.dev">source</a>
  </p>
  <p><samp>[Astro] [Svelte] [Tailwind]</samp></p>
</td>
<td valign="top" width="50%">
  <h3>Current focus</h3>
  <p>
    Browser games with server-authoritative netcode, self-hosted server tools,
    and native macOS and terminal utilities. Each project page says what
    shipped, how it works, and where to try it.
  </p>
</td>
</tr>
</table>

<p align="center">
  <img width="49%" src="https://github-profile-summary-cards.vercel.app/api/cards/stats?username=8tp&theme=github" alt="GitHub stats" />
  <img width="49%" src="https://github-profile-summary-cards.vercel.app/api/cards/repos-per-language?username=8tp&theme=github" alt="Top languages by repo" />
</p>

<p align="center">
  <samp>github.com/8tp</samp>
</p>
