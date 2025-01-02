---
layout: default
title: I2cNxtr_MDD
nav_order: 4
parent: I2cNxtr
---
{% raw %}
# Module -- I2C Nexteer [module----i2c-nexteer]

This document describes the software design and implementation of the
Nexteer inter-integrated circuit (I^2^C) driver for EA3.x applications.

# Equations for Register Settings

Depending on the type of device attached to the I^2^C bus different
register settings may be required. The following equations were used to
determine the module clock frequency and high and low times for the
required device that are documented in this MDD.

## Module Clock Frequency

The module clock frequency determines the frequency at which the I^2^C
module operates. The value in the prescale register (I2CPSC) is
programmable and divides the input clock to produce the module clock.
The module clock frequency must be between 6.7 MHz and 13.3 MHz for
proper operation of the I^2^C module. At the time this specification was
created, the input clock frequency is 80MHz.

$$ModuleClockFrequency = \frac{I2CInputClockFrequency}{(I2CPSC + 1)}\ $$

## Master Clock Frequency

The master clock frequency is the frequency that will be used on the SCL
pin of the TMS570 device when in master mode. Depending on the value of
the I2CPSC and the desired clock low (I2CCKL) and high (I2CCKH) times,
the mast clock frequency can be calculated by one of the two equations
below:

$$MasterClockFrequency = \frac{ModuleClockFrequency}{(I2CCKL + d) + (I2CCKH + d)}$$

$$MasterClockFrequency = \frac{I2CInputClockFrequency}{(I2CPSC + 1)*((I2CCKL + d) + (I2CCKH + d))}$$

Where *d* depends on:

| I2CPSC         | d   |
|----------------|-----|
| 0              | 7   |
| 1              | 6   |
| Greater than 1 | 5   |

#  Variable Data Dictionary

For details on module input / output variable, refer to the Data
Dictionary for the application. Input / output variable names are listed
here for reference.

| Module Inputs | Module Outputs |      |
|---------------|----------------|------|
| None          |                | None |

## Module Internal Variables

This section identifies the name, range and resolutions for module
specific data created by this module. If there are no range restrictions
on the variable, the term “FULL” is placed into the table for legal
range.

<table>
<colgroup>
<col style="width: 37%" />
<col style="width: 11%" />
<col style="width: 12%" />
<col style="width: 13%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Variable Name</th>
<th>Resolution</th>
<th><p>Legal Range</p>
<p>(min)</p></th>
<th><p>Legal Range</p>
<p>(max)</p></th>
<th>Software Segment</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>I2cNxtr_I2cTransfer_Cnt_M_str. Mode_Cnt_b32</td>
<td>1</td>
<td>0</td>
<td>0x10</td>
<td>I2CNXTR_START_SEC_VAR_CLEARED_UNSPECIFIED</td>
</tr>
<tr class="even">
<td>I2cNxtr_I2cTransfer_Cnt_M_str. Length_Cnt_u32</td>
<td>1</td>
<td>FULL</td>
<td>FULL</td>
<td>I2CNXTR_START_SEC_VAR_CLEARED_UNSPECIFIED</td>
</tr>
<tr class="odd">
<td>I2cNxtr_I2cTransfer_Cnt_M_str. DataPtr_Cnt_u08</td>
<td>1</td>
<td>FULL</td>
<td>FULL</td>
<td>I2CNXTR_START_SEC_VAR_CLEARED_UNSPECIFIED</td>
</tr>
</tbody>
</table>

### User defined typedef definition/declaration 

This section documents any user types uniquely used for the module.

