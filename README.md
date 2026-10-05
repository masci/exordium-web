# exordium-web

The site of `exordium.pippi.im`, for the [Exordium](https://github.com/masci/exordium) app: the
`apple-app-site-association` file that opens invite links (`/join/CODE`) in the app, and a page that shows the code to
people who do not have it. It is a separate public repository because GitHub Pages needs one.

Pushing to `main` deploys it (Settings > Pages > Source: GitHub Actions, custom domain `exordium.pippi.im`).
`.well-known` is copied by hand in the workflow because the stock Pages action leaves out dot-directories.
