# CrowdSense public website

This is a static GitHub Pages website for the ESP32 crowd detection project.

## Publish with GitHub Pages
1. Create a public GitHub repository named `crowd-detection-website`.
2. Upload `index.html` to the repository root.
3. Open repository Settings → Pages.
4. Under Build and deployment, select Deploy from a branch, branch `main`, folder `/(root)`, then Save.
5. Wait for deployment. GitHub Pages will show the public URL in Settings → Pages.

## Connect real data
The page expects a Firebase Realtime Database JSON object at `/crowd/latest`:
{
  "people": 1,
  "threshold": 2,
  "alarm": false,
  "status": "NORMAL",
  "updatedAt": 1720000000000
}

Edit `index.html` and set `DATABASE_URL` to your Firebase Realtime Database root URL. Do not enable unrestricted public writes. Use a protected write path/token or a small authenticated backend for Python publishing. The HTML page is only the public display; it does not send data from Python by itself.
