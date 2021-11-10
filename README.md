# Rust ESP board

## MCU

- ESP32C3

## On board peripherals

### Accel/Gyro

- bmi088 - i2c -https://crates.io/crates/bmi088
- lsm9ds1 - i2c/spi - https://crates.io/crates/lsm9ds1
- mpu6051 - i2c - https://crates.io/crates/mpu6050 - NRFD

### Display/Visuals

- LED grid - none = none
- or display for use with https://github.com/embedded-graphics/embedded-graphics
  - Various OLED drivers, many `ssdXXX` drivers are supported
  - https://github.com/embedded-graphics/embedded-graphics#display-drivers
  - spi & i2c interfaces
- ws2812 - https://github.com/smart-leds-rs

### Other Input
- Button
- MEMS microphone - I2S (no driver interface in embedded_hal)

### Power

- USB micro, or USB C should be fine
- Battery connector?

## Design

- Rust logo on it - https://www.rust-lang.org/policies/media-guide
  - Permission required from Rust foundation

