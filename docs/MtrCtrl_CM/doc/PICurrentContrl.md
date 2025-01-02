---
layout: default
title: PICurrentContrl
nav_order: 7
parent: Motor Control
---
{% raw %}
# Module -- PICurrCntrl [module----picurrcntrl]

# High-Level Description

Non-AUTOSAR PI driver required to perform EPS motor control PWM
profiles.

# Figures

## Diagram – Function Data Sharing

This diagram shows all data that is shared between functions within the
module.

<img
src="ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/MtrCtrl_CM/doc/mediax/media/image1.png"
style="width:2.78056in;height:2.91597in" />

# Module Inputs and Outputs

For details on module input / output variable, refer to the Data
Dictionary for the application. Input / output variable names are listed
here for reference.

(Note: Full variable names required in table.)

(Note: All global variables including End Of Line data used should be
shown here)

|                                      |                                       |
|----------------------------------------|--------------------------------|
| Module Inputs (Global Variable Name) | Module Outputs (Global Variable Name) |
| Refer the Data Dictionary            | Refer the Data Dictionary             |
|                                      |                                       |
|                                      |                                       |
|                                      |                                       |
|                                      |                                       |
|                                      |                                       |
|                                      |                                       |
|                                      |                                       |
|                                      |                                       |
|                                      |                                       |
|                                      |                                       |
|                                      |                                       |
|                                      |                                       |
|                                      |                                       |
|                                      |                                       |
|                                      |                                       |
|                                      |                                       |
|                                      |                                       |
|                                      |                                       |
|                                      |                                       |
|                                      |                                       |
|                                      |                                       |
|                                      |                                       |
|                                      |                                       |
|                                      |                                       |
|                                      |                                       |
|                                      |                                       |
|                                      |                                       |

## Module Internal Variables

This section identifies the name, range and resolutions for module
specific data created by this module. If there are no range restrictions
on the variable, the term “FULL” is placed into the table for legal
range.

(Note: If no module specific variables are used by the design, place the
text “None” in the first Variable Name cell in the table)

<table>
<colgroup>
<col style="width: 38%" />
<col style="width: 17%" />
<col style="width: 13%" />
<col style="width: 12%" />
<col style="width: 17%" />
</colgroup>
<tbody>
<tr class="odd">
<td>Variable Name</td>
<td>Resolution</td>
<td><p>Legal Range</p>
<p>(min)</p></td>
<td><p>Legal Range</p>
<p>(max)</p></td>
<td>Software Segment</td>
</tr>
<tr class="even">
<td>Refer the Data Dictionary</td>
<td>Refer the Data Dictionary</td>
<td>Refer the Data Dictionary</td>
<td>Refer the Data Dictionary</td>
<td>Refer the Data Dictionary</td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

###  [section]

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
<tbody>
<tr class="odd">
<td>Typedef Name</td>
<td>Element Name</td>
<td>User Defined Type</td>
<td><p>Legal Range</p>
<p>(min)</p></td>
<td><p>Legal Range</p>
<p>(max)</p></td>
</tr>
<tr class="even">
<td>LowPassFiltBilinear_Str</td>
<td>PrevInput_Uls_f32</td>
<td>Single precision float</td>
<td>FULL RANGE</td>
<td>FULL RANGE</td>
</tr>
<tr class="odd">
<td></td>
<td>PrevOutput_Uls_f32</td>
<td>Single precision float</td>
<td>FULL RANGE</td>
<td>FULL RANGE</td>
</tr>
<tr class="even">
<td></td>
<td>TermN_Uls_f32</td>
<td>Single precision float</td>
<td>FULL RANGE</td>
<td>FULL RANGE</td>
</tr>
<tr class="odd">
<td></td>
<td>TermD_Uls_f32</td>
<td>Single precision float</td>
<td>FULL RANGE</td>
<td>FULL RANGE</td>
</tr>
</tbody>
</table>

# Constant Data Dictionary

## Calibration Constants

This section lists the calibrations used by the module. For details on
calibration constants, refer to the Data Dictionary for the application.

(Note: If no calibrations are used by the design, place the text “None”
in the first location in the table)

