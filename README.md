# Laptop Thermal Control Bridge

This repository contains a static dashboard and a Windows local agent for
reading laptop thermal sensors, applying a conservative fan-speed floor, and
running bounded CPU heat workloads.

## Repository layout

```text
thermal-bridge/
  agent/                 .NET 8 Windows x64 local agent
  web/                   GitHub Pages dashboard
.github/workflows/
  pages.yml              GitHub Pages deployment
  release.yml            Windows release packaging
```

## Run the agent

The agent requires Windows x64, the .NET 8 SDK for development, and
Administrator privileges for LibreHardwareMonitor sensor and controller
access.

```powershell
dotnet publish thermal-bridge/agent/LaptopThermalBridge.csproj `
  -c Release -r win-x64 --self-contained true `
  -p:PublishSingleFile=true -o thermal-bridge/publish
```

Run `thermal-bridge/publish/icastfireball.exe` as Administrator. The agent
listens only on `127.0.0.1:9876` and accepts the configured GitHub Pages
origin.

## Dashboard and releases

Pushes to `main` deploy `thermal-bridge/web` through GitHub Pages. Tags named
`v*` build and attach `icastfireball.exe` to a GitHub Release. The dashboard
downloads the latest asset from:

`https://github.com/bone-fires/thaatha/releases/latest/download/icastfireball.exe`

Enable GitHub Pages with **Source: GitHub Actions** in the repository settings.

## Safety and compatibility

- Fan control is intended to be floor-only: a requested floor must never be
  used to lower a firmware-controlled speed.
- Unsupported or unverifiable fan-control hardware must remain on BIOS/EC
  automatic control.
- Closing the agent or losing the dashboard connection stops stress workers
  and attempts to restore automatic fan control.
- Only one dashboard session is accepted at a time.
- OEM utilities such as Armoury Crate or Lenovo Vantage may compete for fan
  control and should be closed during testing.
- `ws://127.0.0.1` from an HTTPS Pages site may be blocked by browser
  mixed-content policy. Verify this in the target browser before release; a
  secure local transport may be required.

Do not use the fan override on hardware that has not been tested with a safe
restore path. A process crash, forced termination, power loss, or firmware
failure cannot guarantee cleanup code will execute.
