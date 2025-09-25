# Dotfiles

Personal configuration files for my Linux setup, including custom builds of tools and configurations for my preferred apps.

## Contents

- **cava/** – Terminal audio visualizer configuration
- **dmenu/** – Custom build of `dmenu` with patches
- **kitty/** – Terminal emulator config
- **picom/** – Compositor settings
- **qutebrowser/** – Browser config (themes, scripts)
- **scripts/** – Utility scripts (wallpaper setter, session launcher)
- **slock/** – Custom screen locker build
- **st/** – Custom terminal build
- **xprofile** – X session environment settings
- **dmenu-session/** – Session launcher scripts

## Setup

Clone the repository:

```bash
git clone git@github.com:Bl1ndBeholder/dotfiles.git
cd dotfiles
```

### Copy configuration files

Copy the configuration files to their proper locations:

```bash
# X session profile
cp xprofile ~/.xprofile

# Kitty terminal config
mkdir -p ~/.config/kitty
cp -r kitty/* ~/.config/kitty/

# Picom compositor config
mkdir -p ~/.config/picom
cp -r picom/* ~/.config/picom/

# Qutebrowser config
mkdir -p ~/.config/qutebrowser
cp -r qutebrowser/* ~/.config/qutebrowser/
```

### Copy scripts

Copy utility scripts to your local bin directory:

```bash
mkdir -p ~/.local/share/bin
cp -r scripts/* ~/.local/share/bin/
chmod +x ~/.local/share/bin/*
```

### Build custom tools

```bash
# Build st terminal
cd st
make
sudo make install
cd ..

# Build dmenu
cd dmenu
make
sudo make install
cd ..

# Build slock
cd slock
make
sudo make install
cd ..
```

### Optional Cleanup

If you want, you can remove the cloned repo after copying/building everything:

```bash
cd ..
rm -rf dotfiles
```

## Notes

- Files are copied, so the repository does **not** need to remain in your home directory.  
- Some directories (`slock`, `dmenu`, `st`) are custom builds, not just configs.  
- Ensure `~/.local/share/bin` is in your PATH to run scripts easily.

