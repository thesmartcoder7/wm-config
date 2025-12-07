# Window Manager Configuration

A comprehensive configuration setup for tiling window managers including both X11 (suckless tools) and Wayland (Sway) environments.

## ⚠️ Disclaimer

This is an ongoing hobby project messing around with different window managers. The goal is having a minimalist, functional and productive system. It is by no means a polished or production-ready setup, but rather a personal exploration of tiling window managers and their ecosystems.

**This configuration is intended for:**

- Personal use and experimentation
- Those looking to explore different tiling window managers
- Learning about suckless philosophy and Wayland compositors
- Understanding the differences between X11 and Wayland workflows

**Please note:**

- Configurations may break between updates
- Some features might be experimental or incomplete
- Backup your existing dotfiles before trying this setup
- This is tailored to my personal workflow and preferences

Feel free to use this as a starting point for your own window manager journey!

***Run this in a VM before bare metal!***

## 📋 Contents

This configuration includes:

- **Suckless Tools** (X11/Xorg)
  - `dwm` - Dynamic window manager with custom patches
  - `dmenu` - Application launcher and menu system
  - `slstatus` - Status bar for dwm
- **Sway** - Wayland compositor configuration
- **Waybar** - Status bar for Sway
- **Wofi** - Application launcher for Wayland
- **Kitty** - Terminal emulator configuration
- **NeoVim** - Editor configuration with NvChad
- **Wallpapers** - Collection of background images
- **Installation Scripts** - Automated setup tools

## 🚀 Quick Install

Choose your installation method:

### Universal Installer (Recommended)

Automatically detects your distribution and runs the appropriate installer:

```bash
chmod +x install-universal
./install-universal
```

### Distribution-Specific Installers

**Debian/Ubuntu:**

```bash
chmod +x install-debian
./install-debian
```

**Arch Linux:**

```bash
chmod +x install-arch
./install-arch
```

**Fedora:**

```bash
chmod +x install-fedora
./install-fedora
```

### Manual Dependencies

If you prefer manual installation, see the platform-specific commands below:

For X11/Suckless tools:

```bash
sudo apt install xorg xinit libxinerama-dev libx11-dev libxft-dev libx11-xcb-dev libxcb-res0-dev libxrandr-dev build-essential xserver-xorg-input-all xfonts-base
```

For Sway/Wayland:

```bash
sudo apt install sway waybar wofi
```

Additional applications:

```bash
sudo apt install wget curl btop mpv picom audacity chromium kitty clementine gimp neofetch alsa-utils pulseaudio network-manager pavucontrol
```

## 🔧 Building Suckless Tools

Navigate to each suckless directory and compile:

```bash
cd suckless/dwm
sudo make clean install

cd ../dmenu  
sudo make clean install

cd ../slstatus
sudo make clean install
```

## ⚙️ Configuration Features

### DWM Features

- **Gaps**: Inner and outer window gaps (5px)
- **Custom Colors**: Dark theme with gray accents
- **Font**: JetBrainsMono Nerd Font
- **Patches**:
  - Movestack (move windows in stack)
  - Vanitygaps (configurable gaps)
  - Window swallowing support

### Sway Features

- **Borders**: 2px window borders
- **Custom Colors**: Consistent with DWM theme
- **Smart Borders**: Hide edges when appropriate

### Terminal (Kitty)

- Optimized configuration for development
- Custom color scheme matching WM theme

### NeoVim

- **NvChad** base configuration
- **Transparency**: Semi-transparent background
- **File Explorer**: nvim-tree with 30px width
- Custom mappings and options

## 📁 Directory Structure

```text
├── suckless/          # X11 window manager components
│   ├── dwm/           # Dynamic window manager
│   ├── dmenu/         # Application launcher  
│   ├── slstatus/      # Status bar
│   └── *_b/           # Backup configurations
├── sway/              # Wayland compositor config
├── waybar/            # Wayland status bar
├── wofi/              # Wayland app launcher
├── Pictures/          # Wallpapers collection
├── dotfiles/          # Additional dotfiles
├── kitty.conf         # Terminal configuration
├── init.lua           # NeoVim configuration
└── install            # Installation script
```

## 🎨 Customization

### Colors

The configuration uses a consistent dark theme across all components:

- **Background**: `#222222`
- **Foreground**: `#eeeeee`
- **Accent**: `#595959`
- **Border**: `#444444`

### Fonts

- **Primary**: JetBrainsMono Nerd Font (size 14)
- Ensure Nerd Fonts are installed for proper icon display

### Wallpapers

Multiple wallpapers are included in the `Pictures/` directory. Set your preferred background using:

- **X11**: `feh --bg-scale /path/to/wallpaper`
- **Sway**: Update `output` configuration in sway config

## 🔄 Switching Between X11 and Wayland

### X11 (DWM)

```bash
echo "exec dwm" > ~/.xinitrc
startx
```

### Wayland (Sway)

```bash
sway
```

## 📝 Applications List

See `apps.txt` for a comprehensive list of recommended applications and their purposes.

## ⚡ Key Features

- **Minimal**: Lightweight and efficient
- **Customizable**: Easily configurable source code
- **Dual Environment**: Support for both X11 and Wayland
- **Developer Friendly**: Optimized for programming workflows
- **Consistent Theming**: Unified appearance across all components

## 🤝 Contributing

Feel free to fork and customize this configuration to your needs. Submit pull requests for improvements or bug fixes.

## 📄 License

See individual LICENSE files in suckless directories for component-specific licensing.
