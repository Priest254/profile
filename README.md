# Profile Card — Allan Nickson Kipkemboi

A small single-file profile card demonstrating a responsive, accessible profile component for the Slack internship assignment. The UI is implemented in `index.html` and uses a local `prof.jpg` avatar.

## What this is

- A polished, responsive profile card styled with modern CSS (Flexbox + responsive breakpoints).
- Accessible focus styles and semantic HTML (article, figure, nav, section, headings).
- Social links open in a new tab and include rel attributes for safety.
- The current time (milliseconds) is shown and updates once per second.

## Project files

- `index.html` — main profile card implementation (complete).
- `prof.jpg` — avatar image (keep a square image for best cropping).
- `README.md` — this file.

## Requirements mapping (acceptance checklist)

All required items from the assignment are present and their implementation notes:

- Profile card root container — `data-testid="test-profile-card"` — Done (wrapped in `<article>`).
- Name (plain text) — `data-testid="test-user-name"` — Done (`<h2>` inside header).
- Short biography (paragraph) — `data-testid="test-user-bio"` — Done (`<p>`).
- Current time (in milliseconds) — `data-testid="test-user-time"` — Done (updates via `Date.now()` every second).
- Avatar image (user photo) — `data-testid="test-user-avatar"` — Done (`<figure>` + `<img alt="...">`).
- Social links list — `data-testid="test-user-social-links"` — Done (`<nav>` containing a `<ul>`).
  - Each social link also includes an accessible anchor and inline SVG icon. Individual links have optional IDs/data-testids like `test-user-social-twitter`.
- Hobbies list — `data-testid="test-user-hobbies"` — Done (`<section>` with `<ul>`).
- Dislikes list — `data-testid="test-user-dislikes"` — Done (`<section>` with `<ul>`).

Accessibility & Semantics

- Semantic elements used: `article`, `figure`, `header`, `nav`, `section`, headings, and lists.
- All interactive elements are anchors (`<a>`) and keyboard-focusable. Focus styles are visible for keyboard users.
- Avatar has an `alt` attribute describing the image.

Behavior / Implementation notes

- `test-user-time` shows `Date.now()` (milliseconds). The page updates the shown value once per second to balance accuracy and CPU usage.
- Social links open in a new tab and include `rel="noopener noreferrer"`.
- Layout is responsive: on narrow screens the card stacks vertically; on wider screens the avatar sits to the left and content to the right.

How to run locally

Option A — Open the file

- Double-click `index.html` or open it in your browser (`File → Open`). This is fine for a static demo.

Option B — Serve with a simple local server (recommended)

Open PowerShell in the project folder (path shown below) and run either Python or Node static server.

PowerShell (Python 3):

```powershell
# from the project root
python -m http.server 8000
# then open http://localhost:8000 in your browser
```

PowerShell (if you have Node and serve installed):

```powershell
# install once if needed
npm install -g serve
# then run
serve -l 8000 .
# open http://localhost:8000
```

Quick verification checklist (manual)

1. Open the page and use the browser devtools to find elements with the following selectors/data-testids:
   - `article[data-testid="test-profile-card"]`
   - `[data-testid="test-user-name"]`
   - `[data-testid="test-user-bio"]`
   - `#user-time[data-testid="test-user-time"]`
   - `img[data-testid="test-user-avatar"]`
   - `nav[data-testid="test-user-social-links"]`
   - `[data-testid="test-user-hobbies"]`
   - `[data-testid="test-user-dislikes"]`
2. Confirm `#user-time` value is a number near `Date.now()` (allowable delta of a second is expected).
3. Tab through the social links and confirm a visible focus ring appears.
4. Resize the browser: the card should stack on small widths and switch to a side-by-side layout on wider viewports.

Credits & references

- Icons: inline SVGs included in `index.html` (no external icon dependency).

License

---