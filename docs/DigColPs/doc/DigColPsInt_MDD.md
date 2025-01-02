---
layout: default
title: DigColPsInt_MDD
nav_order: 5
parent: DigColPs
---
{% raw %}
# Module -- Digital Column Position Sensor (I2C) Interface [module----digital-column-position-sensor-i2c-interface]

# High-Level Description

This module is responsible for the transport of sensor data between the
I2C peripheral and the DigColPs Component. This module accomplishes this
task by providing a number of interface functions. The functions handle
the complexities of making request and handling the underlying
interrupts to present the periodic task in the DigColPs module with the
requested data on the next iteration.

# Figures

## Diagram – Function Data Sharing

See DigColPs_MDD for sequence diagram and interaction between this
module, the DigColPs module and the physical sensor.

#  Variable Data Dictionary

For details on module input / output variable, refer to the Data
Dictionary for the application. Input / output variable names are listed
here for reference.

| Module Inputs | Module Outputs |                                     |
|---------------|----------------|-------------------------------------|
| Type_Cnt_u08  |                | CommFaults_Cnt_b08                  |
|               |                | DataType_Cnt_u08                    |
|               |                | ColSnsrData_Cnt_u16                 |
|               |                | SpurSnsrData_Cnt_u16                |
|               |                | DigColPsInt_I2CHwCustData_Uls_M_u16 |

## Module Internal Variables

This section identifies the name, range and resolutions for module
specific data created by this module. If there are no range restrictions
on the variable, the term “FULL” is placed into the table for legal
range.