|                           |
|---------------------------|
| Constant Name             |
| Refer the Data Dictionary |
|                           |
|                           |
|                           |

## Program(fixed) Constants

### Embedded Constants

All embedded constants whose values are provided in Eng units will be
evaluated to the equivalent counts by using the FPM_InitFixedPoint_m()
macro within the \#define statement.

#### Local

|                          |                        |          |                  |
|-------------------------------|---------------|----------|-----------------|
| Constant Name            | Resolution             | Units    | Value            |
| D_SCALERADTOCNTS_ULS_F32 | Single Precision Float | Unitless | 10430.3783505F   |
| D_REVWITHROUND_ULS_F32   | Single Precision Float | Unitless | 65536.5F         |
| D_ROUND_ULS_F32          | Single Precision Float | Unitless | 0.5F             |
| D_DEG2RAD_ULS_F32        | Single Precision Float | Unitless | 0.0174532925199F |
| D_GAIN_ULS_F32           | Single Precision Float | Unitless | 0.5              |
| D_VECUMAX_VOLTS_F32      | Single Precision Float | Volts    | 31               |
| D_SQRT3OVR2_ULS_F32      | Single Precision Float | Unitless | 0.866025403784   |
| D_MTRCTRLISRRATE_MS_F32  | Single Precision Float | mSec     | 0.00125          |

####  [section-1]

#### Global

This section lists the global constants used by the module. For details
on global constants, refer to the Data Dictionary for the application.

|                     |
|---------------------|
| Constant Name       |
| D_ZERO_ULS_F32      |
| D_VECUMIN_VOLTS_F32 |

### Module specific Lookup Tables Constants

(This is for lookup tables (arrays) with fixed values, same name as
other tables)

|               |            |       |                  |
|---------------|------------|-------|------------------|
| Constant Name | Resolution | Value | Software Segment |
| None          |            |       |                  |

# Functions/Macros used by the Sub-Modules 

## Library Functions / Macros 

The library functions / Macros that are called by the various sub
modules are identified below,

1.  IntplVarXY_u16_u16Xu16Y_Cnt_m()

2.  FPM_FloatToFixed_m

3.  Sign_f32_m

4.  Sqrtf

5.  Sinf

6.  Cosf

## Data Hiding Functions

The data hiding functions / macros used in this module are identified
below,

Rte_ModeType_StaMd_Mode

MtrCntrl_Read_MtrCurrQax_Amp_f32

MtrCntrl_Read_MtrCurrDax_Amp_f32

MtrCntrl_Read_Vecu_Volt_f32

MtrCntrl_Read_ModIdxSrlComSvcDft_Cnt_lgc

MtrCntrl_Read_SysState_Cnt_Enum

MtrCntrl_Read_MtrCurrOffComOffset_Cnt_u16

MtrCntrl_Read_MtrElecPol_Cnt_s8

MtrCntrl_Read_MtrPosElec_Rev_u0p16

MtrCntrl_Write_MtrCurrQaxFinalRef_Amp_f32

MtrCntrl_Write_MtrDaxVoltage_Volt_f32

MtrCntrl_Write_MtrQaxVoltage_Volt_f32

MtrCntrl_Write_ModIdx_Uls_u16p16

MtrCntrl_Write_PhaseAdvanceFinal_Rev_u0p16

MtrCntrl_Write_CommOffset_Cnt_u16

## Local Functions/Macros Used by this MDD only

Header file: Ap_MtrCntrl_Cfg.h

# Software Module Implementation

## Initialization Functions

None.

## Periodic Functions 

### Per: PICurrCntrl_Per1

#### Design Rationale

This function is responsible for calculating the amount of current to be
supplied to the motor. To control the PWM profiles generated for the
motor. FastDataAccessBufIndex allows the buffer synchronization between
data calculated on slower periodic loop time(2 milli seconds) and are
read by faster periodic run time (ie 0.125ms)

#### Store Module Inputs to Local copies

MtrCntrl_Read_MtrCurrQax_Amp_f32(&MtrCurrQax_Amp_T_f32);

