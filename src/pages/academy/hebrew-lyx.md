---
layout: "../../layouts/Layout.astro"
title: Hebrew LyX
icon: "fa-solid fa-file-pen"
description: "Setup guide for LyX with Hebrew (using TeXLive and pdflatex)."
---

# LyX Hebrew Guide

- Install [TeXLive](https://www.tug.org/texlive/acquire-netinstall.html) using either `install-tl-windows.exe` for Windows or `install-tl-unx.tar.gz` for Linux/macOS.
- Install the `babel-hebrew` package by running `tlmgr install babel-hebrew` in an administrator command-line.
- Download the [culmus fonts](./culmus.zip) and copy the two `tex, fonts` directories into your TeXLive dist directory.
  On windows, it is found in `C:\texlive\{YEAR}\texmf-dist` and on macOS/Linux, somewhere like `/usr/local/texlive/{YEAR}/texmf-dist`.
  Note that I uploaded the files from the open source project found [here](https://sourceforge.net/projects/ivritex/files/culmus-latex/), version 0.7.
- Update the TeXLive font map and other things by running `mktexlsr`, then `updmap-sys`, then `updmap-sys --enable Map=culmus.map`, then `mktexlsr` in an administrator command-line.
- Install LyX by running the installer for your system which can be downloaded from [here](https://www.lyx.org/Download).
  For Windows, install the appropriate `.exe` file and for macOS install the `.dmg` file.
- Update your global (non document-specific) preferences for hebrew by going into `Tools->Preferences` in Windows and Linux or `LyX->Preferences` on macOS.
  - Change `Editing->Keyboard/Mouse` to enable `Use keyboard map` and pick `null` for Primary and `hebrew` for Secondary.
  - Add a shortcut in `Editing->Shortcuts` by pressing `New`, enter `language hebrew` for the `Function` field and then enter your preferred shortcut in shortcut by clicking on it, pressing the keys and then click OK.
    I suggest `Shift+Space` for Windows/Linux and `Control+Space` for macOS.
  - In `File Handling->File Formats` pick `PDF (pdflatex)` for the default output format with TeX fonts.
- Update your document preferences for hebrew (and defaults) by going into `Document->Settings`.
  - In `Document Class` pick `Hebrew Article`.
  - In `Language` pick `Hebrew`.
  - In `Float Placement` I suggest I suggest using `Here definitely`.
  - In `Page Margins` I suggest reducing the defaults to 1.5 for top and bottom and 1 for inner and outer.
  Click `Save as Document Defaults` so all of the documents you create will use the above settings.
