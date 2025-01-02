---
layout: default
title: DigColPs_MDD
nav_order: 4
parent: DigColPs
---
{% raw %}
# Module --  [module---]

# High-Level Description

<img
src="ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/DigColPs/doc/mediax/media/image1.png"
style="width:1.85276in;height:1.02101in" />

The digital column position sensor component reads sensor data from the
digital column position sensor interface and processes the raw angle
data into handwheel position in degrees and determines the validity of
that angle.

# *Figures*

## Data Flow Sequence

<img
src="ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/DigColPs/doc/mediax/media/image2.png"
style="width:6in;height:7.40556in" alt="ES-20DSequence.png" />

<img
src="ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/DigColPs/doc/mediax/media/image3.png"
style="width:6in;height:6.32153in" alt="ES-20DSequence_001.png" />

<img
src="ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/DigColPs/doc/mediax/media/image4.png"
style="width:6in;height:6.66667in" alt="ES-20DSequence_002.png" />

<img
src="ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/DigColPs/doc/mediax/media/image5.png"
style="width:6in;height:6.70694in" alt="ES-20DSequence_003.png" />

<img
src="ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/DigColPs/doc/mediax/media/image6.png"
style="width:5.662in;height:7.27672in" alt="ES-20DSequence_004.png" />

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/DigColPs/doc/mediax/media/image7.emf)

# Variable Data Dictionary

For details on module input / output variable, refer to the Data
Dictionary for the application. Input / output variable names are listed
here for reference.

(Note: Full variable names required in table.)

(Note: All global variables including End Of Line data used should be
shown here)

| Module Inputs     | Module Outputs |                          |
|-------------------|----------------|--------------------------|
| MecState_Cnt_enum |                | I2CHwAbsPos_HwDeg_f32    |
|                   |                | I2CHwAbsPosValid_Cnt_lgc |
|                   |                | TrimComp_Cnt_lgc         |

## Module Internal Variables

This section identifies the name, range and resolutions for module
specific data created by this module. If there are no range restrictions
on the variable, the term “FULL” is placed into the table for legal
range.

