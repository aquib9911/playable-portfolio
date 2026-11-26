# Playable Portfolio

### 🎮 Live at: **[aquib9911.github.io/playable-portfolio](https://aquib9911.github.io/playable-portfolio/)**

---

## Introduction

Most portfolios are a page you scroll. This one is a **game you play**.

Playable Portfolio is a retro side-scrolling platformer built for the web. Visitors control a small pixel-art character and run through a level that *is* the portfolio: jumping into blocks reveals skills, opening treasure chests shows projects, climbing steps raises flags for each job, and hopping into a rocket at the end opens the contact card.

It's made to be memorable for recruiters and clients while staying practical:

- **Works everywhere:** keyboard on desktop, on-screen buttons on phones and tablets.
- **Classic view included:** one click turns the game into a normal, readable page (also great for screen readers).
- **Easy to edit:** all your details live in one block of text at the top of the code, and the level builds itself from it.
- **Zero setup:** a single HTML file, with no build step, framework or install.

---

## Files in this repository

| File | What it is |
| --- | --- |
| [`index.html`](index.html) | The whole website and game: the HTML, the styles, the game code and your portfolio details (the `PORTFOLIO` block near the top of the `<script>`). This is the only file you need to edit. |
| [`README.md`](README.md) | This guide: the live link, an introduction, controls, and instructions for editing and hosting. |

---

## What's in the level

| Zone | What happens |
| --- | --- |
| **Start** | Your name is written in the sky. Hit the **i** block to open your *About* card. |
| **Skills** | Each **!** block unlocks one skill and shows its level as 1–5 stars. Unlocking all of them earns a bonus. |
| **Projects** | Walk up to a treasure chest and press **↓** to open a project card with tech tags and live/source links. |
| **Journey** | Climb the steps. Each flag raises and shows one job or milestone. |
| **Contact** | Jump into the rocket. It launches and opens your contact card with email, links and the final score. |

There are also walking **bugs** you can stomp ("BUG FIXED!"), coins, a score bar, a progress map and sound effects. Falling into a gap just puts you back on solid ground, so nobody gets stuck.

### Controls

| Action | Keyboard | Phone / tablet |
| --- | --- | --- |
| Move | ← → or A / D | ◀ ▶ buttons |
| Jump | Space, ↑, W or Z (hold to jump higher) | **JUMP** button |
| Open chest | ↓, S or E | **OPEN** button |
| Run | Shift | — |
| Mute | M | **SOUND** button |
| Pause | P or Esc | — |

### Classic view

Not everyone wants to play a game. The **CLASSIC VIEW** button (also on the title screen) shows all the same content as a normal scrolling page. That's handy for recruiters in a hurry, and it works with screen readers.

---

## How to make it yours

1. Open `index.html` in any text editor (VS Code, Notepad, TextEdit in plain-text mode, etc.).
2. Near the top of the `<script>` section, find the block that starts with:

   ```js
   const PORTFOLIO = {
   ```

3. Replace the placeholder details with your own:

   ```js
   const PORTFOLIO = {
     name: "Your Name",
     role: "What you do",
     tagline: "One short line about you.",
     location: "Your city",
     bio: "A few sentences about yourself.",
     skills: [
       { name: "JavaScript", level: 5 },   // level is 1-5 stars
       { name: "Figma", level: 4 }
     ],
     projects: [
       {
         title: "Project name",
         year: "2026",
         description: "What it is and why it matters.",
         tech: ["React", "Node.js"],
         links: { live: "https://...", code: "https://github.com/..." }  // either link is optional
       }
     ],
     experience: [
       // oldest first: the level climbs from your first step to now
       { role: "Job title", company: "Company", period: "2022 - Now", summary: "One line about it." }
     ],
     contact: {
       email: "you@example.com",
       links: [
         { label: "GitHub", url: "https://github.com/your-username" },
         { label: "LinkedIn", url: "https://www.linkedin.com/in/your-profile" }
       ]
     }
   };
   ```

4. Save the file and open it in your browser to check it.

**The level builds itself from this data.** If you add or remove skills, projects or jobs, the level grows or shrinks to fit. You don't need to touch anything else.

> Tip: keep skill names short (under ~14 characters). They're shown in big pixel letters when a block is hit.

---

## Run it on your computer

Double-click `index.html` and it opens in your browser. That's it.

If you'd rather use a local server (some browsers are stricter with local files):

```bash
python3 -m http.server 8000
```

Then visit <http://localhost:8000>.

---

## Put it online for free with GitHub Pages

> This repository is already published at **https://aquib9911.github.io/playable-portfolio/**. The steps below are for setting it up again or in a copy of this repository.

1. Open this repository on GitHub.
2. Go to **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to **Deploy from a branch**.
4. Choose the **main** branch and the **/ (root)** folder, then click **Save**.
5. Wait a minute or two, then refresh the page. GitHub shows your live link, which looks like:

   ```
   https://<your-username>.github.io/<repository-name>/
   ```

Every time you change `index.html` and push (or edit it on GitHub), the live site updates within a minute or two.

### Editing directly on GitHub (no tools needed)

1. Click `index.html` in the repository.
2. Click the ✏️ pencil icon (**Edit this file**).
3. Change the `PORTFOLIO` details.
4. Click **Commit changes**. Your live site updates shortly after.

---

## Other places you can host it

Because it's a single static file, it works anywhere:

- **Netlify:** drag the folder onto <https://app.netlify.com/drop>
- **Vercel:** import the repository, with no settings needed
- **Any web host:** upload `index.html` to your public folder

---

## Customising further (optional)

| Want to change… | Where to look in `index.html` |
| --- | --- |
| Colours of the pop-ups and buttons | The `:root { ... }` CSS variables at the top of `<style>` |
| The character's look | The `PAL` colours and the `HEAD` / `BODY` / `FRAMES` pixel rows |
| Jump height or speed | The `update()` function (`maxS`, and the `p.vy = -(13.8 ...)` jump line) |
| Level layout | The `buildLevel()` function |
| Sound effects | The `sfx` object |

---

## Credits

- Fonts: [Press Start 2P](https://fonts.google.com/specimen/Press+Start+2P) and [VT323](https://fonts.google.com/specimen/VT323) from Google Fonts
- All character art, tiles and sounds are original and drawn or generated in code
