# 🌊 Hyprfoil

<div align="center">

[![Crates.io](https://img.shields.io/crates/v/hyprfoil.svg)](https://crates.io/crates/hyprfoil)
[![CI](https://github.com/yourusername/hyprfoil/actions/workflows/ci.yml/badge.svg)](https://github.com/yourusername/hyprfoil/actions/workflows/ci.yml)
[![Documentation](https://img.shields.io/badge/docs-latest-blue.svg)](https://hyprfoil.dev/docs)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Rust Version](https://img.shields.io/badge/rust-1.70%2B-orange.svg)](https://www.rust-lang.org)
[![Discord](https://img.shields.io/discord/your-discord-id?color=7289da&label=discord&logo=discord&logoColor=white)](https://discord.gg/your-invite)

**Elevate your Hyprland experience with browser-style tabs that feel native and perform like lightning ⚡**

[Features](#-features) •
[Installation](#-installation) •
[Quick Start](#-quick-start) •
[Configuration](#-configuration) •
[Documentation](https://hyprfoil.dev/docs) •
[Contributing](#-contributing)

![Hyprfoil Demo](https://raw.githubusercontent.com/yourusername/hyprfoil/main/assets/demo.gif)

</div>

## 🎯 Why Hyprfoil?

Ever felt like switching between windows in Hyprland could be more... fluid? Like water flowing around a hydrofoil? That's exactly what Hyprfoil does - it brings the smooth, intuitive tab experience you love from browsers right into your window manager!

> 💡 **Fun fact**: A hydrofoil is a lifting surface that operates in water, just like our tabs lift and organize your windows in Hyprland's watery environment!

## ✨ Features

- 🚀 **Blazing Fast**: Written in Rust for maximum performance
- 🎨 **Beautiful Design**: Browser-style tabs with smooth animations
- 🎯 **Smart Grouping**: Automatically group related windows
- ⌨️ **Keyboard Driven**: Extensive shortcuts for power users
- 🔄 **Session Persistence**: Your tabs survive restarts
- 📦 **Tab Groups**: Create workspaces within workspaces
- 🌈 **Themeable**: Customize everything from colors to animations
- 🔌 **Plugin System**: Extend functionality with ease

## 🚀 Installation

### Using Cargo (Recommended)

```bash
cargo install hyprfoil
```

### From Source

```bash
git clone https://github.com/yourusername/hyprfoil
cd hyprfoil
cargo build --release
sudo cp target/release/hyprfoil /usr/local/bin/
```

### Arch Linux (AUR)

```bash
yay -S hyprfoil
```

> ⚠️ **Note**: Hyprfoil requires Hyprland 0.35.0 or higher

## 🎯 Quick Start

1. **Create your config file:**
   ```bash
   mkdir -p ~/.config/hyprfoil
   cp /usr/share/hyprfoil/examples/config.toml ~/.config/hyprfoil/
   ```

2. **Start Hyprfoil:**
   ```bash
   hyprfoil
   ```

3. **Try these shortcuts:**
   - `Super + T`: Create new tab
   - `Super + Tab`: Switch tabs
   - `Super + W`: Close tab
   - `Super + G`: Group windows into tabs

## ⚙️ Configuration

Hyprfoil uses a configuration syntax similar to Hyprland:

```toml
# ~/.config/hyprfoil/config.toml

# Appearance
tab_height = 32
tab_width = auto
tab_border_radius = 8
animation_duration = 200

# Colors (Catppuccin Mocha theme)
active_bg = "#1e1e2e"
active_fg = "#cdd6f4"
inactive_bg = "#313244"
inactive_fg = "#bac2de"

# Keybindings
bind = SUPER, TAB, nexttab
bind = SUPER SHIFT, TAB, prevtab
bind = SUPER, W, closetab

# Tab Groups
[tab_groups.dev]
name = "Development"
apps = ["code", "kitty", "postman"]
keybind = "SUPER, D"
```

> 📚 See our [full configuration guide](https://hyprfoil.dev/docs/configuration) for all options!

## 🎨 Themes

Hyprfoil comes with several built-in themes:

<div align="center">
  <img src="https://raw.githubusercontent.com/yourusername/hyprfoil/main/assets/themes/catppuccin.png" width="30%" />
  <img src="https://raw.githubusercontent.com/yourusername/hyprfoil/main/assets/themes/dracula.png" width="30%" />
  <img src="https://raw.githubusercontent.com/yourusername/hyprfoil/main/assets/themes/nord.png" width="30%" />
</div>

## 📸 Screenshots

### Tab Grouping
![Tab Grouping](https://raw.githubusercontent.com/yourusername/hyprfoil/main/assets/screenshots/tab-groups.png)

### Custom Themes
![Custom Themes](https://raw.githubusercontent.com/yourusername/hyprfoil/main/assets/screenshots/themes.png)

### Session Management
![Session Management](https://raw.githubusercontent.com/yourusername/hyprfoil/main/assets/screenshots/sessions.png)

## 🛠️ Advanced Usage

### Tab Groups

Create powerful workflows by grouping related applications:

```toml
[tab_groups.development]
name = "Development"
apps = ["code", "terminal", "browser"]
workspace = 2
layout = "split"  # Options: split, stack, float

[tab_groups.communication]
name = "Communication"
apps = ["slack", "discord", "email"]
workspace = 3
```

### Macros

Automate complex workflows with macros:

```toml
macro = dev_setup, exec, "hyprfoil create-group dev && hyprfoil launch code && hyprfoil launch terminal"
macro = meeting_mode, exec, "hyprfoil hide-all && hyprfoil show communication"
```

## 🔧 Troubleshooting

<details>
<summary><b>Tabs not appearing?</b></summary>

1. Check if Hyprfoil is running: `pgrep hyprfoil`
2. Verify Hyprland version: `hyprctl version`
3. Check logs: `journalctl -u hyprfoil`

</details>

<details>
<summary><b>Performance issues?</b></summary>

- Disable animations: `animation_enabled = false`
- Reduce tab update frequency: `update_interval = 100`
- Check GPU acceleration: `hyprfoil --check-gpu`

</details>

## 🤝 Contributing

We love contributions! Whether it's:

- 🐛 Bug reports
- 💡 Feature requests
- 📖 Documentation improvements
- 🔧 Code contributions

Please read our [Contributing Guide](CONTRIBUTING.md) to get started.

## 📈 Roadmap

- [ ] Multi-monitor support improvements
- [ ] Plugin API v2
- [ ] Tab previews on hover
- [ ] Drag and drop tab reordering
- [ ] Cloud sync for tab sessions
- [ ] Mobile companion app

## 📜 License

Hyprfoil is MIT licensed. See [LICENSE](LICENSE) for details.

## 🙏 Acknowledgments

- The [Hyprland](https://hyprland.org/) team for creating an amazing window manager
- Our [contributors](https://github.com/yourusername/hyprfoil/graphs/contributors) who make Hyprfoil better every day
- The Rust community for excellent tooling and support

---

<div align="center">

**[Website](https://hyprfoil.dev)** • **[Documentation](https://hyprfoil.dev/docs)** • **[Discord](https://discord.gg/your-invite)** • **[Twitter](https://twitter.com/hyprfoil)**

Made with 💙 by the Hyprfoil Team

</div>
