# 🎨 GitHub Profile Customization Cheat Sheet

Quick reference for customizing your enhanced GitHub profile README!

---

## 🎯 Quick Customizations

### Change Theme Colors
**File:** `update-quote.js` (Line with `readme-daily-quotes.vercel.app`)

```javascript
// Change these hex colors:
&bg_color=1f1f1f       // Background
&author_color=6C63FF   // Author text
&accent_color=6C63FF   // Accent

// Popular colors:
6C63FF  → Purple (current)
0077B5  → LinkedIn Blue
00D26A  → Green
FF6B35  → Orange
E63946  → Red
FFB700  → Gold
```

---

## 📊 GitHub Stats Themes

**File:** `README.md` (Multiple locations with `theme=tokyonight`)

Replace `tokyonight` with:
```
dark              highcontrast
radical           dracula
merko             nord
gruvbox           gitdimmed
```

### Example:
```markdown
<!-- From: -->
src="https://github-readme-stats.vercel.app/api?username=snigdho262&theme=tokyonight"

<!-- To: -->
src="https://github-readme-stats.vercel.app/api?username=snigdho262&theme=dracula"
```

---

## ⏰ Quote Update Schedule

**File:** `.github/workflows/update-quote.yml` (Line with `cron:`)

Change the cron schedule:
```yaml
schedule:
  - cron: '30 6 * * *'  # Current: Daily 12:00 PM IST
```

### Common Schedules:
```yaml
'0 0 * * *'      # Daily at midnight (UTC)
'0 12 * * *'     # Daily at noon (UTC)
'0 9 * * 1'      # Every Monday at 9 AM
'0 * * * *'      # Every hour
'*/30 * * * *'   # Every 30 minutes
```

**Note:** Times are in **UTC**, not IST. IST = UTC + 5:30

---

## 🔗 Social Links to Update

**File:** `README.md` (Search for "Connect With Me" section)

```markdown
<!-- Update these URLs: -->

<!-- Email (already set) -->
<a href="mailto:snigdhoroy262@gmail.com">

<!-- Twitter - CHANGE THIS -->
<a href="https://twitter.com/YOUR_HANDLE">

<!-- Instagram (already set) -->
<a href="https://www.instagram.com/s_n_igdho_">

<!-- GitHub (already set) -->
<a href="https://github.com/snigdho262">

<!-- LinkedIn (already set) -->
<a href="https://www.linkedin.com/in/snigdho-roy-b19a24237">

<!-- Dev.to - CHANGE THIS -->
<a href="https://dev.to/YOUR_USERNAME">
```

---

## 📝 Quote Database

**File:** `quotes.json` (Root directory)

Add/remove quotes easily:
```json
{
  "quote": "Your inspiring quote here",
  "author": "Author Name"
}
```

