# Agent Notes

## Project Shape
- This is a static personal CV site served from the repository root, not a Node or framework app.
- `index.html` is the only page; the site CSS lives in the root `style.css`, linked with a relative path so it works both on GitHub Pages and when served locally.
- `CNAME` pins the GitHub Pages custom domain to `cv.m32.nz`; do not remove it when changing site files.
- `robots.txt` disallows all crawlers, and `index.html` also has `NOINDEX, NOFOLLOW`; preserve that privacy posture unless asked otherwise.

## Assets
- Public downloads live in `download/`.
- Assets in `img/` and `download/` are referenced with relative paths, so the site works identically on GitHub Pages and when served locally.

## Website vs PDF Text Deviations
The site text is kept in sync with `download/cv-public.pdf` except for these intentional deviations; do not "fix" them back to match the PDF:
- The PDF header string "Full Stack .NET Developer (TL;DR Stack: C#, JS, SQL - 5+ Years Experience)" is rendered on the site as the role line plus a "TL;DR Stack:" label with chips: C#, JS, SQL, and a separate "5+ Years Experience" badge.
- Technical skill lists render as chips, and the PDF's trailing "and much more" / "and so on" become "..." pills (accent-colored in "Skilled in", gray in "Tools").
- The "5+ Years Experience" number is total professional developer experience in whole years, rounded down, summed across developer roles only (currently: GoSweetSpot Full Stack .NET Developer, Sandfield Solution Developer, Octane Systems Full Stack .NET Developer; the COVID gap and non-developer roles are excluded). Recalculate and update it whenever the PDF is synced or work experience entries are added/changed.
- Decorative " - " separators between entry title, dates, and location are dropped; entry heads are structured as title + parenthetical detail, a date pill, and an icon-prefixed location.
- The site shows a "Last Updated" date (DD/MM/YYYY) matching the PDF's ModDate; the PDF does not display one.
When the PDF text changes, update the site to match while preserving the deviations above.

## Commands
- There is no `package.json`, build step, lint config, test suite, or CI workflow in this repo.
- For local checking, serve the root directory directly, for example `python -m http.server 8000`, then inspect `index.html` in a browser.

## Editing Guidance
- Keep changes plain static HTML/CSS unless adding tooling is explicitly requested.
- Avoid touching binary assets such as `download/cv-public.pdf` unless the task specifically targets them.