<table>
<colgroup>
<col style="width: 40%" />
<col style="width: 10%" />
<col style="width: 10%" />
<col style="width: 10%" />
<col style="width: 28%" />
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
<td>DigColPs_I2CHwColAngle_Deg_M_f32</td>
<td>Single Precision Float</td>
<td>See Data Dictionary</td>
<td>See Data Dictionary</td>
<td>DIGCOLPS_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="even">
<td>DigColPs_I2CHwSpurAngle_Deg_M_f32</td>
<td>Single Precision Float</td>
<td>See Data Dictionary</td>
<td>See Data Dictionary</td>
<td>DIGCOLPS_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="odd">
<td>DigColPs_PrevI2CHwColAngle_Deg_M_f32</td>
<td>Single Precision Float</td>
<td>See Data Dictionary</td>
<td>See Data Dictionary</td>
<td>DIGCOLPS_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="even">
<td>DigColPs_PrevI2CHwSpurAngle_Deg_M_f32</td>
<td>Single Precision Float</td>
<td>See Data Dictionary</td>
<td>See Data Dictionary</td>
<td>DIGCOLPS_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="odd">
<td>DigColPs_PrevColPos_Deg_M_f32</td>
<td>Single Precision Float</td>
<td>See Data Dictionary</td>
<td>See Data Dictionary</td>
<td>DIGCOLPS_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="even">
<td>DigColPs_ColTrimStatic_Deg_M_f32</td>
<td>Single Precision Float</td>
<td>See Data Dictionary</td>
<td>See Data Dictionary</td>
<td>DIGCOLPS_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="odd">
<td>DigColPs_SpurTrimStatic_Deg_M_f32</td>
<td>Single Precision Float</td>
<td>See Data Dictionary</td>
<td>See Data Dictionary</td>
<td>DIGCOLPS_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="even">
<td>DigColPs_VernDiagError_Deg_D_f32</td>
<td>Single Precision Float</td>
<td>See Data Dictionary</td>
<td>See Data Dictionary</td>
<td>DIGCOLPS_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="odd">
<td>DigColPs_ColAngle_Deg_D_f32</td>
<td>Single Precision Float</td>
<td>See Data Dictionary</td>
<td>See Data Dictionary</td>
<td>DIGCOLPS_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="even">
<td>DigColPs_SpurAngle_Deg_D_f32</td>
<td>Single Precision Float</td>
<td>See Data Dictionary</td>
<td>See Data Dictionary</td>
<td>DIGCOLPS_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="odd">
<td>DigColPs_VernierLevel_Deg_D_f32</td>
<td>Single Precision Float</td>
<td>See Data Dictionary</td>
<td>See Data Dictionary</td>
<td>DIGCOLPS_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="even">
<td>DigColPs_ColSensorFaultAcc_Cnt_M_u16</td>
<td>1</td>
<td>See Data Dictionary</td>
<td>See Data Dictionary</td>
<td>DIGCOLPS_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="odd">
<td>DigColPs_ColParityErrorAcc_Cnt_M_u16</td>
<td>1</td>
<td>See Data Dictionary</td>
<td>See Data Dictionary</td>
<td>DIGCOLPS_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="even">
<td>DigColPs_VernCorrDetectAcc_Cnt_M_u16</td>
<td>1</td>
<td>See Data Dictionary</td>
<td>See Data Dictionary</td>
<td>DIGCOLPS_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="odd">
<td>DigColPs_SkipStepFltDetectAcc_Cnt_M_u16</td>
<td>1</td>
<td>See Data Dictionary</td>
<td>See Data Dictionary</td>
<td>DIGCOLPS_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="even">
<td>DigColPs_SpurSensorFaultAcc_Cnt_M_u16</td>
<td>1</td>
<td>See Data Dictionary</td>
<td>See Data Dictionary</td>
<td>DIGCOLPS_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="odd">
<td>DigColPs_SpurParityErrorAcc_Cnt_M_u16</td>
<td>1</td>
<td>See Data Dictionary</td>
<td>See Data Dictionary</td>
<td>DIGCOLPS_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="even">
<td>DigColPs_I2CHwColAngle_Cnt_M_u16</td>
<td>1</td>
<td>See Data Dictionary</td>
<td>See Data Dictionary</td>
<td>DIGCOLPS_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="odd">
<td>DigColPs_I2CHwSpurAngle_Cnt_M_u16</td>
<td>1</td>
<td>See Data Dictionary</td>
<td>See Data Dictionary</td>
<td>DIGCOLPS_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="even">
<td>DigColPs_PrevI2CHwColAngle_Cnt_M_u16</td>
<td>1</td>
<td>See Data Dictionary</td>
<td>See Data Dictionary</td>
<td>DIGCOLPS_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="odd">
<td>DigColPs_PrevI2CHwSpurAngle_Cnt_M_u16</td>
<td>1</td>
<td>See Data Dictionary</td>
<td>See Data Dictionary</td>
<td>DIGCOLPS_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="even">
<td>DigColPs_TrimCompStatic_Cnt_M_u16</td>
<td>1</td>
<td>See Data Dictionary</td>
<td>See Data Dictionary</td>
<td>DIGCOLPS_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="odd">
<td>DigColPs_I2CHwDataType_Cnt_M_u08</td>
<td>1</td>
<td>See Data Dictionary</td>
<td>See Data Dictionary</td>
<td>DIGCOLPS_START_SEC_VAR_CLEARED_8</td>
</tr>
<tr class="even">
<td>DigColPs_I2CSensCommFlts_Cnt_M_u08</td>
<td>1</td>
<td>See Data Dictionary</td>
<td>See Data Dictionary</td>
<td>DIGCOLPS_START_SEC_VAR_CLEARED_8</td>
</tr>
<tr class="odd">
<td>DigColPs_ColRoughTurns_Cnt_M_s16</td>
<td>1</td>
<td>See Data Dictionary</td>
<td>See Data Dictionary</td>
<td>DIGCOLPS_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="even">
<td>DigColPs_SpurRoughTurns_Cnt_M_s16</td>
<td>1</td>
<td>See Data Dictionary</td>
<td>See Data Dictionary</td>
<td>DIGCOLPS_START_SEC_VAR_CLEARED_16</td>
</tr>
<tr class="odd">
<td>DigColPs_ReqI2CSnsrDataType_Cnt_M_u08</td>
<td>1</td>
<td>See Data Dictionary</td>
<td>See Data Dictionary</td>
<td>DIGCOLPS_START_SEC_VAR_CLEARED_8</td>
</tr>
<tr class="even">
<td>DigColPs_PrevVernierLevelNo_Cnt_T_u08</td>
<td>1</td>
<td>See Data Dictionary</td>
<td>See Data Dictionary</td>
<td>DIGCOLPS_START_SEC_VAR_CLEARED_8</td>
</tr>
<tr class="odd">
<td>DigColPs_ColSensorDiagFailed_Cnt_M_lgc</td>
<td>N/A</td>
<td>See Data Dictionary</td>
<td>See Data Dictionary</td>
<td>DIGCOLPS_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
<tr class="even">
<td>DigColPs_SpurSensorDiagFailed_Cnt_M_lgc</td>
<td>N/A</td>
<td>See Data Dictionary</td>
<td>See Data Dictionary</td>
<td>DIGCOLPS_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
<tr class="odd">
<td>DigColPs_I2CColSensorFault_Cnt_M_lgc</td>
<td>N/A</td>
<td>See Data Dictionary</td>
<td>See Data Dictionary</td>
<td>DIGCOLPS_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
<tr class="even">
<td>DigColPs_I2CSpurSensorFault_Cnt_M_lgc</td>
<td>N/A</td>
<td>See Data Dictionary</td>
<td>See Data Dictionary</td>
<td>DIGCOLPS_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
<tr class="odd">
<td>DigColPs_ColParityError_Cnt_M_lgc</td>
<td>N/A</td>
<td>See Data Dictionary</td>
<td>See Data Dictionary</td>
<td>DIGCOLPS_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
<tr class="even">
<td>DigColPs_SpurParityError_Cnt_M_lgc</td>
<td>N/A</td>
<td>See Data Dictionary</td>
<td>See Data Dictionary</td>
<td>DIGCOLPS_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
<tr class="odd">
<td>DigColPs_ColLPFInitDone_Cnt_M_lgc</td>
<td>N/A</td>
<td>See Data Dictionary</td>
<td>See Data Dictionary</td>
<td>DIGCOLPS_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
<tr class="even">
<td>DigColPs_SpurLPFInitDone_Cnt_M_lgc</td>
<td>N/A</td>
<td>See Data Dictionary</td>
<td>See Data Dictionary</td>
<td>DIGCOLPS_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
<tr class="odd">
<td>DigColPs_PrevAngleDataAvailable_Cnt_T_lgc</td>
<td>N/A</td>
<td>See Data Dictionary</td>
<td>See Data Dictionary</td>
<td>DIGCOLPS_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
<tr class="even">
<td>DigColPs_VernierAngleOORange_Cnt_M_lgc</td>
<td>N/A</td>
<td>See Data Dictionary</td>
<td>See Data Dictionary</td>
<td>DIGCOLPS_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
<tr class="odd">
<td>DigColPs_ColAngleLPFKSV_Cnt_M_str</td>
<td>Single Precision Float</td>
<td>See Data Dictionary</td>
<td>See Data Dictionary</td>
<td>DIGCOLPS_START_SEC_VAR_CLEARED_UNSPECIFIED</td>
</tr>
<tr class="even">
<td>DigColPs_SpurAngleLPFKSV_Cnt_M_str</td>
<td>Single Precision Float</td>
<td>See Data Dictionary</td>
<td>See Data Dictionary</td>
<td>DIGCOLPS_START_SEC_VAR_CLEARED_UNSPECIFIED</td>
</tr>
<tr class="odd">
<td>DigColPs_HwAVernCorrFault_Cnt_M_lgc</td>
<td>N/A</td>
<td>See Data Dictionary</td>
<td>See Data Dictionary</td>
<td>DIGCOLPS_START_SEC_VAR_CLEARED_BOOLEAN</td>
</tr>
<tr class="even">
<td>DigColPs_I2CHwTrimTransCnts_Uls_M_u08</td>
<td>1</td>
<td>0</td>
<td>6</td>
<td>DIGCOLPS_START_SEC_VAR_CLEARED_8</td>
</tr>
<tr class="odd">
<td>DigColPs_I2CHwColAngleForTrim_Deg_M_f32</td>
<td>Single Precision Float</td>
<td>See Data Dictionary</td>
<td>See Data Dictionary</td>
<td>DIGCOLPS_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="even">
<td>DigColPs_I2CHwColAngleTrim_Deg_D_f32</td>
<td>Single Precision Float</td>
<td>See Data Dictionary</td>
<td>See Data Dictionary</td>
<td>DIGCOLPS_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="odd">
<td>DigColPs_I2CHwSpurAngleTrim_Deg_D_f32</td>
<td>Single Precision Float</td>
<td>See Data Dictionary</td>
<td>See Data Dictionary</td>
<td>DIGCOLPS_START_SEC_VAR_CLEARED_32</td>
</tr>
<tr class="even">
<td>DigColPs_I2CHWSpurPos_HwDeg_D_f32</td>
<td>Single Precision Float</td>
<td>See Data Dictionary</td>
<td>See Data Dictionary</td>
<td>DIGCOLPS_START_SEC_VAR_CLEARED_32</td>
</tr>
</tbody>
</table>

