

# Release Notes for
# <mark>STM32F4xx CMSIS</mark>
Copyright &copy; 2017 STMicroelectronics\
    
[![ST logo](_htmresc/st_logo_2020.png)](https://www.st.com)

# Purpose

This driver provides the CMSIS device for the stm32f4xx products.


# Update History

<label for="collapse-section34" aria-hidden="true">V2.6.12 / 28-October-2026</label>
<div>

## Main Changes

- Default VTOR to the internal Flash base address if 'USER_VECT_TAB_ADDRESS' is not defined to ensure correct IRQ dispatch
- Add FLASH_SIZE define
- Add missing SYSCFG_CFGR2_PVDL bit definition in STM32F412xx CMSIS headers

</div>

<label for="collapse-section33" aria-hidden="true">V2.6.11 / 25-April-2025</label>
<div>

## Main Changes

- Fix CMSIS-DSP and CMSIS-NN files in CMSIS Core v5.9.0
- Allow redefinition of the macro 'VECT_TAB_OFFSET' externally from the IDE, makefile, or command line.
- Update definitions of USB_OTG_DIEPMSK_NAKM bit.
- Update the DMA_SxCR_CHSEL_x bit definitions to use bitwise shift operations.
- Rename FLASH_SR_SOP_XX bits to FLASH_SR_OPERR_XX.

</div>

<label for="collapse-section32" aria-hidden="true">V2.6.10 / 31-May-2024</label>
<div>

## Main Changes

- Add MCO2PRE[2:0] and MCO2[1:0] bits definition within CMSIS files.

</div>

<label for="collapse-section31" aria-hidden="true">V2.6.9 / 22-September-2022</label>
<div>			

## Main Changes

- Added new atomic register access macros in stm32f4xx.h file.
- Update FLASH_SCALE2_LATENCY4_FREQ value to 120MHz instead of 12MHz.
- Update the GCC startup file to be aligned to IAR/Keil IDE.
- STM32F410/412/413/423:
  - Fix wrong defined value for wake-up pin 3 (PWR_CSR_EWUP3).
  
</div>

<label for="collapse-section30" aria-hidden="true">V2.6.8 / 11-Fabruary-2022</label>
<div>			

## Main Changes

- All source files: update disclaimer to add reference to the new license agreement.
- Correct ETH bits definitions to be in line with naming used in the STM32F4 reference manual documents.
  
</div>

<label for="collapse-section29" aria-hidden="true">V2.6.7 / 16-July-2021</label>
<div>			

## Main Changes

- Add missing definition FLASH_CR_ERRIE to the CMSIS header file.
- Remove unsupported “GPIOF_BASE” and “GPIOG_BASE” defines from STM32F412Vx device.
- Add new atomic register access macros in stm32f4xx.h file.
- Add LSI maximum startup time datasheet value: LSI_STARTUP_TIME.
- Fix a typo in CMSIS STM32F4xx version macro (__STM32F4xx_CMSIS_VERSION).
  
</div>

<label for="collapse-section28" aria-hidden="true">V2.6.6 / 12-Fabruary-2021</label>
<div>			

## Main Changes

- system_stm32f4xx.c:
  - Protect Vector table modification following SRAM or FLASH preprocessor directive by a generic preprocessor directive : USER_VECT_TAB_ADDRESS
  - Update SystemInit_ExtMemCtl() API to initialize the tmpreg variable before each time out loop condition.
- Add License.md and Readme.md files required for GitHub publication
- Improve GCC startup files robustness.
- Fix wrong value for GPIO_MODER_MODE8_Msk and GPIO_MODER_MODE2_Pos.
- Update max number of host channels in FS for STM32F446:
  - Update USB_OTG_FS_HOST_MAX_CHANNEL_NBR value from 8 to 12.
- Add SMBDEN and SMBHEN bit definition for STM32F410Tx device.
  
</div>

<label for="collapse-section27" aria-hidden="true">V2.6.5 / 10-Fabruary-2020</label>
<div>			

## Main Changes

- All header files
  - Update to use new BSD License format
- MDK-ARM startup files
  - Update to fix invalid config wizard annotations
  
</div>

<label for="collapse-section26" aria-hidden="true">V2.6.4 / 06-December-2019</label>
<div>			

## Main Changes

- stm32f446xx.h file
  - Update to support HW flow control on UART4 and UART5 instances
- stm32f412xx.h, stm32f413xx.h and stm32f423xx.h files
  - Remove unused IS_USB_ALL_INSTANCE() assert macro
- All header files
  - Remove unused IS_TIM_SYNCHRO_INSTANCE() assert macro
- system_stm32f4xx.c file
  - Update SystemInit() API to don't reset RCC registers to its reset values
  
</div>

<label for="collapse-section25" aria-hidden="true">V2.6.3 / 08-Fabruary-2019</label>
<div>			

## Main Changes

- CRYP:
  - Update CMSIS devices with correct CRYP data input register name: DIN instead of DR
  - Add Bits definition for CRYP CR ALGOMODE AES GCM/CCM
- HASH:
  - Update HASH_DIGEST_TypeDef structure: resize the HR register
  - Remove MDMAT Bits definition
- TIM:
  - Add requires TIM assert macros:
   - IS_TIM_SYNCHRO_INSTANCE()
   - IS_TIM_CLOCKSOURCE_TIX_INSTANCE()
   - IS_TIM_CLOCKSOURCE_ITRX_INSTANCE()
- RCC
  - Add RCC_CSR_BORRSTF bits definition
- GPIO
  - Fix GPIO BRR bits definition
  - Adjust the GPIO present on STM32F412 devices
- SAI
  - Fix frame length in SAI_xFRCR_FSALL & SAI_xFRCR_FRL bits description
- USB:
  - Add missing Bits Definitions in USB_OTG_DOEPMSK register
   - USB_OTG_DOEPMSK_AHBERRM
   - USB_OTG_DOEPMSK_OTEPSPRM
   - USB_OTG_DOEPMSK_BERRM
   - USB_OTG_DOEPMSK_NAKM
   - USB_OTG_DOEPMSK_NYETM
  - Add missing Bits Definitions in USB_OTG_DIEPINT register
   - USB_OTG_DIEPINT_INEPNM
   - USB_OTG_DIEPINT_AHBERR
   - USB_OTG_DOEPINT_OUTPKTERR
   - USB_OTG_DOEPINT_NAK
   - USB_OTG_DOEPINT_STPKTRX
  - Add missing Bits Definitions in USB_OTG_DCFG register
   - USB_OTG_DCFG_XCVRDLY
   - USB_OTG_DCFG_ERRATIM
  - Update USB OTG max number of endpoints (6 FS and 9 HS instead of 5 and 8)
- I2C/FMPI2C
  - Align Bit naming for FMPI2C_CR1 register: FMPI2C_CR1_DFN--> FMPI2C_CR1_DNF
  - Add IS_SMBUS_ALL_INSTANCE() define
- DFSDM
  - Align Bit naming for DFSDM_FLTICR register: DFSDM_FLTICR_CLRSCSDF--> DFSDM_FLTICR_CLRSCDF
- PWR
  - Remove PWR_CSR_WUPP define: feature not available on STM32F469xx/479xx devices
  
</div>

<label for="collapse-section24" aria-hidden="true">V2.6.2 / 06-October-2017</label>
<div>			

## Main Changes

- Remove Date and Version from all header files
- USB_OTG register clean up: remove duplicated bits definitions
- stm32f401xc.h, stm32f401xe.h, stm32f411xe.h files
  - Remove BKPSRAM_BASE define: feature not available
- stm32f405xx.h, stm32f407xx.h files
  - Rename HASH_RNG_IRQn to RNG_IRQn: HASH instance not available 
- stm32f410xx.h, stm32f412xx.h, stm32f413xx.h,  stm32f423xx.h files
  - Add missing wake-up pins defines
- stm32f412cx.h files
  - Add support of USART3 instance
  
</div>

<label for="collapse-section23" aria-hidden="true">V2.6.1 / 14-Fabruary-2017</label>
<div>			

## Main Changes

- General updates in header files to support LL drivers
  - Align Bit naming for RCC_CSR register (ex: RCC_CSR_PADRSTF --> RCC_CSR_PINRSTF)
  - Add new defines for RCC features support:
   - RCC PLLI2S and RCC PLLSAI support
   - RCC PLLR I2S clock source and RCC PLLR system clock support
   - RCC SAI1A PLL source and RCC SAI1B PLL source support
   - RCC AHB2 support
  - Add RCC_DCKCFGR_PLLI2SDIVQ_X and  RCC_DCKCFGR_PLLSAIDIVQ_X bits definition
  - Add new defines for RCC_PLLI2SCFGR_RST_VALUE, RCC_PLLSAICFGR_RST_VALUE and RCC_PLLCFGR_RST_VALUE
  - Add new defines for RTC features support:
   - RTC Tamper 2 support
   - RTC AF2 mapping support
  - Align Bit naming for RTC_CR and RTC_TAFCR registers (ex: RTC_CR_BCK --> RTC_CR_BKP)
  - Add new define to manage RTC backup register number: RTC_BKP_NUMBER
  - Rename IS_UART_INSTANCE() macro to IS_UART_HALFDUPLEX_INSTANCE()
  - Add new defines to check LIN instance: IS_UART_LIN_INSTANCE
  - Remove USART6 instance from STM32F410Tx header file
  - Rename IS_I2S_ALL_INSTANCE_EXT() macro to IS_I2S_EXT_ALL_INSTANCEE()
  - Add IS_I2S_APB1_INSTANCE() macro to check if I2S instance mapping: API1 or APB2
  - Remove SPI_I2S_SUPPORT define for SPI I2S features support: I2S feature is available on all STM32F4xx devices
  - Add SPI_I2S_FULLDUPLEX_SUPPORT define for STM32F413xx/423xx devices
  - Align SPI_I2SCFGR bit naming: SPI_I2SCFGR_ASTRTEN bit is missing for STM32F412xx devices
  - Add new I2S_APB1_APB2_FEATURE define for STM32F4xx devices where I2S IP's are splited between RCC APB1 and APB2 interfaces
  - Add new FLASH_SR_RDERR define in FLASH_SR register
  - Add FLASH_OTP_BASE and  FLASH_OTP_END defnes to manage FLASH OPT area
  - Add bit definitions for ETH_MACDBGR register
  - Add new defines ADC1_COMMON_BASE and ADC123_COMMON_BASE to replace ADC_BASE define
  - Add new defines ADC1_COMMON and ADC123_COMMON to replace ADC define
  - Add new ADC macros: IS_ADC_COMMON_INSTANCE() and IS_ADC_MULTIMODE_MASTER_INSTANCE()
  - Add new defines for ADC multi mode features support
  - Add new ADC aliases ADC_CDR_RDATA_MST and ADC_CDR_RDATA_SLV for compatibilities with all STM32 Families
  - Update TIM CNT and ARR register mask on 32-bits
  - Add new TIM_OR_TI1_RMP define in TIM_OR register
  - Add new TIM macros to check TIM feature instance support:
   - IS_TIM_COUNTER_MODE_SELECT_INSTANCE()
   - IS_TIM_CLOCK_DIVISION_INSTANCE()
   - IS_TIM_COMMUTATION_EVENT_INSTANCE()
   - IS_TIM_OCXREF_CLEAR_INSTANCE()
   - IS_TIM_CLOCKSOURCE_ETRMODE1_INSTANCE()
   - IS_TIM_CLOCKSOURCE_ETRMODE2_INSTANCE()
   - IS_TIM_REPETITION_COUNTER_INSTANCE()
   - IS_TIM_ENCODER_INTERFACE_INSTANCE()
   - IS_TIM_HALL_SENSOR_INTERFACE_INSTANCE()
   - IS_TIM_BREAK_INSTANCE()
- CAN_IER register clean up: remove duplicated bit definitions
- USB_OTG register: fix the wrong defined values for USB_OTG_GAHBCFG bits
  
</div>

<label for="collapse-section22" aria-hidden="true">V2.6.0 / 04-November-2016</label>
<div>			

## Main Changes

- Add support of STM32F413xx and STM32F423xx devices 
  - Add "stm32f413xx.h" and "stm32f423xx.h" files
  - Add startup files  "startup_stm32f413xx.s" and "startup_stm32f423xx.s" for EWARM, MDK-ARM and SW4STM32 toolchains
  - Add Linker files "stm32f413xx_flash.icf", "stm32f413xx_sram.icf", "stm32f423xx_flash.icf" and "stm32f423xx_sram.icf" used within EWARM Workspaces
- All header files
  - Use _Pos and _Mask macro for all Bit Definitions
  - Update LPTIM_OR Bit Definition
  - Update the defined frequencies by scale for USB exported constants
  - Add UID_BASE, FLASHSIZE_BASE and PACKAGE_BASE defines
  - Add new define DAC_CHANNEL2_SUPPORT to manage DAC channel2 support
  - Use new DAC1 naming
  - Rename PWR_CSR_UDSWRDY define to PWR_CSR_UDRDY in PWR_CSR register
  - Align Bit naming for EXTI_IMR and EXTI_EMR registers (ex: EXTI_IMR_MR0 --> EXTI_IMR_IM0)
  - Add new EXTI_IMR_IM define in EXTI_IMR register
  - Add missing DMA registers definition
  - Add macro to check SMBUS instance support
- stm32f412cx.h, stm32f412zx.h, stm32f412vx.h, stm32f412rx.h files
  - Add missing SYSCFG register: CFGR2
- stm32f405xx.h, stm32f407xx.h, stm32f427xx.h, stm32f429xx.h files
  - Remove HASH_RNG_IRQn in IRQn_Type enumeration
- stm32f405xx.h, stm32f407xx.h, stm32f415xx.h, stm32f417xx.h files
  - Remove I2C FLTR register as not supported
- stm32f407xx.h, stm32f417xx.h, stm32f427xx.h, stm32f429xx.h, stm32f437xx.h, stm32f439xx.h, stm32f469xx.h, stm32f479xx.h files
  - Add missing Bit Definition of ETH_MACDBGR register
- system_stm32f4xx.c file
  - Add APBPrescTable declaration
  
</div>

<label for="collapse-section21" aria-hidden="true">V2.5.1 / 28-June-2016</label>
<div>			

## Main Changes

- stm32f412rx.h, stm32f412vx.h and stm32f412zx.h files:
  - Add QSPI1_V2_1L define to manage the QSPI DMA2 limitation
  
</div>

<label for="collapse-section20" aria-hidden="true">V2.5.0 / 22-April-2016</label>
<div>			

## Main Changes

- Add support of STM32F412Cx, STM32F412Rx, STM32F412Vx and STM32F412Zx devices
  - Add "stm32f412Cx.h", "stm32f412Rx.h", "stm32f412Vx.h" and "stm32f412Zx.h" files
  - Add startup files  "startup_stm32f412cx.s", "startup_stm32f412rx.s", "startup_stm32f412vx.s" and "startup_stm32f412zx.s" for EWARM, MDK-ARM and SW4STM32 toolchains
  - Add Linker files "stm32f412cx_flash.icf", "stm32f412cx_sram.icf", "stm32f412rx_flash.icf", "stm32f412rx_sram.icf", "stm32f412vx_flash.icf", "stm32f412vx_sram.icf", "stm32f412zx_flash.icf" and "stm32f412zx_sram.icf" used within EWARM Workspaces
- Header files for all STM32 devices
  - Remove uint32_t cast and keep only Misra Cast (U) to avoid two types cast duplication
  - Correct some bits definition to be in line with naming used in the Reference Manual
   - WWDG_CR_Tx changed to WWDG_CR_T_x
   - WWDG_CFR_Wx changed to WWDG_CFR_W_x
   - WWDG_CFR_WDGTBx changed to WWDG_CFR_WDGTB_x
- stm32f407xx.h, stm32f417xx.h, stm32f427xx.h, stm32f429xx.h, stm32f437xx.h, stm32f439xx.h, stm32f446xx.h, stm32f469xx.h, stm32f479xx.h files
  - Correct some bits definition to be in line with naming used in the Reference Manual
   - DCMI_RISR_x changed to DCMI_RIS_x
   - DCMI_RISR_OVF_RIS changed to DCMI_RIS_OVR_RIS
   - DCMI_IER_OVF_IE changed to DCMI_IER_OVR_IE
- stm32f427xx.h, stm32f429xx.h, stm32f437xx.h, stm32f439xx.h, stm32f469xx.h, stm32f479xx.h, stm32f446xx.h files
  - Correct some bits definition to be in line with naming used in the Reference Manual
   - SAI_xFRCR_FSPO changed to SAI_xFRCR_FSPOL
  - Rename IS_SAI_BLOCK_PERIPH to IS_SAI_ALL_INSTANCE
- stm32f410cx.h, stm32f410rx.h, stm32f410tx.h files and stm32f446xx.h
  - Remove FMPI2C_CR1_SWRST and FMPI2C_CR1_WUPEN Bit definition for I2C_CR1 register
- stm32f407xx.h, stm32f417xx.h, stm32f427xx.h, stm32f437xx.h, stm32f439xx.h, stm32f469xx.h, stm32f479xx.h files
  - Add missing bits definitions for DMA2D_CR, DMA2D_FGPFCCR, DMA2D_BGPFCCR, DMA2D_OPFCCR registers
- stm32f401xc.h, stm32f401xe.h, stm32f411xe.h files
  - Add missing RCC_DCKCFGR register in RCC_TypeDef structure
  - Add missing Bit definition for RCC_DCKCFGR register
- system_stm32f4xx.c
  - Update SystemInit_ExtMemCtl() API to fix delay optimization problem with GCC compiler: index variable is declared as volatile 
- stm32f4xx.h
  - Rename __STM32F4xx_CMSIS_DEVICE_VERSION_xx defines to __STM32F4_CMSIS_VERSION_xx (MISRA-C 2004 rule 5.1)
  
</div>

<label for="collapse-section19" aria-hidden="true">V2.4.3 / 29-January-2016</label>
<div>			

## Main Changes

- Header file for all STM32 devices
  - Rename ADC overrun flags definitions : ADC_CSR_DOVR1, ADC_CSR_DOVR2 and ADC_CSR_DOVR3 are replaced respectively by ADC_CSR_OVR1, ADC_CSR_OVR2 and ADC_CSR_OVR3 to be aligned with reference manuals
  - Add missing bits definitions for DAC : DAC_CR_DMAUDRIE1 and DAC_CR_DMAUDRIE2
  - Update CMSIS driver to be compliant with MISRA C 2004 rule 10.6
  - Remove the double definition of USB_OTG_HS_MAX_IN_ENDPOINTS and add a new one for  USB_OTG_HS_MAX_OUT_ENDPOINTS
- stm32f446xx.h, stm32f469xx.h, stm32f479xx.h files 
  - Change the bit definition value of QUADSPI_CR_FTHRES
- stm32f446xx.h, stm32f469xx.h, stm32f479xx.h, stm32f429xx.h, stm32f439xx.h files
  - Rename the LTDC_GCR_DTEN to LTDC_GCR_DEN in order to be aligned with the reference manual
  - Rename DCMI_MISR bit definitions to DCMI_MIS
  - Rename DCMI_ICR_OVF_ISC to DCMI_ICR_OVR_ISC
  - Add missing bits definitions for DCMI_ESCR, DCMI_ESUR, DCMI_CWSTRT, DCMI_CWSIZE, DCMI_DR registers
- stm32f407xx.h, stm32f417xx.h, stm32f427xx.h, stm32f437xx.h files
  - Rename DCMI_MISR bit definitions to DCMI_MIS
  - Rename DCMI_ICR_OVF_ISC to DCMI_ICR_OVR_ISC
  - Add missing bits definitions for DCMI_ESCR, DCMI_ESUR, DCMI_CWSTRT, DCMI_CWSIZE, DCMI_DR registers
- stm32f410cx.h, stm32f410rx.h, stm32f410tx.h files
  - Update the LPTIM SNGSTRT defined value
- stm32f427xx.h, stm32f429xx.h, stm32f437xx.h, stm32f439xx.h, stm32f469xx.h, stm32f479xx.h files
  - Rename the DMA2D_IFSR bit definitions to DMA2D_IFCR
- stm32f427xx.h, stm32f429xx.h, stm32f437xx.h, stm32f439xx.h, stm32f469xx.h, stm32f479xx.h, stm32f446xx.h files 
  - Correct a wrong value of SAI_xCR2_CPL definition bit 
  
</div>

<label for="collapse-section18" aria-hidden="true">V2.4.2 / 13-November-2015</label>
<div>			

## Main Changes

- system_stm32f4xx.c file
  - update SystemInit_ExtMemCtl() function implementation to allow the possibility of simultaneous use of DATA_IN_ExtSRAM and DATA_IN_ExtSDRAM
- stm32f4xx.h file
  - add symbols for STM32F411xC devices
- stm32f405xx.h, stm32f407xx.h, stm32f415xx.h, stm32f417xx.h files
  - add FSMC_BCRx_CPSIZE bits definitions
  - remove FSMC_BWTRx_CLKDIV and FSMC_BWTRx_DATLAT bits definitions
- stm32f429xx.h, stm32f427xx.h, stm32f437xx.h files
  - add FMC_BCRx_CPSIZE bits definitions
  - remove FMC_BWTRx_CLKDIV and FMC_BWTRx_DATLAT bits definitions
- stm32f446xx.h, stm32f469xx.h and stm32f479xx.h
  - update USB_OTG_GlobalTypeDef registers structure to remove ADP control registers
  - add USB_OTG_DOEPMSK_OTEPSPRM and USB_OTG_DOEPINT_OTEPSPR bits definitions
  - Remove ADP related bits definitions
  - add IS_PCD_ALL_INSTANCE() and IS_HCD_ALL_INSTANCE() macros
  
</div>

<label for="collapse-section17" aria-hidden="true">V2.4.1 / 09-October-2015</label>
<div>			

## Main Changes

- "stm32f469xx.h", "stm32f479xx.h"
  - Update bits definition for DSI_WPCR and DSI_TCCR registers
  
</div>

<label for="collapse-section16" aria-hidden="true">V2.4.0 / 14-August-2015</label>
<div>			

## Main Changes

- Add support of STM32F469xx and STM32F479xx devices
  - Add "stm32f469xx.h" and "stm32f479xx.h" files
  - Add startup files  "startup_stm32f469xx.s" and "startup_stm32f479xx.s" for EWARM, MDK-ARM and SW4STM32 toolchains
  - Add Linker files "stm32f469xx_flash.icf", "stm32f469xx_sram.icf", "stm32f479xx_flash.icf" and "stm32f479xx_sram.icf" used within EWARM Workspaces
- Add support of STM32F410xx devices
  - Add "stm32f410cx.h", "stm32f410tx.h" and "stm32f410rx.h" files
  - Add startup files  "startup_stm32f410cx.s", "startup_stm32f410rx.s" and "startup_stm32f410tx.s" for EWARM, MDK-ARM and SW4STM32 toolchains
  - Add Linker files "stm32f410cx_flash.icf", "stm32f410cx_sram.icf", "stm32f410rx_flash.icf", "stm32f410tx_sram.icf", "stm32f410tx_flash.icf",  and "stm32f410rx_sram.icf" used within EWARM Workspaces

</div>

<label for="collapse-section15" aria-hidden="true">V2.3.2 / 26-June-2015</label>
<div>			

## Main Changes

- "stm32f405xx.h", "stm32f407xx.h", "stm32f415xx.h" and "stm32f417xx.h"
  - Update FSMC_BTRx_DATAST and FSMC_BWTRx_DATAST (where x can be 1, 2, 3 and 4) mask on 8bits instead of 4bits
- "stm32f427xx.h", "stm32f437xx.h", "stm32f429xx.h" and "stm32f439xx.h"
  - Update the defined mask value for SAI_xSR_FLVL_2
- "stm32f415xx.h", "stm32f417xx.h", "stm32f437xx.h" and "stm32f439xx.h"
  - HASH alignement with bits namming used in documentation
   - Rename HASH_IMR_DINIM to HASH_IMR_DINIE
   - Rename HASH_IMR_DCIM to HASH_IMR_DCIE
   - Rename HASH_STR_NBW to HASH_STR_NBW
- system_stm32f4xx.c
  - Remove __IO on constant table declaration
  - Implement workaround to cover RCC limitation regarding peripheral enable delay
  - SystemInit_ExtMemCtl() update GPIO configuration when external SDRAM is used 

</div>

<label for="collapse-section14" aria-hidden="true">V2.3.1 / 03-April-2015</label>
<div>			

## Main Changes

- Header file for all STM32 devices
  - Update SRAM2, SRAM3 and BKPSRAM Bit-Banding base address defined values
  - Keep reference to SRAM3 only for STM32F42xx and STM32F43xx devices
  - Remove CCMDATARAM_BB_BASE: the CCM Data RAM region is not accessible via Bit-Banding
  - Update the RTC_PRER_PREDIV_S defined value to 0x00007FFF instead of 0x00001FFF

</div>

<label for="collapse-section13" aria-hidden="true">V2.3.0 / 02-March-2015</label>
<div>			

## Main Changes

- Add support of STM32F446xx devices
  - Add "stm32f446xx.h" file
  - Add startup file "startup_stm32f446xx.s" for EWARM, MDK-ARM and TrueSTUDIO toolchains
  - Add Linker files "stm32f446xx_flash.icf" and "stm32f446xx_sram.icf" used within EWARM Workspaces
- Header file for all STM32 devices
  - Add missing bits definition in the EXTI IMR, EMR, RTSR, FTSR, SWIER and PR registers
  - Update RCC_AHB1RSTR_OTGHRST bit definition
  - Update PWR_CR_VOS bits definition for STM32F40xx and STM32F41xx devices
  - update SAI_xCR1_MCKDIV bit definition

</div>

<label for="collapse-section12" aria-hidden="true">V2.2.0 / 15-December-2014</label>
<div>			

## Main Changes

- stm32f4xx.h
  - Add new constant definition STM32F4
- system_stm32f4xx.c
  - Fix SDRAM configuration in SystemInit_ExtMemCtl(): change RowBitsNumber from 11 to 12 (for MT48LC4M32B2 available on STM324x9I_EVAL board)
- Header file for all STM32 devices
  - Add missing bits definition for CAN, FMC and USB peripherals
  - GPIO_TypeDef: change the BSRR register definition, the two 16-bits definition BSRRH and BSRRL are merged in a single 32-bits definition BSRR

</div>

<label for="collapse-section11" aria-hidden="true">V2.1.0 / 19-June-2014</label>
<div>			

## Main Changes

- Add support of STM32F411xExx devices
  - Add "stm32f411xe.h" file
  - Add startup file "startup_stm32f411xx.s" for EWARM, MDK-ARM and TrueSTUDIO toolchains
- All header files
  - Add missing defines for GPIO LCKR Register
  - Add defines for memories base and end addresses: FLASH, SRAM, BKPSRAM and CCMRAM.
  - Add the following aliases for IRQ number and handler definition to ensure compatibility across the product lines of STM32F4 Series;
    - example for STM32F405xx.h

      #define FMC_IRQn              FSMC_IRQn
      #define FMC_IRQHandler     FSMC_IRQHandler
	  
	- and for STM32F427xx.h

      #define FSMC_IRQn            FMC_IRQn
      #define FSMC_IRQHandler   FMC_IRQHandler
	  
- "stm32f401xc.h" and "stm32f401xe.h": update to be in line with latest version of the Reference manual
  - Remove RNG registers structures and the corresponding bit definitions
  - Remove any occurrence to RNG (clock enable, clock reset,…)
  - Add the following bit definition for PWR CR registerAdd the following bit definition for PWR CR register
    - #define  PWR_CR_ADCDC1      ((uint32_t)0x00002000)
	- #define  PWR_CR_LPLVDS      ((uint32_t)0x00000400)
	- #define  PWR_CR_MRLVDS      ((uint32_t)0x00000800)
- "stm32f427xx.h", "stm32f437xx.h", "stm32f429xx.h" and "stm32f439xx.h"
  - Add a new legacy bit definition for PWR to be in line with latest version of the Reference manual
    - #define  PWR_CR_LPUDS        PWR_CR_LPLVDS
	- #define  PWR_CR_MRUDS      PWR_CR_MRLVDS
- Update startup files for EWARM toolchain to cope with compiler enhancement of the V7.10 version
- system_stm32f4xx.c
  - Remove dependency vs. the HAL, to allow using this file without the need to have the HAL drivers
    - Include stm32f4xx.h instead of stm32f4xx_hal.h
	- Add definition of HSE_VALUE and HSI_VALUE, if they are not yet defined in the compilation scope (these values are defined in stm32f4xx_hal_conf).
  - Use “__IO const” instead of “__I”, to avoid any compilation issue when __cplusplus switch is defined

</div>

<label for="collapse-section10" aria-hidden="true">V2.0.0 / 18-Fabruary-2014</label>
<div>			

## Main Changes

- Update based on STM32Cube specification
- This version and later has to be used only with STM32CubeF4 based development
  
</div>

<label for="collapse-section9" aria-hidden="true">V1.3.0 / 08-November-2013</label>
<div>			

## Main Changes

- Add support of STM32F401xExx devices
- Update startup files "startup_stm32f401xx.s" for EWARM, MDK-ARM, TrueSTUDIO and Ride toolchains: Add SPI4 interrupt handler entry in the vector table
  
</div>

<label for="collapse-section8" aria-hidden="true">V1.2.1 / 19-September-2013</label>
<div>			

## Main Changes

- system_stm32f4xx.c : Update FMC SDRAM configuration (RBURST mode activation)
- Update startup files "startup_stm32f427_437xx.s" and "startup_stm32f429_439xx.s"  for TrueSTUDIO and Ride toolchains and maintain the old name of startup files for legacy purpose

</div>

<label for="collapse-section7" aria-hidden="true">V1.2.0 / 11-September-2013</label>
<div>			

## Main Changes

- Add support of STM32F429/439xx and STM32F401xCxx devices
- Update definition of STM32F427/437xx devices : extension of the features to include system clock up to 180MHz, dual bank Flash, reduced STOP Mode current, SAI, PCROP, SDRAM and DMA2D
- stm32f4xx.h
  - Add the following device defines :
    - "#define STM32F40_41xxx" for all STM32405/415/407/417xx devices
	- "#define STM32F427_437xx" for all STM32F427/437xx devices
	- "#define STM32F429_439xx" for all STM32F429/439xx devices
	- "#define STM32F401xx" for all STM32F401xx devices
  - Maintain the old device define for legacy purpose
  - Update IRQ handler enumeration structure to support all STM32F4xx Family devices.
- Add new startup files "startup_stm32f40_41xxx.s","startup_stm32f427_437xx.s", "startup_stm32f429_439xx.s" and "startup_stm32f401xx.s" for all toolchains and maintain the old name for startup files for legacy purpose
- system_stm32f4xx.c
  - Update the system configuration to support all STM32F4xx Family devices.  

</div>

<label for="collapse-section6" aria-hidden="true">V1.1.0 / 11-January-2013</label>
<div>			

## Main Changes

- Official release for STM32F427x/437x devices.
- stm32f4xx.h
  - Update product define: replace "#define STM32F4XX" by "#define STM32F40XX" for STM32F40x/41x devices
  - Add new product define: "#define STM32F427X" for STM32F427x/437x devices.
- Add new startup files "startup_stm32f427x.s" for all toolchains
- rename startup files "startup_stm32f4xx.s" by "startup_stm32f40xx.s" for all toolchains
- system_stm32f4xx.c
  - Prefetch Buffer enabled
  - Add reference to STM32F427x/437x devices and STM324x7I_EVAL board
  - SystemInit_ExtMemCtl() function
    - Add configuration of missing FSMC address and data lines
	- Change memory type to SRAM instead of PSRAM (PSRAM is available only on STM324xG-EVAL RevA) and update timing values

</div>

<label for="collapse-section5" aria-hidden="true">V1.0.2 / 05-March-2012</label>
<div>			

## Main Changes

- All source files: license disclaimer text update and add link to the License file on ST Internet.

</div>

<label for="collapse-section4" aria-hidden="true">V1.0.1 / 28-December-2011</label>
<div>			

## Main Changes

- All source files: update disclaimer to add reference to the new license agreement
- stm32f4xx.h
  - Correct bit definition: RCC_AHB2RSTR_HSAHRST changed to RCC_AHB2RSTR_HASHRST

</div>

<label for="collapse-section3" aria-hidden="true">V1.0.0 / 30-September-2011</label>
<div>

## Main Changes

- First official release for STM32F40x/41x devices
- Add startup file for TASKING toolchain
- system_stm32f4xx.c: driver's comments update

</div>

<label for="collapse-section2" aria-hidden="true">V1.0.0RC2 / 26-September-2011</label>
<div>

## Main Changes

- Official version (V1.0.0) Release Candidate2 for STM32F40x/41x devices
- stm32f4xx.h
  - Add define for Cortex-M4 revision __CM4_REV
  - Correct RCC_CFGR_PPRE2_DIV16 bit (in RCC_CFGR register) value to 0x0000E000
  - Correct some bits definition to be in line with naming used in the Reference Manual (RM0090)
    - GPIO_OTYPER_IDR_x changed to GPIO_IDR_IDR_x
	- GPIO_OTYPER_ODR_x changed to GPIO_ODR_ODR_x
	- SYSCFG_PMC_MII_RMII changed to SYSCFG_PMC_MII_RMII_SEL
	- RCC_APB2RSTR_SPI1 changed to RCC_APB2RSTR_SPI1RST
	- DBGMCU_APB1_FZ_DBG_IWDEG_STOP changed to DBGMCU_APB1_FZ_DBG_IWDG_STOP
	- PWR_CR_PMODE changed to PWR_CR_VOS
	- PWR_CSR_REGRDY changed to PWR_CSR_VOSRDY
	- Add new define RCC_AHB1ENR_CCMDATARAMEN
	- Add new defines SRAM2_BASE, CCMDATARAM_BASE and BKPSRAM_BASE
  - GPIO_TypeDef structure: in the comment change AFR[2] address mapping to 0x20-0x24 instead of 0x24-0x28
- system_stm32f4xx.c
  - SystemInit(): add code to enable the FPU
  - SetSysClock(): change PWR_CR_PMODE by PWR_CR_VOS
  - SystemInit_ExtMemCtl(): remove commented values
- startup (for all compilers)
  - Delete code used to enable the FPU (moved to system_stm32f4xx.c file)
  - File’s header updated
  
</div>

<label for="collapse-section1" aria-hidden="true">V1.0.0RC1 / 25-August-2011</label>
<div>

## Main Changes

- Official version (V1.0.0) Release Candidate1 for STM32F4xx devices

</div>


For complete documentation on <mark>STM32 Microcontrollers</mark> ,
visit: [http://www.st.com/STM32](http://www.st.com/STM32)