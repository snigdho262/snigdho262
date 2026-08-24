# 🚀 GitHub Profile README Setup Guide

This guide walks you through implementing your enhanced GitHub profile with **daily quote automation**, **styled headers**, **skill animations**, and **custom social icons**.

---

## 📋 Files You Need

```
your-username/  (your GitHub profile repo)
├── README.md                    (Main profile - provided)
├── update-quote.js              (Quote update script - provided)
├── quotes.json                  (Quote database - provided)
├── .github/
│   └── workflows/
│       └── update-quote.yml     (GitHub Actions workflow - provided)
├── banner.png                   (Your banner image)
├── Skills_Animation_Dark.gif    (Dark mode skills animation)
├── Skills_Animation_White.gif   (Light mode skills animation)
├── gmail.png                    (Social icon)
├── twitter.png                  (Social icon)
├── instagram.png                (Social icon)
├── github.png                   (Social icon)
├── linkedin.png                 (Social icon)
└── dev_to.png                   (Social icon)
```

---

## 🛠️ Step-by-Step Setup

### Step 1: Create Your Profile Repository

If you don't have one already:
- Go to GitHub and create a **new public repository** named `snigdho262` (your GitHub username)
- Clone it to your local machine

```bash
git clone https://github.com/snigdho262/snigdho262.git
cd snigdho262
```

### Step 2: Add All Files

1. **Copy the provided files** to your repository:
   - `README.md` (the enhanced version)
   - `update-quote.js`
   - `quotes.json`
   - All image files (banner, skills GIFs, social icons)

2. **Create the workflow directory:**
   ```bash
   mkdir -p .github/workflows
   ```

3. **Add the workflow file:**
   - Copy `update-quote.yml` to `.github/workflows/update-quote.yml`

### Step 3: Update Social Links in README

Open `README.md` and customize these links:

```markdown
<!-- Change these URLs to yours -->
<a href="mailto:snigdhoroy262@gmail.com">          <!-- ✅ Already set -->
<a href="https://twitter.com/YOUR_HANDLE">         <!-- Update this -->
<a href="https://www.instagram.com/s_n_igdho_">   <!-- ✅ Already set -->
<a href="https://github.com/snigdho262">           <!-- ✅ Already set -->
<a href="https://www.linkedin.com/in/...">         <!-- ✅ Already set -->
<a href="https://dev.to/YOUR_USERNAME">            <!-- Update this -->
```

### Step 4: Update GitHub Username

The README is **already configured for `snigdho262`**, but if you need to change any usernames:

**Search and replace in README.md:**
- Replace `snigdho262` with your GitHub username (in stats URLs, trophy URLs, etc.)

### Step 5: Commit and Push

```bash
git add .
git commit -m "🎉 Add enhanced GitHub profile with daily quotes"
git push origin main
```

### Step 6: Enable GitHub Actions

1. Go to your GitHub repository → **Settings** → **Actions** → **General**
2. Make sure **"Allow all actions and reusable workflows"** is selected
3. Go to **Actions** tab → Find **"Update Daily Quote"** workflow
4. Click **"Enable workflow"** if it's disabled

### Step 7: Test the Quote System

1. In **Actions** tab, click on **"Update Daily Quote"** workflow
2. Click **"Run workflow"** button
3. Check your README to see if the quote updated!

---

## 📝 Customizing the Quote System

### Change Colors

In `update-quote.js`, modify the theme colors:

```javascript
// Current colors (purple theme matching your profile)
const cardDesign = `
<img src="https://readme-daily-quotes.vercel.app/api?author=${encodeURIComponent(author)}&quote=${encodeURIComponent(quote)}&theme=dark&bg_color=1f1f1f&author_color=6C63FF&accent_color=6C63FF">
`;

// Color codes:
// bg_color=1f1f1f       → Background (dark gray)
// author_color=6C63FF   → Author text (purple - your brand color)
// accent_color=6C63FF   → Accent color (purple)
```

**Popular colors:**
- Purple: `6C63FF`
- Blue: `0077B5`
- Green: `00D26A`
- Orange: `FF6B35`
- Red: `E63946`

### Add/Remove Quotes

Edit `quotes.json`:

```json
[
  {
    "quote": "Your awesome quote here",
    "author": "Author Name"
  },
  {
    "quote": "Another quote",
    "author": "Another Author"
  }
]
```

