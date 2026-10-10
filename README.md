# exordium-web

The site of `exordium.pippi.im`, for the [Exordium](https://github.com/masci/exordium) app: the
`apple-app-site-association` file that opens invite links (`/join/CODE`) in the app, and a page that shows the code to
people who do not have it. It is a separate public repository because GitHub Pages needs one.

It is a [Hugo](https://gohugo.io) site with the [Sugo](https://github.com/psugam/sugo) theme (a git submodule in `themes/sugo`).
Pushing to `main` builds it and deploys it (Settings > Pages > Source: GitHub Actions, custom domain `exordium.pippi.im`).

## Work on it
```
git clone --recurse-submodules <repo>   # or: git submodule update --init
hugo server
```
Hugo extended 0.146 or newer is needed. The workflow pins the version.

## Pages
`content/` holds the home page, `privacy`, `terms` and `support`. Each has an English file and an Italian one (`*.it.md`, served under `/it/`).
The contact address is `params.contactEmail` in `hugo.toml`. It shows in the footer, and it is written in the text of the pages.

`layouts/404.html` is the landing page of the invite links and is self-contained (it is served at paths such as `/join/CODE`, so it cannot use
relative links). `static/` is copied as it is: `CNAME`, `.nojekyll` and `.well-known`. The workflow packs the build with `tar` because the
stock Pages artifact action leaves out dot-directories.

The theme loads Google Fonts by default. `layouts/_partials/head/fonts.html` is empty to turn that off, and `hugo.toml` sets system fonts.
