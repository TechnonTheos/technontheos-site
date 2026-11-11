# technontheos.com

A static site with no build step, hosted on Cloudflare Pages.

## Deploy (one time)
1. Create a GitHub repo named `technontheos-site` and upload these files.
2. In Cloudflare, go to **Workers & Pages → Create → Pages → Connect to Git** and pick the repo.
   - Framework preset: **None**. Build command: *(blank)*. Output directory: `/`
3. Open the Pages project, go to **Custom domains → Add**, and add `technontheos.com` and `www.technontheos.com`.
   - Do **not** touch the existing `ha` DNS record. Home Assistant keeps working.

## Fill in placeholders
Search `index.html` for `YOUR-` and `[` to find them:
- `YOUR-GITHUB`, `YOUR-LINKEDIN`, `YOUR-EMAIL`
- The "Previous career" entry in the timeline
- Add your résumé at `assets/Nathan-Treadway-Resume.pdf`

## Weekly update (about 5 minutes)
1. In `index.html`, find `<!-- NEW WEEK -->` and copy the `<article class="card update">` block below it.
2. Paste the copy at the top of the list and edit the date, title, bullets, and "Next".
3. If a project changed status, change its tag: `done` = Published, `active` = In progress, `planned` = Planned.
4. Commit. Cloudflare redeploys automatically in about 30 seconds.

You can also edit straight on github.com: open the file, click the pencil icon, then commit.

## Public documents (approved only)
1. Scrub the PDF: no IPs, MACs, hostnames, or passwords.
2. Put it in `docs/`.
3. In `docs.html`, uncomment the link on its card and change `tag planned` / "Coming soon" to `tag done` / "Published".
4. Commit.

Drafts belong in the private Hub (hub.technontheos.com), never in this repo.
