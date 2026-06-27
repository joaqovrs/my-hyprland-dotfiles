<div align="center">

# 💧 Hyprland Dotfiles - Sunset

### Mi configuración personal de Hyprland en Arch Linux

Un setup minimalista y dinámico, con temas generados automáticamente
desde el wallpaper usando **Material You** (`matugen`).

<br>

![Hyprland](https://img.shields.io/badge/Hyprland-00AAFF?style=for-the-badge&logo=hyprland&logoColor=white)
![Arch Linux](https://img.shields.io/badge/Arch_Linux-1793D1?style=for-the-badge&logo=arch-linux&logoColor=white)
![Wayland](https://img.shields.io/badge/Wayland-FFBC00?style=for-the-badge&logo=wayland&logoColor=black)
![License](https://img.shields.io/badge/License-MIT-22C55E?style=for-the-badge)

</div>

---

## 📸 Screenshots

<div align="center">

### 🖥️ Escritorio
<img src="assets/desktop.png" width="850" alt="Desktop"/>

### 🐱 Terminal — fastfetch · btop · cava
<img src="assets/terminal.png" width="850" alt="Terminal"/>

<br>

<img src="assets/launcher.png" width="49%" alt="Launcher"/>
<img src="assets/wallpaper-picker.png" width="49%" alt="Wallpaper picker"/>

_Lanzador de aplicaciones · Selector de wallpaper_

</div>

---

## ✨ Componentes

| | Componente | Descripción |
|:-:|:--|:--|
| 🪟 | **[Hyprland](https://hyprland.org/)** | Compositor Wayland con tiling dinámico |
| 🌅 | **hyprsunset** | Filtro de luz azul (modo nocturno) |
| 📊 | **[Waybar](https://github.com/Alexays/Waybar)** | Barra de estado modular |
| 🐱 | **[Kitty](https://sw.kovidgoyal.net/kitty/)** | Emulador de terminal acelerado por GPU |
| 🚀 | **[Rofi](https://github.com/davatorium/rofi)** | Lanzador de aplicaciones |
| 🔔 | **[Mako](https://github.com/emersion/mako)** | Daemon de notificaciones |
| 🎨 | **[Matugen](https://github.com/InioX/matugen)** | Temas Material You generados del wallpaper |
| 🎵 | **[Cava](https://github.com/karlstav/cava)** | Visualizador de audio en la terminal |
| 💻 | **[Fastfetch](https://github.com/fastfetch-cli/fastfetch)** | Info del sistema |

---

## 🎨 Theming dinámico

Los colores de **Waybar, Cava, Mako y Fastfetch** se regeneran automáticamente
a partir del wallpaper gracias a `matugen`. Un solo wallpaper → toda la paleta
del escritorio se actualiza en conjunto.

```
wallpaper  ──▶  matugen  ──▶  waybar · cava · mako · fastfetch
```

---

## ⌨️ Keybinds principales

> Tecla modificadora (`$mainMod`) = **`SUPER`** (tecla Windows)

| Atajo | Acción |
|:--|:--|
| `SUPER` + `Q` | Abrir terminal (kitty) |
| `SUPER` + `R` | Lanzador de apps (rofi) |
| `SUPER` + `E` | Gestor de archivos (nautilus) |
| `SUPER` + `F` | Firefox |
| `SUPER` + `C` | Cerrar ventana |
| `SUPER` + `V` | Ventana flotante |
| `SUPER` + `SHIFT` + `F` | Pantalla completa |
| `SUPER` + `S` | Captura de región (hyprshot + swappy) |
| `SUPER` + `SHIFT` + `W` | Selector de wallpaper |
| `SUPER` + `←↑↓→` | Mover el foco entre ventanas |
| `SUPER` + `1`–`5` | Cambiar de workspace |

---

## 📦 Instalación

> [!WARNING]
> Haz un backup de tu `~/.config` actual antes de copiar nada
> (el instalador lo hace por vos).

### Opción A — Instalador automático (recomendado)

```bash
git clone https://github.com/joaqovrs/sunset-dotfiles.git
cd sunset-dotfiles
./install.sh
```

El script instala las dependencias, hace backup de tu `~/.config`, y copia
las configuraciones, los scripts (`~/.local/bin`) y los wallpapers
(`~/Pictures/Wallpapers`). Usa `./install.sh --no-deps` si solo quieres copiar
los archivos sin tocar paquetes.

### Opción B — Manual

```bash
# 1. Clonar
git clone https://github.com/joaqovrs/sunset-dotfiles.git
cd sunset-dotfiles

# 2. Backup
cp -a ~/.config ~/.config.bak

# 3. Copiar configs, scripts y wallpapers
cp -a .config/.       ~/.config/
mkdir -p ~/.local/bin && cp -a .local/bin/. ~/.local/bin/ && chmod +x ~/.local/bin/*.sh
mkdir -p ~/Pictures/Wallpapers && cp -an wallpapers/. ~/Pictures/Wallpapers/
```

### Dependencias

> Todo está en los **repos oficiales** (core/extra/multilib). No hace falta
> ningún helper de AUR. Funciona igual en **Arch Linux** y en **CachyOS**.

```bash
sudo pacman -S --needed \
  hyprland hyprsunset waybar awww matugen \
  kitty rofi nautilus firefox \
  swaync blueman network-manager-applet polkit-kde-agent \
  cava wireplumber playerctl \
  hyprshot swappy \
  fastfetch btop breeze-icons \
  ttf-jetbrains-mono-nerd ttf-nerd-fonts-symbols ttf-nerd-fonts-symbols-mono
```

| Paquete | Para qué |
|:--|:--|
| `awww` | Daemon de wallpaper con transiciones (fork de swww) |
| `matugen` | Genera la paleta Material You desde el wallpaper |
| `swaync` | Daemon de notificaciones (el que realmente se usa) |
| `polkit-kde-agent` | Agente de autenticación gráfica |
| `network-manager-applet` / `blueman` | Aplets de red y Bluetooth en la bandeja |
| `hyprshot` + `swappy` | Captura de región y edición (`SUPER+S`) |
| `breeze-icons` | Tema de iconos del launcher de Rofi (`breeze-dark`) |
| `*-nerd` fonts | Iconos de Waybar, Fastfetch y la fuente de Rofi |

> [!NOTE]
> **CachyOS**: trae `paru` por defecto en vez de `yay`, pero aquí no necesitas
> ningún helper porque todos los paquetes están en `extra`.

---

## 📂 Estructura

```
.
├── install.sh          # Instalador (deps + configs + scripts + wallpapers)
├── .config/
│   ├── hypr/           # Hyprland + hyprsunset
│   ├── waybar/         # Barra (config, módulos, estilos, tokens de color)
│   ├── kitty/          # Terminal
│   ├── rofi/           # Lanzador + selector de wallpaper
│   ├── mako/           # Plantilla de notificaciones (legacy; se usa swaync)
│   ├── matugen/        # Plantillas de theming Material You
│   ├── cava/           # Visualizador de audio
│   └── fastfetch/      # Info del sistema
├── .local/bin/         # Scripts:
│   ├── set-wallpaper.sh           # aplica wallpaper + regenera paleta
│   └── wallpaper-picker-icons.sh  # selector con rofi (SUPER+SHIFT+W)
└── wallpapers/         # Wallpapers -> ~/Pictures/Wallpapers
```

---