### Change Schedule

In `.github/workflows/update-quote.yml`, modify the cron schedule:

```yaml
schedule:
  - cron: '30 6 * * *'  # Current: Daily at 12:00 PM IST
```

**Common schedules:**
- `0 0 * * *` → Daily at midnight UTC
- `0 12 * * *` → Daily at noon UTC
- `0 9 * * 1` → Every Monday at 9 AM UTC
- `0 * * * *` → Every hour

---

## 🎨 Customizing Skills Animation

You can replace the GIF files with your own:

1. **Light mode**: `Skills_Animation_White.gif`
2. **Dark mode**: `Skills_Animation_Dark.gif`

Or use a different animation library:
- [skillicons.dev](https://skillicons.dev) - Icon library
- [github-readme-streak-stats](https://github-readme-streak-stats.demolab.com/) - Activity visualization
- Custom animated GIFs from [ezgif.com](https://ezgif.com)

---

## 📊 GitHub Stats Customization

### Change Theme

In `README.md`, replace `theme=tokyonight` with:
- `dark`
- `radical`
- `merko`
- `gruvbox`
- `dracula`
- `nord`
- `highcontrast`

### Show/Hide Stats

Modify the stats URLs to customize what shows:

```markdown
<!-- Show specific stats -->
&show_icons=true         → Show icons
&include_all_commits=true → Include all commits
&count_private=true      → Count private repos
&hide=prs,issues         → Hide PRs and issues
```

---

## 🚀 Workflow Triggers

Your quote updates automatically in **3 ways**:

1. **Daily Schedule** - Every day at 12:00 PM IST (6:30 AM UTC)
2. **Manual Trigger** - Click "Run workflow" in Actions tab
3. **On Push** - (Optional) Uncomment in `.github/workflows/update-quote.yml`:

```yaml
on:
  push:
    branches: [ main ]
  # ... rest of config
```

---

## 🐛 Troubleshooting

### Workflow fails to commit
- Make sure **"Allow GitHub Actions to create and approve pull requests"** is enabled in Settings → Actions → General

### Quote doesn't update
- Check **Actions** tab for error logs
- Verify `quotes.json` exists in root directory
- Make sure `update-quote.js` has correct filename in `fs.readFileSync()`

### Images not showing
- Verify all `.png` and `.gif` files are in the repository root
- Check file names match exactly in README.md (case-sensitive)

### Stats not displaying
- Check GitHub username is correct (replace `snigdho262` if needed)
- Verify URLs don't have typos

---

## ✨ Advanced Tips

### Add Profile Views Counter
Already included! Updates automatically:
```markdown
<img src="https://komarev.com/ghpvc/?username=snigdho262&label=Profile%20views&color=6C63FF&style=for-the-badge&logo=star" />
```

### Pin Favorite Projects
Add this section before the quote:
```markdown
<h2 align="center">📌 Featured Projects</h2>

<a href="https://github.com/snigdho262/project-name">
  <img align="center" src="https://github-readme-stats.vercel.app/api/pin/?username=snigdho262&repo=project-name&theme=tokyonight" />
</a>
```

### Add Blog Posts Feed
Use [blog-post-workflow](https://github.com/gautamkrishnar/blog-post-workflow) to auto-update recent blog posts.

### Dark Mode Detection
The skills animation already uses `<picture>` tag for automatic dark/light mode:
```markdown
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="./Skills_Animation_Dark.gif">
  <source media="(prefers-color-scheme: light)" srcset="./Skills_Animation_White.gif">
  <img src="./Skills_Animation_White.gif">
</picture>
```

---

## 📚 Useful Resources

- [GitHub Readme Stats](https://github.com/anuraghazra/github-readme-stats)
- [GitHub Streak Stats](https://github-readme-streak-stats.demolab.com/)
- [GitHub Profile Trophy](https://github.com/ryo-ma/github-profile-trophy)
- [Shields.io](https://shields.io/) - Badge generator
- [readme-typing-svg](https://readme-typing-svg.demolab.com/) - Animated typing

---

## 🎉 You're All Set!

Your enhanced GitHub profile is ready to go! The daily quote will update automatically every day at 12:00 PM IST.

Feel free to customize colors, quotes, schedule, and content to match your style!

**Questions?** Check the GitHub Actions logs for detailed error messages.

Happy coding! 🚀
