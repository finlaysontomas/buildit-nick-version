# BuildIT — Nick's version

An extended copy of [Tomas's BuildIT site](https://buildit-websites.github.io/) so Nick can show Tomas what he would add: real pages in the top navigation, local Northern Beaches positioning, a pricing comparison, a contact form, a story page, a charity offer, a founding-clients offer, optional hosting, and social media marketing. It is plain HTML, CSS and JavaScript. There is no build step, so it can be hosted on GitHub Pages.

Tomas's published site matches the `fix/qa-round-1` branch of [buildit-websites/buildit-websites.github.io](https://github.com/buildit-websites/buildit-websites.github.io), not the shorter page currently on that repo's `main` branch. This copy starts from the live site: same BuildIT branding, offer, examples, current work, FAQ, phone, email and prices.

## Run locally

From this folder:

```sh
python3 -m http.server 8080
```

Open http://localhost:8080

Check a phone width in the browser's device toolbar (about 390px wide). The menu button should open every tab, including Why I'm doing this, Offers and Contact.

## Pages

| Page | File | What it is for |
| --- | --- | --- |
| Home | `index.html` | The offer, why I'm doing this (near the top), four steps, current work, founding and charity offers, prices, and a contact call to action |
| Services | `services.html` | Website, optional hosting, and social media marketing |
| Work | `work.html` | Lux-Lashes, Innovo, Ember & Oat, Ironbark Electrical |
| Pricing | `pricing.html` | Four offers and a comparison table. Two prices say Placeholder |
| Offers | `offers.html` | First 5 clients, optional honest review, and free design and build for any Northern Beaches charity. Hosting at normal rates |
| Why I'm doing this | `story.html` | First person, present tense: changing now, one honest job at a time, and core values tied to what he does |
| How it works | `how-it-works.html` | The four steps, with hosting called out as optional |
| About | `about.html` | First person. Northern Beaches. Links to Why I'm doing this. No invented suburbs or life history |
| FAQ | `faq.html` | The live-site questions, updated where hosting changed, plus the new offers |
| Contact | `contact.html` | Phone, email, the Innovo line, and a form that does not use a server |
| Ideas from Dad | `ideas.html` | These notes, on the site. Hidden from search (`noindex`) |
| Examples | `examples/cafe/`, `examples/electrician/` | Tomas's demo sites, unchanged apart from the "Back to BuildIT" link, which now opens the Work page |

The same list, with the reason for each addition, is on the [Ideas from Dad](ideas.html) page (footer link).

## Ideas from Dad

Each item is something a small web-business site benefits from. Take the ones you want. The rest can be deleted without breaking the others.

1. **Tabs, one job per page.** Home, Why I'm doing this, Services, Social, Work, Pricing, Offers, How it works, About, FAQ and Contact. Social jumps to the social media marketing section. The look is All In: huge type, a tilted magenta word, a cyan price sticker, a scrolling values strip, tilted value cards, and big offer cards. Pricing is levels in that look. Level 3 is social media marketing and the price says Ask me. The cursor trail and the scroll-in reveal are the same code as Tomas's live site. The trail stays off when reduced motion is on. A mouse move draws it on empty background. A touch pointer does not. A finger drag still draws over the background, which is what the live site does.

2. **Your copy stays put.** Branding, Ember & Oat, Ironbark Electrical, Lux-Lashes ([lux-lashes.com](https://www.lux-lashes.com)), Innovo ([innovotech.com](https://www.innovotech.com)), 0403 993 242 and finlaysontomas@gmail.com are from the live site. The dollar amounts are the same: **Design & build $1,250 one-time**, **Design & build + Hosting & monitoring $1,800 up front, then $99 a month**. Hosting is no longer inside the $1,250. See item 15.

3. **Pricing comparison table.** Four columns: Design & build, Design & build + Hosting & monitoring, Hosting & monitoring only, and Social media marketing. Included and not included are written in words. Unset prices say Placeholder. On a narrow screen the table scrolls sideways and the first column stays visible. Items that were only on the published Website + Care plan stay on the $1,800 column. They are listed as themselves, not quietly renamed "monitoring". Backups, security updates and email support on hosting-only say Placeholder, because they were not a separate hosting-only list.

4. **About you, and the Northern Beaches.** Local customers want a name and a place. The About page says "I'm Tomas. BuildIT is my studio." and links to Why I'm doing this. The same place shows in the home eyebrow, the footer, and the page's schema `areaServed`. No suburbs, work history, client numbers or awards were invented.

5. **A contact form that does not pretend to send.** GitHub Pages cannot run a backend. The form is markup: name, business, email, phone, plan and message. The button opens an email draft to BuildIT. Phone and email buttons stay on the page. The status line says nothing was stored on a server.

6. **A next step on every page.** Each customer page ends with Contact, Call, or both, plus the phone number and email. People decide on the page they are already reading.

7. **Mobile navigation.** Why I'm doing this and Offers are extra tabs. From 1040px wide and down, the links move into a menu button. The open menu scrolls on a short screen, Escape closes it, and it closes when a link is chosen. From 1041px to 1420px the desktop links use a slightly tighter gap so the longer tab still fits at 1280px.

8. **Colour contrast.** The dark BuildIT palette is unchanged. Checked against `#070a16`: body text `#eef2ff` about 17.7:1, muted text `#b4bed8` about 10.6:1, cyan `#22d3ee` about 10.9:1, violet `#a78bfa` about 7.3:1, magenta `#f472b6` about 7.5:1. WCAG AA for normal text is 4.5:1. The pricing table still says "Included" and "Not included" in words, so the difference is not colour alone. Focus outlines stay cyan.

9. **Share preview.** Every public page has `og:image`, `og:image:width`, `og:image:height`, `og:image:alt`, `twitter:card` (`summary_large_image`) and `twitter:image`, pointing at the existing `og-image.png` (1200×630). Absolute URLs are required for iMessage, Facebook, LinkedIn and similar. The image file is the one already on Tomas's site.

10. **No invented social proof.** No testimonials, star ratings, client counts or awards. Unset prices still say Placeholder. The why-copy is a first-person draft from the reasons Nick gave. It does not add life events, history, numbers or quotes.

11. **Relative links and `.nojekyll`.** Links between pages are relative, so the site works in a local folder and in a GitHub project site (which is served from `/buildit-nick-version/`, not the domain root). `.nojekyll` tells GitHub Pages to serve the files as they are, instead of running Jekyll.

12. **Why I'm doing this.** `story.html` is a first-person page, linked from the home section under the hero, from About, and from its own nav tab. The draft is present tense: not long ago I was making choices I'm not proud of, and I hurt people. I'm changing that, right now. This business is how I'm doing it, one honest job at a time. I owe my community, so I build websites for free for any Northern Beaches charity. My first 5 clients get a free design and build, and I'll earn an honest review. My core values are what I'm doing now, every day: honesty (real price and timeline, no surprises), owning it (if I get something wrong, I fix it), giving back, earning trust, and showing up (I do what I say, when I say). Hosting is still not included. A review is still not an obligation. Public pages do not say the copy is a placeholder. Ideas from Dad is the only place that asks Tomas to edit it into his own words. The home headline no longer says "We build it, host it and keep it running", because that promised hosting on every job. The Open Graph image still contains that line, so its alt text still describes the image.

13. **Charity offer.** Free design and build only, for any charity on the Northern Beaches, regardless of what they do or who they are. It is a section on the home page, a section on `offers.html`, a short block on Pricing, an FAQ answer, and a contact-form choice. Each public spot has a contact button. Hosting is not free. Hosting is charged at the normal rates, the same rates as any other client. No separate charity hosting price was invented.

14. **Founding clients.** The public copy says: my first 5 clients get a free design and build. That's how I'm earning trust, right now. Hosting is not included, and hosting is charged at the normal rates. That limit is in a highlighted box and in the body. It is the offer, not a count of clients already taken, and there is no "spots remaining" number. I'll earn an honest review. There is no obligation. No review was written.

15. **Hosting is optional.** Design & build is the existing **$1,250** and does not include hosting. Domain setup stayed on that price, because the live site already included the domain at $1,250. Design & build + Hosting & monitoring is the existing **$1,800** up front, then **$99 a month**. Hosting & monitoring only has no price: the card, the table and the form say **Placeholder**. The contact form opens the matching choice from `?plan=design`, `design-hosting`, `hosting`, `social`, `charity` or `founding`.

16. **Social media marketing.** Post building, content creation, and active sales and marketing via socials. Added on Services (`#social`), Pricing (`#social`), the home price cards, the comparison table, the FAQ and the contact form. Not a separate tab. The price says **Placeholder**. Networks and volume are not set. No results, follower counts or ad spend were added. Public pages do not carry a note asking Tomas to fill the price in.

17. **Backed by Innovo.** A bold first-person section is on Home (after the offers), About, Why I'm doing this (`story.html`), Pricing and Contact. It says Nick Finlayson backs BuildIT, Tomas trades under Innovo, and every contract is with Innovo (Ampyre Pty Ltd trading as Innovo). Innovo links to https://innovotech.com. Near every price and above the contact form: "Contracts are with Innovo (Ampyre Pty Ltd, ACN 609 298 455)." Footer on every page: "BuildIT is a business of Innovo (Ampyre Pty Ltd trading as Innovo, ACN 609 298 455). Backed by Nick Finlayson." FAQ question: "Who is the contract with?" No Innovo stats, clients, awards or years in business were added. The Work page line about Nick Finlayson was already there and was left as it was.

18. **Prices are ex GST.** Said on the Pricing page: in the introduction, above the four offers, on the comparison headings, in the table caption, and in the FAQ. The home price section says it too, so those figures are not read as GST-inclusive. The dollar amounts are unchanged. No GST was added on top.

## Files

- `index.html`, `story.html`, `offers.html` and the other pages listed above
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

Also update the copies in each page's `<head>` (title, description, canonical, Open Graph, Twitter, JSON-LD), the email address in `404.html` and `contact.html`, and the prices in `index.html`, `pricing.html`, `contact.html` and `faq.html`. Search for `1,250`, `1,800`, `99` and `Placeholder` so a price change does not leave an old number, or a real number, in a spot that should still say Placeholder.

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
