# Customization Guide - Quick Reference

This guide shows how to make common customizations without diving deep into the code.

## 1. Change Your School Name

**Location in file:** Near the top and middle of the JavaScript

**Find this:**
```html
<title>High School Science Course Planner</title>
```

**Change to:**
```html
<title>Lincoln High School Science Course Planner</title>
```

**Also find this in the JavaScript:**
```javascript
<h1 style={{ fontSize: '28px', fontWeight: '500', marginBottom: '0.5rem', color: 'var(--color-text-primary)' }}>
    Science course planner
</h1>
```

**Change to:**
```javascript
<h1 style={{ fontSize: '28px', fontWeight: '500', marginBottom: '0.5rem', color: 'var(--color-text-primary)' }}>
    Lincoln High School science planner
</h1>
```

## 2. Update RG Drage Technical School Name

**Find:** Search for "RG Drage" in the file (appears multiple times)

**Replace all instances with your actual technical school name**

## 3. Add or Change a Course

**Find the section that looks like:**
```javascript
courses: [
    { grade: 9, course: 'Honors Biology', priority: 'essential', reason: 'Foundation for all health sciences' },
    { grade: 10, course: 'Honors Chem', priority: 'essential', reason: 'Required for pre-med requirements' },
]
```

**To add a new course:**
```javascript
courses: [
    { grade: 9, course: 'Honors Biology', priority: 'essential', reason: 'Foundation for all health sciences' },
    { grade: 10, course: 'Honors Chem', priority: 'essential', reason: 'Required for pre-med requirements' },
    { grade: 11, course: 'AP Biology', priority: 'recommended', reason: 'Strengthens medical school applications' },  // <- NEW COURSE
]
```

**Priority options:**
- `'essential'` - Critical for this path (blue badge)
- `'strongly recommended'` - Very important (orange badge)
- `'recommended'` - Good to have (green badge)
- `'optional'` - Elective (gray badge)

## 4. Change the Welcome Screen Text

**Find:**
```javascript
<p style={{ fontSize: '16px', color: 'var(--color-text-secondary)', lineHeight: '1.6', marginBottom: '0.5rem' }}>
    Let's find your best path through high school science
</p>
```

**Change the text between the `<p>` tags to whatever you want**

## 5. Add a New Career Interest

### Step 1: Add to the interests array

Find your career path (like `'college':`) and in the `interests:` array, add:

```javascript
interests: [
    { id: 'biology-health', label: 'Biology & Health Sciences', icon: '🔬' },
    { id: 'chemistry', label: 'Chemistry & Materials', icon: '⚗️' },
    { id: 'data-science', label: 'Data Science & Computing', icon: '💻' },  // <- NEW
],
```

### Step 2: Add the pathway

In the same career path, in the `pathways:` object, add:

```javascript
'data-science': {
    name: 'Data Science & Computing Path',
    description: 'Data science, computer science, cybersecurity, AI',
    courses: [
        { grade: 9, course: 'Biology', priority: 'recommended', reason: 'Complete requirements' },
        { grade: 10, course: 'Regular Chem', priority: 'recommended', reason: 'Science literacy' },
        { grade: 11, course: 'Physics', priority: 'recommended', reason: 'Computational thinking' },
        { grade: 12, course: 'Any science', priority: 'optional', reason: 'Continue science track' },
    ],
},
```

Done! The new interest will appear in the selection screen.

## 6. Change Colors for Dark Mode Support

At the very top of the file, find the `:root` CSS variables section:

```css
:root {
    --color-background-info: #e6f1fb;
    --color-text-info: #0c447c;
    --color-border-info: #85b7eb;
    /* etc */
}
```

**Light mode colors (default):**
- Light blue for info: `#e6f1fb`
- Dark blue text: `#0c447c`
- Blue border: `#85b7eb`

**Dark mode colors** (in `@media (prefers-color-scheme: dark)` block):
- Dark blue background: `#042c53`
- Light blue text: `#85b7eb`
- Medium blue border: `#185fa5`

You can change these, but keep them consistent between light and dark mode!

**Color scheme examples:**
- School colors blue/gold? Use blue for info and gold for success
- School colors red/white? Use red for warning and white text
- Neutral school? Keep the defaults or use green/teal

## 7. Update the "Pro Tip" Message

