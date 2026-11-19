# Josh Wilson — Personal Academic Website

Static site for [username.github.io](https://username.github.io). Plain HTML and CSS, no build step.

---

## Deploying to GitHub Pages

1. Create a GitHub repo named **`username.github.io`** (replace `username` with your GitHub username).
2. Push the contents of this folder to the `main` branch:
   ```bash
   git init
   git add .
   git commit -m "initial site"
   git remote add origin https://github.com/username/username.github.io.git
   git push -u origin main
   ```
3. In the repo on GitHub, go to **Settings → Pages**, set source to `main` branch, root folder.
4. Your site will be live at `https://username.github.io` within a minute or two.

---

## Common edits

### Add a publication

Open `index.html` and find the `pub-list` div. Copy any existing `<article class="pub">` block and fill in:

```html
<article class="pub">
  <p class="pub-title">
    Your Paper Title Here
  </p>
  <p class="pub-authors">
    First Author, <strong>Josh Wilson</strong>, Last Author
  </p>
  <p class="pub-venue">
    <em>Journal or Conference Name</em> &middot; 2025
  </p>
  <p class="pub-links">
    <a href="https://link-to-pdf.com">PDF</a>
    <a href="https://github.com/yourrepo">Code</a>
    <a href="https://project-page.com">Project</a>
  </p>
</article>
```

Delete any `<a>` tags in `pub-links` that don't apply.

### Group publications by year

Wrap each year's papers in a `<div>` with a heading:

```html
<p class="pub-year">2025</p>
<article class="pub"> ... </article>
<article class="pub"> ... </article>

<p class="pub-year">2024</p>
<article class="pub"> ... </article>
```

The `.pub-year` style is already in `style.css`.

### Swap the headshot

Replace `images/profile.jpg` with your new photo (keep the same filename), or update the `src` attribute in `index.html`:

```html
<img src="images/your-new-photo.jpg" alt="Josh Wilson">
```

The photo is cropped square by CSS. If the face is cut off, adjust `object-position` in `style.css`:

```css
.photo-wrap img {
  object-position: center top; /* try: center, center 20%, top, etc. */
}
```

### Add a Twitter / social link

In `index.html`, find the contact `<nav>` and replace `#` with your URL:

```html
<a href="https://twitter.com/yourhandle" aria-label="Twitter profile">Twitter / X</a>
```

### Add a new section (e.g. Research, Teaching)

After the closing `</section>` of publications, add:

```html
<section id="teaching" aria-labelledby="teaching-heading">
  <h2 id="teaching-heading">Teaching</h2>
  <p>Your content here.</p>
</section>
```

No CSS changes needed — sections inherit all the existing heading and spacing styles.

### Add project images

Drop images into the `images/` folder, then add them anywhere in the page:

```html
<a href="https://your-project-url.com">
  <img src="images/project-name.jpg" alt="Brief description of the project">
</a>
```

---

## File structure

```
/
├── index.html      — all page content
├── style.css       — all styles (commented by section)
├── README.md       — this file
└── images/
    └── profile.jpg — headshot
```
