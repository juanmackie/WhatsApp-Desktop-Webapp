# WhatsApp Desktop Webapp

A lightweight, native desktop wrapper for WhatsApp Web built with [Pake](https://github.com/nicedayzhu/pake).

## Why?

- **Desktop app** — Heavy and slow
- **Web app** — Annoying tab management, constant "use here" prompts when switching tabs

This aims to be the best of both worlds: lightweight, always available, no tab headaches.

## Quickstart

### Download

Grab the latest `.msi` installer from this repository.

### Install

Double-click `WhatsApp Web for Desktop.msi` and follow the prompts.

### Run

Launch "WhatsApp Web for Desktop" from your Start Menu or Desktop shortcut.

### Login

Scan the QR code with your phone to link your account.

The app uses a normal, decorated Windows window: it starts at 1200×780, does not start maximized or fullscreen, and the native minimize, maximize, and close buttons remain available.

## Features

- Native desktop experience without the bloat
- No tab switching or "use here" interruptions
- Lightweight wrapper around WhatsApp Web

## Troubleshooting window behavior

If an older installation opens maximized or fullscreen, close the app and remove its saved window state:

```powershell
Remove-Item "$env:APPDATA\com.pake.a627e2e\.window-state.json" -ErrorAction SilentlyContinue
```

Version 1.0.1 uses a fresh application identifier and explicitly disables fullscreen, maximize-on-start, and hidden window decorations so stale state from the previous build is not reused.

## Build

The Pake build settings are kept in [`pake.config.json`](pake.config.json). From Windows with Node.js, Rust, and the Tauri prerequisites installed:

```powershell
npx -y pake-cli@3.15.1 --config pake.config.json --targets x64 --json
```

## Uninstall

Go to **Settings > Apps > Installed apps**, search for "WhatsApp Web for Desktop", and click Uninstall.

## Requirements

- Windows 10 or later

## Troubleshooting

| Issue | Solution |
|-------|----------|
| App won't open | Run as administrator or reinstall |
| QR code won't load | Check your internet connection and restart the app |
| Notifications not working | Enable notifications in Windows Settings > System > Notifications |

## License

MIT