<table>
<colgroup>
<col style="width: 37%" />
<col style="width: 24%" />
<col style="width: 16%" />
<col style="width: 11%" />
<col style="width: 11%" />
</colgroup>
<thead>
<tr class="header">
<th>Typedef Name</th>
<th>Element Name</th>
<th>User Defined Type</th>
<th><p>Legal Range</p>
<p>(min)</p></th>
<th><p>Legal Range</p>
<p>(max)</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>i2cctrlregs_t</td>
<td><p>OAR</p>
<p>IMR</p>
<p>STR</p>
<p>CLKL</p>
<p>CLKH</p>
<p>CNT</p>
<p>DRR</p>
<p>SAR</p>
<p>DXR</p>
<p>MDR</p>
<p>IVR</p>
<p>EMDR</p>
<p>PSC</p>
<p>PID11</p>
<p>PID12</p>
<p>DMAC</p>
<p>FUN</p>
<p>DIR</p>
<p>DIN</p>
<p>DOUT</p>
<p>SET</p>
<p>CLR</p>
<p>ODR</p>
<p>PD</p>
<p>PSL</p></td>
<td><p>uint32</p>
<p>uint32</p>
<p>uint32</p>
<p>uint32</p>
<p>uint32</p>
<p>uint32</p>
<p>uint32</p>
<p>uint32</p>
<p>uint32</p>
<p>uint32</p>
<p>uint32</p>
<p>uint32</p>
<p>uint32</p>
<p>uint32</p>
<p>uint32</p>
<p>uint32</p>
<p>uint32</p>
<p>uint32</p>
<p>uint32</p>
<p>uint32</p>
<p>uint32</p>
<p>uint32</p>
<p>uint32</p>
<p>uint32</p>
<p>uint32</p></td>
<td><p>0</p>
<p>0</p>
<p>0</p>
<p>0</p>
<p>0</p>
<p>0</p>
<p>0</p>
<p>0</p>
<p>0</p>
<p>0</p>
<p>0</p>
<p>0</p>
<p>0</p>
<p>0</p>
<p>0</p>
<p>0</p>
<p>0</p>
<p>0</p>
<p>0</p>
<p>0</p>
<p>0</p>
<p>0</p>
<p>0</p>
<p>0</p>
<p>0</p></td>
<td><p>1023</p>
<p>255</p>
<p>32767</p>
<p>65535</p>
<p>65535</p>
<p>65535</p>
<p>255</p>
<p>1023</p>
<p>255</p>
<p>65535</p>
<p>7</p>
<p>3</p>
<p>255</p>
<p>65535</p>
<p>255</p>
<p>3</p>
<p>1</p>
<p>3</p>
<p>3</p>
<p>3</p>
<p>3</p>
<p>3</p>
<p>3</p>
<p>3</p>
<p>3</p></td>
</tr>
<tr class="even">
<td>I2cTransferType</td>
<td><p>Mode_Cnt_b32</p>
<p>Length_Cnt_u32</p>
<p>DataPtr_Cnt_u08</p></td>
<td><p>uint32</p>
<p>uint32</p>
<p>*uint8</p></td>
<td><p>FULL</p>
<p>FULL</p>
<p>FULL</p></td>
<td><p>FULL</p>
<p>FULL</p>
<p>FULL</p></td>
</tr>
<tr class="odd">
<td>enum i2cMode</td>
<td><p>I2C_FD_FORMAT</p>
<p>I2C_START_BYTE</p>
<p>I2C_RESET_OUT</p>
<p>I2C_DLOOPBACK</p>
<p>I2C_REPEATMODE</p>
<p>I2C_10BIT_AMODE</p>
<p>I2C_TRANSMITTER</p>
<p>I2C_MASTER</p>
<p>I2C_STOP_COND</p>
<p>I2C_START_COND</p>
<p>I2C_FREE_RUN</p>
<p>I2C_NACK_MODE</p></td>
<td><p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p></td>
<td><p>0x0008</p>
<p>0x0010</p>
<p>0x0020</p>
<p>0x0040</p>
<p>0x0080</p>
<p>0x0100</p>
<p>0x0200</p>
<p>0x0400</p>
<p>0x0800</p>
<p>0x2000</p>
<p>0x4000</p>
<p>0x8000</p></td>
<td><p>0x0008</p>
<p>0x0010</p>
<p>0x0020</p>
<p>0x0040</p>
<p>0x0080</p>
<p>0x0100</p>
<p>0x0200</p>
<p>0x0400</p>
<p>0x0800</p>
<p>0x2000</p>
<p>0x4000</p>
<p>0x8000</p></td>
</tr>
<tr class="even">
<td>enum i2cBitCount</td>
<td><p>I2C_2_BIT</p>
<p>I2C_3_BIT</p>
<p>I2C_4_BIT</p>
<p>I2C_5_BIT</p>
<p>I2C_6_BIT</p>
<p>I2C_7_BIT</p>
<p>I2C_8_BIT</p></td>
<td><p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p></td>
<td><p>0x2</p>
<p>0x3</p>
<p>0x4</p>
<p>0x5</p>
<p>0x6</p>
<p>0x7</p>
<p>0x0</p></td>
<td><p>0x2</p>
<p>0x3</p>
<p>0x4</p>
<p>0x5</p>
<p>0x6</p>
<p>0x7</p>
<p>0x0</p></td>
</tr>
<tr class="odd">
<td>enum i2cIntFlags</td>
<td><p>I2C_AL_INT</p>
<p>I2C_NACK_INT</p>
<p>I2C_ARDY_INT</p>
<p>I2C_RX_INT</p>
<p>I2C_TX_INT</p>
<p>I2C_SCD_INT</p>
<p>I2C_AAS_INT</p>
<p>I2C_RECV_OVERRUN</p></td>
<td><p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p></td>
<td><p>0x0001</p>
<p>0x0002</p>
<p>0x0004</p>
<p>0x0008</p>
<p>0x0010</p>
<p>0x0020</p>
<p>0x0040</p>
<p>0x0800</p></td>
<td><p>0x0001</p>
<p>0x0002</p>
<p>0x0004</p>
<p>0x0008</p>
<p>0x0010</p>
<p>0x0020</p>
<p>0x0040</p>
<p>0x0800</p></td>
</tr>
<tr class="even">
<td>enum i2cStatFlags</td>
<td><p>I2C_AL</p>
<p>I2C_NACK</p>
<p>I2C_ARDY</p>
<p>I2C_RXRDY</p>
<p>I2C_TXRDY</p>
<p>I2C_SCD</p>
<p>I2C_ADDRZEROST</p>
<p>I2C_ADDRASSLV</p>
<p>I2C_XSMT</p>
<p>I2C_RXFULL</p>
<p>I2C_BUSBUSY</p>
<p>I2C_NACKMOD</p>
<p>I2C_SLAVEDIR</p></td>
<td><p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p>
<p>uint16</p></td>
<td><p>0x0001</p>
<p>0x0002</p>
<p>0x0004</p>
<p>0x0008</p>
<p>0x0010</p>
<p>0x0020</p>
<p>0x0100</p>
<p>0x0200</p>
<p>0x0400</p>
<p>0x0800</p>
<p>0x1000</p>
<p>0x2000</p>
<p>0x4000</p></td>
<td><p>0x0001</p>
<p>0x0002</p>
<p>0x0004</p>
<p>0x0008</p>
<p>0x0010</p>
<p>0x0020</p>
<p>0x0100</p>
<p>0x0200</p>
<p>0x0400</p>
<p>0x0800</p>
<p>0x1000</p>
<p>0x2000</p>
<p>0x4000</p></td>
</tr>
<tr class="odd">
<td>enum i2cDMA</td>
<td><p>I2C_TXDMA</p>
<p>I2C_RXDMA</p></td>
<td><p>uint16</p>
<p>uint16</p></td>
<td><p>0x20</p>
<p>0x10</p></td>
<td><p>0x20</p>
<p>0x10</p></td>
</tr>
<tr class="even">
<td>struct g_i2cTransfer</td>
<td><p>mode</p>
<p>length</p>
<p>*data</p></td>
<td><p>uint32</p>
<p>uint32</p>
<p>uint8</p></td>
<td><p>Full</p>
<p>Full</p>
<p>N/A</p></td>
<td><p>Full</p>
<p>Full</p>
<p>N/A</p></td>
</tr>
</tbody>
</table>