### User defined typedef definition/declaration 

This section documents any user types uniquely used for the module.

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 41%" />
<col style="width: 15%" />
<col style="width: 10%" />
<col style="width: 10%" />
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
<td>None</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

# Constant Data Dictionary

## Calibration Constants

This section lists the calibrations used by the module. For details on
calibration constants, refer to the Data Dictionary for the application.

| Constant Name                 |
|-------------------------------|
| k_ColAngSenseLPFFc_Hz_f32     |
| k_SpurAngSenseLPFFc_Hz_f32    |
| k_SelectFromColumn_Cnt_lgc    |
| k_StepDetect_Deg_f32          |
| k_VernCorrErrorThresh_Deg_f32 |
| k_VernCorrErrorDiag_Cnt_str   |
| k_SkipStepErrDiag_Cnt_str     |
| k_VernOORangeThresh_Deg_f32   |
| k_SenseDetErrDiag_Cnt_str     |
| k_SenseParityErrDiag_Cnt_str  |

## Program(fixed) Constants

### Embedded Constants

All embedded constants whose values are provided in Eng units will be
evaluated to the equivalent counts by using the FPM_InitFixedPoint_m()
macro within the \#define statement.

#### Local

| Constant Name                   | Resolution             | Units   | Value            |
|----------------------------|-----------------|--------------|--------------|
| D_INVSPURRATIO_ULS_F32          | Single Precision Float | Uls     | 0.45454545454545 |
| D_SPURRATIO_ULS_F32             | Single Precision Float | Uls     | 2.2              |
| D_INVDUALSPURRATIO_ULS_F32      | Single Precision Float | Uls     | 0.5              |
| D_ONEREV_DEGREESPREV_F32        | Single Precision Float | DegpRev | 360              |
| D_VERNIERANGLECENTEROFF_DEG_F32 | Single Precision Float | Deg     | 900              |
| D_HWANGLEATCENTER_DEG_F32       | Single Precision Float | Deg     | 180              |
| D_ANGLEZEROODDPARITY_CNT_U16    | 1                      | Cnt     | 0x1000           |
| D_ANGLEDATA_CNT_U08             | 1                      | Cnt     | 1                |
| D_ERRORREG_CNT_U08              | 1                      | Cnt     | 3                |
| D_EXTERRORREG_CNT_U08           | 1                      | Cnt     | 4                |
| D_VERNIERLEVEL_CNT_U08          | 1                      | Cnt     | 0                |
| D_COLUMNREVS_CNT_U08            | 1                      | Cnt     | 1                |
| D_SPURREVS_CNT_U08              | 1                      | Cnt     | 2                |
| D_COLSPURTBLXSIZE_CNT_U08       | 1                      | Cnt     | 17               |
| D_DUALSPURTBLXSIZE_CNT_U08      | 1                      | Cnt     | 22               |
| D_MAXHWPOS_HWDEG_F32            | Single Precision Float | HwDeg   | 900              |
| D_TRIMCOMPLETE_CNT_U16          | 1                      | Cnt     | 1                |
| D_TRIMNOTCOMPLETE_CNT_U16       | 1                      | Cnt     | 4488             |
| D_VERNIERLEVELNO_CNT_U08        | 1                      | Cnt     | 3                |
| D_I2CHWTRIMTRANSCNT_ULS_U08     | 1                      | Uls     | 6                |
| D_I2CHWORIGINALSENSOR_CNT_U16   | 1                      | Cnt     | 0                |
| D_I2CHWTRIMINSENSOR_CNT_U16     | 1                      | Cnt     | 1                |
| D_I2CHWDUALSPURSENSOR_CNT_U16   | 1                      | Cnt     | 2                |
| D_DUALSPURRATIO_ULS_F32         | Single Precision Float | Uls     | 2                |
| D_I2HW11TO10TRATIO_ULS_F32      | Single Precision Float | Uls     | 1.1              |

