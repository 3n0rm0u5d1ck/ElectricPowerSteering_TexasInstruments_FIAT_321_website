---
layout: default
title: I2cNxtr_Integration_Manual
nav_order: 3
parent: I2cNxtr
---
{% raw %}
[1 Dependencies [2](#dependencies)](#dependencies)

[1.1 SWCs [2](#swcs)](#swcs)

[1.2 Global Functions(Non RTE) to be provided to Integration Project
[2](#global-functionsnon-rte-to-be-provided-to-integration-project)](#global-functionsnon-rte-to-be-provided-to-integration-project)

[2 Configuration [3](#configuration)](#configuration)

[2.1 Build Time Config [3](#build-time-config)](#build-time-config)

[2.2 Configuration Files to be provided by Integration Project
[3](#configuration-files-to-be-provided-by-integration-project)](#configuration-files-to-be-provided-by-integration-project)

[2.2.1 Da Vinci Parameter Configuration Changes
[3](#da-vinci-parameter-configuration-changes)](#da-vinci-parameter-configuration-changes)

[2.2.2 DaVinci Interrupt Configuration Changes
[3](#davinci-interrupt-configuration-changes)](#davinci-interrupt-configuration-changes)

[2.2.3 Interrupt Enable/Disable Functions
[3](#interrupt-enabledisable-functions)](#interrupt-enabledisable-functions)

[2.2.4 Manual Configuration Changes
[4](#manual-configuration-changes)](#manual-configuration-changes)

[3 Integration [5](#integration)](#integration)

[3.1 Required Global Data Inputs
[5](#required-global-data-inputs)](#required-global-data-inputs)

[3.2 Required Global Data Outputs
[5](#required-global-data-outputs)](#required-global-data-outputs)

[3.3 Specific Include Path present
[5](#specific-include-path-present)](#specific-include-path-present)

[4 Runnable Scheduling [6](#runnable-scheduling)](#runnable-scheduling)

[5 Memory Mapping [7](#memory-mapping)](#memory-mapping)

[5.1 Mapping [7](#mapping)](#mapping)

[5.2 Usage [7](#usage)](#usage)

[5.3 Non RTE NvM Blocks [7](#non-rte-nvm-blocks)](#non-rte-nvm-blocks)

[5.4 RTE NvM Blocks [7](#rte-nvm-blocks)](#rte-nvm-blocks)

[6 Compiler Settings [7](#compiler-settings)](#compiler-settings)

[6.1 Preprocessor MACRO [7](#preprocessor-macro)](#preprocessor-macro)

[6.2 Optimization Settings
[7](#optimization-settings)](#optimization-settings)

[7 Revision Control Log
[8](#revision-control-log)](#revision-control-log)

# Dependencies

## SWCs

| Module | Required Feature |
|--------|------------------|
| None   |                  |

Note : Referencing the external components should be avoided in most
cases. Only in unavoidable circumstance external components should be
referred. Developer should track the references.

## Global Functions(Non RTE) to be provided to Integration Project

-   I2c_Init

-   I2c_Enable

-   I2c_Reset

-   I2c_SetupMasterTransmit

-   I2c_SetupMasterReceive

-   I2c_SwitchMasterReceive

-   I2c_SetCount

-   I2c_SetOwnAdd

-   I2c_SetSlaveAdd

-   I2c_SetFunctional

-   I2c_SetBaudrate

-   I2c_IsTxReady

-   I2c_SendByte

-   I2c_Send

-   I2c_IsRxReady

-   I2c_RxError

-   I2c_ReceiveByte

-   I2c_SetRecv

-   I2c_SetDirection

-   I2c_SetBit

-   I2c_GetBit

-   I2c_EnableNotification

-   I2c_DisableNotification

-   I2c_GenStartCond

-   I2c_GenStopCond

-   I2c_GetIntVect

-   I2c_GetStatus

-   I2c_SetStatus

# Configuration

## Build Time Config

| Modules | Notes |     |
|---------|-------|-----|
| None    |       |     |

##  [section]

## Configuration Files to be provided by Integration Project

### Da Vinci Parameter Configuration Changes

| Parameter | Notes | SWC |
|-----------|-------|-----|
| None      |       |     |

### DaVinci Interrupt Configuration Changes

| ISR Name | VIM \# | Priority Dependency | Notes                                                                    |
|-------------|--------|-----------------------|------------------------------|
| Isr_I2c  | 66     | None                | See comment below about enable/disable for very low priority interrupts. |

### Interrupt Enable/Disable Functions

Verify that interrupt 66 can be enabled and disabled in interrupts.c. It
was found that only interrupts up to 63 could be enabled and disabled
with current code. Below is a suggestion of how the enable function
should look:

And similarly for the disable function:

Additionally, EnableI2CInterrupt and DisableI2CInterrupt will need to be
defined in interrupts.c in a fashion similar to the other Enable\* and
Disable\* interrupts.

####  [section-1]

### Manual Configuration Changes

| Constant                 | Notes                                                   | SWC     |
|-----------------------------|----------------------------------|----------|
| D_COMMBUFFERSIZE_CNT_U08 | Transmit and receive buffer size in bytes.              | I2cNxtr |
| I2c_Notification         | Callback notification issued when I2C interrupt occurs. | I2cNxtr |
| D_I2CREG_STRCPTR         | Pointer to register structure containing I2C registers. | I2cNxtr |
| D_VCLK_HZ_F32            | VCLK frequency used when calculating I2C baud rate.     | I2cNxtr |

# Integration

## Required Global Data Inputs

None

## Required Global Data Outputs

None

## Specific Include Path present

Yes

# Runnable Scheduling 

This section specifies the required runnable scheduling.

| Init | Scheduling Requirements | Trigger |
|------|-------------------------|---------|
| None | None                    | N/A     |

| Runnable | Scheduling Requirements | Trigger |
|----------|-------------------------|---------|
| None     | None                    | N/A     |

**.**

# Memory Mapping

## Mapping

| Memory Section                            | Contents        | Notes |
|-------------------------------------------|-----------------|-------|
| I2CNXTR_START_SEC_VAR_CLEARED_UNSPECIFIED | I2cTransferType |       |
|                                           |                 |       |

\* Each …START_SEC… constant is terminated by a …STOP_SEC… constant as
specified in the AUTOSAR Memory Mapping requirements.

## Usage

| Feature | RAM | ROM |
|---------|-----|-----|
| None    |     |     |

Table 1: ARM Cortex R4 Memory Usage

## Non RTE NvM Blocks

| Block Name |
|------------|
| None       |

Note : Size of the NVM block if configured in developer

##  RTE NvM Blocks

| Block Name |
|------------|
| None       |

Note : Size of the NVM block if configured in developer

# Compiler Settings

##  Preprocessor MACRO

None

## Optimization Settings

None

##  [section-2]

# Revision Control Log

| **Rev \#** | **Change Description**     | **Date**  | **Author** |
|------------|----------------------------|-----------|------------|
| 1          | Initial component creation | 22-Aug-13 | Jared      |

{% endraw %}