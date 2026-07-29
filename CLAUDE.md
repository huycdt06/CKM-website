# Project: CKM website (Cơ Khí Môi Trường)

## Standing instructions (do not forget)
- **ALWAYS give the user the git commands to push AFTER EVERY file update.** The user pushes
  manually from Windows CMD; they want the exact commands each time. This is a hard rule.
- Website language is Vietnamese. Keep all user-facing copy in Vietnamese.

## Setup facts
- This folder (`D:\Claude Playground\Cokhimoitruong`) is a git repo linked to
  GitHub `https://github.com/huycdt06/CKM-website` (branch `main`).
- Live site: https://huycdt06.github.io/CKM-website/  (GitHub Pages, auto-deploys on push)
- Admin/editor page: https://huycdt06.github.io/CKM-website/admin.html
- The folder is mounted to Claude with CREATE/OVERWRITE allowed but NO file deletion and
  git commits fail from Claude's side (lock files can't be unlinked). So: Claude edits files,
  the USER runs git add/commit/push from CMD. If `.git\HEAD.lock` or `.git\index.lock` exist,
  user deletes them first (`del .git\HEAD.lock`).

## Architecture
- `index.html` — public site. Project gallery renders dynamically from `content.json`
  (with automatic placeholder for missing photos + a lightbox on the 🔍 button).
- `admin.html` — content editor. Uses a GitHub fine-grained token (Contents: Read and write,
  scoped to CKM-website) entered by the user; commits `content.json` + uploaded images
  directly via the GitHub Contents API. Token stored only in the browser's localStorage.
- `content.json` — the editable data (projects; services planned).
- `HUONG-DAN.md` — Vietnamese how-to guide for the non-technical manager.

## Standard push commands (give these after each update)
```
cd /d "D:\Claude Playground\Cokhimoitruong"
git add -A
git commit -m "<describe the change>"
git push
```
(First push in a session may open a GitHub browser login — that's expected.
 If commit errors about a lock file: `del .git\HEAD.lock` and `del .git\index.lock` first.)