**Find:**
```javascript
<div style={{ fontSize: '13px', color: 'var(--color-text-secondary)', marginBottom: '0.5rem' }}>
    💡 Pro tip
</div>
<p style={{ fontSize: '14px', color: 'var(--color-text-primary)', margin: 0, lineHeight: '1.6' }}>
    Talk with your guidance counselor about your specific goals. They can help you customize this plan based on your strengths, interests, and college/career requirements.
</p>
```

**Change the message** between the `<p>` tags to anything you want

## 8. Hide or Rename Career Paths

**To remove a career path entirely:**

Find the welcome screen button array:
```javascript
[
    { id: 'college', title: '4-Year College', desc: 'University or bachelor degree', icon: '🎓' },
    { id: 'tradeschool', title: 'Trade School', desc: 'Technical certification', icon: '⚙️' },
    { id: 'workforce', title: 'Direct Workforce', desc: 'Enter job market', icon: '💼' },
].map(path => (
```

**To change just one:**
```javascript
{ id: 'college', title: 'University or College', desc: 'Bachelor degree path', icon: '🎓' },
```

**To remove one, delete the entire line:**
```javascript
{ id: 'tradeschool', title: 'Trade School', desc: 'Technical certification', icon: '⚙️' },
```

## 9. Change Button Icons

Find where career interests are defined:

```javascript
interests: [
    { id: 'biology-health', label: 'Biology & Health Sciences', icon: '🔬' },
    { id: 'chemistry', label: 'Chemistry & Materials', icon: '⚗️' },
],
```

Change the emoji to any icon you want:
```javascript
{ id: 'biology-health', label: 'Biology & Health Sciences', icon: '🧬' },  // DNA helix
{ id: 'chemistry', label: 'Chemistry & Materials', icon: '🧪' },  // Test tube
```

**Popular icon emoji:**
- 🔬 Microscope
- 🧬 DNA
- ⚗️ Alembic/Flask
- ⚙️ Gear
- 🚀 Rocket
- 💻 Laptop
- 🔧 Wrench
- ⚡ Lightning bolt
- 🌍 Earth
- 💡 Lightbulb

## 10. Reorder Pathways

The order courses appear in recommendations is based on how they're listed in the `courses:` array. Just rearrange them:

```javascript
// Original order:
courses: [
    { grade: 9, course: 'Honors Biology', ... },
    { grade: 10, course: 'Honors Chem', ... },
    { grade: 11, course: 'Honors Chem 2', ... },
]

// New order (if you want):
courses: [
    { grade: 9, course: 'Honors Biology', ... },
    { grade: 11, course: 'Honors Chem 2', ... },
    { grade: 10, course: 'Honors Chem', ... },
]
```

## Common Mistakes to Avoid

1. **Missing commas** - Each item needs a comma after it (except the last one)
   ```javascript
   // ✗ Wrong
   { id: 'bio', label: 'Biology' }
   { id: 'chem', label: 'Chemistry' }
   
   // ✓ Correct
   { id: 'bio', label: 'Biology' },
   { id: 'chem', label: 'Chemistry' }
   ```

2. **Mismatched quotes** - Use either single `'` or double `"`, but not mixed
   ```javascript
   // ✗ Wrong
   label: "Biology' 
   
   // ✓ Correct
   label: 'Biology'
   ```

3. **Forgetting closing braces** - Check that every `{` has a matching `}`

4. **Changing course names without updating pathways** - If you change "Honors Chem" to "Honors Chemistry," update ALL occurrences

5. **Using special characters without escaping** - If you need quotes in text, escape them:
   ```javascript
   reason: 'Students call this "the hardest course"'  // Use single quotes outside
   ```

## Testing Your Changes

1. Open `index.html` in a browser
2. Click through all the pathways
3. Check that:
   - All text displays correctly
   - All buttons work
   - Colors look good
   - No error messages in console (F12 → Console tab)

## Rolling Back Mistakes

If something breaks:

1. **On GitHub:** Click on `index.html` → History → Click the ✓ before your change → Click "Revert"
2. **Locally:** Use Git to revert: `git revert [commit-hash]`
3. **Quick fix:** Undo your last edit by pressing Ctrl+Z in the editor

## Need Help?

- **Syntax error?** Check for missing commas or mismatched quotes
- **Course not showing?** Verify it's in BOTH the `interests` array AND the `pathways` object
- **Page looks weird?** Clear your browser cache (Ctrl+Shift+Del)
- **Changes not appearing?** Wait 1-2 minutes for GitHub to deploy, then refresh (Ctrl+F5)

---

**Remember:** Every change gets a commit message so you can track what you've modified. Great for explaining to your IT department what you've customized!
