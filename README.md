# My First HTML + CSS CI/CD Project

A small static website. GitHub Actions checks required files and basic HTML/CSS structure. Vercel deploys the project from the GitHub repository.

## Files

- `index.html` — page markup
- `style.css` — page styling
- `.github/workflows/ci.yml` — CI checks on pushes and pull requests to `main`

## Run locally

Open `index.html` in a browser.

## Publish with GitHub and Vercel

1. Create a new GitHub repository, for example `html-css-cicd-demo`.
2. Upload these files to the repository root, preserving `.github/workflows/ci.yml`.
3. In GitHub, open **Actions** and check that `HTML-CSS CI` passes.
4. Sign in to Vercel and choose **Add New → Project**.
5. Import the GitHub repository and authorize access if requested.
6. For a plain static site, leave the framework preset as **Other** and leave Build Command empty. The output can be the project root (`.`); Vercel can also detect a static HTML project automatically.
7. Click **Deploy**.
8. After deployment, each push to the connected production branch (usually `main`) triggers a new Vercel deployment. Pull requests can receive preview deployments.

## Important

The GitHub Actions workflow performs basic checks; it is not a full HTML/CSS validator. It does not automatically gate Vercel's deployment because Vercel deploys through its own Git integration. To make a strict gate, configure deployment through a workflow that waits for CI and uses Vercel's CLI, or use an appropriate deployment protection/check configuration.

No API key is needed for the basic GitHub Actions checks. Vercel may request that you sign in and authorize the GitHub integration.