####  [section]

#### Global

This section lists the global constants used by the module. For details
on global constants, refer to the Data Dictionary for the application.

| Constant Name  |
|----------------|
| D_2MS_SEC_F32  |
| D_ZERO_ULS_F32 |

### Module specific Lookup Tables Constants

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
<td>T2_ColSpurVernierLUT_Cnt_u16</td>
<td>1</td>
<td><p>{</p>
<p>{-163, -131, -99, -66, -33, 0, 32, 65, 98, 130, 163, 196, 229, 261,
294, 327, 359},</p>
<p>{0, 4, 3, 2, 1, 0, 4, 3, 2, 1, 0, 4, 3, 2, 1, 0, 4},</p>
<p>{0, 8, 6, 4, 2, 0, 9, 7, 5, 3, 1, 10, 8, 6, 4, 2, 10},</p>
<p>{1, 14, 11, 8, 5, 2, 15, 12, 9, 6, 3, 16, 13, 10, 7, 4, 17}</p>
<p>}</p></td>
<td>DIGCOLPS_START_SEC_CONST_16</td>
</tr>
<tr class="even">
<td>T2_DualSpurVernierLUT_Cnt_s16</td>
<td>1</td>
<td><p>{</p>
<p>{-396,-360,-324,-288,-252,-216,-180,-144,-108,-72,-36,0,36,72,108,144,180,216,252,288,324,360},{9,0,1,2,3,4,5,6,7,8,9,0,1,2,3,4,5,6,7,8,9,0},{0,1,2,3,4,5,6,7,8,9,10,0,1,2,3,4,5,6,7,8,9,10},{22,2,4,6,8,10,12,14,16,18,20,1,3,5,7,9,11,13,15,17,19,21}</p>
<p>}</p></td>
<td>DIGCOLPS_START_SEC_CONST_16</td>
</tr>
</tbody>
</table>

