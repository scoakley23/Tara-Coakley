# Tara Coakley — Website

A simple, no-build website: plain HTML, CSS, and JavaScript. No installs, no
frameworks — you can edit it in any text editor (even GitHub's own editor in
the browser) and it will just work.

## Files

```
index.html              Home page
interior-design.html    Interior Design service page
events.html             Event Planning service page
oh-what-fun.html        Oh What Fun pop-up shop page
about.html              About page
contact.html            Contact page + form
css/style.css           All styling and colors
js/main.js              Mobile menu + scroll animations
```

## 1. What's already filled in

Name, location (Elm Grove, WI), email, phone, and Instagram are already in
place across every page. The only placeholders left on purpose are things
only Tara can supply honestly:

- Upcoming Oh What Fun pop-up dates and locations on `oh-what-fun.html`
- Real photos (see step 2)

Search each file for `[` to find anything still bracketed. (Client
testimonials were left out entirely for now rather than filled with
placeholder quotes — easy to add a "What clients say" section later once
there are real ones to use.)

## 2. Add real photos

Right now the galleries use gray placeholder boxes labeled "ADD PHOTO" so the
layout looks finished even without images yet. To swap one in:

1. Put the image file in the `images/` folder (e.g. `images/kitchen-01.jpg`).
2. Find the matching placeholder in the HTML, which looks like this:
   ```html
   <div class="ph-image"><span class="ph-label">Detail shot — tile, hardware, or lighting</span></div>
   ```
3. Replace it with:
   ```html
   <img src="images/kitchen-01.jpg" alt="Renovated kitchen with white oak cabinetry">
   ```
   Write a real, specific `alt` description each time — it helps with
   accessibility and search engines.

You don't have to replace every placeholder at once — add photos as you get
them, a few at a time.

### The two logos

- **TC logo** — the circular navy logo you provided, saved as
  `images/tc-logo.png` with the background already removed. It's used in
  the header and footer on every page, plus large on the About page. To
  swap in a different version later, just replace that file (keep the
  filename the same and everything updates automatically).
- **Oh What Fun logo** — the two watercolor logo files you sent are already in
  place: `images/oh-what-fun-logo-banner.jpeg` (the car illustration) in the
  page's hero, and `images/oh-what-fun-logo-badge.jpeg` (the round badge) in
  that page's footer. Neither appears anywhere else on the site. To adjust
  their size, edit `.fun-logo-hero` and `.fun-logo-badge` in `css/style.css`.

## 3. Turn on the contact form

The contact form uses [Formspree](https://formspree.io), a free service that
emails you form submissions without needing a real backend server.

1. Create a free account at formspree.io.
2. Create a new form and copy the endpoint (looks like `https://formspree.io/f/abcd1234`).
3. In `contact.html`, find this line and replace `YOUR_FORM_ID`:
   ```html
   <form class="form-grid" action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
   ```

Until you do this, the form won't send anywhere — visitors can still use the
email/phone links next to it.

## 4. Put it on GitHub

1. Create a new repository on GitHub (e.g. `mom-website`).
2. Upload all these files and folders, keeping the same structure
   (`css/`, `js/`, `images/` as subfolders — not flattened).
   - Easiest way with no command line: on the repo page, click
     **Add file → Upload files**, then drag the whole folder in.
3. Commit the upload.

## 5. Turn on GitHub Pages

1. In the repository, go to **Settings → Pages**.
2. Under "Build and deployment," set **Source** to "Deploy from a branch."
3. Set the branch to `main` (or `master`) and the folder to `/ (root)`.
4. Save. GitHub will give you a URL like `https://yourusername.github.io/mom-website`
   within a minute or two — check that it works before moving on.

## 6. Connect your custom domain

1. Still in **Settings → Pages**, find "Custom domain" and enter your domain
   (e.g. `ohwhatfundesign.com`). Save — this creates a `CNAME` file in your
   repo automatically (there's already an empty one included here as a
   placeholder, in case you want to add it manually instead).
2. At your domain registrar (wherever you bought the domain — GoDaddy,
   Namecheap, Google Domains, etc.), add these DNS records:

   **If using the root domain (`ohwhatfundesign.com`):**
   Add four `A` records pointing to GitHub Pages' IP addresses:
   ```
   185.199.108.153
   185.199.109.153
   185.199.110.153
   185.199.111.153
   ```

   **If using a `www` subdomain (`www.ohwhatfundesign.com`):**
   Add a `CNAME` record pointing to `yourusername.github.io`.

   Most registrars let you set up both — a common pattern is A records on the
   root domain plus a CNAME on `www` that redirects to it.

3. DNS changes can take anywhere from a few minutes to 24 hours to take
   effect. Once it does, back in **Settings → Pages**, check "Enforce HTTPS"
   so the site loads securely.

GitHub's own guide (with screenshots) is here if you get stuck:
https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site

## Making future edits

Any time you want to change text, colors, or layout:

- **Text**: edit the `.html` files directly — the content is plain, readable text between tags.
- **Colors**: all colors are defined once at the top of `css/style.css` under `:root` — change a value there and it updates everywhere.
- **After editing**: commit and push the change (or use GitHub's web editor to edit and commit directly) — GitHub Pages redeploys automatically within a minute.
