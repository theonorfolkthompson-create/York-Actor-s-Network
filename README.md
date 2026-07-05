# The York Actor's Network

A calendar and community noticeboard for a local acting network, styled as an
antique theatre **playbill**. It is a single, self-contained HTML file — no
build step, no server, no dependencies to install.

![Day and night printings of the playbill theme](docs/preview.png)

> The preview image is optional. Drop a screenshot at `docs/preview.png` (or
> delete this line and the image above) to show the design in your repo.

## What it does

- **Monthly calendar** of auditions, rehearsals, performances, socials and more.
- **Create events** with a category, description, location, time, and optional
  roles/parts that people can sign up for (with per-role capacity limits).
- **Recurring events** — daily, weekly, fortnightly or monthly, with a
  "repeat until" date. Each occurrence keeps its own independent sign-up sheet.
- **Multi-day events** render as a single connected bar across the days they span.
- **Suggestion box** — a second page for website-improvement ideas that visitors
  can submit and upvote, sorted by top or newest.
- **Day / Night theme toggle** — a parchment "day printing" and a candlelit
  "night printing". Your choice is remembered, and it respects your system's
  light/dark preference on first visit.
- **Sign-in** via Slack or Google, so people can manage the events they create.

## Running it

It's just one file. Either:

- **Open `index.html` directly** in a browser, or
- **Serve it locally** (recommended, so browser storage behaves normally):

  ```bash
  python3 -m http.server 8000
  # then visit http://localhost:8000
  ```

## Deploying with GitHub Pages

Because the app is a single `index.html` at the repo root, GitHub Pages hosts it
with no configuration:

1. Push this repository to GitHub (see below).
2. In the repo, go to **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to *Deploy from a branch*,
   choose the `main` branch and the `/ (root)` folder, then **Save**.
4. Your site appears at `https://<your-username>.github.io/york-actors-network/`
   within a minute or two.

## How it's built

- Plain HTML, CSS and JavaScript in one file. No frameworks, no bundler.
- Fonts (Playfair Display, Cormorant Garamond, EB Garamond, Pinyon Script) load
  from Google Fonts, so an internet connection is needed for the intended type.
- All data — events, sign-ups, suggestions, your theme choice — is stored in the
  browser's `localStorage`.

## Known limitations

This is a front-end prototype. Two things to be aware of before relying on it:

- **Sign-in is simulated.** It records a display name locally; it does **not**
  verify passwords or provide real account security.
- **Data is per-device.** Because everything lives in `localStorage`, each
  visitor sees only their own browser's data — events and sign-ups are **not**
  shared between people.

Making this a genuinely shared, multi-user system means adding a backend. A
hosted option such as [Firebase](https://firebase.google.com/) or
[Supabase](https://supabase.com/) would provide real authentication (Google
sign-in works out of the box) and a shared database, replacing the `localStorage`
layer and the simulated login.

## License

Released under the MIT License. See [LICENSE](LICENSE).
