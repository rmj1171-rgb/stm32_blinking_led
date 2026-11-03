# Automatic Sensor-Based LED Control System Using STM32

## Aim

To interface a digital sensor with an STM32 microcontroller and automatically control an LED according to the sensor output.

## Apparatus Required

| S. No. | Component | Quantity |
|---:|---|---:|
| 1 | STM32 development board | 1 |
| 2 | Digital sensor or push button | 1 |
| 3 | LED | 1 |
| 4 | 220–330 Ω resistor | 1 |
| 5 | Breadboard | 1 |
| 6 | Jumper wires | As required |
| 7 | USB cable | 1 |

## Algorithm

1. Start the program.
2. Configure Port 2 as output.
3. Turn LED ON.
4. Generate delay.
5. Turn LED OFF.
6. Generate delay.
7. Repeat forever.

## Program
ORG 0000H

START:
    MOV P2,#00H      ; LED ON (active LOW)
    ACALL DELAY
    MOV P2,#0FFH     ; LED OFF
    ACALL DELAY
    SJMP START

DELAY:
    MOV R7,#255
L1: MOV R6,#255
L2: DJNZ R6,L2
    DJNZ R7,L1
    RET

END

## output
<img width="716" height="717" alt="Screenshot 2026-11-03 142819" src="https://github.com/user-attachments/assets/b4e6b99a-6dcd-4e89-8938-3ffb13542e6a" />



## Result

The digital sensor was successfully interfaced with the STM32 microcontroller. The LED connected to `PA5` turned ON when the sensor input at `PA0` was HIGH and turned OFF when the sensor input was LOW.
