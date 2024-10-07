## STM32 UART Calculator

## Overview
This project implements a simple calculator on the STM32 microcontroller that accepts user input via UART, performs basic arithmetic operations, and outputs the result through UART. An LED is used to indicate errors like overflow or division by zero.

## Features:
Supports addition, subtraction, multiplication, and division.
 Handles 16-bit signed integers.
 Error handling for division by zero and overflow.
 UART communication for input/output.
Uses an LED as a visual error indicator.

## Project Structure:
main.c: The main logic, including UART interrupt handling and arithmetic operations.
stm32f4xx_hal_conf.h: HAL library configuration.
stm32f4xx_it.c: Interrupt service routines.

## Hardware Setup:
Microcontroller: STM32F4 series.
LED: Connected to GPIO_PIN_5 of GPIOA.
UART: USART2 is used for communication at a baud rate of **9600**.

## Pin Connections:
UART TX: PA2
UART RX: PA3
LED: PA5 (default)

## Software Setup:
IDE: STM32CubeIDE
Library: HAL Library
Toolchain: GCC

## Running the Project:
1. Connect the STM32 board to your PC using a USB-to-UART interface or through ST-Link.
2. Load the project into STM32CubeIDE.
3. Compile and upload the code to the STM32 microcontroller.
4. Open a serial terminal (e.g., PuTTY) and set the baud rate to **9600**.
5. Enter arithmetic expressions in the format: `num1 operator num2`. For example: `15 + 23`.

## Example Usage:
Input: `15 + 5`
Output: `Result: 20`
Input: `10 / 0`
Output: `Division by Zero!`

The LED connected to PA5 will blink to indicate an error.

## Error Handling:
Overflow: The system checks for integer overflows during operations and provides a warning message.
Division by Zero: If a division by zero is detected, an error message is displayed, and the LED will turn on for a second.

## Files:
main.c: Core logic for UART reception, interrupt handling, and arithmetic calculations.
stm32f4xx_hal_conf.h: STM32 HAL configuration file.
stm32f4xx_it.c: Interrupt Service Routine handlers for the project.
