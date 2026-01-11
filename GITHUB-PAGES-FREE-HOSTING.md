# 🆓 Free Website Hosting with GitHub Pages
## For smartkitchenforme.com

GitHub Pages is **100% FREE** and lets you host your website with your own domain!

---

## 📋 What You'll Get

- ✅ Free hosting (forever)
- ✅ Use your own domain (smartkitchenforme.com)
- ✅ HTTPS/SSL included (secure)
- ✅ Fast global CDN
- ✅ No ads
- ✅ Unlimited pages

---

## 🚀 Step-by-Step Setup

### Step 1: Create GitHub Account (Free)

1. Go to [https://github.com](https://github.com)
2. Click **Sign Up**
3. Enter your email, create password
4. Verify your email
5. Done! You have a free GitHub account

---

### Step 2: Create a New Repository

1. Click the **+** icon (top right) → **New repository**
2. Fill in:
   - **Repository name:** `smartkitchenforme-website`
   - **Description:** Smart Kitchen For Me website
   - **Public** (must be public for free hosting)
   - ✅ Check "Add a README file"
3. Click **Create repository**

---

### Step 3: Upload Your HTML Files

#### Method A: Web Upload (Easiest)

1. In your new repository, click **Add file** → **Upload files**
2. Drag and drop these files:
   - `index.html` (home page)
   - `share.html` (rename from share-page.html)
3. Scroll down, add commit message: "Add website files"
4. Click **Commit changes**

#### Method B: Create Files Directly

1. Click **Add file** → **Create new file**
2. Name it: `index.html`
3. Paste the entire content from the index.html template
4. Click **Commit new file**
5. Repeat for `share.html`

---

### Step 4: Enable GitHub Pages

1. In your repository, click **Settings** (tab at top)
2. Scroll down to **Pages** (left sidebar)
3. Under "Source", select:
   - Branch: `main`
   - Folder: `/ (root)`
4. Click **Save**
5. Wait 1-2 minutes
6. You'll see: "Your site is live at https://YOUR-USERNAME.github.io/smartkitchenforme-website/"

**Test it!** Open that URL - your website is now live!

---

### Step 5: Connect Your GoDaddy Domain

Now let's make smartkitchenforme.com point to your GitHub Pages site.

#### Part A: Add Custom Domain in GitHub

1. In repository **Settings** → **Pages**
2. Under "Custom domain", enter: `smartkitchenforme.com`
3. Click **Save**
4. ✅ Check "Enforce HTTPS" (after DNS is set up)

#### Part B: Configure DNS in GoDaddy

1. Log in to GoDaddy
2. Go to **My Products** → **Domains**
3. Find `smartkitchenforme.com` → Click **DNS** or **Manage DNS**
4. You need to add/edit these records:

**For Apex Domain (smartkitchenforme.com):**

Delete any existing A records, then add these 4 A records:

| Type | Name | Value | TTL |
|------|------|-------|-----|
| A | @ | 185.199.108.153 | 600 |
| A | @ | 185.199.109.153 | 600 |
| A | @ | 185.199.110.153 | 600 |
| A | @ | 185.199.111.153 | 600 |

**For www subdomain:**

| Type | Name | Value | TTL |
|------|------|-------|-----|
| CNAME | www | YOUR-USERNAME.github.io | 600 |

(Replace YOUR-USERNAME with your actual GitHub username)

5. Click **Save** after adding each record
6. Wait 15-30 minutes for DNS to propagate

#### Part C: Verify It Works

1. Go back to GitHub → Repository → Settings → Pages
2. It should show: "Your site is live at https://smartkitchenforme.com"
3. Check "Enforce HTTPS"
4. Test your site!

---

### Step 6: Create CNAME File

This helps GitHub remember your custom domain:

1. In your repository, click **Add file** → **Create new file**
2. Name it: `CNAME` (all caps, no extension)
3. Content (just one line):
```
smartkitchenforme.com
```
4. Click **Commit new file**

---

## 📁 Final Repository Structure

Your repository should look like:
```
smartkitchenforme-website/
├── index.html          (home page)
├── share.html          (recipe share page)
├── CNAME              (custom domain config)
└── README.md          (optional description)
```

---

## ✅ Testing Everything

### Test 1: Home Page
- Open: `https://smartkitchenforme.com`
- Should show your home page

### Test 2: Share Page (Empty)
- Open: `https://smartkitchenforme.com/share.html`
- Should show "No Recipe Found" message

### Test 3: Share Page with Recipe
- Open this URL:
```
https://smartkitchenforme.com/share.html?recipe=%7B%22title%22%3A%22Test%20Recipe%22%2C%22time%22%3A%2215%20min%22%2C%22difficulty%22%3A%22Easy%22%2C%22ingredients%22%3A%5B%22Chicken%22%2C%22Garlic%22%5D%2C%22instructions%22%3A%5B%22Step%201%22%2C%22Step%202%22%5D%7D
```
- Should show the test recipe!

### Test 4: From the App
1. Open Smart Kitchen app
2. Share a recipe to community
3. Should open smartkitchenforme.com with your recipe

---

## 🔧 Updating Your Website

Whenever you want to make changes:

1. Go to your GitHub repository
2. Click on the file you want to edit (e.g., `index.html`)
3. Click the pencil icon (Edit)
4. Make your changes
5. Click **Commit changes**
6. Changes go live in ~1 minute!

---

## 💡 Pro Tips

### Tip 1: Remove .html from URLs
Create a file called `404.html` with redirect logic, or organize files in folders:
```
smartkitchenforme-website/
├── index.html
├── share/
│   └── index.html    (this becomes /share/)
```

### Tip 2: Add More Pages
Just create more HTML files:
- `about.html` → smartkitchenforme.com/about.html
- `contact.html` → smartkitchenforme.com/contact.html
- `recipes.html` → smartkitchenforme.com/recipes.html

### Tip 3: Use a Template
GitHub has free website templates at [https://pages.github.com/themes/](https://pages.github.com/themes/)

---

## 🆚 GoDaddy vs GitHub Pages Comparison

| Feature | GoDaddy Free | GoDaddy Premium | GitHub Pages |
|---------|-------------|-----------------|--------------|
| Price | $0 | $12-23/month | **$0** |
| Custom Domain | ❌ Limited | ✅ | ✅ |
| Add Pages | ❌ | ✅ | ✅ Unlimited |
| Custom HTML | ❌ | ✅ | ✅ |
| HTTPS/SSL | ✅ | ✅ | ✅ |
| Ads | ❌ | ❌ | ❌ |
| Storage | Limited | 25-50GB | 1GB (plenty!) |

**Winner: GitHub Pages** 🏆

---

## ❓ Troubleshooting

### Domain not working?
- DNS changes take 15-60 minutes to propagate
- Clear your browser cache
- Try incognito/private window
- Check DNS with: https://dnschecker.org

### 404 Error?
- Make sure file is named exactly `index.html`
- Check GitHub Pages is enabled in Settings
- Verify branch is set to `main`

### HTTPS not working?
- Wait for DNS to fully propagate first
- Then enable "Enforce HTTPS" in GitHub Pages settings

---

## 🎉 Done!

You now have a **FREE professional website** at smartkitchenforme.com!

No monthly fees. No limitations. Full control.

---

## 📞 Need Help?

- GitHub Pages Docs: https://docs.github.com/en/pages
- GitHub Community: https://github.community