#  Functions/Macros used by the Sub-Modules 

## Library Functions / Macros 

The library and functions / Macros that are called by the various sub
modules are identified below,

1.  LPF_KUpdate_f32_m

2.  LPF_OpUpdate_f32_m

3.  FPM_FixedToFloat_m

4.  Abs_f32_m

5.  Abs_s16_m

6.  DiagPStep_m

7.  DiagNStep_m

8.  DiagFailed_m

9.  TableSize_m

10. Min_m

## Data Hiding Functions

1.  DigColPsEOLType()

## Global Functions/Macros Defined by this Module

None

## Local Functions/Macros Used by this MDD only

### Odd Parity Fault

|                      |                 |         |      |       |      |          |
|----------------------|-----------------|---------|------|-------|------|----------|
| **Function Name**    | OddParityFault  | Type    | Dir. | Min   | Max  | UTP Tol. |
| **Arguments Passed** | Input_Cnt_T_u16 | uint16  | In   | FULL  | FULL |          |
| **Return Value**     | Error_Cnt_T_lgc | boolean | Out  | FALSE | TRUE | N/A      |

#### Description

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/DigColPs/doc/mediax/media/image8.emf)

### Diagnostic Threshold

|                      |                                  |                  |        |       |      |          |
|--------------|-------------------------|------|------|-------|--------|-------|
| **Function Name**    | DiagnosticThreshold              | Type             | Dir.   | Min   | Max  | UTP Tol. |
| **Arguments Passed** | FaultPresent_Cnt_T_lgc           | Boolean          | In     | FALSE | TRUE |          |
|                      | DiagSettings_Cnt_T_str           | DiagSettings_Str | In     | FULL  | FULL |          |
|                      | DiagSettings_Cnt_T_str.NStep     | uint16           | In     | FULL  | FULL |          |
|                      | DiagSettings_Cnt_T_str.PStep     | uint16           | In     | FULL  | FULL |          |
|                      | DiagSettings_Cnt_T_str.Threshold | uint16           | In     | FULL  | FULL |          |
|                      | AccumulatorPtr_Cnt_T_u16         | uint16           | In/Out | FULL  | FULL |          |
| **Return Value**     | DiagFailed_Cnt_T_lgc             | boolean          | Out    | FALSE | TRUE | N/A      |

