# 🧱 piBrick Serial Shell

**A browser-based serial terminal for connecting to and debugging piBrick hardware.**

piBrick Serial Shell provides a convenient way to access a serial console directly from your web browser. It uses [xterm.js](https://xtermjs.org/) to provide a terminal interface and supports both Web Serial and WebUSB for compatible USB-to-serial devices.

🌐 **Live application:** https://serial.amarullz.com/

---

## ✨ Features

- 🖥️ **Terminal emulator** — Interactive terminal powered by xterm.js.
- 🔌 **Web Serial support** — Connect to serial devices through the browser's Serial API.
- 🔗 **WebUSB support** — Connect to compatible CH340 USB-to-serial adapters.
- ⚙️ **Configurable serial settings** — Adjust baud rate, data bits, parity, and stop bits.
- ⌨️ **Virtual keyboard** — Access special keys and terminal shortcuts without a physical keyboard.
- 🔁 **Key repeat** — Hold supported virtual keys to repeat their input.
- 🛠️ **Command macros** — Quickly enter frequently used commands and shortcuts.
- 📱 **Mobile-friendly interface** — Use the terminal on supported mobile devices.
- 🖥️ **Fullscreen mode** — Expand the terminal for a more spacious workspace.
- 🔒 **Browser-based operation** — Connect directly from a supported browser without a dedicated desktop terminal application.

## 📋 Requirements

### 🌐 Supported browser

Use a modern browser that supports the required Web Serial or WebUSB APIs. Chromium-based browsers such as Google Chrome and Microsoft Edge are recommended.

The application must be served from a secure context, such as HTTPS or localhost, for browser hardware APIs to work.

### 🔌 Supported connections

**Web Serial**

Use Web Serial to connect to a serial device exposed by your operating system.

**WebUSB — CH340**

The application supports compatible CH340 USB-to-serial adapters using the following USB identifier:

| Property | Value |
|---|---|
| Vendor ID (VID) | `0x1A86` |
| Product ID (PID) | `0x7523` |
| Device | CH340 USB-to-serial adapter |

Device availability depends on browser support, operating-system permissions, and the USB adapter being used.

## 🚀 Getting Started

### 1. 🌐 Open Serial Shell

Open the application in a supported browser:

**https://serial.amarullz.com/**

### 2. 🔌 Connect your device

Choose the appropriate connection method:

- **Serial** — Connect using the Web Serial API.
- **USB** — Connect using the supported WebUSB CH340 interface.

When prompted, select your serial device and grant the browser permission to access it.

### 3. ⚙️ Configure serial settings

Select the serial parameters required by your target device.

| Setting | Available options |
|---|---|
| Baud rate | 9600, 19200, 38400, 57600, 115200, 230400 |
| Data bits | 7, 8 |
| Parity | None, Even, Odd |
| Stop bits | 1, 2 |

The settings on the target device and Serial Shell must match. Incorrect parameters can produce unreadable output or prevent communication.

### 4. 💻 Start using the terminal

Once connected, received serial data appears in the terminal. Type commands using your physical keyboard or the virtual keyboard.

To end the connection, use the **Disconnect** button.

## ⌨️ Virtual Keyboard

The virtual keyboard provides quick access to keys commonly needed in terminal sessions, especially on mobile devices.

### 🔑 Available keys

| Key | Purpose |
|---|---|
| Ctrl | Modifier for control-key combinations |
| Alt | Modifier for terminal shortcuts |
| Tab | Tab character |
| Esc | Escape character |
| `/` | Slash character |
| `~` | Tilde character |
| ↑ ↓ ← → | Arrow keys |
| Del | Delete sequence |
| Home / End | Navigate to the beginning or end |
| PgUp / PgDn | Page navigation |
| F1–F12 | Function keys |

### 🔁 Key repeat

Supported virtual keys can be held to generate repeated input. A short press sends a single key, while a longer press activates repeated input.

The keyboard also supports touch interaction, making it useful when a physical keyboard is unavailable.

## 🛠️ Macro Menu

The macro menu provides shortcuts for frequently used commands and terminal actions.

### 🍓 Raspberry Pi configuration

The included command macros provide quick access to common Raspberry Pi configuration files and tools:

| Macro | Command |
|---|---|
| Edit boot configuration | `sudo nano /boot/firmware/config.txt` |
| Edit kernel command line | `sudo nano /boot/firmware/cmdline.txt` |
| Raspberry Pi configuration | `sudo raspi-config` |

These commands assume a Raspberry Pi OS installation with the listed paths and utilities available.

### ⌨️ Terminal shortcuts

The macro menu also provides shortcuts for common control characters, including:

- **Ctrl+C** — Send the interrupt character.
- **Ctrl+D** — Send the end-of-file character.
- **Ctrl+X** — Send the corresponding control character.
- **Ctrl+Z** — Send the suspend-related control character.

The effect of each shortcut depends on the program running in the terminal and the target system's configuration.

### 📐 Terminal size

A terminal-size macro is also available for quickly sending the corresponding terminal command.

## 🖥️ Fullscreen Mode

Use the **Fullscreen** button to expand the terminal and make better use of the available screen space.

Fullscreen mode is particularly useful when working with long command output or when using a mobile device with limited display space.

Browser support and fullscreen permissions may vary by device.

## 📱 Mobile Usage

Serial Shell is designed to be usable on mobile devices with a compatible browser and supported hardware connection.

### 💡 Tips for mobile users

- Connect a compatible USB-to-serial adapter using an appropriate USB OTG adapter or hub.
- Keep the virtual keyboard available for terminal control keys.
- Use the macro menu to avoid repeatedly typing long commands.
- Use fullscreen mode when you need more terminal space.
- When scrolling the virtual-key row, move horizontally to access additional keys.
- Avoid moving your finger significantly while holding a virtual key if you intend to trigger that key.

Some devices and browsers may restrict Web Serial or WebUSB access. Compatibility depends on the operating system, browser, and USB hardware.

## 🔧 Troubleshooting

### 🔌 The browser cannot find my serial device

- Check that the USB-to-serial adapter is connected properly.
- Verify that the adapter is supported by the selected connection method.
- Try reconnecting the adapter and reopening the device-selection dialog.
- Confirm that the browser supports Web Serial or WebUSB.
- Check whether another application is already using the serial port.

### 🔤 Terminal output contains unreadable characters

Verify that the baud rate, data bits, parity, and stop bits match the target device.

Also check whether the target device is transmitting text, binary data, or a terminal-specific control sequence.

### ⌨️ Keyboard input does not work

- Confirm that the connection is active.
- Click or tap the terminal to focus it.
- Check whether the target device is waiting for a particular command or prompt.
- If using a virtual key, try tapping it instead of holding it.

### 📱 The mobile keyboard disappears

Tap the terminal input area to focus it again. Browser and operating-system behavior can affect when the native on-screen keyboard appears.

### 🔒 WebUSB or Web Serial is unavailable

- Open the application using HTTPS.
- Use a compatible browser.
- Check browser permission settings.
- Verify that the operating system recognizes the connected adapter.

## 🔒 Privacy and Permissions

Serial Shell requests browser permission to access the serial device you select.

Only connect to devices you trust. Commands sent through the terminal are delivered to the connected hardware and may modify its configuration or data.

Browser permission prompts and device access are managed by the browser and operating system.

## 🔗 Related Resources

- 🌐 **Serial Shell:** https://serial.amarullz.com/
- 📖 **USB Serial Console Guide:** https://github.com/amarullz/piBrick/wiki/USB-Serial-Console-Guide
- 🧱 **piBrick Project:** https://github.com/amarullz/piBrick

---

*Built for the piBrick community to make serial-console access more convenient across desktop and mobile devices.*