MtrCntrl_Read_MtrCurrDax_Amp_f32(&MtrCurrDax_Amp_T_f32);

MtrCntrl_Read_Vecu_Volt_f32(&Vecu_Volt_T_f32);

MtrCntrl_Read_ModIdxSrlComSvcDft_Cnt_lgc(&ModIdxSrlComSvcDft_Cnt_T_lgc);

MtrCntrl_Read_SysState_Cnt_Enum(&SysState_Cnt_T_Enum);

FwdDataAcessBuffer_Cnt_T_u16= (ActWriteAccBufIndex_Cnt_T_u16)

MtrCurrQaxRef_Amp_T_f32=MtrCurrQaxRef_Amp_M_f32\[FwdDataAcessBuffer_Cnt_T_u16\];

MtrCurrDaxRef_Amp_T_f32=MtrCurrDaxRef_Amp_M_f32\[FwdDataAcessBuffer_Cnt_T_u16\];

PIDaxIntegralGain_Uls_T_f32=MtrDaxIntegralGain_Uls_M_f32\[FwdDataAcessBuffer_Cnt_T_u16\];

PIDaxPropotionalGain_Uls_T_f32=MtrDaxPropotionalGain_Uls_M_f32\[FwdDataAcessBuffer_Cnt_T_u16\]

PIQaxIntegralGain_Uls_T_f32=MtrQaxIntegralGain_Uls_M_f32\[FwdDataAcessBuffer_Cnt_T_u16\];

PIQaxPropotionalGain_Uls_T_f32=MtrQaxPropotionalGain_Uls_M_f32\[FwdDataAcessBuffer_Cnt_T_u16\]

ElecPosDelayComp_Rad_T_f32=MtrPosComputationDelay_Rad_M_f32\[FwdDataAcessBuffer_Cnt_T_u16\]

MtrVoltDaxFF_Volt_T_f32=MtrVoltDaxFF_Volt_M_f32\[FwdDataAcessBuffer_Cnt_T_u16\]MtrVoltQaxFF_Volt_T_f32=MtrVoltQaxFF_Volt_M_f32\[FwdDataAcessBuffer_Cnt_T_u16\];

Program Flow Start

Refer FDD for flowcharts

#### Store Local copy of outputs into Module Outputs

MtrCntrl_Write_MtrCurrQaxFinalRef_Amp_f32(MtrCurrQaxFinalRef_Amp_T_f32)

MtrCntrl_Write_MtrDaxVoltage_Volt_f32(MtrDaxVoltage_Volt_T_f32)

MtrCntrl_Write_MtrQaxVoltage_Volt_f32(MtrQaxVoltage_Volt_T_f32)

MtrCntrl_Write_ModIdx_Uls_u16p16(FPM_FloatToFixed_m(ModIdx_Uls_T_u16p16))

MtrCntrl_Write_PhaseAdvanceFinal_Rev_u0p16(PhaseAdvanceFinal_Rev_T_u0p16)

MtrCntrl_Write_CommOffset_Cnt_u16(CommOffset_Cnt_T_u16)

MtrCntrl_Write_MtrVolt_Volt_f32(MtrVoltCmdFinal_Volt_T_f32)

MtrCntrl_Write_MtrCurrDaxIntg_Volt_f32(MtrCurrDaxIntg_Volt_T_f32)

MtrCntrl_Write_MtrCurrQaxIntg_Volt_f32(MtrCurrQaxIntg_Volt_T_f32)

MtrCurrQaxFinalRef_Amp_M_f32\[SlowDataAccessBufIndex_Cnt_M_u16\]=
MtrCurrQaxFinalRef_Amp_T_f32;

MtrVoltDax_Volt_M_f32\[SlowDataAccessBufIndex_Cnt_M_u16\] =
MtrDaxVoltage_Volt_T_f32;

MtrVoltQax_Volt_M_f32\[SlowDataAccessBufIndex_Cnt_M_u16\] =
MtrQaxVoltage_Volt_T_f32

#### Program Flow End

N/A

## Periodic Functions 

### Per: PICurrCntrl_Per2

#### Design Rationale

