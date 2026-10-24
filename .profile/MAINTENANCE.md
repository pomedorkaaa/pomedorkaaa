# Profile renderer

Based on https://github.com/metawka/expressive-profile at commit
`0dacdd6b4cd8d649b71ace733afbfe1b92649955` (MIT).

The private-repository language query is removed, so both local and scheduled renders use public data only.

The bundled renderer supports explicit `palettes.light` / `palettes.dark` in
`profile.json`. These override generated Material color roles so the supplied
blue / lavender / graphite palette survives every scheduled update.

To rebuild: check out the upstream commit, apply `palette-support.patch`,
run `npm ci`, `npm run assets`, `npm run renderer`, and copy
`action/render.mjs` here. Keep the bundled license files.

Edit content, ordering, icons and colors in `profile.json`.
The workflow uses GitHub's built-in token and public repository statistics.
No personal access token is required. `.profile/data.json` is a public-data cache.

`hero.avatarPath` points to the local PNG used in the header instead of the GitHub avatar. Replace `.profile/avatar.png` to change it; scheduled updates preserve this image.
