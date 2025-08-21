# How to Change Favicon.ico in Your Jekyll Chirpy Wiki

This guide explains how to change the favicon (the small icon displayed in browser tabs) for your Jekyll site using the Chirpy theme.

## Overview

Your site already has the proper directory structure set up. Favicons are stored in `/assets/img/favicons/` and the Chirpy theme automatically detects and uses them.

## Quick Steps

### 1. Prepare Your Icon Image
- Start with a high-resolution square image (at least 512x512 pixels)
- PNG format with transparent background works best
- Keep the design simple as it will be displayed at very small sizes

### 2. Generate Favicon Files
You need multiple sizes and formats for different browsers and devices:

**Required files for modern browsers:**
- `favicon.ico` (classic format, 32x32 or 16x16)
- `favicon-16x16.png`
- `favicon-32x32.png` 
- `android-chrome-192x192.png`
- `android-chrome-512x512.png`
- `apple-touch-icon.png` (180x180)
- `mstile-150x150.png` (for Windows tiles)
- `site.webmanifest` (web app manifest)

### 3. Use Online Favicon Generators (Recommended)

**Option A: RealFaviconGenerator (Most Comprehensive)**
1. Go to https://realfavicongenerator.net/
2. Upload your source image (512x512 or larger)
3. Customize settings for different platforms
4. Download the generated files
5. Extract and copy all files to `/assets/img/favicons/`

**Option B: Favicon.io (Simple)**
1. Go to https://favicon.io/
2. Upload your image or use their text/emoji generators
3. Download the generated zip file
4. Copy all PNG and ICO files to `/assets/img/favicons/`

### 4. Manual Placement
Copy all the generated files to your repository's favicon directory:
```bash
/assets/img/favicons/
├── favicon.ico
├── favicon-16x16.png
├── favicon-32x32.png
├── android-chrome-192x192.png
├── android-chrome-512x512.png
├── apple-touch-icon.png
├── mstile-150x150.png
└── site.webmanifest
```

### 5. Verify the Installation

1. **Push your changes to GitHub**
2. **Wait for GitHub Pages to rebuild** (usually 1-2 minutes)
3. **Test in multiple browsers:**
   - Clear your browser cache (Ctrl+F5 or Cmd+Shift+R)
   - Visit your site and check the favicon in the browser tab
   - Test on mobile devices for touch icons

## Advanced: Using Command Line Tools

If you prefer command-line tools, you can use ImageMagick to generate different sizes:

```bash
# Install ImageMagick (if not available)
# Ubuntu/Debian: sudo apt-get install imagemagick
# macOS: brew install imagemagick

# Generate different sizes from a source image
convert source-icon.png -resize 16x16 assets/img/favicons/favicon-16x16.png
convert source-icon.png -resize 32x32 assets/img/favicons/favicon-32x32.png
convert source-icon.png -resize 192x192 assets/img/favicons/android-chrome-192x192.png
convert source-icon.png -resize 512x512 assets/img/favicons/android-chrome-512x512.png
convert source-icon.png -resize 180x180 assets/img/favicons/apple-touch-icon.png
convert source-icon.png -resize 150x150 assets/img/favicons/mstile-150x150.png

# Create ICO file (multi-size)
convert source-icon.png -resize 32x32 -resize 16x16 assets/img/favicons/favicon.ico
```

## Troubleshooting

### Favicon Not Showing
1. **Clear browser cache**: Hard refresh with Ctrl+F5 (Windows) or Cmd+Shift+R (Mac)
2. **Check file paths**: Ensure files are in `/assets/img/favicons/` exactly
3. **Wait for deployment**: GitHub Pages takes 1-2 minutes to update
4. **Try incognito/private browsing**: To bypass cache completely

### Files Not Found
- Verify the directory path is exactly `/assets/img/favicons/` (note the 's' in assets)
- Check that files are committed and pushed to your repository
- Ensure file names match exactly (case-sensitive)

### Quality Issues
- Use PNG format for better quality at small sizes
- Keep designs simple - complex images don't work well at 16x16 pixels
- Test your favicon at actual size before deploying

## Current Status

✅ Directory structure is set up: `/assets/img/favicons/`
✅ Sample files created for demonstration
⚠️  PNG files are placeholders - replace with real images
✅ Web manifest configured for PWA support

## Next Steps for You

1. Create or obtain your desired icon image (512x512 PNG recommended)
2. Use RealFaviconGenerator.net to create all required formats
3. Replace the placeholder files in `/assets/img/favicons/`
4. Commit and push your changes
5. Test the new favicon in your browser

The Chirpy theme will automatically detect and use your favicon files once they're in the correct location!