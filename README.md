# The Bell Family History

A shareable, interactive family history website — nine generations of the Bell
family, from an 1814 Ohio land patent signed by President Madison down to today.

**Live site:** https://lkbell.github.io/bell-family-history/

Built from *The Bell Family History* by **Mary Wiltse Heck** (September 1985,
104 pages) and the 2026 research that digitized it, verified key facts against
primary records, and restored a missing branch of the family.

## What's here

- An **interactive family tree** — step through the generations one couple at a
  time, search 998 relatives by name, and open any person's record.
- **The direct line** — nine unbroken generations in a single thread.
- **The story** — the family's arc from Ulster to Virginia to Ohio to Iowa.
- **Original documents** — land maps, an 1833 handwritten will, marriage
  licenses, and photographs from the 1985 book.
- **About** — full credit to Mary Wiltse Heck's book and the 2026 research.

By the numbers: **998 people**, **309 families**,
**9 generations**. *(Built 2026-07-10.)*

## Privacy

This is a **public** website, so **living relatives appear by name only** — no
dates, no places, no personal details. That rule is enforced in the build
itself: living people are reduced to name-only in the data layer *before* the
page is generated, and the build refuses to write a file that would leak a
living person's details. The full private records (and a GEDCOM file for
genealogy software) are kept within the family and never published.

A person is treated as living when there's no death record and they were born
after 1926, plus an explicit family-private list. See `build.py` for the exact rule.

## Rebuilding the site

The site is generated from the family's structured data
(`people.json` + `families.json`, kept in the private data layer):

```
cd structured/site
python3 build.py          # writes dist/index.html + dist/README.md
```

The published `index.html` at the repo root is the generated, privacy-scrubbed
output. It is fully **self-contained** — plain HTML, CSS, and JavaScript with the
data and images embedded, no build framework and no external services. It works
straight from `file://` and from GitHub Pages.

## Credits

- **Mary Wiltse Heck** — *The Bell Family History*, 1985. The source of nearly
  everything here.
- **2026 research & digitization** — transcription, structured data, primary-source
  verification, and the site.
