# AI Meter Reader — ESP32-S3-CAM

Firmware for the dual-mode prototype featured in the engineering portfolio:

- Offline 4-band and 5-band resistor calculator
- OV5640 pressure-gauge image capture
- Gemini-based gauge reading and risk-zone classification
- OLED, I2S audio, web dashboard, and Telegram notifications
- Manual analysis and automatic analysis every 30 seconds

## Hardware

- ESP32-S3-CAM with OV5640 camera
- SSD1306 128×64 I2C OLED
- MAX98357A I2S amplifier and speaker
- Stable USB-C power supply

## Arduino libraries

- ArduinoJson
- Adafruit GFX Library
- Adafruit SSD1306
- ESP32 camera, Wi-Fi, HTTP client, and I2S libraries

## Configuration

1. Copy `secrets.example.h` to `secrets.h`.
2. Add your Wi-Fi credentials, Gemini API key, Telegram bot token, and Telegram chat ID.
3. Keep `secrets.h` private. It is excluded by the repository `.gitignore`.
4. Add the audio-data headers referenced by the sketch (`Start.h`, `Resistormode.h`, `Gaugemode.h`, `Resistorcomplete.h`, `GaugeSafe.h`, `GaugeHigh.h`, and `GaugeDanger.h`). These generated WAV headers are not included in this public repository.
5. Open `ai_meter_reader.ino` in Arduino IDE, select the matching ESP32-S3 board configuration, and upload.

## Security note

The public source contains no Wi-Fi passwords, API keys, Telegram tokens, or chat IDs. Do not commit `secrets.h`.