<table>
<colgroup>
<col style="width: 39%" />
<col style="width: 11%" />
<col style="width: 9%" />
<col style="width: 8%" />
<col style="width: 32%" />
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
<td>DigColPsInt_CurrentStepNo_Cnt_M_enum</td>
<td>1</td>
<td>0</td>
<td>36</td>
<td>DIGCOLPSINT_START_SEC_VAR_CLEARED_UNSPECIFIED</td>
</tr>
<tr class="even">
<td>DigColPsInt_InitialTime_mS_M_u32</td>
<td>1</td>
<td>0</td>
<td>FULL</td>
<td>DIGCOLPSINT_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="odd">
<td>DigColPsInt_ColSnsrData_Cnt_M_u16</td>
<td>1</td>
<td>0</td>
<td>65535</td>
<td>DIGCOLPSINT_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="even">
<td>DigColPsInt_SpurSnsrData_Cnt_M_u16</td>
<td>1</td>
<td>0</td>
<td>65535</td>
<td>DIGCOLPSINT_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="odd">
<td>DigColPsInt_ColSnsrErrData_Cnt_D_u16</td>
<td>1</td>
<td>0</td>
<td>FULL</td>
<td>DIGCOLPSINT_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="even">
<td>DigColPsInt_ColSnsrExtErrData_Cnt_D_u16</td>
<td>1</td>
<td>0</td>
<td>FULL</td>
<td>DIGCOLPSINT_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="odd">
<td>DigColPsInt_ColSnsrCheckStatData_Cnt_D_u16</td>
<td>1</td>
<td>0</td>
<td>FULL</td>
<td>DIGCOLPSINT_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="even">
<td>DigColPsInt_SpurSnsrErrData_Cnt_D_u16</td>
<td>1</td>
<td>0</td>
<td>FULL</td>
<td>DIGCOLPSINT_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="odd">
<td>DigColPsInt_SpurSnsrExtErrData_Cnt_D_u16</td>
<td>1</td>
<td>0</td>
<td>FULL</td>
<td>DIGCOLPSINT_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="even">
<td>DigColPsInt_SpurSnsrCheckStatData_Cnt_D_u16</td>
<td>1</td>
<td>0</td>
<td>FULL</td>
<td>DIGCOLPSINT_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="odd">
<td>DigColPsInt_CurrentSlave_Cnt_M_u08</td>
<td>1</td>
<td>0</td>
<td>127</td>
<td>DIGCOLPSINT_START_SEC_VAR_CLEARED_8</td>
</tr>
<tr class="even">
<td>DigColPsInt_RecvdDataType_Cnt_M_u08</td>
<td>1</td>
<td>0</td>
<td>5</td>
<td>DIGCOLPSINT_START_SEC_VAR_CLEARED_8</td>
</tr>
<tr class="odd">
<td>DigColPsInt_Buffer_Cnt_M_u08[]</td>
<td>1</td>
<td>0</td>
<td>255</td>
<td>DIGCOLPSINT_START_SEC_VAR_CLEARED_8</td>
</tr>
<tr class="even">
<td>DigColPsInt_PrevReqDataType_Cnt_M_u08</td>
<td>1</td>
<td>0</td>
<td>5</td>
<td>DIGCOLPSINT_START_SEC_VAR_CLEARED_8</td>
</tr>
<tr class="odd">
<td>DigColPsInt_TransactionCnt_Cnt_M_u08</td>
<td>1</td>
<td>0</td>
<td>255</td>
<td>DIGCOLPSINT_START_SEC_VAR_CLEARED_8</td>
</tr>
<tr class="even">
<td>DigColPsInt_PrevTransactionCnt_Cnt_M_u0 8</td>
<td>1</td>
<td>0</td>
<td>255</td>
<td>DIGCOLPSINT_START_SEC_VAR_CLEARED_8</td>
</tr>
<tr class="odd">
<td>DigColPsInt_InitFailedOnce_Cnt_M_lgc</td>
<td>N/A</td>
<td>FALSE</td>
<td>TRUE</td>
<td>DIGCOLPSINT_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
<tr class="even">
<td>DigColPsInt_BusBusySeqError_Cnt_M_lgc</td>
<td>N/A</td>
<td>FALSE</td>
<td>TRUE</td>
<td>DIGCOLPSINT_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
<tr class="odd">
<td>DigColPsInt_NackOccured_Cnt_M_lgc</td>
<td>N/A</td>
<td>FALSE</td>
<td>TRUE</td>
<td>DIGCOLPSINT_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
<tr class="even">
<td>DigColPsInt_SkipRegisterWrite_Cnt_M_lgc</td>
<td>N/A</td>
<td>FALSE</td>
<td>TRUE</td>
<td>DIGCOLPSINT_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
<tr class="odd">
<td>DigColPsInt_RecvOverrunError_Cnt_M_lgc</td>
<td>N/A</td>
<td>FALSE</td>
<td>TRUE</td>
<td>DIGCOLPSINT_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
<tr class="even">
<td>DigColPsInt_SensInitialized_Cnt_M_lgc</td>
<td>N/A</td>
<td>FALSE</td>
<td>TRUE</td>
<td>DIGCOLPSINT_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
<tr class="odd">
<td>DigColPsInt_I2CHwCustData_Uls_M_u16</td>
<td>1</td>
<td>0</td>
<td>511</td>
<td>DIGCOLPSINT_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="even">
<td>DigColPsInt_I2CHwIncompleteCustData_Uls_M_u16</td>
<td>1</td>
<td>0</td>
<td>255</td>
<td>DIGCOLPSINT_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="odd">
<td>DigColPsInt_AttempOccurForCustDatRead_Cnt_M_u08</td>
<td>1</td>
<td>0</td>
<td>11</td>
<td>DIGCOLPSINT_START_SEC_VAR_CLEARED_8</td>
</tr>
<tr class="even">
<td>DigColPsInt_CmdFailOccurred_Cnt_M_lgc</td>
<td>N/A</td>
<td>FALSE</td>
<td>TRUE</td>
<td>DIGCOLPSINT_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
<tr class="odd">
<td>DigColPsInt_ColCustDatFound_Cnt_M_lgc</td>
<td>N/A</td>
<td>FALSE</td>
<td>TRUE</td>
<td>DIGCOLPSINT_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
<tr class="even">
<td>DigColPsInt_SpurCustDatFound_Cnt_M_lgc</td>
<td>N/A</td>
<td>FALSE</td>
<td>TRUE</td>
<td>DIGCOLPSINT_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
</tbody>
</table>