# Constant Data Dictionary

## Calibration Constants

This section lists the calibrations used by the module. For details on
calibration constants, refer to the Data Dictionary for the application.

| Constant Name |
|---------------|
| None          |

## Program(fixed) Constants

### Embedded Constants

All embedded constants whose values are provided in Eng units will be
evaluated to the equivalent counts by using the FPM_InitFixedPoint_m()
macro within the \#define statement.

#### Local

| Constant Name            | Resolution | Units  | Value |
|--------------------------|------------|--------|-------|
| D_CLKRESETPULSES_CNT_U08 | 1          | Counts | 18    |
| D_CLOCKPERIOD_US_U08     | 1          | uS     | 5     |

####  [section]

#### Global

This section lists the global constants used by the module. For details
on global constants, refer to the Data Dictionary for the application.

| Constant Name |
|---------------|
| None          |

### Module specific Lookup Tables Constants

(This is for lookup tables (arrays) with fixed values, same name as
other tables)

| Constant Name | Resolution | Value | Software Segment |
|---------------|------------|-------|------------------|
| None          |            |       |                  |

#  Functions/Macros used by the Sub-Modules 

## Library Functions / Macros 

The library and functions / Macros that are called by the various sub
modules are identified below,

1.  None

## Data Hiding Functions

1.  None

## Global Functions/Macros Defined by this Module

### I2C Init

