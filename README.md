##### Installing Apps #####

##### frontend
sudo pacman -S --needed hyprland kitty rofi swww neofetch lightdm swaylock thunar firefox code

# eww
sudo pacman -S --needed gtk3 gtk-layer-shell pango gdk-pixbuf2 libdbusmenu-gtk3 cairo glib2 gcc-libs glibc cargo
git clone https://github.com/elkowar/eww
cd eww
cargo build --release --no-default-features --features=wayland
cd target/release
chmod +x ./eww
./eww daemon

##### backend
sudo pacman -S --needed git github-cli stow vim tree playerctl brightnessctl pipewire

# yay
sudo pacman -S --needed base-devel
git clone https://aur.archlinux.org/yay.git
cd yay
makepkg -si


##### Stow files #####
- cd into the Wayland-dotfiles repo and run these commands:
stow -S eww hypr kitty rofi --override=hypr --verbose=1
mkdir -p ~/.local/share/
stow -t ~/ -S fonts --verbose=1