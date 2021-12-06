# Rust ESP Board

Welcome to the Rust ESP Development board project.

## Project Specification 

This board is based on the ESP32-C3, and includes sensors, LED, buttons, battery charger and USB type-C connector.

### SoC Features


* IEEE 802.11 b/g/n-compliant
* Bluetooth 5, Bluetooth mesh
* 32-bit RISC-V single-core processor, up to 160MHz
* 384 KB ROM
* 400 KB SRAM (16 KB for cache)
* 8 KB SRAM in RTC
* 22 × programmable GPIOs
* 3 × SPI
* 2 × UART
* 1 × I2C
* 1 × I2S
* 2 × 54-bit general-purpose timers
* 3 × watchdog timers
* 1 × 52-bit system timer
* Remote Control Peripheral (RMT)
* LED PWM controller (LEDC)
* Full-speed USB Serial/JTAG controller
* General DMA controller (GDMA)
* 1 × TWAI®
* 2 × 12-bit SAR ADCs, up to 6 channels
* 1 × temperature sensor

For the complete description, see the [ESP32-C3 Datasheet](https://www.espressif.com/sites/default/files/documentation/esp32-c3_datasheet_en.pdf).

### I2C Peripherals

This board includes the following peripherals over the I2C bus:

| Peripheral                | Part number  | Reference                                                                   | Crate |
|---------------------------|--------------|-----------------------------------------------------------------------------|-------|
| IMU                       | ICM-42670-P  | [Datasheet](https://invensense.tdk.com/download-pdf/icm-42670-p-datasheet/) | N/A   |
| Temperature and Humidity  | SHTC3        | [Datasheet](https://www.sensirion.com/en/environmental-sensors/humidity-sensors/digital-humidity-sensor-shtc3-our-new-standard-for-consumer-electronics/)            | [Link](https://crates.io/crates/shtcx)       |

#### I2C Bus Connection

| Signal     | GPIO        |
|------------|-------------|
| SDA        | GPIO10      |
| SCL        | GPIO8       |

### I/Os

The following devices are connected thought GPIO:

| I/O Devices | GPIO   |
|-------------|--------|
| LED         | GPIO7  |
| Button/Boot | GPIO9  |

### Power

* USB type-C (*no PD compatability*)

### Pin Layout

> This is the preliminary pin layout and changes may occur!

#### Left Side (J?)

| Pin Number | Description    | SoC     |
|------------|----------------|---------|
| 1          | Reset          |         |
| 2          | 3V3            |         |
| 3          | N/C            |         |
| 4          | GND            |         |
| 5          | IO0/ADC1-0     | GPIO0   |
| 6          | IO1/ADC1-1     | GPIO1   |
| 7          | IO2/ADC1-2     | GPIO2   |
| 8          | IO3/ADC1-3     | GPIO3   |
| 9          | IO4/ADC2-1     | GPIO4   |
| 10         | IO5/ADC2-0     | GPIO5   |
| 11         | IO6/MTCK       | GPIO6   |
| 12         | IO7/MTDO/LED   | GPIO7   |
| 13         | IO9/LOG        | GPIO8   |
| 14         | IO21/U0RXD     | GPIO21  |
| 15         | IO20/U0TXD     | GPIO20  |
| 16         | IO9/BOOT       | GPIO9   |

#### Right Side (J?)

| Pin Number | Description    | SoC     |
|------------|----------------|---------|
| 1          | VBAT           |         |
| 2          | EN [1]         |         |
| 3          | VBUS [2]       |         |
| 4          | IO12/SPIHD     | GPIO12  |
| 5          | IO16/SPID      | GPIO16  |
| 6          | IO17/SPIQ      | GPIO17  |
| 7          | IO13/SPIWP     | GPIO13  |
| 8          | IO15/SPICLK    | GPIO15  |
| 9          | IO19/USB_D+    | GPIO19  |
| 10         | IO18/USB_D-    | GPIO18  |
| 11         | IO8/SCL        | GPIO8   |
| 12         | IO10/SDA       | GPIO10  |

*[1] Connected to LDO enable pin*

*[2]Connected to USB 5V*

## Project KiCad Libraries

* [ESP32C3](https://github.com/espressif/kicad-libraries)

### Board Design

> This is the preliminary layout and changes may occur!

![Board Layout](/assets/Rust_Board_Footprint.png)

## Design

* Rust logo on it - https://www.rust-lang.org/policies/media-guide
  * Permission required from Rust foundation