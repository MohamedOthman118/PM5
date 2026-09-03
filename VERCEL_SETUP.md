# Vercel deployment setup

This project now builds as a native Next.js application on Vercel.

## Required once for Share links and team photos

1. In Vercel, open the project.
2. Go to **Storage** → **Create Database** → **Blob**.
3. Create a **Private** Blob store and connect it to this project.
4. Vercel automatically adds `BLOB_READ_WRITE_TOKEN` to the project.
5. Redeploy.

The main planner works without Blob because project data is saved locally in the browser. Blob is only required for cross-device manager share links and uploaded team photos.

## Build settings

- Framework: Next.js (automatic detection)
- Build command: `npm run build`
- Output directory: leave blank / default
- Node.js: 22.x

Do not set a custom Vite, Vinext, Wrangler, or Cloudflare build command on Vercel.
