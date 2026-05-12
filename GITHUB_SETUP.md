# GitHub Pages Setup Guide

Follow these steps to deploy the Science Course Planner to GitHub Pages.

## Prerequisites

- GitHub account (free at github.com)
- Git installed on your computer (or use GitHub Desktop)

## Step-by-Step Instructions

### 1. Create a GitHub Repository

**Option A: Using GitHub Website (Easiest)**

1. Go to https://github.com/new
2. Fill in repository details:
   - **Repository name:** `science-course-planner`
   - **Description:** "Interactive tool for high school science course planning"
   - **Public** (so students can access it)
   - ✓ Initialize with README (recommended)
3. Click "Create repository"

**Option B: Fork Existing Repository**

If you have access to a template repository, click the "Fork" button.

### 2. Add Files to Repository

#### Via GitHub Website (No coding needed)

1. Go to your repository
2. Click "Add file" → "Upload files"
3. Upload these files:
   - `index.html` (the main application)
   - `README.md` (documentation)
   - `.gitignore` (optional but recommended)
4. Commit changes with message: "Initial commit: add science planner"

#### Via Command Line (If you know Git)

```bash
# Clone the repository
git clone https://github.com/YOUR-USERNAME/science-course-planner.git
cd science-course-planner

# Copy the files into the directory
# index.html, README.md, .gitignore

# Stage, commit, and push
git add .
git commit -m "Initial commit: add science planner"
git push origin main
```

### 3. Enable GitHub Pages

1. Go to your repository
2. Click **Settings** (top right)
3. In the left sidebar, click **Pages**
4. Under "Build and deployment":
   - **Source:** Select "Deploy from a branch"
   - **Branch:** Select `main`
   - **Folder:** Select `/root` 
5. Click **Save**

You should see a message: "Your site is live at https://YOUR-USERNAME.github.io/science-course-planner/"

*Note: It may take 1-2 minutes for the site to go live.*

### 4. Verify It's Working

1. Wait 1-2 minutes
2. Visit: `https://YOUR-USERNAME.github.io/science-course-planner/`
3. You should see the "Science course planner" landing page

## Making Changes

### To Update the Course Recommendations

1. Go to your repository
2. Click on `index.html`
3. Click the ✏️ (edit) button
4. Find the `courseData` section (around line 50)
5. Make your changes
6. Click "Commit changes..." and add a message
7. Changes will appear on your live site in 30-60 seconds

### To Customize School Name

1. Edit `index.html`
2. Find: `<title>High School Science Course Planner</title>`
3. Change to: `<title>Your School Science Course Planner</title>`
4. Also find the heading text and update it
5. Commit changes

### To Add More Career Paths

1. Edit `index.html`
2. Find the `courseData = {` section
3. Add a new object following the existing format
4. Update the welcome screen button array
5. Commit changes

## Customization Examples

### Change School Name

In `index.html`, find this section:
```html
<title>High School Science Course Planner</title>
```

And in the JavaScript, find:
```javascript
<h1 style={{ fontSize: '28px', fontWeight: '500', marginBottom: '0.5rem', color: 'var(--color-text-primary)' }}>
    Science course planner
</h1>
```

Update both to your school's name.

### Update RG Drage Technical School

Find the text "RG Drage Technical School" in the code and replace with your technical school's name. Update all references.

### Customize Colors

The site uses CSS variables at the top of the file. Change these for your school colors:

```css
--color-background-info: #e6f1fb;      /* Blue */
--color-text-info: #0c447c;            /* Dark blue text */
--color-border-info: #85b7eb;          /* Light blue border */
```

## Sharing with Students

Once live, share this URL with students:
```
https://YOUR-USERNAME.github.io/science-course-planner/
```

### Create a QR Code

Use a free QR code generator (qr-code-generator.com) to create a QR code pointing to your live site. Print it on course selection materials!

### Add to School Website

If your school has a website, add this code to link to the planner:

```html
<a href="https://YOUR-USERNAME.github.io/science-course-planner/" class="button">
    Science Course Planner
</a>
```

Or embed it directly:

```html
<iframe 
    src="https://YOUR-USERNAME.github.io/science-course-planner/" 
    style="width:100%; height:900px; border:none;">
</iframe>
```

## Troubleshooting

### Site not showing up

1. Check that you've enabled GitHub Pages (Settings → Pages)
2. Verify the branch is set to `main`
3. Wait 1-2 minutes for deployment
4. Check the "Actions" tab to see if deployment succeeded

### Old version showing

1. Clear your browser cache (Ctrl+Shift+Del or Cmd+Shift+Del)
2. Try in an incognito/private window
3. GitHub may take 30-60 seconds to update

### File not uploading

1. Make sure you're uploading to the main directory, not a subfolder
2. Keep the filename exactly as: `index.html` (case-sensitive)
3. Try uploading one file at a time

### Changes not appearing

1. Refresh the page (Ctrl+F5 or Cmd+Shift+R)
2. Wait 1-2 minutes for GitHub to deploy
3. Check the "Actions" tab for any deployment errors

## Custom Domain (Optional)

If you want to use a custom domain (like `science-planner.yourschool.edu`):

1. Go to Settings → Pages
2. Under "Custom domain," enter your domain
3. Follow the DNS configuration steps
4. Add a CNAME file if needed

This requires domain ownership and DNS access.

## Next Steps

1. ✓ Customize course pathways for your school
2. ✓ Add your technical school's name
3. ✓ Test on phone and desktop
4. ✓ Share link with guidance counselors and students
5. ✓ Print QR code for course selection materials

## Support

For GitHub Pages specific questions, visit:
https://docs.github.com/en/pages

For customization questions, see README.md in the repository.

---

**Questions?** Check that:
- Your repository is public (Settings → General → Visibility)
- GitHub Pages is enabled (Settings → Pages)
- Files are in the root directory
- index.html is spelled correctly
