# Hitfactor Visualizer

## Files
- `index.html` - GitHub Pages app
- `worker.js` - Cloudflare Worker source

## Deploy
Upload `index.html` to your GitHub repo root and enable GitHub Pages from the root branch.

## Share URL parameters
- `tab=elo` or `tab=classifiers`
- `division=carry_optics` etc.
- `start=YYYY-MM-DD`
- `end=YYYY-MM-DD`
- `shooters=Name One|Name Two`

## Notes
The app assumes your worker forwards:
- `/v1/shooters?q=name`
- `/v1/shooters/{id}/elo`
- `/v1/shooters/{id}/classifiers`
