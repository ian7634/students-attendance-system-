# Render deployment notes

## Render Web Service
- Runtime: Node
- Branch: main
- Root Directory: leave blank
- Build Command: `npm install`
- Start Command: `npm start`
- Node version: 22.x (set by package.json)

## Persistent SQLite data
If you attach a Render persistent disk, set:
- Mount Path: `/data`
- Environment Variable: `DATA_DIR=/data`

The app stores its SQLite database at `${DATA_DIR}/attendance.db`.
Without a persistent disk, SQLite data may be lost when the service is redeployed.

## Frontend files
The server serves the `public/` folder when it exists. If your HTML/CSS/JS files are in the repository root, it serves the root as a fallback while blocking server/config files.