This function is responsible for calculating the amount of current to be
supplied to the motor. To control the PWM profiles generated for the
motor.

SlowDataAccessBufIndex allows the buffer synchronization between data
calculated on faster periodic loop time(125 micro seconds) and are read
by slower periodic run time (ie 2ms)

#### Store Module Inputs to Local copies

ReadBuffer_Cnt_T_u16 = SlowDataAccessBufIndex_Cnt_M_u16

WriteBuffer_Cnt_T_u16 = (ReadBuffer_Cnt_T_u16 & 1U) \^ 1U

SlowDataAccessBufIndex_Cnt_M_u16 = WriteBuffer_Cnt_T_u16

EstKe_VpRadpS_T_f32= Rte_IRead_PICurrCntrl_Per2_EstKe_VpRadpS_f32();

EstR_Ohm_T_f32 = Rte_IRead_PICurrCntrl_Per2_EstR_Ohm_f32();

MRFMtrVel_MtrRadpS_T_f32 =
Rte_IRead_PICurrCntrl_Per2_MRFMtrVel_MtrRadpS_f32();

CorrMtrPosElec_Rev_T_f32 =
Rte_IRead_PICurrCntrl_Per2_CorrMtrPosElec_Rev_f32();

MtrCurrDaxRef_Amp_T_f32 =
Rte_IRead_PICurrCntrl_Per2_MtrCurrDaxRef_Amp_f32();

MtrVoltDax_Volt_T_f32 = MtrVoltDax_Volt_M_f32\[ReadBuffer_Cnt_T_u16\];

MtrVoltQax_Volt_T_f32 = MtrVoltQax_Volt_M_f32\[ReadBuffer_Cnt_T_u16\];

MtrCurrQaxFinalRef_Amp_T_f32 =
MtrCurrQaxFinalRef_Amp_M_f32\[ReadBuffer_Cnt_T_u16\];

#### Program Flow Start

Rte_Call_PICurrCntrl_Per2_CP0_CheckpointReached()

#### Processing

> ![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/MtrCtrl_CM/doc/mediax/media/image2.wmf)

#### Store Local copy of outputs into Module Outputs

Rte_IWrite_PICurrCntrl_Per2_DervLambdaAlphaDiag_Volt_f32(DervLambdaAlphaDiag_Volt_T_f32);

Rte_IWrite_PICurrCntrl_Per2_DervLambdaBetaDiag_Volt_f32(DervLambdaBetaDiag_Volt_T_f32);

#### Program Flow End

Rte_Call_PICurrCntrl_Per2_CP1_CheckpointReached()

## Local Functions 

### Local Function \#8

|                      |                             |                         |            |            |          |
|-------------|------------------------|---------------|-------|-------|-------|
| **Function Name**    | CalLowPassFiltBilinearOut   | Type                    | Min        | Max        | UTP Tol. |
| **Arguments Passed** | Input_Uls_T_f32             | Float32                 | FULL RANGE | FULL RANGE |          |
|                      | \*LowPassFiltBilinear_T_Str | LowPassFiltBilinear_Str | FULL RANGE | FULL RANGE |          |
|                      |                             |                         |            |            |          |
| **Return Value**     | Output_Uls_T_f32            | Float32                 | FULL RANGE | FULL RANGE |          |

#### Description

###  [section-2]

### Local Function \#9 CalLowPassFiltBilinearTerm

|                      |                            |                         |            |            |          |
|--------------|-------------------------|---------------|-------|-------|------|
| **Function Name**    | CalLowPassFiltBilinearTerm | Type                    | Min        | Max        | UTP Tol. |
| **Arguments Passed** | Freq_Hz_T_f32              | Float32                 | FULL RANGE | FULL RANGE |          |
|                      | TimeCons_Sec_T_f32         | Float32                 | FULL RANGE | FULL RANGE |          |
| **Return Value**     | LowPassFiltBilinear_T_Str  | LowPassFiltBilinear_Str | FULL RANGE | FULL RANGE |          |

#### Description

###  [section-3]

# Execution Requirements

## Execution Sequence of the Module

N/A

## Execution Rates for sub-modules called by the Scheduler

