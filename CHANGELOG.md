
# Changelog
All notable changes to Specula HUD are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project loosely follows [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.5.0-preview] – Playable Preview / Foundation Update - 2026-01-25

> ⚠️ This is a **Playable Preview** build.
> This update focuses primarily on internal structure, utilities, and future-facing systems.
> Some features are unfinished or include placeholder logic.

### Added
- Added **Pause Menu Preferences** entry.
  - Opens the in-game **Options menu**, allowing access to:
    - Controls
    - Preferences
    - Others
  - Fully functional, but does **not** redirect to the custom Preferences menu.

- Added a shared **UI utility layer** to support future features and reduce duplicated logic:
  - Color utilities
  - Gradient color utilities
  - Font loading utilities
  - General value helper utilities

### Changed
- Refactored core HUD modules to rely on shared utilities instead of embedded logic:
  - Judgement Counter
  - Score Bar
  - Song Intro
  - Watermark

- Reorganized the script folder structure for improved readability and maintainability.
- Song Intro logic has been expanded internally, but behavior remains mostly unchanged in this preview.

### Refactored
- Extracted color, font, gradient, and value-handling logic from feature modules into reusable scripted utilities.
- Reduced coupling between HUD components to make future updates easier to implement.
- Cleaned up preference access patterns in preparation for future systems.

### Removed
- Removed basic logging utilities.
  - Logging triggered repeatedly when certain HUD elements (e.g. Judgement Counter) were disabled.
  - Will be reintroduced later in a more controlled form.

### Known Issues
- Song Intro transition helpers exist but are **not functional** in this preview.
- Some Song Intro options are placeholders for future updates.
- Background color systems are not finalized.
- Utility modules may change before the final 0.5.0 release.

---

## [0.4.5] – New Year Release!! - 2025-12-30
> New Year Release!!!

### Added
- New **Song Intro** settings menu to control intro behavior and fade.
- **Score Bar Bop** effect with an intensity slider.
- More **background colors** for HUD elements.
- More **font choices** for Judgment Counter and Score Bar.

### Improved
- Improved the **Preferences** menu layout with clearer section headers.
- More stable **saving** so settings persist reliably.

### Tweaks
- Fixed a font rendering issue on the Score Bar.
- Tweaked default opacity and corner-radius values for a nicer appearance.

### Removed
- Removed the ranking badge because it interfered with the Score Bar Bop effect.

---

## [0.4.0] - 2025-12-17

### Added
- Custom fonts support for HUD elements (Score Bar & Judgment Counter).
- Five new font options available in options.
- Judgment Counter positioning (Left / Right).
- Rounded corner options for the Judgment Counter.
- Five new color presets: **Cyan, Magenta, Lime, Teal, Violet**.

### Feature
- Score Bar now displays Score, Combo / MaxCombo, Accuracy, Rank, and Health.
- Score Bar health now interpolates (lerp) for smoother updates.

### Adjustment
- Score Bar colors updated to match rank badges in Freeplay.

### Refactor
- Reworked preference reading to support new keys (font, radius, position, textsize).
- Consolidated rounded-background drawing and safe-destroy helpers.
- Cleaned up Judgment Counter and Score Bar update logic.

### Optimization
- Fewer allocations and redraws during gameplay (checks values before updating).
- Safer cleanup and more stable refresh between states.

### Improvement
- Improved font loading with graceful fallback to defaults.
- Reduced unnecessary HUD redraws via broader caching (prev* checks).
- More defensive preference reading to avoid invalid values mid-song.

---

## [0.3.5] – BETA - 2025-12-10

### Tweaks
- Tweaked score text formatting for consistency.
- Adjusted UI size to be smaller and less intrusive.

### Bugfixes
- Fixed font issues.
- Fixed score text not appearing when the player disables the score bar.

### Added
- Added 5 new color options (bringing total to 10).
- Added new intro text lines for fun.
- Added **watermark system** with customizable position and proper save data support.

### Overhaul / Refactor
- Major rewrite of the accuracy system.
- Watermark system introduced and integrated with save data.
- Cleaned up code structure and improved font system using custom font loading.

### Improvement
- Improved HUD clarity and readability.
- UI elements now scale better and look cleaner.
- Better load handling between states to avoid glitches.

**Note:** Learned custom font handling by inspecting other HUDs (inspired by Oliver’s files).

---

## [0.2.5] – HUD Options Update (BETA) - 2025-12-02

### Added
- Option to toggle HUD on/off in Preferences.
- Background color customization.
- Background opacity slider.
- Adjustable text size for HUD elements.
- Colored text for the Judgment Counter.

### Improved
- Improved overall HUD readability.

### Tweaks & Fixes
- Fixed scaling issues on some resolutions.
- General optimization and minor bug fixes.

**Summary:** This release introduced more personal customization options (color, opacity, text size) and improved usability and stability for the HUD.

---
