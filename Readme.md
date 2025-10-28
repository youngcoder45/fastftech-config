# fastfetch — Configuration README

A minimal README describing the included fastfetch configuration and how to use it.

## Overview
This repository contains a fastfetch configuration tuned for a compact, informative system summary. It prints key OS, hardware, and environment details with a small ASCII/logo and sensible defaults.

## Installation
1. Ensure fastfetch is installed (package manager or built from source).
2. Copy the bundled config to your fastfetch config folder:
    - User: `~/.config/fastfetch/fastfetch.conf`
    - System: `/etc/xdg/fastfetch/fastfetch.conf`

Example:
```
mkdir -p ~/.config/fastfetch
cp /home/aditya/mydotfiles/.config/fastfetch/fastfetch.conf ~/.config/fastfetch/fastfetch.conf
```

## Usage
Run fastfetch normally:
```
fastfetch
```
Or with an explicit config:
```
fastfetch --config ~/.config/fastfetch/fastfetch.conf
```

## Key configuration sections (examples)
- Basic info fields:
```
print_os = on
print_host = on
print_uptime = on
print_kernel = on
print_packages = on
print_shell = on
print_de = on
print_wm = on
```
- Logo and colors:
```
logo = "auto"        # auto, ascii file, or "none"
logo_color = true
color_mode = "auto"  # auto, truecolor, 256, 16, none
```
- Modules and custom labels:
```
# Example custom module
info "Username" "$USER"
info "CPU" "%cpu"
info "Memory" "%mem"
```

Refer to the inline comments in the config for available placeholders and module names.

## Custom logos
Place a custom ascii logo or image in the config directory and point `logo` to it. Use small art for best terminal fit.

## Tuning and tips
- Disable modules you don't need to reduce runtime.
- Use `--print-config` to debug which settings are loaded.
- For color issues, force `color_mode` to match terminal capabilities.

## Troubleshooting
- If output is empty, run `fastfetch --debug` to see errors.
- Ensure the config file is readable and syntactically correct.

## License
This config is configuration text; include your preferred license file if you plan to redistribute.

## Contact
For changes, edit the config under this directory and test with `fastfetch --config path/to/fastfetch.conf`.