|                      |                     |               |        |                   |                   |          |
|----------------|---------------------|----------|-------|--------|--------|-----|
| **Function Name**    | I2c_Init            | Type          | Dir.   | Min               | Max               | UTP Tol. |
| **Arguments Passed** | I2cRegPtr_Cnt_T_str | i2cctrlregs_t | In/Out | See section 2.1.1 | See section 2.1.1 |          |
| **Return Value**     | N/A                 |               |        |                   |                   |          |

#### Description

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/I2cNxtr/doc/mediax/media/image1.emf)

### I2C Enable

|                      |                     |               |        |                   |                   |          |
|----------------|---------------------|----------|--------|-------|-------|-----|
| **Function Name**    | I2c_Enable          | Type          | Dir.   | Min               | Max               | UTP Tol. |
| **Arguments Passed** | I2cRegPtr_Cnt_T_str | i2cctrlregs_t | In/Out | See section 2.1.1 | See section 2.1.1 |          |
| **Return Value**     | N/A                 |               |        |                   |                   |          |

#### Description

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/I2cNxtr/doc/mediax/media/image2.emf)

### I2C Reset

|                      |                     |               |        |                   |                   |          |
|----------------|---------------------|-----------|-------|--------|--------|-----|
| **Function Name**    | I2c_Reset           | Type          | Dir.   | Min               | Max               | UTP Tol. |
| **Arguments Passed** | I2cRegPtr_Cnt_T_str | i2cctrlregs_t | In/Out | See section 2.1.1 | See section 2.1.1 |          |
| **Return Value**     | N/A                 |               |        |                   |                   |          |

#### Description

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/I2cNxtr/doc/mediax/media/image3.emf)

### I2C Setup Master Transmit

|                      |                         |               |        |                   |                   |          |
|----------------|---------------------|----------|-------|--------|--------|-----|
| **Function Name**    | I2c_SetupMasterTransmit | Type          | Dir.   | Min               | Max               | UTP Tol. |
| **Arguments Passed** | I2cRegPtr_Cnt_T_str     | i2cctrlregs_t | In/Out | See section 2.1.1 | See section 2.1.1 |          |
|                      | SlaveAddress_Cnt_T_u08  | uint8         | In     | 0                 | 127               |          |
|                      | DataLength_Cnt_T_u16    | uint16        | In     | FULL              | FULL              |          |
| **Return Value**     | N/A                     |               |        |                   |                   |          |

#### Description

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/I2cNxtr/doc/mediax/media/image4.emf)

### I2C Setup Master Receive

|                      |                        |               |        |                   |                   |          |
|----------------|-----------------------|----------|------|--------|-------|-----|
| **Function Name**    | I2c_SetupMasterReceive | Type          | Dir.   | Min               | Max               | UTP Tol. |
| **Arguments Passed** | I2cRegPtr_Cnt_T_str    | i2cctrlregs_t | In/Out | See section 2.1.1 | See section 2.1.1 |          |
|                      | SlaveAddress_Cnt_T_u08 | uint8         | In     | 0                 | 127               |          |
|                      | DataLength_Cnt_T_u16   | uint16        | In     | FULL              | FULL              |          |
| **Return Value**     | N/A                    |               |        |                   |                   |          |

#### Description

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/I2cNxtr/doc/mediax/media/image5.emf)

### I2C Switch Master Receive

|                      |                         |               |        |                   |                   |          |
|----------------|-----------------------|----------|------|-------|--------|-----|
| **Function Name**    | I2c_SwitchMasterReceive | Type          | Dir.   | Min               | Max               | UTP Tol. |
| **Arguments Passed** | I2cRegPtr_Cnt_T_str     | i2cctrlregs_t | In/Out | See section 2.1.1 | See section 2.1.1 |          |
|                      | DataLength_Cnt_T_u16    | uint16        | In     | FULL              | FULL              |          |
| **Return Value**     | N/A                     |               |        |                   |                   |          |

#### Description

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/I2cNxtr/doc/mediax/media/image6.emf)

### I2C Set Count

|                      |                     |               |        |                   |                   |          |
|----------------|----------------------|---------|-------|--------|--------|-----|
| **Function Name**    | I2c_SetCount        | Type          | Dir.   | Min               | Max               | UTP Tol. |
| **Arguments Passed** | I2cRegPtr_Cnt_T_str | i2cctrlregs_t | In/Out | See section 2.1.1 | See section 2.1.1 |          |
|                      | Count_Cnt_T_u16     | uint16        | In     | 0                 | 65535             |          |
| **Return Value**     | N/A                 |               |        |                   |                   |          |

#### Description

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/I2cNxtr/doc/mediax/media/image7.emf)

### I2C Set Own Address

