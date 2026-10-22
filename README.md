# BuildIT — Nick's version

An extended copy of [Tomas's BuildIT site](https://buildit-websites.github.io/) so Nick can show Tomas what he would add: real pages in the top navigation, local Northern Beaches positioning, a pricing comparison, and a contact form. It is plain HTML, CSS and JavaScript. There is no build step, so it can be hosted on GitHub Pages.

Tomas's published site matches the `fix/qa-round-1` branch of [buildit-websites/buildit-websites.github.io](https://github.com/buildit-websites/buildit-websites.github.io), not the shorter page currently on that repo's `main` branch. This copy starts from the live site: same BuildIT branding, offer, examples, current work, FAQ, phone, email and prices.

## Run locally

From this folder:

```sh
python3 -m http.server 8080
```

Open http://localhost:8080

Check a phone width in the browser's device toolbar (about 390px wide). The menu button should open every tab, including Contact.

## Pages

| Page | File | What it is for |
| --- | --- | --- |
| Home | `index.html` | The offer, four steps, current work, both prices, and a contact call to action |
| Services | `services.html` | Website, domain, hosting and care, plus why BuildIT |
| Work | `work.html` | Lux-Lashes, Innovo, Ember & Oat, Ironbark Electrical |
| Pricing | `pricing.html` | Both plan cards and a comparison table |
| How it works | `how-it-works.html` | The four steps and what to have ready |
| About | `about.html` | Tomas, Northern Beaches. Bio text is marked placeholder |
| FAQ | `faq.html` | The questions already on the live site |
| Contact | `contact.html` | Phone, email, and a form that does not use a server |
| Ideas from Dad | `ideas.html` | These notes, on the site. Hidden from search (`noindex`) |
| Examples | `examples/cafe/`, `examples/electrician/` | Tomas's demo sites, unchanged apart from the "Back to BuildIT" link, which now opens the Work page |

The same list, with the reason for each addition, is on the [Ideas from Dad](ideas.html) page (footer link).

## Ideas from Dad

Each item is something a small web-business site benefits from. Take the ones you want. The rest can be deleted without breaking the others.

1. **Tabs, one job per page.** Home, Services, Work, Pricing, How it works, About, FAQ and Contact. The live site is one long page, which is a solid first version. Separate pages let a visitor open Pricing or Work on their own, share that link, and see the shape of the business in the menu.

2. **Your copy stays put.** Branding, the four-part offer, the four steps, Ember & Oat, Ironbark Electrical, Lux-Lashes ([lux-lashes.com](https://www.lux-lashes.com)), Innovo ([innovotech.com](https://www.innovotech.com)), the FAQ, 0403 993 242 and finlaysontomas@gmail.com are from the live site. Prices are unchanged: **Website $1,250 one-time**, **Website + Care $1,800 up front, then $99 a month** for domain and hosting.

3. **Pricing comparison table.** The two cards are still there. The table on the Pricing page lines up included and not included in words. The Website + Care list is long, and a table is easier to scan, including on a phone (swipe sideways). Items only listed on Website + Care are marked not included on the Website plan. That follows the plan cards and the FAQ. It is not a new promise.

4. **About you, and the Northern Beaches.** Local customers want a name and a place. The About page calls Tomas a Northern Beaches web designer and says BuildIT is for local businesses on Sydney's Northern Beaches. The same place shows in the home eyebrow, the footer, and the page's schema `areaServed`. The personal bio is a dashed **Placeholder** box. Fill it in with your own words. Nothing there is a made-up history.

5. **A contact form that does not pretend to send.** GitHub Pages cannot run a backend. The form is markup: name, business, email, phone, plan and message. The button opens an email draft to BuildIT. Phone and email buttons stay on the page. The status line says nothing was stored on a server.

6. **A next step on every page.** Each customer page ends with Contact, Call, or both, plus the phone number and email. People decide on the page they are already reading.

7. **Mobile navigation.** Eight items do not fit in a phone header. From 1040px wide and down, the links move into a menu button. The open menu scrolls on a short screen, Escape closes it, and it closes when a link is chosen. That is the same pattern as the live site, with the breakpoint moved up so the extra tabs do not overflow.

8. **Colour contrast.** The dark BuildIT palette is unchanged. Checked against `#070a16`: body text `#eef2ff` about 17.7:1, muted text `#b4bed8` about 10.6:1, cyan `#22d3ee` about 10.9:1, violet `#a78bfa` about 7.3:1, magenta `#f472b6` about 7.5:1. WCAG AA for normal text is 4.5:1. The pricing table still says "Included" and "Not included" in words, so the difference is not colour alone. Focus outlines stay cyan.

9. **Share preview.** Every public page has `og:image`, `og:image:width`, `og:image:height`, `og:image:alt`, `twitter:card` (`summary_large_image`) and `twitter:image`, pointing at the existing `og-image.png` (1200×630). Absolute URLs are required for iMessage, Facebook, LinkedIn and similar. The image file is the one already on Tomas's site.

10. **No invented social proof.** No testimonials, star ratings, client counts or awards. Where a sentence still needs Tomas's voice, it is marked Placeholder.

11. **Relative links and `.nojekyll`.** Links between pages are relative, so the site works in a local folder and in a GitHub project site (which is served from `/buildit-nick-version/`, not the domain root). `.nojekyll` tells GitHub Pages to serve the files as they are, instead of running Jekyll.

## Files

- `index.html` and the other pages listed above
- `styles.css`: Tomas's styles, plus layout for the page heroes, comparison table, form, placeholders and the earlier menu breakpoint
- `main.js`: site details (name, email, phone), mobile nav, the contact-form mailto, scroll reveal, card tilt, cursor trail
- `404.html`: missing URLs. On GitHub project Pages, a small script points its CSS at `/buildit-nick-version/` when the missing address is nested
- `favicon.svg`, `og-image.png`, `robots.txt`, `sitemap.xml`
- `work/`: screenshots of Lux-Lashes and Innovo
- `examples/cafe/` and `examples/electrician/`: the two demo sites (each a single `index.html` with its own CSS, photos in `img/`, and `preview.webp` for the thumbnail)
- `netlify.toml`: only used if the site is also published on Netlify. GitHub Pages ignores it
- `.nojekyll`: see above

`ideas.html` is left out of `sitemap.xml` and marked `noindex`. Remove the footer link if you do not want customers to see the notes.

## Changing the business name, email, phone or prices

Edit the `SITE` object at the top of `main.js` for the name, email and phone that JavaScript fills in.

Also update the copies in each page's `<head>` (title, description, canonical, Open Graph, Twitter, JSON-LD), the email address in `404.html` and `contact.html`, and the prices in `index.html`, `pricing.html`, `contact.html` and `faq.html`. Search for `1,250` and `99` so a price change does not leave an old number behind.

The public site URL used for sharing is:

`https://finlaysonnick74-source.github.io/buildit-nick-version/`

It is written in each page's canonical and social tags, in `sitemap.xml`, in `robots.txt`, and in the JSON-LD on the home page. If the GitHub Pages address or a future domain is different, replace that URL everywhere. Social images must stay absolute (`https://…/og-image.png`).

## GitHub Pages

Pages is not on for this repo yet. This session could not turn it on, because that is a repository setting change. After this pull request is merged into `main`:

1. Open [the Pages settings](https://github.com/finlaysonnick74-source/buildit-nick-version/settings/pages) for this repo.
2. Under **Build and deployment**, set **Source** to **Deploy from a branch**.
3. Set **Branch** to `main` and the folder to **`/ (root)`**, then save.
4. Wait until the Pages panel shows a live URL. For this repo it should be `https://finlaysonnick74-source.github.io/buildit-nick-version/`.
5. You do not need a GitHub Actions workflow. There is no build. `.nojekyll` is already in the root so Pages will not run Jekyll.

If the URL GitHub shows is different from the one above, update the absolute URLs described in the previous section, or link previews and the sitemap will point at the wrong place.

To confirm it worked, open the Pages URL, click every tab, open Ember & Oat and Ironbark Electrical, and check a link preview by pasting the home URL into a message or into [opengraph.xyz](https://www.opengraph.xyz/).
