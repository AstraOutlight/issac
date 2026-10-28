# The Binding of Isaac — fullscreen GitHub Pages

The website has no visible controls and loads the SWF fullscreen. It uses **local Ruffle files** after a one-time GitHub Actions setup, with no runtime CDN calls.

## Setup
1. Upload **all files including the hidden `.github` folder** to a repository (e.g. `username.github.io`) on its `main` branch.
2. Open **Actions → Bundle Ruffle locally → Run workflow**. Wait until it succeeds. The action downloads the official self-hosted Ruffle release and commits the actual emulator JS/WASM files into `ruffle/`.
3. In **Settings → Pages**, deploy from `main` branch, `/ (root)`.
4. Visit your Pages URL. If the workflow cannot push, set **Settings → Actions → General → Workflow permissions → Read and write permissions**, then rerun.

The ZIP cannot contain Ruffle binaries because they could not be downloaded in the packaging environment. The GitHub workflow fetches and stores them in your repository before the site is usable. This is **not** a runtime CDN dependency.

Flash game compatibility depends on Ruffle. Publishing a copyrighted SWF publicly requires distribution permission.
