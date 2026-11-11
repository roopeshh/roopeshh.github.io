# hosting/

Static folder that serves RAYS-T's **public** key at

    https://<your-domain>/.well-known/appspecific/com.tesla.3p.public-key.pem

`tools/make-keys.sh` writes the key file here. Deploy the folder as-is:

- **GitHub Pages** — `.nojekyll` makes Pages serve the `.well-known` folder.
- **Cloudflare Pages** — no build command, output directory `hosting`; `_headers` is applied.
- **Netlify** — base directory `hosting`; `netlify.toml` and `_headers` are applied.

`callback/` is only used if your Tesla developer app needs an `https://` redirect URI.
Nothing secret belongs in this folder.
