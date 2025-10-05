# Guide: How to Update Lunair Q&A Page

## Quick Update (Recommended)

### Option 1: Using Claude Code
Simply tell Claude Code what changes you need, for example:
- "Update the answer to question X"
- "Add a new FAQ about Y"
- "Change the header color"

Claude Code will automatically edit, commit, and deploy for you.

### Option 2: Manual Update
1. **Edit the file:**
   - Open `index.html` in your text editor
   - Make your changes
   - Save the file

2. **Commit to GitHub:**
   ```bash
   cd "C:\Users\owner\Downloads"
   git add index.html
   git commit -m "Update: describe your changes here"
   git push
   ```

3. **Deploy to Vercel:**
   ```bash
   vercel --prod --yes
   ```

---

## One-Time Setup: Auto-Deploy from GitHub

Set this up once to automatically deploy whenever you push to GitHub (no need to run `vercel` command):

1. **Go to Vercel Dashboard:**
   - Visit: https://vercel.com/dashboard
   - Find your project: `lunair-qa`

2. **Connect to GitHub:**
   - Go to Settings → Git
   - Connect the repository: `Yedidiwah/lunair-Q-A`
   - Set deployment branch: `master`

3. **Done!** Now every `git push` will auto-deploy

---

## Common Tasks

### Add a New FAQ Item
Add this HTML before the closing `</div>` of the relevant section:

```html
<div class="faq-item">
    <div class="question">
        <span>ש: Your question here?</span>
    </div>
    <div class="answer">
        <p>ת: Your answer here.</p>
    </div>
</div>
```

### Change Colors
Edit the `<style>` section (lines 8-73):
- Header gradient: line 44
- Section titles: line 53
- Highlights: line 62

### Update Contact Info
Edit the footer section (line 222-224)

---

## Project Structure

```
C:\Users\owner\Downloads\
├── index.html          # Main FAQ page (edit this)
├── vercel.json         # Vercel config (don't edit)
├── .gitignore          # Git ignore rules (don't edit)
└── .vercelignore       # Vercel ignore rules (don't edit)
```

---

## URLs

- **Production Site:** https://lunair-2nkpe31mh-yedidyas-projects.vercel.app
- **GitHub Repo:** https://github.com/Yedidiwah/lunair-Q-A
- **Vercel Dashboard:** https://vercel.com/yedidyas-projects/lunair-qa

---

## Troubleshooting

**Problem:** Changes don't appear on the live site
**Solution:** Clear your browser cache or open in incognito mode

**Problem:** `git push` rejected
**Solution:** Pull first: `git pull origin master` then push again

**Problem:** Vercel deployment fails
**Solution:** Check that only `index.html` and config files are being deployed (large files are ignored)
