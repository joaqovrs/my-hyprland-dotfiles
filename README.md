<div align="center">

# <svg xmlns="http://www.w3.org/2000/svg" xml:space="preserve" viewBox="0 330 241.24 312.89">
  <defs>
      <linearGradient id="hl-45deg" x1="10%" y1="90%" x2="90%" y2="10%">
        <stop offset="0%" stop-color="rgb(0, 168, 244)" />
        <stop offset="100%" stop-color="rgb(0, 229, 208)" />
      </linearGradient>
    </defs>
  <style>
    path {
      fill: url(#hl-45deg)
    }
  </style>
  <path d="M107 330c-25.9 39.39-61.43 86.28-79.3 114.97C9.83 473.67-1.86 502.32.24 536.26c3.85 62.1 56.46 106.63 120.38 106.63v-27.4c-51.66 0-90.07-33.06-93.03-80.93-1.67-26.96 6.9-48.66 23.37-75.1 14.07-22.6 33.9-47.95 56.03-80.2zm27.25 0c25.89 39.39 61.42 86.28 79.29 114.97 17.87 28.7 29.56 57.35 27.46 91.29-3.85 62.1-56.46 106.63-120.38 106.63v-27.4c51.66 0 90.07-33.06 93.03-80.93 1.67-26.96-6.9-48.66-23.37-75.1-14.07-22.6-33.9-47.95-56.03-80.2z" />
</svg> Hyprland Dotfiles



# 🪟 Hyprland Dotfiles

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
> Hacé un backup de tu `~/.config` actual antes de copiar nada.

```bash
# 1. Clonar el repo
git clone https://github.com/joaqovrs/my-hyprland-dotfiles.git
cd my-hyprland-dotfiles

# 2. (Opcional) Backup de tu config actual
cp -a ~/.config ~/.config.bak

# 3. Copiar las configuraciones
cp -a .config/* ~/.config/
```

### Dependencias

```bash
sudo pacman -S hyprland waybar kitty rofi mako cava fastfetch
# matugen y hyprsunset están en el AUR:
yay -S matugen-bin hyprsunset
```

---

## 📂 Estructura

```
.config/
├── hypr/        # Hyprland + hyprsunset
├── waybar/      # Barra (config, módulos, estilos, tokens de color)
├── kitty/       # Terminal
├── rofi/        # Lanzador
├── mako/        # Notificaciones
├── matugen/     # Plantillas de theming Material You
├── cava/        # Visualizador de audio
└── fastfetch/   # Info del sistema
```

---
