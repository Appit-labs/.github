# Creating the Appit Labs organisation

Checked 2026-11-18. `appit-labs` was free at that time; `Appit` itself is taken by a **user**
account, and users and organisations share one namespace.

## 1. Create it (web UI — GitHub has no API for this)

<https://github.com/organizations/new> → **Free** → name `appit-labs` → contact email → create.

Then:

1. **Avatar** — upload `profile/assets/appit-avatar.png` (512×512, generated from the logo).
2. **Display name**: `Appit Labs`.
3. **Bio**: `AI and apps projects — plus the agent skills we use to ship them.`
4. **Website**: `https://github.com/Appit-labs/appit-skills` (until there is a real site).

## 2. Publish the profile README

The `profile/` folder in this directory is a complete GitHub profile repository:

```bash
cd ~/work/appit-labs-org
gh repo create appit-labs/.github --public --source=. --remote=origin --push \
  --description "Appit Labs — AI and apps projects, and the agent skills we ship with"
```

GitHub renders `profile/README.md` on <https://github.com/appit-labs> automatically. The logo and
avatar live beside it in `profile/assets/`, so every page keeps working if the repo is renamed.

## 3. Move the code in

```bash
cd ~/work/appit-skills
scripts/migrate-to-org.sh --yes          # transfers the 9 skill repos, rewrites every reference
cd ~/work/appit-labs-org
```

The migration script repoints READMEs, `plugin.json`, `package.json` and the marketplace sources
from `Appit-labs/…` to `appit-labs/…`, sets topics, and pushes. GitHub leaves redirects behind, so
existing links keep working.

## 4. Keep the org tidy

- **Teams**: `skills-maintainers` (write), `skills-reviewers` (triage).
- **Repo defaults**: issues on, wiki off, "require PR review" for `main`, secret scanning on.
- **Profile repo**: `.github` — the README there is the org landing page.
- **Pin** the six public repos people should see first; leave the rest unpinned.