### User defined typedef definition/declaration 

This section documents any user types uniquely used for the module.

<table style="width:100%;">
<colgroup>
<col style="width: 20%" />
<col style="width: 44%" />
<col style="width: 13%" />
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
<td>CommStepType</td>
<td><p>INIT_NOT_INITIALIZED</p>
<p>INIT_SENSOR1_READERROR_SETREG</p>
<p>INIT_SENSOR1_READERROR_READ</p>
<p>INIT_SENSOR1_READEXTERR_SETREG</p>
<p>INIT_SENSOR1_READEXTERR_READ</p>
<p>INIT_SENSOR1_SENDCMD</p>
<p>INIT_SENSOR1_CHECKSTAT_SETREG</p>
<p>INIT_SENSOR1_CHECKSTAT_READ</p>
<p>INIT_SENSOR2_READERROR_SETREG</p>
<p>INIT_SENSOR2_READERROR_READ</p>
<p>INIT_SENSOR2_READEXTERR_SETREG</p>
<p>INIT_SENSOR2_READEXTERR_READ</p>
<p>INIT_SENSOR2_SENDCMD</p>
<p>INIT_SENSOR2_CHECKSTAT_SETREG</p>
<p>INIT_SENSOR2_CHECKSTAT_READ</p>
<p>INIT_SENSOR1_EXTREADADDRREG_SENDCMD</p>
<p>INIT_SENSOR1_EXTREADCTRLREG_SENDCMD</p>
<p>INIT_SENSOR1_DUMMY_SEND,</p>
<p>INIT_SENSOR1_DUMMY_READ,</p>
<p>INIT_SENSOR2_EXTREADADDRREG_SENDCMD</p>
<p>INIT_SENSOR2_EXTREADCTRLREG_SENDCMD</p>
<p>INIT_SENSOR2_DUMMY_SEND,</p>
<p>INIT_SENSOR2_DUMMY_READ,</p>
<p>INIT_SENSOR1_EXTREADCTRLREG_SETREG</p>
<p>INIT_SENSOR1_EXTREADCTRLREG_READ</p>
<p>INIT_SENSOR2_EXTREADCTRLREG_SETREG</p>
<p>INIT_SENSOR2_EXTREADCTRLREG_READ</p>
<p>INIT_SENSOR1_EXTREADDATREG_SETREG</p>
<p>INIT_SENSOR1_EXTREADDATREG_READ</p>
<p>INIT_SENSOR2_EXTREADDATREG_SETREG</p>
<p>INIT_SENSOR2_EXTREADDATREG_READ</p>
<p>INIT_COMPLETE</p>
<p>READ_SENSOR1_SETREG</p>
<p>READ_SENSOR1_GETDATA</p>
<p>READ_SENSOR2_SETREG</p>
<p>READ_SENSOR2_GETDATA</p>
<p>READ_COMPLETE</p></td>
<td><p>uint8</p>
<p>uint8</p>
<p>uint8</p>
<p>uint8</p>
<p>uint8</p>
<p>uint8</p>
<p>uint8</p>
<p>uint8</p>
<p>uint8</p>
<p>uint8</p>
<p>uint8</p>
<p>uint8</p>
<p>uint8</p>
<p>uint8</p>
<p>uint8</p>
<p>uint8</p>
<p>uint8</p>
<p>uint8</p>
<p>uint8</p>
<p>uint8</p>
<p>uint8</p>
<p>uint8</p>
<p>uint8</p>
<p>uint8</p>
<p>uint8</p>
<p>uint8</p>
<p>uint8</p>
<p>uint8</p>
<p>uint8</p>
<p>uint8</p>
<p>uint8</p>
<p>uint8</p>
<p>uint8</p>
<p>uint8</p>
<p>uint8</p>
<p>uint8</p>
<p>uint8</p></td>
<td><p>0</p>
<p>1</p>
<p>2</p>
<p>3</p>
<p>4</p>
<p>5</p>
<p>6</p>
<p>7</p>
<p>8</p>
<p>9</p>
<p>10</p>
<p>11</p>
<p>12</p>
<p>13</p>
<p>14</p>
<p>15</p>
<p>16</p>
<p>17</p>
<p>18</p>
<p>19</p>
<p>20</p>
<p>21</p>
<p>22</p>
<p>23</p>
<p>24</p>
<p>25</p>
<p>26</p>
<p>27</p>
<p>28</p>
<p>29</p>
<p>30</p>
<p>31</p>
<p>32</p>
<p>33</p>
<p>34</p>
<p>35</p>
<p>36</p></td>
<td><p>0</p>
<p>1</p>
<p>2</p>
<p>3</p>
<p>4</p>
<p>5</p>
<p>6</p>
<p>7</p>
<p>8</p>
<p>9</p>
<p>10</p>
<p>11</p>
<p>12</p>
<p>13</p>
<p>14</p>
<p>15</p>
<p>16</p>
<p>17</p>
<p>18</p>
<p>19</p>
<p>20</p>
<p>21</p>
<p>22</p>
<p>23</p>
<p>24</p>
<p>25</p>
<p>26</p>
<p>27</p>
<p>28</p>
<p>29</p>
<p>30</p>
<p>31</p>
<p>32</p>
<p>33</p>
<p>34</p>
<p>35</p>
<p>36</p></td>
</tr>
</tbody>
</table>

