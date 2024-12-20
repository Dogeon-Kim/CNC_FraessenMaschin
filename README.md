# CNC Arduino GRBL

## Introduction

This project provides a guide and source files for creating a CNC machine powered by an Arduino running the GRBL firmware. GRBL is a high-performance, open-source firmware for controlling CNC machines. It operates on Arduino boards and supports G-code, the standard programming language for CNC machines.

---

## Features

- **GRBL Firmware**: Compact and efficient CNC control software for Arduino boards.
- **G-code Support**: Compatible with standard G-code for a wide range of CNC operations.
- **Real-Time Controls**: Streamlined motion planning for high-speed CNC operations.
- **Modular Design**: Easy to customize for various CNC hardware setups.

---

## Requirements

### Hardware
- **Arduino Board**: (Recommended) Arduino Uno R3 or compatible model.
- **CNC Shield**: GRBL-compatible CNC shield for Arduino.
- **Stepper Motors**: At least 2 NEMA stepper motors (3 for 3-axis CNC).
- **Motor Drivers**: A4988 or DRV8825 drivers.
- **Power Supply**: 12V-24V, depending on motor specifications.
- **Limit Switches**: Optional for enhanced precision and safety.
- **Frame and Mechanical Components**: Custom-built or pre-made CNC frame.

### Software
- **Arduino IDE**: Version 1.8 or later.
- **GRBL Firmware**: Latest version available from the GRBL GitHub repository.
- **G-code Sender**: Universal G-code Sender (UGS), CNCjs, or any GRBL-compatible software.

---

## Installation

### 1. Set Up Arduino
1. Install the Arduino IDE from [Arduino Official Website](https://www.arduino.cc/en/software).
2. Download the latest GRBL firmware from the [GRBL GitHub repository](https://github.com/gnea/grbl).
3. Open the GRBL firmware in the Arduino IDE:
   - Navigate to `File > Open`.
   - Select the `grbl` folder and load the `grblUpload` sketch.
4. Connect your Arduino to your computer using a USB cable.
5. Upload the GRBL firmware:
   - Select the correct board and port from `Tools > Board` and `Tools > Port`.
   - Click the upload button.

### 2. Configure Hardware
1. Mount the CNC shield onto the Arduino board.
2. Attach the stepper motor drivers to the CNC shield.
3. Connect the stepper motors, limit switches, and power supply as per the CNC shield documentation.

### 3. Test Connection
1. Open a G-code sender (e.g., UGS).
2. Connect to the Arduino via the correct COM port and baud rate (default: `115200`).
3. Send a command like `$` to verify communication with GRBL.

---

## Configuration

After uploading the firmware, configure GRBL settings for your CNC machine:

1. Connect to the Arduino using a G-code sender.
2. Enter the following commands to configure GRBL:
   - `$100`, `$101`, `$102`: Set steps/mm for X, Y, Z axes.
   - `$110`, `$111`, `$112`: Set maximum feed rates for X, Y, Z axes.
   - `$120`, `$121`, `$122`: Set acceleration rates for X, Y, Z axes.
   - `$130`, `$131`, `$132`: Set maximum travel distances for X, Y, Z axes.

For detailed configuration options, refer to the [GRBL Wiki](https://github.com/gnea/grbl/wiki/Configuring-Grbl-v1.1).

---

## Usage

1. Prepare your G-code file using any CAM software (e.g., Fusion 360, Carbide Create).
2. Load the G-code into the G-code sender.
3. Home the CNC machine using the `G28` or `$H` command (if limit switches are installed).
4. Start the CNC operation and monitor progress.

---

## Troubleshooting

- **Connection Issues**:
  - Ensure the correct COM port and baud rate (`115200`) are selected.
  - Check the USB cable and connection.
- **Stepper Motor Not Moving**:
  - Verify motor driver connections and configuration.
  - Check power supply voltage and current.
- **GRBL Error Codes**:
  - Refer to the [GRBL Error Codes](https://github.com/gnea/grbl/wiki/Grbl-v1.1-Interface#alarm--error-codes) for detailed descriptions.

---

## Resources

- [GRBL GitHub Repository](https://github.com/gnea/grbl)
- [Universal G-code Sender](https://winder.github.io/ugs/)
- [Arduino Official Documentation](https://www.arduino.cc/en/Guide/HomePage)
- [GRBL Configuration Guide](https://github.com/gnea/grbl/wiki/Configuring-Grbl-v1.1)

---

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

---

## Contributing

Feel free to submit issues, suggestions, or pull requests to improve this project.

---

## Acknowledgments

Special thanks to the GRBL community for maintaining and improving this powerful firmware for CNC enthusiasts.
