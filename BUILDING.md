# Building in VS Code on Windows

This plugin builds as a 64-bit OBS module DLL. It uses the official OBS plugin template CMake files, so VS Code can build it through the CMake Tools extension.

## Install once

1. Install Visual Studio 2026 Community or Build Tools for Visual Studio 2026.
2. In the installer, select **Desktop development with C++**.
3. Make sure these components are included:
   - MSVC x64/x86 build tools
   - Windows 11 SDK
   - C++ ATL for latest build tools
4. Install CMake 4.2 or newer.
5. Install Git for Windows.
6. In VS Code, install:
   - C/C++
   - CMake Tools

## Configure

Open this folder in VS Code, then run:

```powershell
cmake --preset windows-x64
```

The first configure can take a while. The OBS template downloads OBS sources and prebuilt dependencies, builds the OBS development pieces it needs, and then configures this plugin.

## Build

From VS Code, run **CMake: Build** from the command palette, or use:

```powershell
cmake --build --preset windows-x64
```

The built DLL will be copied to:

```text
build_x64/rundir/RelWithDebInfo/acc-obs-plugin.dll
```

## Install into OBS

Close OBS, then copy the DLL to the OBS plugin folder:

```text
C:/Program Files/obs-studio/obs-plugins/64bit
```

Restart OBS after replacing the DLL.
