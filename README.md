# Cardputer-ILI9341-MP3PLayer
A feature-rich MP3/WAV player for M5Cardputer with a retro Winamp-style interface.

# Wiring: Cardputer-Adv EXT Connector → ILI9341

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
