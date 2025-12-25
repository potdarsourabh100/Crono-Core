# Project Synopsis  
## STM32 Multipurpose Clock

### 1. Introduction

The **STM32 Multipurpose Clock** is a compact, battery-powered embedded system designed to combine multiple time-based utilities into a single, efficient device. Built around the **STM32F070F6P6** microcontroller, the project demonstrates how a feature-rich product can be implemented using a small, resource-constrained MCU through clean architecture and modular firmware design.

This project serves both as a **practical daily-use device** and as a **reference implementation** for embedded system design, covering real-time clocks, user interfaces, power management, and application-layer abstraction.

---

### 2. Motivation and Objectives

Modern embedded devices often integrate multiple functionalities while operating under strict hardware and power constraints. This project was developed with the following objectives:

- Design a multipurpose timing device using a low-pin-count microcontroller
- Implement multiple applications without compromising firmware readability
- Demonstrate clean separation between hardware drivers and application logic
- Support battery-powered operation with safe charging and protection
- Provide a well-documented, open-source platform for learning and extension

---

### 3. System Overview

The system integrates the following functional blocks:

- **Real-Time Clock (RTC):**  
  A DS1307 RTC module provides accurate timekeeping independent of MCU power cycles.

- **Display Unit:**  
  A TM1637-controlled 4-digit 7-segment display with a colon is used to present time, timers, and status information in a minimal yet readable format.

- **User Input Interface:**  
  Five push buttons enable intuitive interaction. Two larger buttons support multipurpose actions through short and long presses, while three smaller buttons are dedicated to precise adjustments such as hour, minute, unit selection, and format toggling.

- **Environmental Sensing:**  
  A DHT22 sensor measures ambient temperature and humidity, allowing the device to display environmental data alongside time-based information.

- **Audio Feedback:**  
  A buzzer driven using timer-based PWM provides audible feedback for alarms, button interactions, and Pomodoro cycle transitions.

- **Power Management:**  
  The device is powered by two parallel 18650 Li-ion cells, charged via a TP4056 charging module and protected using a DW01 and FS8205A battery protection circuit. USB Type-C is used strictly for 5V power input and UART communication.

- **Connectivity & Debugging:**  
  A CH340G USB-to-UART converter enables firmware debugging, logging, and future firmware updates.

---

### 4. Functional Capabilities

The STM32 Multipurpose Clock supports multiple operating modes:

- **Clock Mode:**  
  Displays real-time hours and minutes with optional 12-hour or 24-hour format.

- **Timer Mode:**  
  Allows users to set and run countdown timers with audible alerts upon completion.

- **Stopwatch Mode:**  
  Measures elapsed time with start, stop, and reset functionality.

- **Pomodoro Mode:**  
  Implements structured work and break intervals to aid productivity, with audible and visual notifications for cycle transitions.

- **Settings Mode:**  
  Enables configuration of time, date, temperature units, display behavior, and application preferences.

---

### 5. Firmware Architecture

The firmware is organized using a **layered, state-machine–based architecture**:

- **Hardware Abstraction Layer (HAL):**  
  Provides low-level access to STM32 peripherals.

- **Driver Layer:**  
  Contains reusable drivers for the display, RTC, sensor, buzzer, and communication interfaces.

- **Board Support Package (BSP):**  
  Maps generic drivers to the specific hardware configuration and pin assignments of the board.

- **Application Layer:**  
  Implements individual application modes such as clock, timer, stopwatch, and Pomodoro.

- **Utilities Layer:**  
  Handles common tasks such as debouncing, timing utilities, logging, and state transitions.

A central state machine manages mode switching and event handling, ensuring deterministic behavior and simplified debugging.

---

### 6. Power and Efficiency Considerations

Given its battery-powered nature, the project incorporates multiple power-saving strategies:

- Display dimming during inactivity
- Selective peripheral enable/disable
- Efficient timer usage for periodic tasks
- Non-blocking firmware design to reduce CPU load

These strategies extend battery life while maintaining responsive user interaction.

---

### 7. Extensibility and Future Enhancements

The project is designed with extensibility in mind. Potential future enhancements include:

- Non-volatile storage for user settings
- Automatic display brightness control
- Support for higher-accuracy RTC modules
- Additional sensors or wireless connectivity
- Enhanced low-power sleep modes

---

### 8. Conclusion

The STM32 Multipurpose Clock demonstrates how a thoughtfully designed firmware architecture can transform a small microcontroller into a capable, multipurpose device. By combining modular design, clear documentation, and practical hardware choices, the project serves as both a functional product and a valuable learning platform for embedded systems development.