|                      |                     |               |        |                   |                   |          |
|----------------|-----------------------|----------|-------|-------|-------|-----|
| **Function Name**    | I2c_SetOwnAdd       | Type          | Dir.   | Min               | Max               | UTP Tol. |
| **Arguments Passed** | I2cRegPtr_Cnt_T_str | i2cctrlregs_t | In/Out | See section 2.1.1 | See section 2.1.1 |          |
|                      | Address_Cnt_T_u16   | uint16        | In     | 1                 | 127               |          |
| **Return Value**     | N/A                 |               |        |                   |                   |          |

#### Description

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/I2cNxtr/doc/mediax/media/image8.emf)

### I2C Set Slave Address

|                      |                     |               |        |                   |                   |          |
|----------------|----------------------|---------|-------|--------|--------|-----|
| **Function Name**    | I2c_SetSlaveAdd     | Type          | Dir.   | Min               | Max               | UTP Tol. |
| **Arguments Passed** | I2cRegPtr_Cnt_T_str | i2cctrlregs_t | In/Out | See section 2.1.1 | See section 2.1.1 |          |
|                      | Address_Cnt_T_u16   | uint16        | In     | 1                 | 127               |          |
| **Return Value**     | N/A                 |               |        |                   |                   |          |

#### Description

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/I2cNxtr/doc/mediax/media/image9.emf)

### I2C Set Functional

|                      |                     |               |        |                   |                   |          |
|----------------|-----------------------|----------|-------|-------|--------|-----|
| **Function Name**    | I2c_SetFunctional   | Type          | Dir.   | Min               | Max               | UTP Tol. |
| **Arguments Passed** | I2cRegPtr_Cnt_T_str | i2cctrlregs_t | In/Out | See section 2.1.1 | See section 2.1.1 |          |
|                      | Port_Cnt_T_u08      | Uint8         | In     | 0                 | 1                 |          |
| **Return Value**     | N/A                 |               |        |                   |                   |          |

#### Description

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/I2cNxtr/doc/mediax/media/image10.emf)

### I2C Set Baudrate

|                      |                     |               |        |                   |                   |          |
|----------------|----------------------|----------|-------|-------|-------|-----|
| **Function Name**    | I2c_SetBaudrate     | Type          | Dir.   | Min               | Max               | UTP Tol. |
| **Arguments Passed** | I2cRegPtr_Cnt_T_str | i2cctrlregs_t | In/Out | See section 2.1.1 | See section 2.1.1 |          |
|                      | Baud_Hz_T_u32       | uint32        | In     | 1                 | FULL              |          |
| **Return Value**     | N/A                 |               |        |                   |                   |          |

#### Description

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/I2cNxtr/doc/mediax/media/image11.emf)

### I2C Is TX Ready

|                      |                     |               |        |                   |                   |          |
|----------------|----------------------|---------|-------|--------|--------|-----|
| **Function Name**    | I2c_IsTxReady       | Type          | Dir.   | Min               | Max               | UTP Tol. |
| **Arguments Passed** | I2cRegPtr_Cnt_T_str | i2cctrlregs_t | In/Out | See section 2.1.1 | See section 2.1.1 |          |
| **Return Value**     | Ready_Cnt_T_lgc     | boolean       | Out    | FALSE             | TRUE              | N/A      |

#### Description

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/I2cNxtr/doc/mediax/media/image12.emf)

### I2C Send Byte

|                      |                     |               |        |                   |                   |          |
|----------------|------------------------|---------|-------|-------|-------|-----|
| **Function Name**    | I2c_SendByte        | Type          | Dir.   | Min               | Max               | UTP Tol. |
| **Arguments Passed** | I2cRegPtr_Cnt_T_str | i2cctrlregs_t | In/Out | See section 2.1.1 | See section 2.1.1 |          |
|                      | Byte_Cnt_T_u08      | uint8         | In     | FULL              | FULL              |          |
| **Return Value**     | N/A                 |               |        |                   |                   |          |

#### Description

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/I2cNxtr/doc/mediax/media/image13.emf)

### I2C Send

|                      |                     |               |        |                   |                   |          |
|----------------|-----------------------|----------|-------|-------|--------|-----|
| **Function Name**    | I2c_Send            | Type          | Dir.   | Min               | Max               | UTP Tol. |
| **Arguments Passed** | I2cRegPtr_Cnt_T_str | i2cctrlregs_t | In/Out | See section 2.1.1 | See section 2.1.1 |          |
|                      | Length_Cnt_T_u32    | uint32        | In     | FULL              | FULL              |          |
|                      | DataPtr_Cnt_T_u08   | \*uint8       | In     | FULL              | FULL              |          |
| **Return Value**     | N/A                 |               |        |                   |                   |          |

