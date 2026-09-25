# BatteryTray: Battery Monitor for Windows 10/11 System Tray

A lightweight, clean, and informative battery status monitor for Windows 10 and Windows 11, residing in the system notification area (near the clock).

---

## Features

1. **Clean Visual States & Windows Clock Font Height**:
   - **Green Background for AC Power (Charging)**: When connected to AC power, the icon displays a vibrant rounded green background with crisp white digits. No extra lightning bolt clutter.
   - **Red Background for Low Battery Alert**: When unplugged on battery and charge drops to or below threshold (default: <= 20%), the icon displays a warning red background with crisp white digits.
   - **Transparent Background for Normal Mode**: When operating normally on battery power, the background is completely transparent.
   - **Two Built-in Themes (for Transparent Mode)**:
     - **Black**: Flat black digits on transparent (default, for light taskbars).
     - **White**: Flat white digits on transparent (for dark taskbars).

2. **Interactive Test View Menu**:
   - Right-click menu -> **Test View**:
     - **1%**, **9%**, **15%** (test low battery red alert states)
     - **25%**, **50%**, **99%** (test normal transparent states)
     - **100%** (test 100% full capacity)
     - **AC On / Off** (toggle charging green background in real time)
     - **Return to Real Mode** (direct action to restore live battery sensor readings)

3. **Configuration in `config.ini`**:
   - Simple INI format with instant hot-reloading when changed via menu.
   ```ini
   [Settings]
   theme = black
   low_battery_threshold = 20
   refresh_interval_sec = 3
   enable_notifications = true
   autostart = false

4. **Context Menu (Right-Click on Tray Icon)**:
   - **Test View**: Interactive instant tester for percentages, AC charging, and No Sleep mode.
   - **Settings (Cascading Submenu)**:
     - **Theme**: Select Black or White digits for transparent battery mode.
     - **Red Alert Threshold**: Quick select (10%, 15%, 20%, 25%, 30%) or enter a custom threshold.
     - **Low Battery Notifications**: Toggle Windows toast notifications.
     - **Start with Windows**: Toggle autostart on system boot (via Windows Registry `HKCU\Software\Microsoft\Windows\CurrentVersion\Run`).
     - **Open config.ini**: Directly opens the configuration file in your default text editor (e.g., Notepad).
   - **No Sleep Mode**: Toggle Windows screen & system sleep prevention (shows vibrant blue tray icon).

## How to Run & Build

### Running
Run directly:
- **`BatteryTray.exe`**

### Command-Line Usage
```cmd
# Check current battery status from console
BatteryTray.cmd /status

# Stop any running BatteryTray instance gracefully
BatteryTray.cmd /stop
```

