# CoachApp OTA Installation Setup

This guide will help you set up Over-The-Air (OTA) installation for CoachApp via GitHub.

## Files Included

- `CoachApp.ipa` - The iOS app file
- `manifest.plist` - Installation manifest (already configured)
- `index.html` - Installation page with download link
- `DistributionSummary.plist` - App distribution details
- `ExportOptions.plist` - Export configuration

## GitHub Setup Instructions

### Step 1: Create/Use GitHub Repository

1. Go to your GitHub repository: `https://github.com/ZaidAqrawi/fittest`
2. Make sure the repository is public (required for raw.githubusercontent.com to work)

### Step 2: Upload Files to GitHub

Upload the following files to the `main` branch of your repository:

1. **CoachApp.ipa** - Upload to the root of the repository
2. **manifest.plist** - Upload to the root of the repository
3. **index.html** - Upload to the root of the repository (optional, for a nice installation page)
4. **image57.png** - App icon (57x57 pixels) - if you have it
5. **image512.png** - App icon (512x512 pixels) - if you have it

### Step 3: Verify File URLs

After uploading, verify that these URLs work (they should download the files directly):

- ✅ `https://raw.githubusercontent.com/ZaidAqrawi/fittest/main/CoachApp.ipa`
- ✅ `https://raw.githubusercontent.com/ZaidAqrawi/fittest/main/manifest.plist`
- ✅ `https://raw.githubusercontent.com/ZaidAqrawi/fittest/main/index.html`
- ✅ `https://raw.githubusercontent.com/ZaidAqrawi/fittest/main/image57.png` (if uploaded)
- ✅ `https://raw.githubusercontent.com/ZaidAqrawi/fittest/main/image512.png` (if uploaded)

### Step 4: Access the Installation Page

Once files are uploaded, you can access the installation page at:

```
https://raw.githubusercontent.com/ZaidAqrawi/fittest/main/index.html
```

Or better yet, enable GitHub Pages:

1. Go to repository Settings → Pages
2. Select source: "Deploy from a branch"
3. Select branch: "main" and folder: "/ (root)"
4. Save

Then access via:
```
https://zaidaqrawi.github.io/fittest/
```

## Direct Installation Link

Users can install directly using this link (works on iOS devices):

```
itms-services://?action=download-manifest&url=https://raw.githubusercontent.com/ZaidAqrawi/fittest/main/manifest.plist
```

## Important Notes

1. **Repository must be public** - Private repositories won't work with raw.githubusercontent.com
2. **File names must match** - The manifest.plist references `CoachApp.ipa`, so make sure the file is named exactly that
3. **HTTPS required** - iOS requires HTTPS for OTA installations
4. **Certificate trust** - Users will need to trust the developer certificate in Settings after installation
5. **Ad-hoc distribution** - This app is configured for ad-hoc distribution, so only devices registered in the provisioning profile can install it

## Testing

1. Open the installation link on an iOS device
2. Tap "Install" when prompted
3. Go to Settings → General → VPN & Device Management
4. Trust the developer certificate
5. Launch the app from the home screen

## Troubleshooting

- **"Unable to Download App"** - Check that all file URLs in manifest.plist are accessible
- **"Cannot connect to [server]"** - Verify the repository is public
- **Installation fails** - Ensure the device UDID is registered in the provisioning profile
- **Certificate error** - User needs to trust the developer in Settings