# Constant Data Dictionary

## Calibration Constants

This section lists the calibrations used by the module. For details on
calibration constants, refer to the Data Dictionary for the application.

| Constant Name                      |
|------------------------------------|
| k_ColSensorI2CAddress_Cnt_u08      |
| k_I2CHWInitTransactionTime_Sec_f32 |
| k_SpurSensorI2CAddress_Cnt_u08     |

## Program(fixed) Constants

### Embedded Constants

All embedded constants whose values are provided in Eng units will be
evaluated to the equivalent counts by using the FPM_InitFixedPoint_m()
macro within the \#define statement.

#### Local

| Constant Name                       | Resolution | Units | Value          |
|-------------------------------------|------------|-------|----------------|
| D_COLSENSOR_CNT_U08                 | 1          | Cnt   | 0              |
| D_SPURSENSOR_CNT_U08                | 1          | Cnt   | 1              |
| D_CLEARSTATUSBITS_CNT_U16           | 1          | Cnt   | 0x0007         |
| D_RESETCMD_CNT_U16                  | 1          | Cnt   | 0x0746         |
| D_EXTREADADDRREGCMD_CNT_U16         | 1          | Cnt   | 0x0307         |
| D_EXTREADCTRLREGCMD_CNT_U16         | 1          | Cnt   | 0x8000         |
| D_NACKOCCURRED_CNT_U08              | 1          | Cnt   | 2              |
| D_BBSEQERR_CNT_U08                  | 1          | Cnt   | 4              |
| D_TRANSNOTCOMP_CNT_U08              | 1          | Cnt   | 16             |
| D_ANGLEDATA_CNT_U08                 | 1          | Cnt   | 1              |
| D_NONE_CNT_U08                      | 1          | Cnt   | 0x00           |
| D_ANGLEREG_CNT_U08                  | 1          | Cnt   | 0x20           |
| D_CONTROLREG_CNT_U08                | 1          | Cnt   | 0x1E           |
| D_ERRORREG_CNT_U08                  | 1          | Cnt   | 0x24           |
| D_EXTERRORREG_CNT_U08               | 1          | Cnt   | 0x26           |
| D_STATUSREG_CNT_U08                 | 1          | Cnt   | 0x22           |
| D_RECVOVERRUNERR_CNT_U08            | 1          | Cnt   | 0x08           |
| D_SENSINITDELAY_MS_U08              | 1          | mS    | 32             |
| D_CMDFAILED_CNT_U08                 | 1          | Cnt   | 0x20           |
| D_EXTREADADDRREG_CNT_U08            | 1          | Cnt   | 0x0A           |
| D_EXTREADCTRLREG_CNT_U08            | 1          | Cnt   | 0x0C           |
| D_EXTREADDATREG_CNT_U08             | 1          | Cnt   | 0x0E           |
| D_MAXATTEMPTSFORCUSTDATREAD_CNT_U08 | 1          | Cnt   | 10             |
| D_SENSINITNOTDONE_CNT_U08           | 1          | Cnt   | 1\<\<7U (0x80) |
| D_SECTOMILLSEC_CNT_F32              | 1          | Cnt   | 1000.0F        |

