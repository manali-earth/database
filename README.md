# Portfolio database repo (demo content)

This is exactly what your database repo should contain — the admin panel
expects every page's JSON file plus `photos/` at the **root** of this repo
(not nested inside another `database/` folder).

```
home.json
my-story.json
education-experience.json
projects.json
publications.json
conferences.json
leadership.json
photos/
  home/            (has real demo photos)
  projects/        (has real demo photos)
  my-story/        (empty — .gitkeep only)
  education-experience/  (empty — .gitkeep only)
  publications/    (empty — .gitkeep only)
  conferences/     (empty — .gitkeep only)
  leadership/      (empty — .gitkeep only)
```

## What to do with it

1. Create a new GitHub repo (public or private — your choice; private just
   means the token you use later needs repo access).
2. Upload this content to it, preserving the folder structure exactly as
   above (drag-and-drop through the GitHub web UI works, or `git init` +
   push from this folder — either is fine).
3. Send me:
   - the repo, as `owner/name`
   - its default branch (usually `main`)
   - whether it's public or private

## What happens next

Once I have that, I'll switch the admin panel from `DATA_PROVIDER=local` to
`DATA_PROVIDER=github` and point `DATABASE_REPO` at this repo. You'll still
need a `WEBSITE_REPO` too (the repo holding the actual site's HTML/CSS/JS
plus `database/database.json`, which is a separate, smaller piece — the
routing index that lists these JSON files' locations and an `imageBase`
pointing at this repo's raw file URLs). If you don't have that repo set up
yet, say so and I'll generate it from the current website source.

You'll also need a GitHub Personal Access Token (fine-grained, with
Contents: read+write on the database repo and Contents: read on the website
repo) — **don't paste that token into chat**. It goes into your own
`.env.local` for local development, or into Cloudflare Pages' encrypted
secrets for the deployed version.
