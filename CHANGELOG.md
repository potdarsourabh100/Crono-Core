# Changelog
All notable changes to **ChronoCore** will be documented in this file.

This project follows the principles of
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/)
and uses semantic versioning where applicable.

---

## [Unreleased]

### Added
- Initial project structure with separated `firmware`, `hardware`, and `docs` directories
- Core application framework for multipurpose clock functionality
- State-machine–based application flow
- Button handling concept with short-press and long-press support
- Documentation covering architecture, power management, and display behavior

### Changed
- N/A

### Fixed
- N/A

### Planned
- Persistent settings storage (EEPROM / Flash)
- Low-power sleep modes
- Configurable buzzer tone patterns
- Display brightness control
- Improved RTC accuracy handling

---

## [0.1.0] – Initial Public Release

### Added
- STM32F070F6P6 microcontroller support
- DS1307 RTC integration
- TM1637-based 4-digit 7-segment display support
- Clock mode with 12/24-hour format
- Timer and stopwatch application modes
- Pomodoro productivity timer
- DHT22 temperature and humidity sensing
- Buzzer output using timer/PWM
- USB Type-C power input
- UART debugging via CH340G
- Battery-powered operation with TP4056 charging and DW01 + FS8205A protection

### Changed
- N/A

### Fixed
- N/A

---

## Versioning Notes

- **Major** version increments indicate breaking changes in architecture, APIs or hardware
- **Minor** version increments indicate new features or application modes
- **Patch** version increments indicate bug fixes or internal improvements

---

## Contribution Notes

- Every meaningful change should be recorded under **[Unreleased]**
- Entries should be moved to a versioned section upon release
- Keep descriptions concise but descriptive