####  [section]

#### Global

This section lists the global constants used by the module. For details
on global constants, refer to the Data Dictionary for the application.

| Constant Name |
|---------------|
| None          |
|               |

### Module specific Lookup Tables Constants

(This is for lookup tables (arrays) with fixed values, same name as
other tables)

<table style="width:100%;">
<colgroup>
<col style="width: 32%" />
<col style="width: 11%" />
<col style="width: 40%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>Constant Name</th>
<th>Resolution</th>
<th>Value</th>
<th>Software Segment</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>T_DataRegisters_Cnt_u08[6]</td>
<td>1</td>
<td><p>D_NONE_CNT_U08,</p>
<p>D_ANGLEREG_CNT_U08,</p>
<p>D_CONTROLREG_CNT_U08,</p>
<p>D_ERRORREG_CNT_U08,</p>
<p>D_EXTERRORREG_CNT_U08,</p>
<p>D_STATUSREG_CNT_U08,</p>
<p>D_EXTREADADDRREG_CNT_U08,</p>
<p>D_EXTREADCTRLREG_CNT_U08,</p>
<p>D_EXTREADDATREG_CNT_U08</p></td>
<td>DIGCOLPSINT_START_SEC_CONST_8</td>
</tr>
</tbody>
</table>

#  Functions/Macros used by the Sub-Modules 

## Library Functions / Macros 

The library and functions / Macros that are called by the various sub
modules are identified below,

1.  None

## Data Hiding Functions

1.  None

## Global Functions/Macros Defined by this Module

### Initialize

|                      |                  |      |      |     |     |          |
|----------------------|------------------|------|------|-----|-----|----------|
| **Function Name**    | DigColPsInt_Init | Type | Dir. | Min | Max | UTP Tol. |
| **Arguments Passed** | None             |      |      |     |     |          |
| **Return Value**     | None             |      |      |     |     |          |

#### Description

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/DigColPs/doc/mediax/media/image1.emf)

### Get Data

|                      |                           |        |      |      |      |          |
|----------------|-----------------------------|-------|------|------|------|-----|
| **Function Name**    | DigColPsInt_GetData       | Type   | Dir. | Min  | Max  | UTP Tol. |
| **Arguments Passed** | ColSnsrDataPtr_Cnt_T_u16  | uint16 | Out  | FULL | FULL |          |
|                      | SpurSnsrDataPtr_Cnt_T_u16 | uint16 | Out  | FULL | FULL |          |
|                      | DataTypePtr_Cnt_T_u08     | uint8  | Out  | 0    | 5    |          |
| **Return Value**     | CommFaults_Cnt_T_b08      | uint8  | Out  | 0    | 16   | 0        |

#### Description

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/DigColPs/doc/mediax/media/image2.emf)

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/DigColPs/doc/mediax/media/image3.emf)

### Start Request

