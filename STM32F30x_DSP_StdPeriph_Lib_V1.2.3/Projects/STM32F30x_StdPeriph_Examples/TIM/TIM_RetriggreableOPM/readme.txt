/**
  @page TIM_RetriggerableOPM TIM Retrigerrable OPM
 
  @verbatim
  ******************** (C) COPYRIGHT 2015 STMicroelectronics *******************
  * @file    TIM/TIM_RetriggerableOPM/readme.txt 
  * @author  MCD Application Team
  * @version V1.1.2
  * @date    14-August-2015
  * @brief   TIM Retrigerrable OPM Example Description.
  ******************************************************************************
  *
  * Licensed under MCD-ST Liberty SW License Agreement V2, (the "License");
  * You may not use this file except in compliance with the License.
  * You may obtain a copy of the License at:
  *
  *        http://www.st.com/software_license_agreement_liberty_v2
  *
  * Unless required by applicable law or agreed to in writing, software 
  * distributed under the License is distributed on an "AS IS" BASIS, 
  * WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
  * See the License for the specific language governing permissions and
  * limitations under the License.
  *   
  ******************************************************************************
   @endverbatim

@par Example Description 

This example shows how to use the TIM peripheral to generate a Retrigerrable One pulse Mode 
after a Rising edge of an external signal is received in Timer Input pin.

TIM2CLK = SystemCoreClock, we want to get TIM2 counter clock at 36 MHz:
  - Prescaler = (TIM2CLK / TIM2 counter clock) - 1

SystemCoreClock is set to 72 MHz.

The Autoreload value is 65535 (TIM2->ARR), so the maximum frequency value to 
trigger the TIM2 input is 36000000/65535 = 549.3 Hz.

The TIM2 is configured as follows: 
The Retrigerrable One Pulse mode is used, the external signal is connected to TIM2 CH2 pin (PA.01), 
the rising edge is used as active edge, the One Pulse signal is output on TIM2_CH1 (PA.00).

The TIM_Pulse defines the One Pulse value, the pulse value is fixed to:
Retrigerrable One Pulse value = TIM_Period/TIM2 counter clock 
                              = 65535 / 36000000 = 1.8 ms.
 
@par Directory contents 

  - TIM/TIM_RetriggerableOPM/stm32f30x_conf.h    Library Configuration file
  - TIM/TIM_RetriggerableOPM/stm32f30x_it.c      Interrupt handlers
  - TIM/TIM_RetriggerableOPM/stm32f30x_it.h      Interrupt handlers header file
  - TIM/TIM_RetriggerableOPM/main.c              Main program
  - TIM/TIM_RetriggerableOPM/system_stm32f30x.c  stm32f30x system source file
  
@note The "system_stm32f30x.c" is generated by an automatic clock configuration 
      system and can be easily customized to your own configuration. 
      To select different clock setup, use the "STM32F30x_Clock_Configuration_V1.0.0.xls" 
      provided with the AN4152 package available on <a href="http://www.st.com/internet/mcu/family/141.jsp">  ST Microcontrollers </a>
    
@par Hardware and Software environment

  - This example runs on STM32F303xC and STM32F303xE Devices.
  
  - This example has been tested with STMicroelectronics STM32303C-EVAL (STM32F30x)
    evaluation board and can be easily tailored to any other supported device 
    and development board.

  - STM32303C-EVAL Set-up
    - Connect the external signal to the TIM2_CH2 pin (PA.01)
    - Connect the TIM2_CH1 (PA.00) pin to an oscilloscope to monitor the waveform.

@par How to use it ? 

In order to make the program work, you must do the following :
 - Copy all source files from this example folder to the template folder under
   Projects\STM32F30x_StdPeriph_Templates
 - Open your preferred toolchain 
 - Rebuild all files and load your image into target memory
 - Run the example
    
 * <h3><center>&copy; COPYRIGHT STMicroelectronics</center></h3>
 */
