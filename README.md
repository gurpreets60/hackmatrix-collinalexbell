# HackMatrix (Arch Linux)

Simple install/build instructions for Arch-based systems.

## 1) Install dependencies

```bash
sudo pacman -S --needed \
  base-devel git meson ninja pkgconf \
  protobuf zeromq libx11 libxcomposite libxtst libxext libxfixes \
  spdlog fmt glfw-x11 mesa assimp sqlite \
  wayland wayland-protocols libxkbcommon pixman libdisplay-info libinput libdrm seatd \
  xdotool dmenu xorg-server xorg-xinit xorg-xwininfo xorg-xrandr
```

## 2) Get submodules

```bash
git submodule update --init --recursive
```

## 3) Build

```bash
make
```

This builds `matrix` and `matrix-debug`.

## 4) Optional: install binary

```bash
sudo make DESTDIR=/usr/local/ install
```

This installs `matrix` to `/usr/local/bin/matrix`.

## 5) Run

```bash
./matrix
```

If wlroots is missing on your system, build the local wlroots tree first:

```bash
make wlroots-local
make
```

Originally made by collinalexbell
https://github.com/collinalexbell/HackMatrix