|                      |                          |       |      |     |     |          |
|----------------|-----------------------------|-------|------|------|------|-----|
| **Function Name**    | DigColPsInt_StartRequest | Type  | Dir. | Min | Max | UTP Tol. |
| **Arguments Passed** | Type_Cnt_T_u08           | uint8 | Out  | 0   | 5   |          |
| **Return Value**     | None                     |       |      |     |     |          |

#### Description

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/DigColPs/doc/mediax/media/image4.emf)

### Interrupt Notification

|                      |                                   |        |      |     |     |          |
|----------------|-----------------------------|-------|------|------|------|-----|
| **Function Name**    | DigColPsInt_InterruptNotification | Type   | Dir. | Min | Max | UTP Tol. |
| **Arguments Passed** | Flags_Cnt_T_b16                   | uint16 | In   | 1   | 64  |          |
| **Return Value**     | None                              |        |      |     |     |          |

#### Design Rationale

The interrupt notification function needs to be setup by the integrator
to be called by the Isr_I2C interrupt service inside of the I2cNxtr
component through the use of the I2cNxtr_Cfg.h header file. A template
for that header file can be found in the I2cNxtr includes directory.

In the FDD rev.005 the timeout requirement for ‘Customer Data’ read was
5 to 10 ms. Instead of timeout it is implemented by counting the ‘Number
of Attempts’ occurred to read ‘Customer Data’, because it speeds up the
interrupt execution time. ‘Number of Attempts’ required to fulfill the
same timeout operation is determined in the following calculation.

Number of bits sends and receives by the master to determine whether the
‘Customer Data’ is ready to read is 47bits.

> So for 100Kb baud speed total time required to check control register
> data for both column and spur sensors is (47\*2)/100K = 0.94 ms
>
> Therefore for 5 ms timeout ‘Number of Attempts’ occurred = 5/0.94 =
> 5.32
>
> Similarly for 10 ms timeout ‘Number of Attempts’ occurred = 10/0.94 =
> 10.64

Number **10** is chosen in this implementation

#### Notification Processing

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/DigColPs/doc/mediax/media/image5.emf)

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/DigColPs/doc/mediax/media/image6.emf)

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/DigColPs/doc/mediax/media/image7.emf)

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/DigColPs/doc/mediax/media/image8.emf)

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/DigColPs/doc/mediax/media/image9.emf)

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/DigColPs/doc/mediax/media/image10.emf)

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/DigColPs/doc/mediax/media/image11.emf)

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/DigColPs/doc/mediax/media/image12.emf)

### Get Cust Data

|                      |                                     |        |      |     |     |          |
|----------------|-----------------------------|-------|------|------|------|-----|
| **Function Name**    | DigColPsInt_GetCustData             | Type   | Dir. | Min | Max | UTP Tol. |
| **Arguments Passed** | None                                |        |      |     |     |          |
| **Return Value**     | DigColPsInt_I2CHwCustData_Uls_M_u16 | Uint16 | Out  | 0   | 511 | 0        |

#### Description

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/DigColPs/doc/mediax/media/image13.emf)

## Local Functions/Macros Used by this MDD only

### Setup Write - Data

|                      |                    |        |      |      |      |          |
|----------------------|--------------------|--------|------|------|------|----------|
| **Function Name**    | SetupWriteData     | Type   | Dir. | Min  | Max  | UTP Tol. |
| **Arguments Passed** | Register_Cnt_T_u08 | uint8  | In   | 0    | 127  |          |
|                      | Data_Cnt_T_u16     | uint16 | In   | FULL | FULL |          |
| **Return Value**     | None               |        |      |      |      |          |

#### Description

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/DigColPs/doc/mediax/media/image14.emf)

### Setup Write - Register

|                      |                    |       |      |     |     |          |
|----------------------|--------------------|-------|------|-----|-----|----------|
| **Function Name**    | SetupWriteRegister | Type  | Dir. | Min | Max | UTP Tol. |
| **Arguments Passed** | Register_Cnt_T_u08 | uint8 | In   | 0   | 127 |          |
| **Return Value**     | None               |       |      |     |     |          |

