# LED-BLINK
# 💡 Experiment 01 – Interfacing a Digital Output (LED) with ARM Development Board

### 🎯 **Aim**
To interface a digital output (LED) to an ARM development board and write a blink code.

---

### ⚙️ **Components Required**
- STM32CubeIDE  
- NUCLEO ARM Development Board  

---

### 🧠 **Theory**

**ARM (Advanced RISC Machine)** is a 32-bit processor architecture developed by ARM Holdings. It is widely used in embedded systems and SoC (System-on-Chip) products. Many semiconductor companies like Samsung, Atmel, and Texas Instruments license ARM architecture to design their own SoCs.
### 🧩 **What is an ARM7 Processor?**
The **ARM7 processor** is commonly used in embedded system applications. It provides a balance between the classic ARM architecture and the newer Cortex series, offering an excellent platform for both hardware and software development.
### 🔍 **LPC2148 Microcontroller**
The **LPC2148**, developed by NXP Semiconductors (Philips), is a 16/32-bit ARM7-based microcontroller featuring a wide range of peripherals.
#### **Key Features**
- 16/32-bit ARM7TDMI-S core in LQFP64 package  
- On-chip **Flash memory**: 32 KB – 512 KB  
- On-chip **SRAM**: 8 KB – 40 KB  
- **ISP/IAP** via on-chip bootloader  
- **Embedded ICE-RT** and **Real Monitor** for real-time debugging  
- **USB 2.0** full-speed device controller with 2 KB endpoint RAM  
- **10-bit ADC** (6 or 14 channels, 2.44 μs conversion time)  
- **10-bit DAC** for analog output  
- **Timers:** Two 32-bit timers, watchdog, and PWM unit  
- **RTC** with 32 kHz clock input  
- **UARTs (2x), I²C (2x)** up to 400 kbit/s  
- **5V-tolerant GPIOs**, 21 external interrupt pins  
- **Max CPU Clock:** 60 MHz using on-chip PLL (lock time 100 µs)  
- **Crystal Frequency:** 1 MHz – 25 MHz  
- **Power modes:** Idle and Power-down with peripheral clock scaling  

---

### 🧭 **Procedure**

1. Open **STM32CubeIDE**.
  
<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/cf8068d3-0f8e-453f-b270-fb7f059be7da" />

2. Click **File → New STM32 Project**.
   
<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/07e98618-45bf-4c53-ae74-aceb95e76c2e" />

3. Select the **target microcontroller** or board and click **Next**.
  
<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/2fe3356f-9afb-479f-a719-faee3e97e01a" />

4. Name the project.
   
<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/c8c14ff3-701a-43ab-a7e3-216fff38be83" />

5. The corresponding `.ioc` file will be generated automatically.
  
<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/d1c74e40-8fd3-460f-93f0-56fac402c57c" />

6. Configure the pins as **GPIO (Input/Output)**, **USART**, etc. as needed.
   
<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/5fae5485-8b29-48e3-bcac-249bc791635e" />

7. Save the configuration (`Ctrl + S`) – the base C program will be generated automatically.
   
<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/755845c8-aa75-4c63-a1c6-187c5dbe29a3" />

8. Edit the generated main program as required.
   
<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/fb2d7a94-281a-471e-8f1c-963fabde80ce" />
<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/386e1544-f898-4c19-8e42-cd8ca9d2b117" />

9. Click **Project → Build All**.
    
<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/30c06352-555c-42b0-a95e-0049b08a97d0" />

10. Link the **HEX file** using the post-build process.
    
<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/4d432865-523c-4188-9eac-ee0db871b193" />

11. Click **Debug** and connect the **STM Nucleo Board**.
    
<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/22997709-9036-4ab3-80b7-beded7b6a751" />

12. Click **Run** to execute the program.
    
---

### 💻 **Program**


```c
#include "main.h"

void SystemClock_Config(void);
static void MX_GPIO_Init(void);

int main(void)
{
    HAL_Init();
    SystemClock_Config();
    MX_GPIO_Init();

    while (1)
    {
        HAL_GPIO_WritePin(GPIOA, GPIO_PIN_5, GPIO_PIN_RESET);
        HAL_Delay(1000);
        HAL_GPIO_WritePin(GPIOA, GPIO_PIN_5, GPIO_PIN_SET);
        HAL_Delay(1000);
    }
}
```
---
### OUTPUT
CASE 1: LED ON 

![on](https://github.com/user-attachments/assets/0b4d206e-fedf-446b-b167-2ed9f23c6d4b)

CASE 2: LED OFF

![off](https://github.com/user-attachments/assets/83aa12b5-7e8a-4fca-a5df-a4ee04850f65)

---
### RESULT
Interfacing a digital output with ARM microcontroller is executed and the results are verified.
