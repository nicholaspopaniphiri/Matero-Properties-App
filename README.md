# Matero Properties App

A real-estate web application (Matero Properties). This repository contains the application source under the `src/` folder. The repository previously included Rich Text Format placeholder files (e.g. `package.json..rtf`, `tsconfig.json.rtf`) that block builds on Vercel — replace those with valid JSON files as described below.

## Quick status (what to fix now)
- Remove any `*.rtf` placeholder files such as:
  - `package.json..rtf`
  - `tsconfig.json.rtf`
- Add valid files at the repository root:
  - `package.json`
  - `tsconfig.json`
  - (optional) `next-env.d.ts` if using Next.js + TypeScript
- Do NOT delete the `src/` folder — it contains your application code.

## Recommended root files
I previously provided templates for:
- `package.json` (Next.js + TypeScript default)
- `tsconfig.json`
- `next-env.d.ts`
- `.gitignore`

Use the template that matches your framework (Next.js is the default recommended for Vercel).

## Fix RTF placeholders (safe commands)
If you work locally, run these commands from the repository root:

1. Inspect RTF files:
```bash
git ls-files '*.rtf' || true
```

2. Remove the RTF placeholder files (example):
```bash
git rm "package.json..rtf" "tsconfig.json.rtf"
git commit -m "Remove RTF placeholder files"
```

3. Add valid root files (create `package.json`, `tsconfig.json`, etc.), then:
```bash
git add package.json tsconfig.json next-env.d.ts .gitignore
git commit -m "Add valid package.json, tsconfig and helpers"
git push origin main
```

If you prefer the GitHub web UI: create the new files using "Add file → Create new file", paste the content, commit to `main`, and delete the `.rtf` files using the trash icon.

## Run locally (example for Next.js)
Install dependencies:
```bash
npm install
```

Run dev server:
```bash
npm run dev
```

Build for production:
```bash
npm run build
npm start
```

(If your project uses CRA or a plain Node server, the commands differ — use the appropriate `package.json` scripts.)

## Vercel deployment notes
- Vercel auto-detects Next.js projects when a valid `package.json` is at the repository root.
- If your project source lives in a subfolder (e.g., `/frontend`), either:
  - Move `package.json` to repo root, or
  - Set Project → Settings → General → Root Directory in Vercel to that subfolder.
- After pushing the valid root files, Vercel will trigger a redeploy automatically. If the build fails, capture the Vercel build log and use it to diagnose missing dependencies or build errors.

## Environment variables
If your app depends on API keys or other secrets, configure them in Vercel:
- Vercel Dashboard → Project → Settings → Environment Variables
- Add keys for `VERCEL_ENV`, `API_KEY`, etc., as required by your code.

## Do not delete `src`
The `src` folder is your application code. The deployment error you saw was caused by missing/invalid `package.json`, not by `src`. Keep all app files intact.

## Support / Next steps
- If your app is NOT Next.js (for example, Create React App or plain Node), tell me which framework and I'll provide the correct `package.json` and instructions.
- After you push the corrected root files, paste the Vercel build log here if anything fails and I’ll help you fix it.

Thank you — once you add the corrected root files and remove the RTF placeholders, the repo should build on Vercel. If you want, I can paste the exact `README.md` file into your repo (or push the other files) — tell me whether you want the Next.js template or a different framework.
