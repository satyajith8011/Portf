# Satyajith Halder — Portfolio Site

Two-page static site: `index.html` (portfolio) + `blog.html` (Field Notes).
No build step, no dependencies to install — just HTML/CSS/JS files.

## Deploy it (pick one, both are free)

**Netlify (easiest)**
1. Go to https://app.netlify.com/drop
2. Drag this whole folder onto the page.
3. Done — you get a live URL in seconds. Add a custom domain later under Site settings → Domain management.

**GitHub Pages**
1. Create a new GitHub repo (e.g. `satyajith-portfolio`).
2. Upload `index.html`, `blog.html`, and this `README.md` to the repo.
3. Go to repo Settings → Pages → set Source to "Deploy from branch", branch `main`, folder `/root`.
4. Your site goes live at `https://<your-username>.github.io/<repo-name>/`.

## Add a new blog post

Open `blog.html`, find the `POSTS` array near the bottom (inside the `<script>` tag), and add a new object at the **top** of the array:

```js
{
  id: "your-post-slug",       // no spaces, used in the URL
  title: "Your Post Title",
  date: "20 Jul 2026",
  tags: ["Career", "Security"],
  excerpt: "One or two sentence teaser.",
  body: `
    <p>Your first paragraph.</p>
    <p>Your second paragraph.</p>
  `
}
```

Save the file, refresh the page — no build step needed.

## Feature a LinkedIn post

LinkedIn has no public API for auto-syncing posts into an outside site, so this uses LinkedIn's own **"Embed this post"** feature instead:

1. Open the post on LinkedIn (desktop web works best for this).
2. Click the **•••** menu on the post → **Embed this post**.
3. Copy the `<iframe>...</iframe>` code LinkedIn gives you.
4. Open `index.html`, find the `<!-- LINKEDIN FEED -->` section, and paste the iframe
   into one of the `.li-embed` panels, replacing the placeholder `<div class="li-placeholder">...</div>`.

## Update your job status

If you change roles, update:
- `index.html` → hero "Character Status" card (`Status` row)
- `index.html` → Experience card badge (`CURRENT` tag) and the date range
- `index.html` → About section "Quick Facts" panel (`Current role` row)

## Files

- `index.html` — the main portfolio (manga/chapter-style design)
- `blog.html` — Field Notes blog, posts defined in a JS array inside the file
- `README.md` — this file
