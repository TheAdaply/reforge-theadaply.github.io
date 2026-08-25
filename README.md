# theadaply.github.io

The re-forge landing page, served at <https://theadaply.github.io/>.

This repo holds the **built static output only** — plain HTML, CSS, JS and a
logo. There is no backend, no dashboard, no API calls: the page is fully
static and nothing runs behind it.

## Source

The page is built from the `showcase/` directory of the private
`TheAdaply/re-forge` repo (Vite + React).

To rebuild and republish:

```sh
# in TheAdaply/re-forge
cd showcase
npm ci
npm run build          # -> showcase/dist

# copy the landing page files into a clone of this repo, then commit + push
cp dist/index.html dist/logo.jpeg dist/favicon-16.png dist/favicon-32.png \
   dist/apple-touch-icon.png <clone>/
rm -rf <clone>/assets && cp -R dist/assets <clone>/assets
```

`dist/` also contains standalone collateral (pitch/brief/tech/product pages,
PDFs, the team-sync video). None of it is linked from the landing page, so it
is deliberately **not** published here.

`.nojekyll` disables Jekyll processing so GitHub Pages serves the files as-is.
