# Haize Blog

Your Hugo blog with Sveltia CMS, ready for Cloudflare Pages.

---

## Setup Instructions

### Step 1: Create GitHub Repository

1. Go to [github.com](https://github.com) and log in
2. Click the **+** icon (top right) → **New repository**
3. Name it `haize-blog`
4. Keep it **Public** (required for Sveltia CMS)
5. Click **Create repository**

### Step 2: Upload These Files

**Option A: Using GitHub's web interface**
1. On your new repository page, click **uploading an existing file**
2. Drag and drop all the files from this folder
3. Click **Commit changes**

**Option B: Using Git (if you have it installed)**
```bash
cd haize-blog
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/YOUR_USERNAME/haize-blog.git
git push -u origin main
```

### Step 3: Update CMS Config

1. In GitHub, open `static/admin/config.yml`
2. Click the pencil icon to edit
3. Replace `YOUR_USERNAME` with your actual GitHub username:
   ```yaml
   backend:
     name: github
     repo: YOUR_USERNAME/haize-blog
   ```
4. Click **Commit changes**

### Step 4: Connect to Cloudflare Pages

1. Go to [Cloudflare Dashboard](https://dash.cloudflare.com)
2. Click **Workers & Pages** → **Create application** → **Pages**
3. Click **Connect to Git**
4. Select your `haize-blog` repository
5. Configure build settings:
   - **Framework preset**: Hugo
   - **Build command**: `hugo`
   - **Build output directory**: `public`
   - **Environment variable**: Add `HUGO_VERSION` = `0.139.0`
6. Click **Save and Deploy**

### Step 5: Set Up Your Domain

1. Once deployed, go to your Pages project in Cloudflare
2. Click **Custom domains** → **Set up a custom domain**
3. Enter `blog.haize-realty.com` (or your preferred subdomain)
4. Follow the DNS instructions

### Step 6: Enable Sveltia CMS

1. Go to `blog.haize-realty.com/admin`
2. Click **Login with GitHub**
3. Authorize the app
4. You're in! Start writing posts.

---

## How to Use

### Writing Posts

1. Go to `yourblog.com/admin`
2. Click **Blog Posts** → **New Blog Post**
3. Write your post
4. Click **Publish**

### Editing Settings

In the CMS, go to **Site Settings** to change:
- Page title ("Journal")
- Page subtitle
- Featured label
- Author name & bio
- Extra sidebar text
- Toggle banner, newsletter, search, etc.

### Changing Design

Edit these files in GitHub (or ask me for help):
- `static/css/style.css` - All styling
- `layouts/partials/sidebar.html` - Sidebar layout
- `layouts/index.html` - Home page layout
- `layouts/_default/single.html` - Post page layout

---

## File Structure

```
haize-blog/
├── config.toml              # Hugo settings
├── content/
│   └── posts/               # Your blog posts (Markdown)
├── data/                    # CMS-editable settings
├── layouts/
│   ├── _default/
│   │   ├── baseof.html      # Base template
│   │   └── single.html      # Single post template
│   ├── partials/
│   │   └── sidebar.html     # Sidebar component
│   └── index.html           # Home page
├── static/
│   ├── admin/
│   │   ├── config.yml       # CMS configuration
│   │   └── index.html       # CMS page
│   ├── css/
│   │   └── style.css        # All styling
│   └── images/              # Your images
└── archetypes/
    └── posts.md             # Template for new posts
```

---

## Need Help?

If you need design changes or have issues, the files are just HTML/CSS in your GitHub repository. Same workflow as your main website.