**Tip:** Use a JSON validator at [jsonlint.com](https://www.jsonlint.com/) to check syntax!

---

## 👤 GitHub Username References

**File:** `README.md` (Multiple locations)

Find and replace all instances:
```
snigdho262  →  your_github_username
```

These appear in:
- Profile stats URLs
- Trophy URLs
- Streak stats URLs
- Activity graph URLs
- Social links

**Search these patterns:**
```
github.com/snigdho262
username=snigdho262
user=snigdho262
```

---

## 🎬 Skills Animation

**File:** `README.md` (Lines with `Skills_Animation`)

### Keep Current GIFs
No changes needed - already set up for light/dark mode!

### Use Your Own GIFs
Replace these files in repository root:
- `Skills_Animation_White.gif` - Light mode
- `Skills_Animation_Dark.gif` - Dark mode

### Alternative: Use Icon Grid
Instead of GIF, use icons:
```markdown
<img src="https://skillicons.dev/icons?i=html,css,js,ts,react,angular,py,java,c,cpp,php,dart,mongodb,mysql,figma" />
```

Available icons: [skillicons.dev](https://skillicons.dev)

---

## 📊 GitHub Stats Customization

### Hide Certain Stats
In stats URL, add `&hide=` parameter:
```markdown
&hide=prs,issues,contribs    # Hide PRs, issues, contributions
&hide=contribs,prs_merged    # Hide contributions, merged PRs
```

### Show Specific Stats
```markdown
&show_icons=true             # Show stat icons
&include_all_commits=true    # Count all commits (default: current year)
&count_private=true          # Include private repos
&rank_icon=github            # GitHub-style rank icon
```

### Example:
```markdown
<!-- From: -->
api?username=snigdho262&count_private=true&show_icons=true&theme=tokyonight

<!-- To hide PRs and show only merged: -->
api?username=snigdho262&count_private=true&show_icons=true&theme=tokyonight&hide=prs&show=reviews,prs_merged
```

---

## 🏆 Trophy Customization

**File:** `README.md` (Line with `github-profile-trophy`)

### Change Layout
```markdown
&row=1&column=7     # Current: 1 row, 7 columns
&row=2&column=3     # 2 rows, 3 columns each
&row=3&column=4     # 3 rows, 4 columns each
```

### Change Theme
```markdown
&theme=tokyonight   # Current (all standard themes work)
&theme=flat         # Flat style
&theme=nord         # Nord theme
```

---

## 🎪 Activity Graph Customization

**File:** `README.md` (Line with `github-readme-activity-graph`)

### Change Colors
```markdown
&bg_color=220a28        # Background
&color=ffffff           # Default color
&line=c56a90            # Line color
&point=ffeb95           # Point color
```

### Hide/Show Elements
```markdown
&hide_border=true       # Hide border
&area=false             # Hide area fill
```

---

## 📌 Common Edit Locations

| What | File | Search For |
|------|------|-----------|
| Change theme | README.md | `theme=` |
| Update username | README.md | `snigdho262` |
| Add social link | README.md | `Connect With Me` |
| Adjust quote time | update-quote.yml | `cron:` |
| Change quote colors | update-quote.js | `accent_color=` |
| Add/remove quotes | quotes.json | `{` `}` |

---

## ✅ Testing Changes

### Test Quote System
```bash
# Install dependencies first
npm install

# Run the update script manually
node update-quote.js

# Check if README.md was updated
git diff README.md
```

### Test JSON Syntax
```bash
# Validate quotes.json
node -e "console.log(JSON.parse(require('fs').readFileSync('quotes.json', 'utf8')))"
```

### Preview Markdown
Use [GitHub's markdown preview](https://github.com/github/markdownlint) or VSCode extension.

---

## 🔧 Workflow Commands

### Manually Trigger Quote Update
1. Go to: **Actions** → **Update Daily Quote**
2. Click: **Run workflow** button
3. Select branch: **main**
4. Click: **Run workflow**

### Check Workflow Status
1. Go to: **Actions** tab
2. Click: **Update Daily Quote**
3. View logs of recent runs

### Disable Workflow
1. Go to: **Actions** → **Update Daily Quote**
2. Click three dots (···) → **Disable workflow**

---

## 🚨 Common Issues & Fixes

| Issue | Solution |
|-------|----------|
| Quotes not updating | Check `quotes.json` exists & has valid JSON |
| Images not showing | Verify filenames match exactly (case-sensitive) |
| Stats not displaying | Check GitHub username is correct everywhere |
| Workflow fails | Check Actions logs for specific error message |
| Colors look weird | Ensure hex codes start with `#` or remove it entirely |

---

## 📚 Quick Links

- **GitHub Docs:** https://docs.github.com/en/account-and-profile/profile
- **Markdown Guide:** https://www.markdownguide.org/
- **Color Picker:** https://htmlcolorcodes.com/
- **Cron Generator:** https://crontab.guru/
- **JSON Validator:** https://jsonlint.com/

---

## 💾 Before Making Changes

Always backup your current working version:
```bash
git add -A
git commit -m "Backup before customization"
git push
```

Then make changes and test locally before pushing!

---

**Need help?** Check `SETUP_GUIDE.md` for detailed instructions! 🚀
