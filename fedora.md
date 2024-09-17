# Fedora Config

## Package List

[base]
git
base-devel

[config]
stow

[editor]
neovim

[Xorg DE]
xorg
xorg-xinit
nitrogen
picom

### Networking

Required: networkmanager, bluez

```
dnf install networkmanager bluez bluez-utils
```

```
systemctl enable --now NetworkManager bluetooth
```

### Import Dotfiles

```
cd ~
git clone https://github.com/kavyadeepdev/dotfiles.git
cd ./dotfiles
stow .
```

### Neovim

```
dnf install neovim
```

Config: gets installed automatically on opening neovim the next time if dotfiles have been imported

### Install DWM

Required: dwm, dmenu, slstatus, st, lxsession/xfce-polkit, nm-applet, blueman-applet

```
dnf install lxsession network-manager-applet blueman
```

```
cd ./.config
cd ./dwm && sudo make clean install && cd ..
cd ./dmenu && sudo make clean install && cd ..
cd ./slstatus && sudo make clean install && cd ..
cd ./st && sudo make clean install && cd ..
cd
```

### Shortcuts

Required: sxhkd, brillo

```
dnf copr enable leloubil/brillo
dnf isntall sxhkd brillo
```

Config: imported by default

### Tmux

```
dnf install tmux
```

TPM:

```
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
```

```
tmux source ~/.tmux.conf
```