#### Description

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/I2cNxtr/doc/mediax/media/image14.emf)

### I2C Is RX Ready

|                      |                     |               |        |                   |                   |          |
|----------------|----------------------|---------|--------|-------|--------|-----|
| **Function Name**    | I2c_IsRxReady       | Type          | Dir.   | Min               | Max               | UTP Tol. |
| **Arguments Passed** | I2cRegPtr_Cnt_T_str | i2cctrlregs_t | In/Out | See section 2.1.1 | See section 2.1.1 |          |
| **Return Value**     | Ready_Cnt_T_lgc     | boolean       | Out    | FALSE             | TRUE              |          |

#### Description

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/I2cNxtr/doc/mediax/media/image15.emf)

### I2C RX Error

|                      |                     |               |        |                   |                   |          |
|---------------|------------------------|---------|------|-------|-------|-----|
| **Function Name**    | I2c_RxError         | Type          | Dir.   | Min               | Max               | UTP Tol. |
| **Arguments Passed** | I2cRegPtr_Cnt_T_str | i2cctrlregs_t | In/Out | See section 2.1.1 | See section 2.1.1 |          |
| **Return Value**     | Status_Cnt_T_b32    | uint32        | Out    | FULL              | FULL              |          |

#### Description

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/I2cNxtr/doc/mediax/media/image16.emf)

### I2C Receive Ready

|                      |                     |               |        |                   |                   |          |
|---------------|--------------------------|---------|-----|-------|-------|-----|
| **Function Name**    | I2c_ReceiveByte     | Type          | Dir.   | Min               | Max               | UTP Tol. |
| **Arguments Passed** | I2cRegPtr_Cnt_T_str | i2cctrlregs_t | In/Out | See section 2.1.1 | See section 2.1.1 |          |
| **Return Value**     | Data_Cnt_T_u08      | uint8         | Out    | FULL              | FULL              |          |

#### Description

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/I2cNxtr/doc/mediax/media/image17.emf)

### I2C Set Receive

|                      |                     |               |        |                   |                   |          |
|----------------|-----------------------|---------|-------|-------|--------|-----|
| **Function Name**    | I2c_SetRecv         | Type          | Dir.   | Min               | Max               | UTP Tol. |
| **Arguments Passed** | I2cRegPtr_Cnt_T_str | i2cctrlregs_t | In/Out | See section 2.1.1 | See section 2.1.1 |          |
|                      | Length_Cnt_T_u32    | uint32        | In     | FULL              | FULL              |          |
|                      | DataPtr_Cnt_T_u08   | \*uint8       | Out    | FULL              | FULL              |          |
| **Return Value**     | N/A                 |               |        |                   |                   |          |

#### Description

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/I2cNxtr/doc/mediax/media/image18.emf)

### I2C Set Direction

|                      |                     |               |        |                   |                   |          |
|----------------|------------------------|---------|-------|-------|-------|-----|
| **Function Name**    | I2c_SetDirection    | Type          | Dir.   | Min               | Max               | UTP Tol. |
| **Arguments Passed** | I2cRegPtr_Cnt_T_str | i2cctrlregs_t | In/Out | See section 2.1.1 | See section 2.1.1 |          |
|                      | Dir_Cnt_T_u08       | uint8         | In     | 0                 | 3                 |          |
| **Return Value**     | N/A                 |               |        |                   |                   |          |

#### Description

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/I2cNxtr/doc/mediax/media/image19.emf)

### I2C Set Bit

|                      |                     |               |        |                   |                   |          |
|----------------|---------------------|----------|-------|--------|--------|-----|
| **Function Name**    | I2c_SetBit          | Type          | Dir.   | Min               | Max               | UTP Tol. |
| **Arguments Passed** | I2cRegPtr_Cnt_T_str | i2cctrlregs_t | In/Out | See section 2.1.1 | See section 2.1.1 |          |
|                      | Bit_Cnt_T_u08       | uint8         | In     | 0                 | 1                 |          |
|                      | Value_Cnt_T_u08     | uint8         | In     | 0                 | 1                 |          |
| **Return Value**     | N/A                 |               |        |                   |                   |          |

#### Description

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/I2cNxtr/doc/mediax/media/image20.emf)

### I2C Get Bit

