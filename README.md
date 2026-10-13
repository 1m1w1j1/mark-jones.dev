# mark-jones.dev

A simple, responsive static portfolio for Mark Jones: aspiring backend developer, systems administrator, and Linux/homelab enthusiast. It uses only plain HTML, CSS, and JavaScript.

## Preview locally

From this folder, start any static-file server, for example:

```sh
python3 -m http.server 8000
```

Then visit `http://localhost:8000`. A local server is preferable to opening `index.html` directly because it matches how the browser will load the site in production.

## Project structure

- `index.html` — page content and semantic structure
- `homelab.html` — deliberately high-level homelab overview
- `styles.css` — responsive dark/light styling
- `script.js` — persistent theme toggle and mobile navigation
- `assets/images/` — compressed WebP assets used by the site
- `assets/originals/` — the original supplied PNG artwork, retained untouched

## Content notes

The project descriptions are deliberately conservative. Update the clearly marked “coming soon” text with verified details and links once each project is ready. Homelab content must remain high-level: never add secrets, credentials, private IPs or hostnames, serial numbers, network diagrams, service addresses, or other identifying infrastructure details. No email address, repository URL, deployment claim, or technical accomplishment is implied by this site.

## Future deployment plan: Caddy + Podman

Do not expose this site until the server, DNS, firewall, TLS configuration, and security posture have been reviewed.

When ready, a safe high-level approach is:

1. Create a GitHub repository and push this source after reviewing its contents.
2. On the intended server, clone a specific reviewed revision into a non-privileged deployment directory.
3. Serve the static directory from a small, read-only Podman container or Caddy’s static-file support.
4. Configure Caddy for `mark-jones.dev` and `www.mark-jones.dev` only after DNS points to the server and ports 80/443 are intentionally opened.
5. Verify HTTPS, security headers, logs, renewals, backups, and rollback steps before announcing the site.

Deployment is intentionally not included in this project so it cannot publish anything without an explicit review and authorization.
