# Smart Home Simulation using STM32 (Nucleo F303K8)

This project simulates a basic smart-home system using the STM32 Nucleo-F303K8.  
It reads temperature, humidity, and light levels, and controls two LEDs based on sensor values.

---

## Hardware Used
- STM32 Nucleo-F303K8  
- DHT11 temperature/humidity sensor  
- LDR (photoresistor) + 10kΩ resistor (voltage divider)  
- Breadboard + jumper wires  

---

## Connections (High-Level)
- **LDR output → PA1** (ADC input)  
- **DHT11 data → PB0**  
- **LED (light indicator) → PF1**  
- **LED (fan indicator) → PB3**  
- **All sensors share 3.3V and GND**

See `/Docs/wiring_diagram.jpeg` for diagram.

---

## System Behavior
- The **LDR** value controls the PF1 LED (light indicator).  
- The **DHT11** temperature value controls the PB3 LED (fan indicator).  
- Sensor readings are printed over UART.

Example output:
```
TEMP=27C HUM=45% | FAN OFF | LDR=1823
TEMP=31C HUM=48% | FAN ON  | LDR=974
```

---

## Project Structure
```
Firmware/
   Inc/
   Src/
   Startup/

Docs/
   wiring_diagram.jpeg
   hardware_setup.png

.gitignore
README.md
```

---

## Build Instructions
1. Open the project in **STM32CubeIDE**.  
2. Build and flash to **Nucleo-F303K8**.  
3. Open a serial terminal at **38400 baud**.  
4. Reset the board to start reading sensor data.

