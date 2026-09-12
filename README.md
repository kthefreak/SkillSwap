# SkillSwap

A prototype for the "Future of Work & Education" theme — students trade skills directly with each other instead of paying for lessons. No backend: a single self-contained `index.html` (vanilla HTML/CSS/JS, no build step, no dependencies) with a seeded network of 8 sample students so the whole product feels alive immediately.

## Run it

Just open `index.html` in any browser. Nothing to install.

## The flow this prototype proves out

Sign up → pick skills to teach/learn → get ranked matches with a smart-match score → view a match's profile → send a swap request → get accepted → schedule a session → chat, share notes & resources in the session workspace → mark it complete → rate & badge your partner → see your own progress bars update automatically.

## Feature map

- **Profiles** — teach/learn skill tags, ratings, badges, completed-session count.
- **Matching** — a transparent scoring model (shared availability, mutual skill fit, teaching track record) ranks every other student and explains *why* the top pick was chosen.
- **Sessions** — scheduling modal, then a workspace with live chat, autosaving shared notes, and a resource list.
- **Progress** — per-skill topic checklists and progress bars, populated automatically as sessions complete.
- **Ratings & badges** — star ratings plus awardable badges ("Python Mentor", "Great Teacher", …) shown on profiles.
- **Community** — a directory of active learners and a popular-skills breakdown for the school network.

## Notes

- State lives in `localStorage` (falls back to in-memory if storage is unavailable) — reloading keeps your progress.
- All eight seed students and their skills/ratings are fictional sample data for demo purposes.
