# Visio2Img

A Microsoft Visio add-in for exporting selected shapes to high-quality images.

## Why This Add-in?

Exporting images from Visio has always been a frustrating experience:

- Every export requires tedious repetitive steps: "Select folder → Enter filename → Choose format"
- After modifying a shape, overwriting the original file means going through the entire process again
- Visio doesn't support direct PDF export
- Batch exporting multiple shapes requires manual operation one by one

As someone who frequently (well, not that frequently) inserts Visio diagrams into academic papers, the author was deeply frustrated by these issues and had long wanted to develop an add-in to solve them. Unfortunately, lacking C# programming skills made this idea impossible to realize for years. With the recent rise of AI coding assistants, this long-held dream finally became reality. That's how **Visio2Img** was born — making image export simple and efficient.

## Features

- ⚡ **Quick Export**: One-click export with default settings — say goodbye to repetitive operations
- 🔄 **Repeat Export**: One-click overwrite of last exported file — no need to reselect path after modifications
- 📦 **Batch Export**: Export multiple selected shapes as individual files
- 🖼️ **Multi-format Export**: TIFF, PNG, JPEG, EMF, SVG, **PDF**
- 📋 **Copy to Clipboard**: Optionally copy exported image to clipboard
- 🎯 **Selection Export**: Export only selected shapes with automatic boundary cropping
- ⌨️ **Keyboard Shortcuts**: Configurable global shortcuts (optional)
- 💾 **Settings Persistence**: Remember your export preferences

### Supported Export Formats

| Format | Extension | Type | Features | Best For |
|--------|-----------|------|----------|----------|
| TIFF | `.tif` | Raster | LZW lossless compression, high quality | Print, archive, academic papers |
| PNG | `.png` | Raster | Lossless, supports transparency | Web, presentations |
| JPEG | `.jpg` | Raster | Lossy compression, small file size | Photos, web |
| EMF | `.emf` | Vector | Windows vector format, lossless scaling | Office documents, Word |
| SVG | `.svg` | Vector | Open vector format, editable | Web, graphic design |
| PDF | `.pdf` | Vector | Universal document format (requires ImageMagick) | Print, sharing, archive |

## System Requirements

### Required
- Windows 10/11 64-bit
- Microsoft Visio 2016 or later (64-bit)
- .NET Framework 4.8
- .NET SDK 6.0 or later (for building)

### Optional
- [ImageMagick](https://imagemagick.org/script/download.php) (required for PDF export)
  - During installation, check "Add application directory to your system path"

## Installation

### 1. Check Environment
```batch
check_environment.bat
```
Run this script to verify all dependencies are installed.

### 2. Build Project
```batch
dotnet build --configuration Release
```

### 3. Install Add-in
Run as Administrator:
```batch
install.bat
```

### 4. Verify Installation
Start Visio. You should see a **Visio2Img** tab in the ribbon.

## Usage

### Export to TIFF
1. Select shapes in Visio
2. Click **Visio2Img** tab → **Export TIFF...**
3. Configure export settings:
   - **DPI**: Resolution (default 1000)
   - **Compression**: LZW lossless compression (recommended)
4. Choose save location and confirm

### Export to PDF
1. Select shapes in Visio
2. Click **Visio2Img** tab → **Export PDF...**
3. Configure settings and confirm

> ⚠️ PDF export requires ImageMagick

### Quick Export
- **Quick Export TIFF**: One-click export with default settings
- **Quick Export PDF**: One-click export with default settings

Quick export automatically creates a timestamped file in the Visio document's folder.

### Keyboard Shortcuts
1. Click **Settings** button
2. Check **Enable shortcuts** checkbox
3. Click the shortcut input field and press your desired key combination
4. Click **Save**

Default shortcuts (must be enabled in settings first):
| Function | Default Shortcut |
|----------|-----------------|
| Export TIFF | Ctrl+Shift+T |
| Export PDF | Ctrl+Shift+P |
| Repeat Export | Ctrl+Shift+R |
| Batch Export | Ctrl+Shift+B |

> ⚠️ Shortcuts are disabled by default; enable in settings

## Uninstall

Run as Administrator:
```batch
uninstall.bat
```

## Project Structure

```
Visio2Img/
├── Visio2Img.csproj      # Project file
├── Connect.cs            # COM add-in entry point
├── RibbonController.cs   # Ribbon button handlers
├── ImageExporter.cs      # Image export core logic
├── ExportDialog.cs       # Export dialog
├── ExportSettings.cs     # Settings persistence
├── SettingsDialog.cs     # Settings dialog
├── Program.cs            # Standalone test entry
├── install.bat           # Install script
├── uninstall.bat         # Uninstall script
├── check_environment.bat # Environment check script
└── README.md             # Documentation
```

## Technical Details

- **Framework**: .NET Framework 4.8
- **Type**: COM Add-in (IDTExtensibility2 + IRibbonExtensibility)
- **Image Processing**: System.Drawing.Imaging
- **PDF Conversion**: ImageMagick CLI

## Development

### Build Requirements
Building this project requires **Microsoft Visio** to be installed on the build machine, as the project depends on Visio Interop assemblies (COM type libraries).

If Visio is not installed, you can create a `lib` folder and place the following DLL files in it:
- `Microsoft.Office.Interop.Visio.dll`
- `Office.dll`
- `Extensibility.dll`

These files can be copied from a machine with Visio installed.

### Build Command

> ⚠️ **Important**: Close Visio before building, otherwise the build may fail due to DLL being locked.

```powershell
dotnet build Visio2Img.csproj --configuration Release
```

### Debug
1. Build with Debug configuration
2. Run `install.bat` to register debug version
3. Attach to VISIO.EXE process in Visual Studio

## Troubleshooting

### Q: Add-in tab doesn't appear?
A:
1. Ensure `install.bat` was run as Administrator
2. Verify Visio is 64-bit version
3. Check Visio Options → Add-ins → COM Add-ins

### Q: PDF export fails?
A:
1. Ensure ImageMagick is installed
2. Ensure ImageMagick is in system PATH
3. Run `check_environment.bat` to verify

### Q: Exported image is blurry?
A: Try increasing DPI value. For print quality, use 300 DPI or higher.

## License

MIT License

> **Note**: When redistributing or creating derivative works, please include a link to the original project.

## Author

**PandaK404**

If you find this add-in helpful, please give it a ⭐ Star!

