
# Deploy to Hostinger (hPanel) — Vite React SPA

## 1) Build locally
```bash
npm install
npm run build
```
This generates a `dist/` folder.

## 2) Upload to Hostinger
- Open **hPanel → Files → File Manager**
- Go to your domain root, usually: `/public_html`
- Upload the contents of `dist/` into `/public_html/` (not the folder itself; the files inside it)
- Ensure **`index.html`** is directly under `/public_html/`
- Upload the provided `.htaccess` to `/public_html/` if not already present

> Subfolder deployment? If you want `yourdomain.com/app/`, create `/public_html/app/` and put `dist/` files there. Then set the rewrite base in `.htaccess`:
> ```
> RewriteBase /app/
> ```

## 3) SPA routing (already handled)
Your repo includes **`public/.htaccess`** with this rule:
```
RewriteEngine On
RewriteBase /
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_FILENAME} !-d
RewriteRule ^ index.html [L]
```
Copy that file as `/public_html/.htaccess` (or adjust `RewriteBase /app/`). This ensures deep links like `/dashboard/photographer/orders` load correctly.

## 4) Environment config (optional)
- If serving from a subpath, set Vite base in `vite.config.js`:
```js
export default defineConfig({ base: '/app/', /* ... */ })
```
- And set router basename:
```jsx
<BrowserRouter basename="/app">
  {/* ... */}
</BrowserRouter>
```

## 5) Cache
The `.htaccess` sets CDN/browser cache headers for `/assets/`. On release, always re-upload the new `dist/` bundle so filenames (with hashes) change and users get the latest build.

## 6) Troubleshooting
- **Blank page**: Check `.htaccess` exists at the correct path and `index.html` is in the web root.
- **404 on refresh**: Missing SPA rewrite; ensure rules above are active.
- **Old assets after update**: Clear CDN cache or wait; file names are hashed so new deploys propagate automatically.
