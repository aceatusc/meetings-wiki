# Publishing The Wiki With Quartz

This repository publishes the generated `wiki/` layer as a Quartz website through GitHub Pages.

## What Gets Published

Published:

- `wiki/`

Not published:

- `raw/transcripts/`
- `raw/assets/`
- `.obsidian/`

This keeps the public/collaborator website focused on synthesized wiki pages rather than raw meeting transcripts.

## GitHub Setup

In the GitHub repository:

1. Open `Settings`.
2. Open `Pages`.
3. Under `Build and deployment`, set `Source` to `GitHub Actions`.
4. Push to `main`.
5. Watch the `Deploy Quartz site to GitHub Pages` workflow in the `Actions` tab.

Expected URL:

```text
https://aceatusc.github.io/meetings-wiki/
```

## Updating The Site

After editing or ingesting new notes:

```shell
git add .
git commit -m "Update wiki"
git push origin main
```

GitHub Actions will rebuild and redeploy the site.

## Notes

- The workflow uses `wiki/` as the Quartz source folder.
- The generated site is uploaded from `public/`.
- If the graph does not appear, check the GitHub Actions logs first. Quartz graph view depends on Quartz's content index generation.

