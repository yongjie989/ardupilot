# SparkNavi Blue Flight Controller

![SparkNavi Blue](sparknavi-blue.png)

The SparkNavi Blue is a STM32H743-based flight controller designed by [SparkNavi](https://www.sparknavi.com/) and supported by the ArduPilot firmware.

---

## Features

* **Processor**

  * STM32H743 480MHz MCU
  * STM32F103 IOMCU
* **Sensors**

  * ICM42652 IMU
  * ICM42688 IMU
  * BMP280 barometer
  * HMC5883L compass
* **Interfaces**

  * 6 × UART ports
  * 2 × CAN FD ports
  * External I2C bus
  * SPI expansion port
  * USB Type-C
* **Storage**

  * microSD card for logging
* **Outputs**

  * 14 PWM outputs

    * 8 MAIN outputs via IOMCU
    * 6 AUX outputs via FMU
* **Power**

  * Dual redundant power inputs
  * Voltage and current monitoring

---

## Pinout

![SparkNavi Blue Pinout](sparknavi-blue-pinout.png)

---

## UART Mapping

| SERIAL Port | UART            |
| ----------- | --------------- |
| SERIAL0     | USB             |
| SERIAL1     | USART1 (GPS1)   |
| SERIAL2     | UART4 (GPS2)    |
| SERIAL3     | USART2 (TELEM1) |
| SERIAL4     | USART3 (TELEM2) |
| SERIAL5     | UART7 (Debug)   |
| SERIAL6     | UART8 (IOMCU)   |

---

## RC Input

RC input is available through the **SBUS connector**.

Supported protocols:

* SBUS
* RSSI input

---

## PWM Outputs

The SparkNavi Blue supports **14 PWM outputs**.

### MAIN Outputs

MAIN outputs are controlled by the **IOMCU** and support hardware failsafe.

MAIN OUT 1-8

Recommended for motors and other critical actuators.

### AUX Outputs

AUX outputs are controlled directly by the **FMU**.

AUX OUT 1-6

Typical uses include payload control, camera trigger, landing gear, and lighting.

---

## Battery Monitoring

Voltage and current monitoring are available through the **POWER1 / POWER2** connectors.

Both inputs support redundant power supply operation.

* BATT_MONITOR 4
* BATT_VOLT_PIN 16
* BATT_CURR_PIN 17
* BATT_VOLT_MULT 16.76111
* BATT_AMP_PERVLT 100
* BATT2_MONITOR 4
* BATT2_VOLT_PIN 14
* BATT2_CURR_PIN 15
* BATT2_VOLT_MULT 16.76111
* BATT2_AMP_PERVLT 100

---

## Compass

The board has a builtin HMC5883L compass.

External compasses can be connected via the **external I2C port**.

Recommended compass modules include:

* RM3100
* IST8310

---

## Loading Firmware

Firmware for this board can be found on the **ArduPilot firmware server**.

The board comes pre-installed with an ArduPilot compatible bootloader, allowing the loading of *.apj firmware files with Mission Planner.
