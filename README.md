# Wireless Notice Board with LCD

This project is a simple Wireless Notice Board using an Arduino, a 16x2 LCD display, and a Bluetooth module or other wireless communication device. The messages are sent via wireless communication and displayed on the LCD.

## Features

- Receives messages via wireless communication (Bluetooth, RF, etc.) using the `SoftwareSerial` library.
- Displays messages on a 16x2 LCD using the `LiquidCrystal` library.
- Automatically scrolls long messages on the display.

## Requirements

- **Arduino Uno (or similar)**: The microcontroller used in this project.
- **16x2 LCD Display**: To display messages.
- **Bluetooth Module (HC-05/HC-06)** or any device that can communicate over `SoftwareSerial`.
- Jumper Wires and Breadboard.
- **Arduino IDE** for uploading the code.

## Libraries

- [LiquidCrystal](https://www.arduino.cc/en/Reference/LiquidCrystal): To control the 16x2 LCD display.
- [SoftwareSerial](https://www.arduino.cc/en/Reference/softwareSerial): For serial communication with wireless devices (Bluetooth, RF).

You can install these libraries using the Arduino Library Manager or download them from their respective links.

## Hardware Setup

1. **LCD Connections**:
   - RS (LCD Pin 4) -> Arduino Pin 4
   - E (LCD Pin 6) -> Arduino Pin 5
   - D4 -> Arduino Pin 6
   - D5 -> Arduino Pin 7
   - D6 -> Arduino Pin 8
   - D7 -> Arduino Pin 9
   - VSS -> GND
   - VDD -> 5V
   - V0 -> Potentiometer for contrast
   - RW -> GND
   - A (LED+) -> 5V
   - K (LED-) -> GND

2. **Bluetooth Module** (e.g., HC-05) or other communication device:
   - TX -> Arduino Pin 2 (SoftwareSerial RX)
   - RX -> Arduino Pin 3 (SoftwareSerial TX)
   - GND -> GND
   - VCC -> 5V

## Code Overview

The code initializes the LCD and the serial communication. It waits for data to be sent via wireless communication and displays it on the LCD. If the message is longer than the display width, it scrolls the message across the LCD.

### Key Variables:
- `val`: Stores the incoming data from the wireless communication.
- `oldval`: Stores the previous data for comparison.
- `newval`: Stores the new data that will be displayed on the LCD.

### Functions:
- `setup()`: Initializes the LCD and serial communication, and displays a welcome message.
- `loop()`: Continuously reads incoming data, checks if it's new, and displays it on the LCD.

## Usage

1. Connect the LCD and Bluetooth module to the Arduino as per the hardware setup.
2. Upload the code to the Arduino using the Arduino IDE.
3. Send messages via Bluetooth (or other wireless communication methods). The received messages will be displayed on the LCD screen.
4. Messages will scroll if they exceed the display length.

## License

This project is open-source and free to use for educational purposes.