#### Description

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/DigColPs/doc/mediax/media/image9.emf)

### Vernier Lookup

|                                                                                                             |                            |          |      |                |                |
|----------------|----------------------------|-------|-------|--------|--------|
| **Function Name**                                                                                           | VernierLookup              | Type     | Dir. | Min            | Max            |
| **Arguments Passed**                                                                                        | VernierLUT_Cnt_T_s16\[\]   | sint16\* | In   | See sec. 4.2.2 | See sec. 4.2.2 |
|                                                                                                             | LookupTableXSize_Cnt_T_u08 | uint8    | In   | 17\*           | 22\*           |
|                                                                                                             | Level_Deg_T_f32            | float32  | In   | -792           | 360            |
|                                                                                                             | ColRevPtr_Cnt_T_u08        | uint8\*  | Out  | 0              | 9              |
|                                                                                                             | SpurRevPtr_Cnt_T_u08       | uint8\*  | Out  | 0              | 10             |
|                                                                                                             | VernierLevelNo_Cnt_T_u08   | uint8\*  | Out  | 1              | 22             |
| **Return Value**                                                                                            | None                       |          |      |                |                |
| \* LookupTableXSize_Cnt_T_u08 table can be of two size (17 or 22). It’s not a range but two discrete values |                            |          |      |                |                |

####  [section-1]

#### Description

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/DigColPs/doc/mediax/media/image10.emf)

### Compute Rough Turns

|                      |                           |         |        |       |      |          |
|--------------|-------------------------|------|------|-------|--------|-------|
| **Function Name**    | ComputeRoughTurns         | Type    | Dir.   | Min   | Max  | UTP Tol. |
| **Arguments Passed** | Delta_Deg_T_f32           | float32 | In     | -360  | 360  |          |
|                      | RoughTurnAccPtr_Cnt_T_s16 | sin16   | In/Out | -5    | 5    |          |
| **Return Value**     | RoughTurnCount_Deg_T_f32  | float32 | Out    | -1800 | 1800 | 4.8E-04  |

#### Description

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/DigColPs/doc/mediax/media/image11.emf)

### Constrain One Rev

|                      |                 |         |      |       |      |          |
|----------------------|-----------------|---------|------|-------|------|----------|
| **Function Name**    | ConstrainOneRev | Type    | Dir. | Min   | Max  | UTP Tol. |
| **Arguments Passed** | Input_Deg_T_f32 | float32 | In   | -1800 | 1800 |          |
| **Return Value**     | Input_Deg_T_f32 | float32 | Out  | 0     | 360  | 4.8E-04  |

#### Description

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/DigColPs/doc/mediax/media/image12.emf)

# Software Module Implementation

## Runtime Environment (RTE) Initial Values

This section lists the initial values of data written by this module but
controlled by the RTE. After RTE initialization, the data in this table
will contain these values.

| Data                     | Value |
|--------------------------|-------|
| I2CHwAbsPos_HwDeg_f32    | 0     |
| I2CHwAbsPosValid_Cnt_lgc | FALSE |
| TrimCompEOL_Cnt_lgc      | FALSE |

## Initialization Functions

### Init: DigColPs_Init1

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/DigColPs/doc/mediax/media/image13.emf)

#### Design Rationale

None

#### Module Outputs

None

#### Module Internal 

None

##  Periodic Functions

### Per: \_Per1()

#### Design Rationale

None

#### Program Flow Start

Rte_Call_DigColPs_Per1_CP0_CheckpointReached()

#### Store Module Inputs to Local copies

None

#### Processing of Function

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/DigColPs/doc/mediax/media/image14.emf)

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/DigColPs/doc/mediax/media/image15.emf)

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/DigColPs/doc/mediax/media/image16.emf)

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/DigColPs/doc/mediax/media/image17.emf)

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/DigColPs/doc/mediax/media/image18.emf)

#### Store Local copy of outputs into Module Outputs

None

#### Program Flow End

Rte_Call_DigColPs_Per1_CP1_CheckpointReached()

### Per: \_Per2()

#### Design Rationale

None

