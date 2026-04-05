# Quick Deployment Guide - Knowledge Crystal

## Option 1: GitHub Pages Deployment (Recommended)

### Step 1: Create GitHub Repository
1. Go to https://github.com/new
2. Create a new repository named: `knowledgecrystal.com`
3. Make it **public** for GitHub Pages
4. Do NOT initialize with README (we have files already)

### Step 2: Initialize Git & Push
```bash
cd /sessions/happy-clever-keller/mnt/knowledgecrystal_site

# Initialize git if not already done
git init
git add .
git commit -m "Initial Knowledge Crystal site"

# Add remote and push
git remote add origin https://github.com/yourusername/knowledgecrystal.com.git
git branch -M main
git push -u origin main
```

### Step 3: Enable GitHub Pages
1. Go to your repository: `github.com/yourusername/knowledgecrystal.com`
2. Click "Settings" tab
3. Scroll to "Pages" section (left sidebar)
4. Set:
   - Source: `Deploy from a branch`
   - Branch: `main` / `/ (root)`
5. Save

### Step 4: Configure Custom Domain (Optional)
1. In GitHub Pages settings, under "Custom domain":
   - Enter: `knowledgecrystal.com`
   - Click Save
2. Update DNS records with your domain registrar:
   ```
   Type: A Records
   Points to GitHub IP:
   - 185.199.108.153
   - 185.199.109.153
   - 185.199.110.153
   - 185.199.111.153

   OR if using subdomain:
   Type: CNAME
   Points to: yourusername.github.io
   ```
3. Wait 24 hours for DNS propagation

### Step 5: Verify Deployment
- GitHub Actions will automatically build and deploy
- Check "Actions" tab in your repo for build status
- Visit: https://knowledgecrystal.com or https://yourusername.github.io/knowledgecrystal.com
- Should see site with warm amber colors and working navigation

---

## Option 2: Local Testing Before Deployment

### Test Locally First
```bash
cd /sessions/happy-clever-keller/mnt/knowledgecrystal_site

# Install dependencies
bundle install

# Start local development server
bundle exec jekyll serve

# Open browser to: http://localhost:4000
```

### What to Test:
- Navigation between Home, About, Projects, Blog
- Responsive design (resize window to test mobile)
- Hover effects on cards and buttons
- Blog post reading time calculation
- All links are working

### Build for Production
```bash
bundle exec jekyll build
# Output is in _site/ directory
```

---

## Option 3: Deploy to Static Host

If you prefer Netlify, Vercel, or other static hosts:

### Netlify (Easiest)
1. Connect GitHub repo to Netlify
2. Build command: `jekyll build`
3. Publish directory: `_site`
4. Deploy!

### Vercel
1. Import GitHub repo
2. Framework preset: Other
3. Build command: `jekyll build`
4. Output directory: `_site`
5. Deploy!

---

## Post-Deployment Checklist

- [ ] Site loads without errors
- [ ] Navigation works (all 4 pages accessible)
- [ ] Colors display correctly (warm amber, dark background)
- [ ] Responsive design works on mobile
- [ ] Blog posts display with correct formatting
- [ ] Project cards display with tags
- [ ] Links to external sites work
- [ ] Social media links are functional
- [ ] Page load time is fast (<1 second)

## Update Content After Deployment

### Add New Blog Post
1. Create file: `_posts/YYYY-MM-DD-slug.md`
2. Add frontmatter (copy from existing post)
3. Write content in Markdown
4. Commit and push to main
5. GitHub automatically rebuilds

### Update About Page
1. Edit: `about.md`
2. Update bio, skills, or anything else
3. Commit and push
4. Changes live in ~1-2 minutes

### Update Projects
1. Edit: `projects.md`
2. Add/modify project cards
3. Commit and push
4. Changes live immediately

---

## Troubleshooting

### Site Not Building
1. Check GitHub Actions tab for error messages
2. Ensure Jekyll syntax is correct
3. Check file names and permalinks
4. Verify YAML frontmatter is valid

### Colors Not Showing
- All CSS is inline in `_layouts/default.html`
- If colors don't show, check browser cache
- Hard refresh: Ctrl+Shift+R (Windows) or Cmd+Shift+R (Mac)

### Links Broken
- Always use Jekyll tags: `{{ '/about.html' | prepend: site.baseurl }}`
- Use relative paths, not absolute URLs
- Check permalinks in _config.yml

### Mobile Not Responsive
- Clear browser cache
- Check media queries in default.html (max-width: 768px)
- Test with browser DevTools (F12)

---

## Monitoring & Maintenance

### Google Analytics (Optional)
Add to _config.yml:
```yaml
google_analytics: UA-XXXXXXXXX-X
```

### Search Console (Optional)
1. Verify site in Google Search Console
2. Submit sitemap: `yoursiteurl.com/sitemap.xml`
3. Monitor search performance

### Regular Updates
- Write new blog posts monthly
- Update project work as you complete it
- Keep links and contact info current
- Fix any broken links regularly

---

## Support & Resources

- Jekyll Docs: https://jekyllrb.com/docs/
- GitHub Pages: https://docs.github.com/en/pages
- GitHub Actions: https://docs.github.com/en/actions
- Markdown Guide: https://www.markdownguide.org/

---

## Next Steps

1. **This Week**: Deploy to GitHub Pages
2. **First Month**: Write 2-3 new blog posts
3. **Ongoing**: Add projects as you complete them
4. **Monthly**: Review analytics and update content

Good luck with Knowledge Crystal! 🔮
