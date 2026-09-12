# SkillSwap

**Future of Work & Education — trade skills, not tuition fees.**

SkillSwap is a peer-to-peer learning platform where students teach each other instead of paying for lessons: teach what you know, learn what you don't, and let a smart-match score do the introductions. This repo is a single-page, self-contained prototype — no backend, no build step, no dependencies — built to prove out one complete product flow end to end with realistic sample data.

## Run it

Just open `index.html` in a browser. That's it — no `npm install`, no server, no build.

```bash
open index.html        # macOS
start index.html        # Windows
```

Or clone the repo and double-click the file. Everything (markup, styles, app logic, the brand logo) lives in that one file; it works straight from disk over `file://` as well as hosted anywhere static (GitHub Pages, Netlify, S3, …).

## The flow this prototype proves out

Sign up → pick skills to teach/learn → get ranked matches with a smart-match score → view a match's profile → send a swap request → get accepted → schedule a session → join a video call, chat, share notes & resources in the session workspace → mark it complete → rate & badge your partner → see your own progress bars update automatically.

## Feature map

- **Profiles** — teach/learn skill tags, ratings, badges, completed-session count, availability.
- **Matching** — a transparent scoring model (shared availability, mutual skill fit, teaching track record) ranks every other student and explains *why* the top pick was chosen — no black-box "AI," just legible rules.
- **Sessions** — a scheduling modal, then a workspace with live chat, autosaving shared notes, and a resource list.
- **Video calls (demo)** — "Join video call" opens a full-screen call screen with a live timer and mic/camera controls. Your own tile requests real camera/mic access (`getUserMedia`) for a genuine self-preview and degrades gracefully to an avatar if that's denied or unavailable; your partner's tile simulates a "Connecting… → Live" handshake, since there's no real second participant or signaling server behind this — it's a UI demo, not a working call.
- **Progress** — per-skill topic checklists and progress bars, populated automatically as sessions complete.
- **Ratings & badges** — star ratings plus awardable badges ("Python Mentor", "Great Teacher", …) shown on profiles.
- **Community** — a directory of active learners and a popular-skills breakdown for the school network.
- **Account** — sign-up accepts a free-text school/community (no forced default), and a "Log out" action that permanently clears local profile/session data so you can restart the flow.
- **Mobile** — a dedicated sticky top bar and bottom tab bar (not a squeezed-down desktop sidebar) so every section is reachable with a tap, no sideways scrolling.

## Design system

A deliberately monochrome, ink-on-paper look rather than a generic SaaS gradient: `Archivo` for bold display type, `Work Sans` for body copy, `IBM Plex Mono` for stats and timestamps, on a warm paper background with a halftone dot-grain texture on the hero (pure CSS, no image). "What you can teach" and "what you want to learn" are told apart structurally — filled ink chips vs. outlined chips — rather than by color, and the brand mark is the logo in `logo.jpg`, embedded inline so the page stays a single dependency-free file.

## Project structure

```
index.html   the entire app — markup, styles, and logic
logo.jpg     source file for the brand mark; index.html embeds it inline as a
             base64 data URI (also used for the browser-tab favicon), so
             logo.jpg itself isn't fetched at runtime — it's kept here as
             the editable source
README.md    this file
```

## Notes & known limitations

- **Data lives in `localStorage`** (falls back to in-memory if storage is unavailable, e.g. some sandboxed previews) — reloading the page keeps your progress; "Log out" clears it permanently.
- **All sample students, ratings, and badges are fictional** demo data seeded on first load.
- **The match score is a real, rule-based calculation** (skill overlap, availability overlap, rating), not a call to any external AI service.
- **Video calling is a single-browser demo** — camera/mic preview only works over a secure context (`https://`, not a local `file://` open), and the "other participant" is always simulated.
- No account system, no real-time sync between devices/users — this is a self-contained prototype, not a multi-user backend.

---

Built for a hackathon under the "Future of Work & Education" theme.