#### Description

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/DigColPs/doc/mediax/media/image15.emf)

### Setup Read

|                      |           |      |      |     |     |          |
|----------------------|-----------|------|------|-----|-----|----------|
| **Function Name**    | SetupRead | Type | Dir. | Min | Max | UTP Tol. |
| **Arguments Passed** | None      |      |      |     |     |          |
| **Return Value**     | None      |      |      |     |     |          |

#### Description

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/DigColPs/doc/mediax/media/image16.emf)

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

### None [none]

##  Serial Communication Functions

None

##  

# Execution Requirements

## Execution Sequence of the Module

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

| Name of Sub Module                | Software Segment |
|-----------------------------------|------------------|
| DigColPsInt_Init                  | N/A              |
| DigColPsInt_GetData               | N/A              |
| DigColPsInt_StartRequest          | N/A              |
| DigColPsInt_InterruptNotification | N/A              |
| DigColPsInt_GetCustData           | N/A              |

##  [section-3]

## Local Functions

This table identifies the software segments for local functions
identified in this module.

| Name of Sub Module | Software Segment |
|--------------------|------------------|
| None               |                  |

#  [section-4]

#  Known Issues / Limitations With Design

1.  INLINE functions in GlobalMacro.h are not unit tested

#  Revision Control Log

<table style="width:100%;">
<colgroup>
<col style="width: 6%" />
<col style="width: 6%" />
<col style="width: 64%" />
<col style="width: 11%" />
<col style="width: 11%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Item #</strong></td>
<td><strong>Rev #</strong></td>
<td><strong>Change Description</strong></td>
<td><strong>Date</strong></td>
<td><strong>Author Initials</strong></td>
</tr>
<tr class="even">
<td>1</td>
<td>1</td>
<td>Initial component creation</td>
<td>21-Aug-13</td>
<td>Jared</td>
</tr>
<tr class="odd">
<td>2</td>
<td>2</td>
<td><p>Implemented the FDD rev.003:</p>
<p>Changed inside the functions DigColPsInt_Init(),
DigColPsInt_GetData(), DigColPsInt_StartRequest() and
DigColPsInt_InterruptNotification().</p>
<p>Added delay before sensors initialization.</p>
<p>Added six new display variables.</p>
<p>Added receiver overrun error checking and action.</p>
<p>Added a bit for receive overrun error in
CommFaults_Cnt_T_b08</p></td>
<td>27-Feb-14</td>
<td>Rijvi</td>
</tr>
<tr class="even">
<td>3</td>
<td>3</td>
<td><p>Implemented the FDD rev.005.</p>
<p>Fixed anomaly 6089.</p>
<p>Fixed anomaly 6471.</p></td>
<td>20-Mar-14</td>
<td>Rijvi</td>
</tr>
<tr class="odd">
<td>4</td>
<td>4</td>
<td>Implemented the FDD rev.006</td>
<td>26-Mar-14</td>
<td>Rijvi</td>
</tr>
<tr class="even">
<td>5</td>
<td>5</td>
<td>Implemented the FDD rev 007</td>
<td>11-May-14</td>
<td>Selva</td>
</tr>
<tr class="odd">
<td>6</td>
<td>6</td>
<td>Updated to FDD ver 008</td>
<td>27-Jun-14</td>
<td>Jared</td>
</tr>
<tr class="even">
<td>7</td>
<td>7</td>
<td>Updated to FDD ver12 compatibility with DSS</td>
<td>05-Sep-14</td>
<td>Vishnu</td>
</tr>
<tr class="odd">
<td>8</td>
<td>8</td>
<td>Unit Testing Finding Fixes</td>
<td>13-Oct-14</td>
<td>KPIT-PM</td>
</tr>
</tbody>
</table>

{% endraw %}