This table serves as reference for the Scheduler design

<table>
<colgroup>
<col style="width: 37%" />
<col style="width: 21%" />
<col style="width: 40%" />
</colgroup>
<tbody>
<tr class="odd">
<td>Function Name</td>
<td>Calling Frequency</td>
<td>System State(s) in which the function is called</td>
</tr>
<tr class="even">
<td><h3 id="picurrcntrl_per1" class="unnumbered">
PICurrCntrl_Per1</h3></td>
<td>0.125ms</td>
<td>All</td>
</tr>
<tr class="odd">
<td><h3 id="picurrcntrl_per2" class="unnumbered">
PICurrCntrl_Per2</h3></td>
<td>2ms</td>
<td>All</td>
</tr>
</tbody>
</table>

## Execution Requirements for Serial Communication Functions 

|               |                                                  |
|---------------|--------------------------------------------------|
| Function Name | Sub-Module called by (Serial Comm Function Name) |
| N/A           |                                                  |

#   [section-4]

# Memory Map Definition Requirements

## Sub Modules (Functions)

This table identifies the software segments for functions identified in
this module.

|                    |                                        |
|--------------------|----------------------------------------|
| Name of Sub Module | Software Segment                       |
| PICurrCntrl_Per1   | PICurrCntrl_CODE                       |
| PICurrCntrl_Per2   | RTE_START_SEC_AP_PICURRCNTRL_APPL_CODE |

## Local Functions

This table identifies the software segments for local functions
identified in this module.

1.  *- Denotes functions that* are vector call-backs only included to
    avoid compiler errors.

|                    |                  |
|--------------------|------------------|
| Name of Sub Module | Software Segment |
| N/A                |                  |

#  Known Issues / Limitations With Design

> The computation of commoffset and ModIndex service defeat part of
> FDD15D is implemented in this component inaddition to 99B requirements
>
> The reason for the implementation is to keep the sine voltage driver
> common across components

# Revision Control Log

<table>
<colgroup>
<col style="width: 6%" />
<col style="width: 7%" />
<col style="width: 63%" />
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
<td>1.0</td>
<td>Initial release with changes for IPM</td>
<td>6/12/2012</td>
<td>AD/KPIT</td>
</tr>
<tr class="odd">
<td>2</td>
<td>1.0</td>
<td>Changes for memap statements added</td>
<td>11/20/2012</td>
<td>Selva</td>
</tr>
<tr class="even">
<td>3</td>
<td>2.0</td>
<td><p>Updated for SF99B –v8 with only changes needed for voltage
command</p>
<p>integrity check for torque reasonableness</p></td>
<td>02/24/2013</td>
<td>Selva</td>
</tr>
<tr class="odd">
<td>4</td>
<td>3.0,</td>
<td>Updated for SF99B –v8</td>
<td>03/21/2013</td>
<td>Selva</td>
</tr>
<tr class="even">
<td>5</td>
<td>4.0</td>
<td>Corrected for SF99B –v8</td>
<td>04/19/2013</td>
<td>Selva</td>
</tr>
<tr class="odd">
<td>6</td>
<td>5.0</td>
<td>Updated for SF99B –v10</td>
<td>21-Oct-13</td>
<td>Selva</td>
</tr>
<tr class="even">
<td>7</td>
<td>6.0</td>
<td>Updated for SF99B –v10</td>
<td>7-Nov-13</td>
<td>Selva</td>
</tr>
<tr class="odd">
<td>8</td>
<td>7.0</td>
<td>Updated for V12 of FDD SF99</td>
<td>27-Nov-13</td>
<td>Selva</td>
</tr>
<tr class="even">
<td>9</td>
<td>8.0</td>
<td>Updated for V15 of FDD SF99</td>
<td>27-Mar-15</td>
<td>Selva</td>
</tr>
<tr class="odd">
<td>10</td>
<td>9.0</td>
<td>Updated for V17 of FDD SF99 EA3#A283,EA3#1777 fixed</td>
<td>21-Aug-15</td>
<td>Selva</td>
</tr>
</tbody>
</table>

{% endraw %}