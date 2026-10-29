# Legal Practice SEO

Static marketing site for legalpracticeseo.com. Plain HTML and CSS, no build step, no JavaScript.

```
index.html      Home
work.html       Work / proof
contact.html    Contact (cal.com button only)
styles.css      All styles
images/         Search Console screenshot + client message screenshot
```

## Replace the cal.com link

Every "Book a call" button points to `https://cal.com/hiren-thakkar/30min`. To change it, swap the URL in all three HTML files at once.

macOS:

```bash
sed -i '' 's#https://cal.com/hiren-thakkar/30min#https://cal.com/your-real-link#g' *.html
```

Linux / Git Bash on Windows:

```bash
sed -i 's#https://cal.com/hiren-thakkar/30min#https://cal.com/your-real-link#g' *.html
```

Or open each file in your editor and use find-and-replace on `https://cal.com/hiren-thakkar/30min`.

Check nothing was missed (should print nothing):

```bash
grep -n "hiren-thakkar/30min" *.html
```

If you change the meeting length, also update the "30 minutes" wording in the copy.

## Other things to check before going live

- **Canonical and Open Graph URLs** use `https://legalpracticeseo.com/`. If you deploy somewhere else first, change them, or leave them as they are if the domain will point there.
- **Screenshot captions.** The Search Console screenshot is captioned "a site I work on". If you want to name the site, edit the `figcaption` in `index.html` and `work.html`.
- **Social preview image.** `og:image` uses the Search Console screenshot. Replace it with a 1200x630 image if you make one.

## Deploy

Upload the folder as-is. Works on Netlify (drag and drop), Cloudflare Pages, or GitHub Pages (Settings > Pages > deploy from branch, root folder).
