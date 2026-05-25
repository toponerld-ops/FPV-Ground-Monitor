# FPV Ground Monitor 

A custom-built open-source FPV ground station monitor built on the **Radxa Zero 3W** SBC, featuring a custom uHAT PCB for power management, a RTL8812AU WiFi dongle for receiving **OpenIPC** video streams from drones via **WFB-ng**.

Designed to pair with the **MAR Racing Drone** -- a custom 75mm FPV tiny whoop with a fully custom 8-in-1 AIO flight controller (also Hackclub Fallout funded), this monitor closes the loop on a fully open-source, end-to-end FPV video system.

---

## What is it?

A portable, battery-powered FPV video ground station that:

- Receives HD video from an OpenIPC-based drone over 5.8GHz via WFB-ng
- Displays live feed on a 7" HDMI screen via PixelPilot OS on the Radxa Zero 3W
- Powers everything from a 3S 11.1V li-ion battery via a custom uHAT buck converter PCB
- Features 3x WS2812B RGB LEDs for link/recording/battery status
- Has 3 navigation buttons + 1 power button for PixelPilot UI control
- Has an SSD1306 OLED for IP/battery/link status display
- Exposes a UART debug header for development

---

## Why did I make it?

I'm building the MAR Racing Drone -- a fully custom FPV drone with a custom AIO flight controller and an OpenIPC video system (SSC338Q + IMX415). To test and use the video link, I needed a ground station that:

1. Works with OpenIPC/WFB-ng (no DJI goggles)
2. Is portable and battery powered
3. Is fully open source and hackable
4. Is cheap enough to actually build

Commercial alternatives (DJI Goggles, Walksnail) cost $300-600 and lock you into a proprietary ecosystem. This monitor costs under ₹15,000 (~$180) and works with any OpenIPC drone.

---

## How do you use it?

1. Flash PixelPilot OS onto the 64GB microSD card
2. Plug the RTL8812AU dongle into the USB-A port on the uHAT
3. Connect the 3S battery to the XT30 connector on the uHAT
4. Power on via the power button
5. Connect your 7" HDMI display
6. Power on your OpenIPC drone
7. PixelPilot auto-connects via WFB-ng and displays the video feed

---

## Hardware

### BOM

| Component | Part | Source | Qty | Price (INR) |
|---|---|---|---|---|
| SBC | Radxa Zero 3W 2GB | Hubtronics | 1 | ₹6,900 |
| WiFi Module | RTL8812AU USB dongle | Robokits | 1 | ₹975 |
| Display | Waveshare 7" HDMI Capacitive | Robu | 1 | ₹2,500 |
| Battery | 3S 11.1V 2000mAh Li-ion | Robu | 1 | ₹900 |
| MicroSD | SanDisk 64GB A1 | Robu | 1 | ₹550 |
| uHAT PCB | Custom (this repo) | JLCPCB | 1 | ~₹800 |
| Buck Converter | MP2307DN-LF-Z | LCSC C18921 | 1 | - |
| RGB LEDs | WS2812B-V5 | LCSC C691873 | 3 | - |
| Buttons | TS-1187A-B-A-B | LCSC C318884 | 4 | - |
| OLED | SSD1306 128x64 I2C module | AliExpress | 1 | ₹150 |
| 40-pin Header | IDC-SMD_40P-P2.54 | LCSC C9900016611 | 1 | - |
| USB-A Socket | USB3.0VerticalTypeA | LCSC C9900010398 | 1 | - |
| Battery Connector | KF301-2P | LCSC C9900016950 | 1 | - |

Full BOM with LCSC part numbers in `/bom/BOM.csv`

---

## PCB -- uHAT

The custom uHAT PCB sits on top of the Radxa Zero 3W's 40-pin GPIO header and provides:

- **Power**: 11.1V 3S battery → MP2307 buck converter → 5V rail for Zero 3W + display
- **USB**: Routes USB 2.0 from GPIO header pins 27/28 to USB-A socket for WiFi dongle
- **Interface**: 4x tactile buttons, 3x WS2812B RGB LEDs, SSD1306 OLED connector
- **Debug**: UART header (TX/RX/GND) for serial debug access
- **Protection**: Polyfuse on battery input, 100nF decoupling on all power rails

### PCB Specs
- Size: 65 x 30mm
- Layers: 2
- Manufacturer: JLCPCB standard

![PCB 3D View](images/pcb_3d.png)

---

## Files

```
FPV-Ground-Monitor/
├── README.md
├── JOURNAL.md
├── bom/
│   └── BOM.csv
├── gerbers/
│   └── gerbers.zip
├── pcb/
│   └── uHAT.epro
├── schematic/
│   └── schematic.pdf
├── firmware/
│   └── README.md (PixelPilot OS setup instructions)
└── images/
    └── pcb_3d.png
```

---

## Software

This project runs **PixelPilot OS** on the Radxa Zero 3W -- a purpose-built Linux image for OpenIPC ground stations.

- Download: [PixelPilot GitHub](https://github.com/OpenIPC/PixelPilot)
- Flash to microSD with Balena Etcher
- RTL8812AU driver is included in PixelPilot OS
- WFB-ng handles the actual WiFi broadcast link

---

## Zine Page

![Zine Page](Images/ZINE.png)

---

**Made by Aman | Age 16 | Hyderabad, India**
