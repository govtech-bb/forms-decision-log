# Form Decision Log — GovTech Barbados

A live, single-file HTML tool for documenting design and field decisions made during the GovTech Barbados forms digitisation programme.

**Live site:** https://govtech-bb.github.io/forms-decision-log/

---

## What it is

The decision log is a lightweight reference tool for the forms prototyping team. Every significant design call — the decision itself, the context that prompted it, and the rationale behind it — is logged here. It is styled to match the [alpha.gov.bb](https://alpha.gov.bb) design system and is shared with the team and MDAs as a live reference.

---

## Features

- **Log decisions** via a modal form — title, category, status, context, decision, rationale, applies to, and author
- **Edit and delete** any decision inline
- **Six categories** — Email, Field, Validation, Structure, Conditional, Process
- **Status tracking** — Active, Under review, Superseded
- **Clickable status stats** at the top — click to filter by status
- **Activity timeline** — shows all decisions sorted by most recent, with an "edited" badge for anything changed in the current session
- **Export** — download all decisions as CSV, JSON, or Markdown
- **Collapsible cards** — decisions expand to show context, decision, and rationale in a three-column grid
- **Supabase persistence** — decisions are saved to a cloud database and available to the whole team in real time
- **Offline fallback** — if the database is unavailable, the page loads seed data and displays a warning banner

---

## File structure

```
decision-log.html    — the entire application (HTML, CSS, JS in one file)
README.md            — this file
supabase-setup.md    — instructions for setting up the Supabase database
```

---

## How to use

### Logging a decision
Click **New decision** and fill in the form. All fields marked * are required. The decision is saved to Supabase immediately and appears in the list.

### Editing a decision
Open any decision card and click the **edit icon** (pencil) in the top right of the card. The modal pre-fills with the existing values. Save to update. Edited decisions show an "edited" badge in the activity timeline for the rest of the session.

### Deleting a decision
Click the **delete icon** (bin) on any card. You will be asked to confirm before the decision is removed from both the page and the database.

### Filtering
- Click any **status stat card** at the top to filter by Active, Under review, or Superseded
- Click a category in the filter bar to filter by category
- Click again to clear the filter

### Exporting
Click the **Export** button and choose CSV, JSON, or Markdown.

---

## Supabase setup

The database connection is configured in the script block near the top of `decision-log.html`:

```js
const SUPABASE_URL  = 'https://zijwusnnogcpnewvmivd.supabase.co';
const SUPABASE_ANON_KEY = 'your-anon-key-here';
```

See `supabase-setup.md` for the full setup instructions including the table schema and RLS policies required.

### If the project is paused
Supabase pauses free tier projects after a period of inactivity. To restore:
1. Go to [supabase.com](https://supabase.com) and sign in
2. Open your project and click **Restore project**
3. Wait a minute, then reload the decision log — it will reconnect automatically

---

## Deploying changes

The site is hosted on GitHub Pages from the `main` branch. To publish an update:

1. Open the repository at [github.com/amogendukwe-png/forms-decision-log](https://github.com/amogendukwe-png/forms-decision-log)
2. Navigate to `decision-log.html` (or `index.html`)
3. Click the pencil icon to edit, paste the updated file contents, and commit to `main`
4. GitHub Pages will rebuild automatically — allow 1–2 minutes

---

## Design system

The page follows the [alpha.gov.bb](https://alpha.gov.bb) design system:

- **Font:** Figtree
- **Navy:** `#00267f`
- **Yellow:** `#ffc726`
- **Blue-10:** `#e5e9f2`
- **GOB wordmark:** inline SVG with exact path data from alpha.gov.bb

---

## Built by

The Forms Prototyping Team, GovTech Barbados.
