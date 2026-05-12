# Science Course Planner

An interactive web-based tool for high school students to explore personalized science course pathways based on their career goals. Perfect for career guidance, course selection meetings, and student planning.

## 🚀 Quick Start

### Option 1: Use on GitHub Pages (Recommended)

1. **Fork or clone this repository**
   ```bash
   git clone https://github.com/yourusername/science-course-planner.git
   cd science-course-planner
   ```

2. **Enable GitHub Pages**
   - Go to repository Settings → Pages
   - Select "Deploy from a branch"
   - Choose `main` branch and `/root` folder
   - Save

3. **Access your site**
   - Your planner will be live at: `https://yourusername.github.io/science-course-planner`

### Option 2: Run Locally

1. **Download or clone the repository**

2. **Open in a browser**
   - Simply open `index.html` in any web browser
   - No server or installation needed

## 📋 Features

- **Career Path Selection** - Students choose between college, trade school, or direct workforce
- **Interest-Based Guidance** - Tailored recommendations based on specific career interests
- **Grade-by-Grade Course Sequencing** - Clear pathway from 9th through 12th grade
- **Priority Indicators** - Essential, strongly recommended, recommended, and optional courses
- **Dark Mode Support** - Automatically adapts to user's system preferences
- **Mobile Responsive** - Works perfectly on phones, tablets, and desktops
- **No Backend Required** - Static HTML file; deploys anywhere

## 🎯 Career Paths Included

### College/University
- Biology & Health Sciences
- Chemistry & Materials
- Physics & Engineering
- Environmental/Earth Science

### Trade School
- Construction & HVAC
- Electrical & Plumbing
- Automotive & Mechanics
- Welding & Manufacturing

### Direct Workforce
- Skilled Trades
- Service & Hospitality
- Military/Public Service
- Entrepreneurship

## 🛠️ Customization Guide

### Edit Course Recommendations

Open `index.html` in a text editor and find the `courseData` object (around line 50). Here's the structure:

```javascript
'biology-health': {
    name: 'Biology & Health Sciences Path',
    description: 'Pre-med, nursing, veterinary, biomedical sciences',
    courses: [
        { grade: 9, course: 'Honors Biology', priority: 'essential', reason: 'Foundation for all health sciences' },
        { grade: 10, course: 'Honors Chem', priority: 'essential', reason: 'Required for pre-med requirements' },
        // Add more courses...
    ],
},
```

**Priority levels:**
- `essential` - Red/orange badge
- `strongly recommended` - Yellow badge
- `recommended` - Green badge
- `optional` - Gray badge

### Add a New Career Path

1. Add the path definition to `courseData`:
   ```javascript
   mynewpath: {
       title: 'My New Path',
       subtitle: 'Brief description',
       interests: [
           { id: 'interest1', label: 'Interest Label', icon: '🔬' },
       ],
       pathways: {
           'interest1': {
               name: 'Interest 1 Path',
               description: 'Longer description',
               courses: [
                   { grade: 9, course: 'Biology', priority: 'essential', reason: 'Why this course' },
               ],
           },
       },
   }
   ```

2. Add to the welcome screen button list (look for the button array in `renderWelcome`)

### Change School Name

1. Edit the `<title>` tag at the top of the file
2. Edit the "Science course planner" heading in the `renderWelcome` function
3. Update any introductory text as needed

### Customize Colors

The site uses CSS variables that automatically support light and dark modes. Edit the `:root` section:

```css
--color-background-info: #e6f1fb;
--color-text-info: #0c447c;
--color-border-info: #85b7eb;
```

## 📱 Sharing with Students

### Method 1: Direct Link
If hosted on GitHub Pages:
```
https://yourusername.github.io/science-course-planner
```

### Method 2: QR Code
Create a QR code pointing to your GitHub Pages link. Print it on course selection materials.

### Method 3: Embed in School Website
Add this to your school's website:
```html
<iframe src="https://yourusername.github.io/science-course-planner" style="width:100%; height:800px; border:none;"></iframe>
```

### Method 4: PDF Print
Students can use "Print to PDF" to save their recommended pathway.

## 🔧 Technical Details

- **Built with:** React 18 (loaded from CDN)
- **Styling:** CSS Variables with light/dark mode support
- **Browser Support:** All modern browsers (Chrome, Firefox, Safari, Edge)
- **File Size:** Single ~50KB HTML file
- **Dependencies:** None (React loaded from CDN)

## 🎨 Customization Examples

### Example 1: Add a Specific Tech School

Find where it says "RG Drage Technical School" in the code and update:
- Change the pathways for students who select that option
- Customize courses specific to your technical program
- Update career descriptions

### Example 2: Change Grade Structure

If your school uses different grade levels:
1. Change `{ grade: 9, ... }` to your actual grade structure
2. Update the `renderWelcome` text to reflect your grade labels

### Example 3: Add More Career Interests

Within each career path (college, tradeschool, workforce), add new interests to the array and corresponding pathways:

```javascript
interests: [
    { id: 'new-interest', label: 'New Interest', icon: '🎯' },
],
pathways: {
    'new-interest': {
        // Define courses here
    },
}
```

## 📊 Student Experience Flow

1. Student arrives at the planner
2. Selects their post-graduation goal (college, trade school, or workforce)
3. Selects their specific career interest within that path
4. Receives personalized course recommendations
5. Can explore other pathways or print their recommendations

## 🚀 Deployment Options

### GitHub Pages (Free)
- Most recommended for educators
- Free hosting
- Easy updates via git push

### School Website
- Embed as an iframe
- Host alongside other career resources

### Netlify (Free)
- Drag and drop deployment
- Free tier includes custom domain

### Your Own Server
- Download the HTML file
- Upload to your web server
- No special requirements

## 📝 License

This tool is open source and free for educational use. Customize it for your school!

## ❓ FAQ

**Q: Can I modify the course requirements for different tracks?**
A: Yes! All pathways are fully customizable. Edit the course arrays in the `courseData` object.

**Q: Can students save their recommendations?**
A: Students can print or take a screenshot. For persistent saving, you'd need a backend (optional enhancement).

**Q: How do I update the tool?**
A: Edit `index.html` and commit changes to GitHub. If on GitHub Pages, changes will deploy automatically.

**Q: Can I add more career paths?**
A: Yes! Add new entries to `courseData` and update the welcome screen buttons.

**Q: Does it work offline?**
A: Yes, the tool works locally. However, React is loaded from CDN, so internet is required on first load.

## 🤝 Support & Questions

For questions about customizing this tool, consult the customization guide above or create an issue in the repository.

---

**Created for:** High school course planning and career guidance
**Customizable for:** Any school with any course structure
**Perfect for:** Course selection meetings, college prep, guidance counseling
