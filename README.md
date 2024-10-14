# 📢 **MOEXHAWK**
The **MOEXHAWK V1.0.2 Baseboard** is a versatile single-board platform that combines a swappable Pixhawk flight controller and the Raspberry Pi CM4 companion computer. This baseboard offers a compact design, integrating all essential development connections in one place. It facilitates a smooth experience for developers needing an efficient and integrated solution for UAV or robotics projects.

It follows the [Pixhawk Connector](https://github.com/pixhawk/Pixhawk-Standards/blob/master/DS-009%20Pixhawk%20Connector%20Standard.pdf) and [Autopilot Bus Standard](https://github.com/pixhawk/Pixhawk-Standards/blob/master/DS-010%20Pixhawk%20Autopilot%20Bus%20Standard.pdf), allowing easy swap of FC Module with any FC that follows the Pixhawk Bus Standard.

![image](https://github.com/user-attachments/assets/62828502-ffd1-4036-b971-44623e944b1c)

# 🔶 **Features**

| **Feature**                   | **Description**                                                |
|-------------------------------|----------------------------------------------------------------|
| **CSI Camera Port**           | 1x CSI camera for the Raspberry Pi CM4                        |
| **CM4 Ethernet Port**         | 1x Ethernet port for CM4                                      |
| **I2C/SPI/UART Ports**        | 1x each of I2C, SPI, and UART/I2C ports                      |
| **CAN Ports**                 | 1x CAN port                                                  |
| **Telemetry Ports**           | 1x Telemetry port                                            |
| **Safety Switch**             | 1x Built-in Safety Switch on board                           |
| **CM4 GPIO Ports**            | 20x CM4 GPIO  ports                                          |
| **FC Port**                   | 1x FC port                                                   |
| **USB Port**                  | 1x Type-C USB port                                           |
| **FAN Connector**             | 1x FAN connector                                             |
| **Status LEDs**               | 4x CM4 and 1x FC status LEDs                                 |
| **Power Connectors**          | 1x Power connectors and 1x XT30                              |
| **UBEC**                      | 1x 4-6s; the built-in UBEC powers the CM4 and I/O PWM ports.  |





# 🔶 **Supported Firmwares**

## [**Ardupilot**](https://firmware.ardupilot.org/Copter/)

- Version Requirement: Must use ArduPilot versions 3.8 and later with the Pixhawk
- **Guide**: [Ardupilot Wiki on Running Companion Computer](https://ardupilot.org/dev/docs/companion-computers.html)

## [**PX4**](https://github.com/PX4/PX4-Autopilot/releases)
- **Version Requirement**: Must use PX4 1.13.1 Stable and newer.
- **Guide**: [PX4 Guide on Running Companion Computer](https://docs.px4.io/main/en/companion_computer/pixhawk_companion.html) - Provides information on how to run a companion computer.
  
 ## **Tested Firmware**

| **Test Cases**         | **Status**         |
|------------------------|--------------------|
| **ArduPilot**          | ✅ Tested          |
| **PX4**                | ❌ Not Tested      |


# 🔶 **Connections & Ports**

### RPi CM4 & FC Serial Connection
The flight controller `TELEM2` port is internally connected to RPi CM4 as shown:
| **RPi CM4** | **FC TELEM2 (FMU)** |
|-----------------|-------------------------|
| GPIO14 (TXD)    | TXD                     |
| GPIO15 (RXD)    | RXD                     |
| GPIO16 (CTS)    | CTS                     |
| GPIO17 (RTS)    | RTS                     |


### POWER1 Pinout
| **Pin**    | **Signal**        | **Voltage**       |
|------------|-------------------|-------------------|
| 1 (red)    | VCC               | +5V               |
| 2 (red)    | VCC               | +5V               |
| 3 (blk)    | CURRENT sensing   | +3.3V             |
| 4 (blk)    | VOLTAGE sensing   | +3.3V             |
| 5 (blk)    | GND               | GND               |
| 6 (blk)    | GND               | GND               |

### I2C Pinout
| **Pin**    | **Signal**   | **Voltage**           |
|------------|--------------|-----------------------|
| 1 (red)    | VCC          | +5V                   |
| 2 (blk)    | SCL          | +3.3V (pullups)       |
| 3 (blk)    | SDA          | +3.3V (pullups)       |
| 4 (blk)    | GND          | GND                   |

### CAN2 Pinout
| **Pin**    | **Signal**   | **Voltage**           |
|------------|--------------|-----------------------|
| 1 (red)    | VCC          | +5V                   |
| 2 (blk)    | CAN_H        | +12V                  |
| 3 (blk)    | CAN_L        | +12V                  |
| 4 (blk)    | GND          | GND                   |

### USB Pinout
| **Pin**    | **Signal**        | **Voltage**       |
|------------|-------------------|-------------------|
| 1 (red)    | VCC               | +5V               |
| 2 (blk)    | OTG_DP1           | +3.3V             |
| 3 (blk)    | OTG_DM1           | +3.3V             |
| 4 (blk)    | GND               | GND               |
| 5 (blk)    | BUZZER            | Battery voltage   |
| 6 (blk)    | FMU Error LED     |                   |

### TELEM1 Pinout
| **Pin**    | **Signal**        | **Voltage**       |
|------------|-------------------|-------------------|
| 1 (red)    | VCC               | +5V               |
| 2 (blk)    | TX (OUT)          | +3.3V to 5V       |
| 3 (blk)    | RX (IN)           | +3.3V to 5V       |
| 4 (blk)    | CTS (OUT)         | +3.3V to 5V       |
| 5 (blk)    | RTS (IN)          | +3.3V to 5V       |
| 6 (blk)    | GND               | GND               |

### I/O PWM OUT (MAIN)
| Pin  | Signal         | Volt     |
|------|----------------|----------|
| S    | IO_CH1~8       | +3.3V    |
| +    | VDD_SERVO      | 0~36V    |
| -    | GND            | GND      |



