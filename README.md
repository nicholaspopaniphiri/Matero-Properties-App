# Matero Properties App (root helper files)

These are helper root files to allow Vercel to detect and build the project.

Steps to apply:
1. Create files in the repository root:
   - package.json (contents from package.json block)
   - tsconfig.json (contents from tsconfig.json block)
   - next-env.d.ts (contents from next-env.d.ts block)
   - .gitignore (contents from .gitignore block)
2. Remove the invalid RTF files:
   - Delete files named like `package.json..rtf` and `tsconfig.json.rtf` from the repo.
3. Commit & push to main:
   - git add package.json tsconfig.json next-env.d.ts .gitignore
   - git rm "package.json..rtf" "tsconfig.json.rtf"   (or delete them in the GitHub web UI)
   - git commit -m "Add valid package.json & tsconfig; remove RTF placeholders"
   - git push origin main
4. Vercel will auto-redeploy. If it does not, trigger a redeploy from the Vercel dashboard.

If your app is not Next.js + TypeScript:
- Tell me which framework it uses (Next.js + JS, Create React App, plain Node, or if the app files live in a subfolder like `/frontend`) and I will provide the correct package.json and instructions.

If you want, paste the Vercel build log after you push and I’ll confirm the next steps.
