# Restlez-Internship-Tasks

Details of Implementation:

1. GPIO Implementation:

Pin PA0 is configured as an output.

The LED connected to PA0 toggles every 500 ms.

Code:

HAL_GPIO_WritePin(GPIOA, GPIO_PIN_0, GPIO_PIN_RESET);
HAL_Delay(500);
HAL_GPIO_WritePin(GPIOA, GPIO_PIN_0, GPIO_PIN_SET);
HAL_Delay(500);



2. UART Implementation:

Configured using USART1 at 9600 baud rate.

Transmits the string "hello world."

Result: Displayed on the virtual terminal in Proteus.

Code:

unsigned char string[] = "hello world";
HAL_UART_Transmit(&huart1, string, 11, 0x500);



3. I2C Implementation:

Configured using I2C1 with a clock speed of 100 kHz and 7-bit addressing mode.

Ready for communication with external I2C devices.

Code:

hi2c1.Instance = I2C1;
hi2c1.Init.ClockSpeed = 100000;
hi2c1.Init.DutyCycle = I2C_DUTYCYCLE_2;
hi2c1.Init.OwnAddress1 = 0;
hi2c1.Init.AddressingMode = I2C_ADDRESSINGMODE_7BIT;
hi2c1.Init.DualAddressMode = I2C_DUALADDRESS_DISABLE;
hi2c1.Init.OwnAddress2 = 0;
hi2c1.Init.GeneralCallMode = I2C_GENERALCALL_DISABLE;
hi2c1.Init.NoStretchMode = I2C_NOSTRETCH_DISABLE;
if (HAL_I2C_Init(&hi2c1) != HAL_OK)
{
    Error_Handler();
}


Conclusion:
The GPIO successfully toggles the LED, UART displays "hello world" on the virtual terminal, and I2C is configured for communication. All functionalities were verified using Proteus simulation.
