# Rent Manager — install as an app

This folder turns your Rent Manager page into an installable app (PWA) for
both Android and iPhone: home-screen icon, full-screen (no browser bar),
and it keeps working offline.

## 1. Put it online (required for install + offline mode)

Phones need to load this over `https://` for "Add to Home Screen" to give a
real app install (not just a bookmark) and for offline mode to work. Easiest
free options — drag-and-drop the whole `rent-manager-app` folder in:

- **Netlify Drop**: https://app.netlify.com/drop
- **GitHub Pages**: push the folder to a repo, enable Pages in Settings
- **Vercel**: https://vercel.com/new (drag & drop or connect a repo)

Any of these gives you a link like `https://your-app.netlify.app`.

## 2. Install on Android

1. Open the link in **Chrome**.
2. Tap the **⋮** menu → **Add to Home screen** (or you may see an
   automatic **Install app** banner/prompt).
3. Confirm — it now opens full-screen from your home screen, like a normal app.

## 3. Install on iPhone

1. Open the link in **Safari** (must be Safari, not Chrome — iOS only
   allows installing from Safari).
2. Tap the **Share** icon (square with an arrow) → **Add to Home Screen**.
3. Confirm — it now opens full-screen from your home screen.

## Notes

- **Data lives on the device**: this app stores tenants/payments/expenses in
  the browser's local storage on each phone. It does **not** sync between
  your phone and someone else's — each install has its own data. If you
  need the same data on multiple devices, that requires adding real backend
  storage (e.g. a small database + login), which isn't part of this file.
- **Sending WhatsApp receipts**: the app opens `wa.me` with the tenant's
  number pre-filled and saves the receipt file to your device — WhatsApp
  itself doesn't allow a link to auto-attach a file, so you still tap the
  paperclip once to attach the file that was just saved. This is a
  restriction of WhatsApp, not this app.
- Re-upload/redeploy this folder any time you want to update the app;
  installed users will get the update automatically next time they open it
  and have a connection (thanks to the service worker).
