# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.3.0] - 2025-12-21

### Added
- **Live Screen Color Picker**: Pick colors from anywhere on screen (including Visio) with real-time preview tooltip
- **One-Click Import Colors**: Import color palettes from comma-separated HEX values (e.g., `#237B9F, #71BFB2, #AD0B08`)
- **Group Reorder**: Move palette groups up/down with dedicated buttons

### Changed
- **High DPI Support**: Palette Manager dialog now properly scales on 100%/125%/150%/200% display settings
- **Improved Layout**: All controls use flexible layout panels (TableLayoutPanel/FlowLayoutPanel) to prevent clipping
- **Better Focus Handling**: Dialog uses Visio window as owner for consistent z-order
- **Group Name Auto-Save**: Editing group name now auto-saves when focus leaves the input field
- **Install Script**: Now prioritizes Release builds (removed Debug fallback)

### Fixed
- Controls being clipped on high DPI displays
- Screen color picker pushing Visio window to background
- Group name changes not persisting when switching between groups

## [1.2.0] - 2025

### Added
- **Palette Feature**: Apply colors to selected shapes with one click
- **Palette Manager**: Customize up to 6 groups of colors
- PNG, JPEG, EMF, SVG format export support
- Batch export feature (export each shape to a separate file)
- Copy to clipboard option after export
- Global keyboard shortcuts support (optional feature)
- Shortcut configuration dialog

### Changed
- Improved UI layout
- Better error handling

## [1.1.0] - 2025

### Added
- "Repeat Export" feature - one-click overwrite of last exported file
- Improved UI layout

## [1.0.0] - 2025

### Added
- Initial release
- TIFF export with LZW compression
- PDF export (requires ImageMagick)
- Quick export feature with default settings
- Settings persistence

