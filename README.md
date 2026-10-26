# Jongwon Kim — Official Minimal Light Jekyll Theme

This site uses the **official** upstream Minimal Light Jekyll theme by Yaoyao Liu, via `remote_theme: yaoyao-liu/minimal-light`. It does not imitate or rewrite the theme's CSS.

Official source: https://github.com/yaoyao-liu/minimal-light

## Publish on GitHub Pages

1. Recommended: rename your repository to `Jong-w.github.io` (exactly matching your GitHub username, case-insensitively). Then the site is available at https://jong-w.github.io/.
2. Upload **the contents of this folder** to the root of the repository (not the folder itself). Delete older `index.html`, `style.css`, and `script.js` from the previous version, because Jekyll needs `index.md` to generate the homepage.
3. Settings > Pages > Deploy from a branch > `main` / `(root)` > Save.
4. GitHub Pages uses Jekyll to load the official remote theme. The first build can take a few minutes. Check Actions for build errors.

If you keep the repository named `JongWon.github.io` under the `Jong-w` account, this is a project site instead of a root user site. For that case add `baseurl: /JongWon.github.io` and `url: https://jong-w.github.io` to `_config.yml`, and change absolute site links accordingly. Renaming is easier.

## Edit
- Profile, social links and theme: `_config.yml`
- About, interests, education, experience: `index.md`
- Papers: `_data/publications.yml`
- Publication layout: `_includes/publications.md` (based on upstream include)
- Images and public CV: `assets/`

Note: the official remote theme is downloaded during the GitHub Pages build, so this ZIP alone cannot be opened by double-clicking `index.md` as a local HTML page. The source and assets are included, but the theme is intentionally loaded from its official upstream.