#### Program Flow Start

Rte_Call_DigColPs_Per2_CP0_CheckpointReached()

#### Store Module Inputs to Local copies

MecState_Cnt_T_enum = Rte_IRead_DigColPs_Per2_MecState_Cnt_enum()

#### Processing of Function

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/DigColPs/doc/mediax/media/image19.emf)

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/DigColPs/doc/mediax/media/image20.emf)

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/DigColPs/doc/mediax/media/image21.emf)

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/DigColPs/doc/mediax/media/image22.emf)

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/DigColPs/doc/mediax/media/image23.emf)

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/DigColPs/doc/mediax/media/image24.emf)

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/DigColPs/doc/mediax/media/image25.emf)

#### Store Local copy of outputs into Module Outputs

Rte_IWrite_DigColPs_Per2_I2CHwAbsPosValid_Cnt_lgc(I2CHwPosValid_Cnt_T_lgc)

Rte_IWrite_DigColPs_Per2_I2CHwAbsPos_HwDeg_f32(I2CAbsHwPos_HwDeg_T_f32)

Rte_IWrite_DigColPs_Per2_TrimComp_Cnt_lgc(TrimComplete_Cnt_T_lgc)

#### Program Flow End

Rte_Call_DigColPs_Per2_CP1_CheckpointReached()

##  Fault Recovery Functions

None

##  Shutdown Functions

None

##  Interrupt Functions

None

##  Serial Communication Functions

### SComm: DigColPs_SCom_CustClrTrim

#### Design Rationale

None

#### Program Flow Start

None

#### Store Module Inputs to Local copies

None

#### Customer Clear Trim

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/DigColPs/doc/mediax/media/image26.emf)

#### Store Local copy of outputs into Module Outputs

None

#### Program Flow End

None

### SComm: DigColPs_SCom_CustSetTrim

#### Design Rationale

None

#### Program Flow Start

None

#### Store Module Inputs to Local copies

GetResource(RES_SCHEDULER)

I2CColSensorFault_Cnt_T_lgc = DigColPs_I2CColSensorFault_Cnt_M_lgc

I2CSpurSensorFault_Cnt_T_lgc = DigColPs_I2CSpurSensorFault_Cnt_M_lgc

I2CHwColAngle_Deg_T_f32 = DigColPs_I2CHwColAngle_Deg_M_f32

I2CHwSpurAngle_Deg_T_f32 = DigColPs_I2CHwSpurAngle_Deg_M_f32

I2CHwCustData_Uls_T_u16 = DigColPsInt_GetCustData()

I2CHwColAngleForTrim_Deg_T_f32 =
DigColPs_I2CHwColAngleForTrim_Deg_M_f32ReleaseResource(RES_SCHEDULER)

#### Customer Set Trim

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/DigColPs/doc/mediax/media/image27.emf)

#### Store Local copy of outputs into Module Outputs

None

#### Program Flow End

None

### SComm: DigColPs_SCom_NxtClrTrim

#### Design Rationale

None

#### Program Flow Start

None

#### Store Module Inputs to Local copies

None

#### Nexteer Clear Trim

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/DigColPs/doc/mediax/media/image28.emf)

#### Store Local copy of outputs into Module Outputs

None

#### Program Flow End

None

### SComm: DigColPs_SCom_NxtSetTrim

#### Design Rationale

None

#### Program Flow Start

None

#### Store Module Inputs to Local copies

GetResource(RES_SCHEDULER)

I2CColSensorFault_Cnt_T_lgc = DigColPs_I2CColSensorFault_Cnt_M_lgc

I2CSpurSensorFault_Cnt_T_lgc = DigColPs_I2CSpurSensorFault_Cnt_M_lgc

I2CHwColAngle_Deg_T_f32 = DigColPs_I2CHwColAngle_Deg_M_f32

I2CHwSpurAngle_Deg_T_f32 = DigColPs_I2CHwSpurAngle_Deg_M_f32

I2CHwCustData_Uls_T_u16 = DigColPsInt_GetCustData()

I2CHwColAngleForTrim_Deg_T_f32 = DigColPs_I2CHwColAngleForTrim_Deg_M_f32

ReleaseResource(RES_SCHEDULER)

#### Nexteer Set Trim

![](ElectricPowerSteering_TexasInstruments_FIAT_321_website/docs/DigColPs/doc/mediax/media/image29.emf)

