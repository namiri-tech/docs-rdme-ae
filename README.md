# DigiTax UAE API Hub

Source for the DigiTax UAE API Hub on [ReadMe](https://readme.com), published at
[ae.docs.digitax.tech](https://ae.docs.digitax.tech). It holds the guides (`docs/`), the API reference guide pages
and the endpoint pages generated from `reference/openapi.yaml` (`reference/`), and the files those pages link to.

The live branch is `v1.0`, which ReadMe syncs with. Make changes on a feature branch and open a pull request into
`v1.0`.

## Checks

Lint the docs as ReadMe sees them:

```sh
npx @readme/cli lint
```

Markdown style (rules in `.markdownlint.json`) and spelling (project words in `cspell-word-list.txt`):

```sh
npx markdownlint-cli2 "docs/**/*.md" "reference/**/*.md"
npx cspell "docs/**/*.md" "reference/**/*.md"
```

`reference/openapi.yaml` and the endpoint pages under `reference/DigiTax UAE API Endpoints/` come from the API spec in the backend
repository. Change the spec there rather than editing them by hand.