|                      |                     |               |        |                   |                   |          |
|----------------|-----------------------|----------|-------|--------|-------|-----|
| **Function Name**    | I2c_GetBit          | Type          | Dir.   | Min               | Max               | UTP Tol. |
| **Arguments Passed** | I2cRegPtr_Cnt_T_str | i2cctrlregs_t | In/Out | See section 2.1.1 | See section 2.1.1 |          |
|                      | Bit_Cnt_T_u08       | uint8         | In     | 0                 | 31                |          |
| **Return Value**     | Value_Cnt_T_u08     | uint8         | Out    | 0                 | 1                 |          |

#### Description

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/I2cNxtr/doc/mediax/media/image21.emf)

### I2C Enable Notification

|                      |                        |               |        |                   |                   |          |
|----------------|---------------------|----------|-------|--------|--------|-----|
| **Function Name**    | I2c_EnableNotification | Type          | Dir.   | Min               | Max               | UTP Tol. |
| **Arguments Passed** | I2cRegPtr_Cnt_T_str    | i2cctrlregs_t | In/Out | See section 2.1.1 | See section 2.1.1 |          |
|                      | Flags_Cnt_T_b32        | uint32        | In     | 0                 | 127               |          |
| **Return Value**     | N/A                    |               |        |                   |                   |          |

#### Description

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/I2cNxtr/doc/mediax/media/image22.emf)

### I2C Disable Notification

|                      |                         |               |        |                   |                   |          |
|----------------|-----------------------|----------|-------|-------|-------|-----|
| **Function Name**    | I2c_DisableNotification | Type          | Dir.   | Min               | Max               | UTP Tol. |
| **Arguments Passed** | I2cRegPtr_Cnt_T_str     | i2cctrlregs_t | In/Out | See section 2.1.1 | See section 2.1.1 |          |
|                      | Flags_Cnt_T_b32         | uint32        | In     | FULL              | FULL              |          |
| **Return Value**     | N/A                     |               |        |                   |                   |          |

#### Description

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/I2cNxtr/doc/mediax/media/image23.emf)

### I2C Generate Start Condition

|                      |                     |               |        |                   |                   |          |
|----------------|-----------------------|----------|-------|-------|--------|-----|
| **Function Name**    | I2c_GenStartCond    | Type          | Dir.   | Min               | Max               | UTP Tol. |
| **Arguments Passed** | I2cRegPtr_Cnt_T_str | i2cctrlregs_t | In/Out | See section 2.1.1 | See section 2.1.1 |          |
| **Return Value**     | N/A                 |               |        |                   |                   |          |

#### Description

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/I2cNxtr/doc/mediax/media/image24.emf)

### I2C Generate Stop Condition

|                      |                     |               |        |                   |                   |          |
|----------------|---------------------|-----------|-------|-------|--------|-----|
| **Function Name**    | I2c_GenStopCond     | Type          | Dir.   | Min               | Max               | UTP Tol. |
| **Arguments Passed** | I2cRegPtr_Cnt_T_str | i2cctrlregs_t | In/Out | See section 2.1.1 | See section 2.1.1 |          |
| **Return Value**     | N/A                 |               |        |                   |                   |          |

#### Description

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/I2cNxtr/doc/mediax/media/image25.emf)

### I2C Get Interrupt Vector

|                      |                     |               |        |                   |                   |          |
|----------------|---------------------|----------|-------|--------|--------|-----|
| **Function Name**    | I2c_GetIntVect      | Type          | Dir.   | Min               | Max               | UTP Tol. |
| **Arguments Passed** | I2cRegPtr_Cnt_T_str | i2cctrlregs_t | In/Out | See section 2.1.1 | See section 2.1.1 |          |
| **Return Value**     | Vector_Cnt_T_u08    | uint8         | Out    | 0                 | 7                 |          |

#### Description

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/I2cNxtr/doc/mediax/media/image26.emf)

### I2C Get Status

|                      |                     |               |        |                   |                   |          |
|----------------|-----------------------|----------|-------|-------|--------|-----|
| **Function Name**    | I2c_GetStatus       | Type          | Dir.   | Min               | Max               | UTP Tol. |
| **Arguments Passed** | I2cRegPtr_Cnt_T_str | i2cctrlregs_t | In/Out | See section 2.1.1 | See section 2.1.1 |          |
| **Return Value**     | Status_Cnt_T_u16    | uint16        | Out    | 0                 | 32767             |          |

#### Description

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/I2cNxtr/doc/mediax/media/image27.emf)

### I2C Set Status

