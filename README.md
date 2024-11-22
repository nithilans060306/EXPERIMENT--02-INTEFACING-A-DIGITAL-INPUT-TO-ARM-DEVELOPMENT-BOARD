# EXPERIMENT--02-INTEFACING-A-DIGITAL-INPUT-TO-ARM-DEVELOPMENT-BOARD
## Aim: To Interface a Digital Input  (userpush button  ) to ARM   development board and write a  program to obtain  the data and flash the led  
## Components required: STM32 CUBE IDE, ARM IOT development board,  STM programmer tool.
## Theory 
The full form of an ARM is an advanced reduced instruction set computer (RISC) machine, and it is a 32-bit processor architecture expanded by ARM holdings. The applications of an ARM processor include several microcontrollers as well as processors. The architecture of an ARM processor was licensed by many corporations for designing ARM processor-based SoC products and CPUs. This allows the corporations to manufacture their products using ARM architecture. Likewise, all main semiconductor companies will make ARM-based SOCs such as Samsung, Atmel, TI etc.

 
  
## Procedure:

1. Click on **STM32CubeIDE**, the following screen will appear:  
   <img src="https://user-images.githubusercontent.com/36288975/226189166-ac10578c-c059-40e7-8b80-9f84f64bf088.png" width="500">

2. Click on **File**, then click on **New STM32 Project**:  
   <img src="https://user-images.githubusercontent.com/36288975/226189215-2d13ebfb-507f-44fc-b772-02232e97c0e3.png" width="500">  
   <img src="https://user-images.githubusercontent.com/36288975/226189230-bf2d90dd-9695-4aaf-b2a6-6d66454e81fc.png" width="500">

3. Select the target to be programmed as shown below and click on **Next**:  
   <img src="https://user-images.githubusercontent.com/36288975/226189280-ed5dcf1d-dd8d-43ae-815d-491085f4863b.png" width="500">

4. Select the program name:  
   <img src="https://user-images.githubusercontent.com/36288975/226189316-09832a30-4d1a-4d4f-b8ad-2dc28f137711.png" width="500">

5. The corresponding .ioc file will be generated automatically:  
   <img src="https://user-images.githubusercontent.com/36288975/226189378-3abbdee2-0df6-470f-a3cd-79c74e3d3ad8.png" width="500">

6. Select the appropriate pins as GPIO, IN or OUT, USART, or required options, and configure:  
   <img src="https://user-images.githubusercontent.com/36288975/226189403-f7179f1a-3eae-4637-826b-ab4ec35ba1e1.png" width="500">  
   <img src="https://user-images.githubusercontent.com/36288975/226189425-2b2414ce-49b3-4b61-a260-c658cb2e4152.png" width="500">

7. Press `Ctrl + S`, and the C program will be generated automatically:  
   <img src="https://user-images.githubusercontent.com/36288975/226189443-8b43451d-0b14-47e4-a20b-cc09c6ad8458.png" width="500">  
   <img src="https://user-images.githubusercontent.com/36288975/226189450-85ffa969-2ffb-4788-81e5-72d60fdda0f1.png" width="500">

8. Edit the program as required:  
   <img src="https://user-images.githubusercontent.com/36288975/226189461-a573e62f-a109-4631-a250-a20925758fe0.png" width="500">

9. Use the **Project** menu and click **Build All**:  
   <img src="https://user-images.githubusercontent.com/36288975/226189554-3f7101ac-3f41-48fc-abc7-480bd6218dec.png" width="500">

10. Once the project is built:  
    <img src="https://user-images.githubusercontent.com/36288975/226189577-c61cc1eb-3990-4968-8aa6-aefffc766b70.png" width="500">

11. Click on the **Debug** option:  
    <img src="https://user-images.githubusercontent.com/36288975/226189625-37daa9a3-62e9-42b5-a5ce-2ac63345905b.png" width="500">

12. Connect the ARM board to the power supply and USB.

13. Check the execution of the output using the **Run** option.




## STM 32 CUBE PROGRAM :
```c
#include "main.h"
#include "stdbool.h"
bool button;
void led_blink();

void SystemClock_Config(void);
static void MX_GPIO_Init(void);
int main(void)
{
  HAL_Init();
  MX_GPIO_Init();
  while (1)
  {
	  led_blink();
  }
}

void led_blink()
{
	if (button==0)
	{
		HAL_GPIO_WritePin(GPIOA,GPIO_PIN_5,GPIO_PIN_SET);
		HAL_Delay(1000);
		HAL_GPIO_WritePin(GPIOA,GPIO_PIN_5,GPIO_PIN_RESET);
		HAL_Delay(1000);
	}
	else
	{
		HAL_GPIO_WritePin(GPIOA,GPIO_PIN_5,GPIO_PIN_RESET);
		HAL_Delay(1000);
	}
}
```



## Output:

### LED OFF:  
<img src="https://github.com/user-attachments/assets/24a59902-ab1a-486e-8c0b-603cc94f16d7" width="500">

### LED ON:  
<img src="https://github.com/user-attachments/assets/074ea7b7-c408-458e-913a-91f0d5fb168b" width="500">




## Layout of the Circuit:  
<img src="https://github.com/user-attachments/assets/cf0adecf-1d98-4339-b52d-e07aff529975" width="500">

 
## Result :
Interfacing a digital Input (Pushbutton ) with ARM microcontroller based IOT development is executed and the results are verified.
