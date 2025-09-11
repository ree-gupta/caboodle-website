# Cake Caboodle Website - Editing Guide

This is your complete guide to editing and customizing your Cake Caboodle website.

## 🚀 Quick Start

1. **Start development server**: `hugo server`
2. **View site**: Open http://localhost:1313 in browser
3. **Make changes**: Edit files as described below
4. **Deploy**: Changes auto-deploy when pushed to main branch

## 📝 Common Edits

### 🖼️ Change Logo
**File**: `assets/images/logo.png`
- Replace this file with your new logo (keep same filename)
- **OR** add new logo and update `config.yaml` line 17: `logo: "images/new-logo.png"`
- Logo size controlled in `layouts/index.html` line 59: `width: 240px`

### 📍 Update Store Information
**File**: `config.yaml`
- **Address** (line 30): Update store location
- **Store Hours**: Edit in `layouts/index.html` line 280 (currently "11 AM - 11 PM")
- **Email** (line 32): Change contact email
- **WhatsApp** (line 60): Update phone number

### 🔗 Update Links
**File**: `layouts/index.html` (lines 298-338)
- **Google Directions**: Line 298 - Update maps URL
- **Google Menu**: Line 304 - Update Google Business URL  
- **Zomato**: Line 310 - Update Zomato store link
- **Swiggy**: Line 316 - Update Swiggy store link
- **Instagram**: Line 322 - Update in `config.yaml` line 25
- **WhatsApp**: Line 328 - Update phone number and message

### 🎨 Change Colors
**File**: `layouts/index.html` (lines 18-23)
```css
--primary-pink: #9e5868;      /* Main pink color */
--secondary-brown: #af7124;   /* Brown accent */
--light-pink: #eee3e8;       /* Background pink */
```

### ✍️ Update Text Content
**File**: `layouts/index.html`
- **Main Title** (line 271): "Cake Caboodle"
- **Tagline** (line 272): "Cakes For All Occasions"
- **Service Description** (lines 273-274): Update emoji descriptions
- **About Section** (lines 342-359): Edit Prashansha's story
- **Footer Message** (line 362): Change closing message

### 📱 Social Media
**File**: `config.yaml`
- **Instagram** (line 25): Update handle
- **Facebook** (line 26): Update page URL
- **WhatsApp** (line 60): Update number

## 🛠️ Advanced Customizations

### Button Styling
**File**: `layouts/index.html` (lines 130-200)
- Each button has its own color class (location-btn, zomato-btn, etc.)
- Change `background: linear-gradient(...)` for button colors

### Typography
**File**: `layouts/index.html`
- **Main font**: Line 12-13 (Google Fonts import)
- **Title font**: Playfair Display
- **Body font**: Inter
- **Font sizes**: Lines 64-90 (CSS classes)

### Layout Spacing
**File**: `layouts/index.html`
- **Container padding**: Line 51 (`padding: 60px 40px`)
- **Button spacing**: Line 126 (`gap: 16px`)
- **Section margins**: Line 163 (`margin: 32px 0`)

## 📂 File Structure

```
caboodle-website/
├── config.yaml              # Site settings, social links, contact info
├── layouts/index.html        # Main page design and content
├── assets/images/logo.png    # Your logo file
├── data/home/               # Not used in current design
├── content/                 # Not used in current design  
├── static/                  # Additional static files
└── public/                  # Generated site (don't edit)
```

## 🔄 Development Workflow

1. **Make changes** to files
2. **Save files** - Hugo auto-reloads
3. **Check browser** to see changes
4. **If changes don't appear**: Restart server with `hugo server --disableFastRender`

## 🚢 Deployment

- **Auto-deploy**: Pushes to `main` branch deploy automatically via GitHub Actions
- **Custom domain**: Set in CNAME file (currently: cakecaboodle.in)
- **Build command**: `hugo --minify` (done automatically)

## 💡 Tips

- **Test locally first**: Always preview changes at http://localhost:1313
- **Mobile-friendly**: Design is responsive, test on mobile too
- **Brand colors**: Stick to your color palette (#9e5868, #af7124, #eee3e8)
- **Image optimization**: Hugo automatically optimizes images
- **Backup**: Keep backups of your customizations before major changes

## 🆘 Troubleshooting

- **Server not starting**: Run `hugo server --disableFastRender`
- **Changes not showing**: Hard refresh browser (Ctrl+F5 / Cmd+Shift+R)
- **Logo not updating**: Clear browser cache, restart server
- **Build errors**: Check Hugo version with `hugo version`

---

**Need help?** Check the CLAUDE.md file for technical details or create an issue in the GitHub repository.