#### Store Local copy of outputs into Module Outputs

None

#### Program Flow End

None

##  

# Execution Requirements

## Execution Sequence of the Module

(Describe in words relevant details about the execution sequence of the
different sub modules.)

## Execution Rates for sub-modules called by the Scheduler

This table serves as reference for the Scheduler design

| Function Name  | Calling Frequency | System State(s) in which the function is called |
|--------------------------|-----------------|------------------------------|
| DigColPs_Init1 | On Init           | Cold Init                                       |
| DigColPs_Per1  | 2ms               | All                                             |
| DigColPs_Per2  | 4ms               | All                                             |

## Execution Requirements for Serial Communication Functions 

| Function Name             | Sub-Module called by (Serial Comm Function Name) |
|-----------------------------|-------------------------------------------|
| DigColPs_SCom_CustClrTrim | EPS_DiagSrvcs_ISO                                |
| DigColPs_SCom_CustSetTrim | EPS_DiagSrvcs_ISO                                |
| DigColPs_SCom_NxtClrTrim  | EPS_DiagSrvcs_ISO                                |
| DigColPs_SCom_NxtSetTrim  | EPS_DiagSrvcs_ISO                                |

#  [section-3]

#  Memory Map Definition Requirements

## Sub Modules (Functions)

This table identifies the software segments for functions identified in
this module.

| Name of Sub Module        | Software Segment                    |
|---------------------------|-------------------------------------|
| DigColPs_Init1            | RTE_START_SEC_SA_DIGCOLPS_APPL_CODE |
| DigColPs_Per1             | RTE_START_SEC_SA_DIGCOLPS_APPL_CODE |
| DigColPs_Per2             | RTE_START_SEC_SA_DIGCOLPS_APPL_CODE |
| DigColPs_SCom_CustClrTrim | RTE_START_SEC_SA_DIGCOLPS_APPL_CODE |
| DigColPs_SCom_CustSetTrim | RTE_START_SEC_SA_DIGCOLPS_APPL_CODE |
| DigColPs_SCom_NxtClrTrim  | RTE_START_SEC_SA_DIGCOLPS_APPL_CODE |
| DigColPs_SCom_NxtSetTrim  | RTE_START_SEC_SA_DIGCOLPS_APPL_CODE |

##  [section-4]

## Local Functions

This table identifies the software segments for local functions
identified in this module.

| Name of Sub Module  | Software Segment |
|---------------------|------------------|
| OddParityFault      | N/A              |
| DiagnosticThreshold | N/A              |
| VernierLookup       | N/A              |
| ComputeRoughTurns   | N/A              |
| ConstrainOneRev     | N/A              |

#  [section-5]

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
<td>Updates for anomalies 5895, 5906, and 5721 – vernier fault polarity,
filter init, and new TrimComplete output</td>
<td>20-Nov-13</td>
<td>Jared</td>
</tr>
<tr class="even">
<td>3</td>
<td>3</td>
<td><p>Updated for FDD rev.003.</p>
<p>Fixed anomaly 6135</p></td>
<td>03-Mar-14</td>
<td>Rijvi</td>
</tr>
<tr class="odd">
<td>4</td>
<td>4</td>
<td>Updated for FDD rev.005</td>
<td>20-Mar-14</td>
<td>Rijvi</td>
</tr>
<tr class="even">
<td>5</td>
<td>5</td>
<td>Updated for FDD rev.006</td>
<td>26-Mar-14</td>
<td>Rijvi</td>
</tr>
<tr class="odd">
<td>6</td>
<td>6</td>
<td>Updated for FDD rev 007. A6680 fix added</td>
<td>13-May-14</td>
<td>Selva</td>
</tr>
<tr class="even">
<td>7</td>
<td>7</td>
<td>Updated to FDD rev 008</td>
<td>27-Jun-14</td>
<td>Jared</td>
</tr>
<tr class="odd">
<td>8</td>
<td>8</td>
<td>Updated to FDD rev 009, v10, v11</td>
<td>31-July-14</td>
<td>Selva</td>
</tr>
<tr class="even">
<td>9</td>
<td>9</td>
<td>Ranges updated for UTP;</td>
<td>10-Oct-14</td>
<td>Selva</td>
</tr>
</tbody>
</table>

{% endraw %}