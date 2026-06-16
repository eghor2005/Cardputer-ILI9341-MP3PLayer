# Cardputer-ILI9341-MP3PLayer

A feature-rich MP3/WAV player for M5Cardputer with a retro Winamp-style interface.

## Overview

Transform your M5Cardputer into a portable audio player with full hardware keyboard controls, graphical interface, and automatic support for both Standard and Advanced hardware variants.


## The Final Device

![M5Cardputer Audio Player](images/1.jpg)

## Features

- 🎵 **Audio Playback**: MP3 and WAV files from microSD card
- 🔄 **Dual Hardware Support**: Auto-detects M5Cardputer (Standard) and M5Cardputer-Adv
- 🎨 **Retro Interface**: Winamp-inspired GUI with visual equalizer
- ⌨️ **Full Keyboard Control**: Playback, volume, brightness, and track navigation
- 🎧 **Headphone Detection**: Auto speaker muting (Advanced variant)
- 🔋 **Battery Status**: Real-time percentage display
- 📜 **Scrolling Track Info**: Track titles with smooth scroll

## Hardware Support

### Compatible Devices
- M5Cardputer (Standard) - AW88298 amplifier
- M5Cardputer-Adv - ES8311 codec with headphone detection

### Required Components
- microSD card with FAT32 format
- External ILI9341 display (SPI interface)
- Headphones (optional, for Advanced variant)

### Wiring: Cardputer-Adv EXT Connector → ILI9341

| ILI9341 Pin | EXT Pin | GPIO | Description    |
|---|---|---|---|
| VCC    | PIN 15  | -    | 3.3V Power    |
| GND    | PIN 11  | -    | Ground    |
| CS    | PIN 13  | G5    | Chip Select    |
| RST/RESET   | PIN 1   | G3    | Reset    |
| DC/RS    | PIN 5   | G6    | Data/Command    |
| SDI/MOSI    | PIN 9   | G14   | SPI Data In    |
| SCK/CLK    | PIN 7   | G40   | SPI Clock    |
| LED/BLK    | -      | -    | Backlight (connect to VCC or use PWM) |
| SDO/MISO    | -      | -    | Not used    |


## Installation

### Prerequisites
- Arduino IDE or PlatformIO
- ESP32 board support package

### Required Libraries
Install via Arduino Library Manager:
- M5Cardputer (official)
- ESP32-audioI2S (v2.0.0)
- ESP32Time (v2.0.6)
- LovyanGFX

### Build & Upload
```bash
# PlatformIO
platformio run --target upload

# Arduino IDE: Select M5Cardputer board and click Upload
```

## Usage

### Audio Files
1. Format microSD as FAT32
2. Create `/mp3s` folder (optional)
3. Place MP3/WAV files in folder or root
4. Insert SD card and power on

### Keyboard Controls

| Key | Function |
|-----|----------|
| `A` | Play/Pause |
| `V` | Volume cycle |
| `L` | Brightness cycle |
| `N` | Next track |
| `P` | Previous track |
| `;` | Skip backward |
| `.` | Skip forward |
| `B` | Random track |
| `Enter` | Play selected track |


## System Architecture

- **Core 0**: Display updates and keyboard input
- **Core 1**: Audio playback and codec management
- **Auto-detection**: I2C probing for hardware variant
- **Fallback Support**: Automatic codec fallback if initialization fails