|                      |                     |               |        |                   |                   |          |
|----------------|----------------------|----------|-------|-------|--------|-----|
| **Function Name**    | I2c_SetStatus       | Type          | Dir.   | Min               | Max               | UTP Tol. |
| **Arguments Passed** | I2cRegPtr_Cnt_T_str | i2cctrlregs_t | In/Out | See section 2.1.1 | See section 2.1.1 |          |
|                      | Status_Cnt_T_u16    | uint16        | In     | FULL              | FULL              |          |
| **Return Value**     | N/A                 |               |        |                   |                   |          |

#### Description

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/I2cNxtr/doc/mediax/media/image28.emf)

## Local Functions/Macros Used by this MDD only

None

# Software Module Implementation

## Runtime Environment (RTE) Initial Values

This section lists the initial values of data written by this module but
controlled by the RTE. After RTE initialization, the data in this table
will contain these values.

| Data | Value |
|------|-------|
| None |       |

## Initialization Functions

None

##  Periodic Functions

None

##  Fault Recovery Functions

None

##  Shutdown Functions

None

##  Interrupt Functions

### Isr: Isr_I2c

#### Design Rationale

None

#### Program Flow Start

Metrics_TaskStart(D_I2CNXT_CNT_U08)

#### I2c Notification

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/I2cNxtr/doc/mediax/media/image29.emf)

#### Program Flow End

Metrics_TaskEnd(D_I2CNXT_CNT_U08)

##  Serial Communication Functions

None

##  

# Execution Requirements

## Execution Sequence of the Module

(Describe in words relevant details about the execution sequence of the
different sub modules.)

## Execution Rates for sub-modules called by the Scheduler

This table serves as reference for the Scheduler design

| Function Name | Calling Frequency | System State(s) in which the function is called |
|--------------------------|-----------------|------------------------------|
| None          |                   |                                                 |

## Execution Requirements for Serial Communication Functions 

| Function Name | Sub-Module called by (Serial Comm Function Name) |
|---------------|--------------------------------------------------|
| None          |                                                  |

#  [section-2]

#  Memory Map Definition Requirements

## Sub Modules (Functions)

This table identifies the software segments for functions identified in
this module.

| Name of Sub Module      | Software Segment |
|-------------------------|------------------|
| I2c_Init                | N/A              |
| I2c_Enable              | N/A              |
| I2c_Reset               | N/A              |
| I2c_SetupMasterTransmit | N/A              |
| I2c_SetupMasterReceive  | N/A              |
| I2c_SwitchMasterReceive | N/A              |
| I2c_SetCount            | N/A              |
| I2c_SetOwnAdd           | N/A              |
| I2c_SetSlaveAdd         | N/A              |
| I2c_SetFunctional       | N/A              |
| I2c_SetBaudrate         | N/A              |
| I2c_IsTxReady           | N/A              |
| I2c_SendByte            | N/A              |
| I2c_Send                | N/A              |
| I2c_IsRxReady           | N/A              |
| I2c_RxError             | N/A              |
| I2c_ReceiveByte         | N/A              |
| I2c_SetRecv             | N/A              |
| I2c_SetDirection        | N/A              |
| I2c_SetBit              | N/A              |
| I2c_GetBit              | N/A              |
| I2c_EnableNotification  | N/A              |
| I2c_DisableNotification | N/A              |
| I2c_GenStartCond        | N/A              |
| I2c_GenStopCond         | N/A              |
| I2c_GetIntVect          | N/A              |
| I2c_GetStatus           | N/A              |
| I2c_SetStatus           | N/A              |

##  [section-3]

## Local Functions

This table identifies the software segments for local functions
identified in this module.

| Name of Sub Module | Software Segment |
|--------------------|------------------|
| None               |                  |

#  [section-4]

#  Known Issues / Limitations With Design

1.  None

#  Revision Control Log

|             |            |                                                                       |           |                     |
|------|------|--------------------------------------------|---------|---------|
| **Item \#** | **Rev \#** | **Change Description**                                                | **Date**  | **Author Initials** |
| 1           | 1          | Initial component creation                                            | 22-Aug-13 | Jared               |
| 2           | 2          | Add Metrics hook.                                                     | 7-Oct-13  | BWL                 |
| 3           | 3          | New enum is created and receiver overrun is checked when receive data | 24-Feb-14 | Rijvi               |
| 4           | 4          | Updated init code to add new bit-banged SCK strobe for A6836          | 3-Jun-14  | Jared               |
| 5           | 5          | Updated as per Unit Test findings.                                    | 24-Jul-14 | KPIT_SM             |

{% endraw %}