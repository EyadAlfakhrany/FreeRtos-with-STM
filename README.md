# FreeRTOS STM32 Projects

This repository contains a set of FreeRTOS-based embedded systems projects developed on STM32 microcontrollers. The projects demonstrate key real-time operating system concepts such as task scheduling, synchronization mechanisms, inter-task communication, and peripheral interfacing.

## Projects Overview

### 1. Digital and Analog Reader with Mutex Synchronization

- Uses two parallel tasks:
  - One reads a digital input (user button).
  - The other reads analog data from pin A0.
- A mutex is used to control access to the serial port, ensuring consistent and conflict-free logging.

### 2. LED Blinker and Analog Sensor Plotting

- Implements:
  - A blinking LED task using `vTaskDelay`.
  - An analog reader task that logs sensor data over serial.
- Demonstrates multitasking and FreeRTOS task timing.

### 3. Real-Time SD Card Data Logger using FIFO Buffer

- Separates sensor sampling and SD card writing using:
  - One task for sensor data collection.
  - One task for logging data to the SD card.
- Uses counting semaphores to manage a FIFO queue of sensor readings.
- Prevents SD card write latency from affecting data acquisition timing.

### 4. Rate Monotonic Scheduler Simulation

- Simulates Rate Monotonic Scheduling (RMS) theory from Liu & Layland.
- Allows selection of predefined task sets with varying CPU loads.
- Displays whether each task set meets its deadlines under RMS.
- Demonstrates priority-based preemptive scheduling and CPU utilization analysis.

## Dependencies

- STM32 microcontroller (e.g., Blue Pill or Nucleo)
- FreeRTOS
- STM32 HAL or Arduino STM32 core (based on platform)
- SD card module (for logger project)
- Serial terminal for monitoring output

## Building and Running

1. Clone this repository.
2. Open each project in STM32CubeIDE or your preferred IDE.
3. Flash the code to the STM32 board.
4. Connect via serial monitor at 9600 baud.
5. For the Rate Monotonic project, follow the on-screen prompt to choose the task set.

## License
