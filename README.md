# xiloader - with XIPivot support

FFXI Server Emulator Boot Loader -- Launches client without PlayOnline.

## XiPivot support
Includes XIPivot support, for those pesky DATs the Windower addon cannot handle such as the Spells DAT.


Limitations:
- The overlays are loaded from a folder named `overlays` in the same directory as the bootloader executable.
- Overlays are loaded in the order they are found in the folder. Use numeric prefixes to control the order. Example: `01_ffxihd`, `02_ffximaps`, etc.
- Unlike the addon, overlays cannot be added or removed while the game is running.

All credits go to HealsCodes/XIPivot[https://github.com/HealsCodes/XIPivot] for the original code.

### Example layout
```
pol.exe
overlays/
  00-privateserver/
	ROM
  01-ffxi-hd/
    ROM
	ROM2
  02-ffxi-maps/
	ROM
  03-xiview/
    ROM
```

### Logging
XIPivot logs are written to the console.
```
[01/11/25 04:32:51] [XIPivot] m_hooksSet = true
[01/11/25 04:32:51] [XIPivot] m_rootPath = 'C:\xxx\overlays'
[01/11/25 04:32:51] [XIPivot] addOverlay: '00-privateserver'
[01/11/25 04:32:51] [XIPivot] => success
[01/11/25 04:32:51] [XIPivot] addOverlay: '01-ffxi-hd'
[01/11/25 04:32:51] [XIPivot] => success
```
## Build

```sh
mkdir build
cmake -S . -B build -A Win32
cmake --build build
```

## Release notes

### Windows

Requires VC2022 redist, included in https://aka.ms/vs/17/release/vc_redist.x86.exe

### Linux (through Wine)

Requires `winetricks vcrun2022`
