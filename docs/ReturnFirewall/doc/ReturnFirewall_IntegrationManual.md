---
layout: default
title: ReturnFirewall_IntegrationManual
nav_order: 4
parent: Return Firewall (Safety)
---
{% raw %}
**Integration Manual**

**For**

**Return Firewall**

**VERSION: 1.0**

**DATE: 15-JAN-2015**

**Prepared By:**

**Spandana Balani**

**  
Revision History**

|            |                        |           |            |
|------------|------------------------|-----------|------------|
| **Rev \#** | **Change Description** | **Date**  | **Author** |
| 1          | Initial version        | 15-Jan-15 | SB         |

**<u>  
Table of Contents</u>**

[1 Abbrevations And Acronyms
[4](#abbrevations-and-acronyms)](#abbrevations-and-acronyms)

[2 References [5](#references)](#references)

[3 Dependencies [6](#dependencies)](#dependencies)

[3.1 SWCs [6](#swcs)](#swcs)

[3.2 Global Functions(Non RTE) to be provided to Integration Project
[6](#global-functionsnon-rte-to-be-provided-to-integration-project)](#global-functionsnon-rte-to-be-provided-to-integration-project)

[4 Configuration REQUIREMeNTS
[7](#configuration-requirements)](#configuration-requirements)

[4.1 Build Time Config [7](#build-time-config)](#build-time-config)

[4.2 Configuration Files to be provided by Integration Project
[7](#configuration-files-to-be-provided-by-integration-project)](#configuration-files-to-be-provided-by-integration-project)

[4.3 Da Vinci Parameter Configuration Changes
[7](#da-vinci-parameter-configuration-changes)](#da-vinci-parameter-configuration-changes)

[4.4 DaVinci Interrupt Configuration Changes
[7](#davinci-interrupt-configuration-changes)](#davinci-interrupt-configuration-changes)

[4.5 Manual Configuration Changes
[7](#manual-configuration-changes)](#manual-configuration-changes)

[5 Integration DATAFLOW REQUIREMENTS
[8](#integration-dataflow-requirements)](#integration-dataflow-requirements)

[5.1 Required Global Data Inputs
[8](#required-global-data-inputs)](#required-global-data-inputs)

[5.2 Required Global Data Outputs [8](#_Toc389222329)](#_Toc389222329)

[5.3 Specific Include Path present [8](#_Toc357692829)](#_Toc357692829)

[6 Runnable Scheduling [9](#runnable-scheduling)](#runnable-scheduling)

[7 Memory Map REQUIREMENTS
[10](#memory-map-requirements)](#memory-map-requirements)

[7.1 Mapping [10](#mapping)](#mapping)

[7.2 Usage [10](#usage)](#usage)

[7.3 Non RTE NvM Blocks [10](#non-rte-nvm-blocks)](#non-rte-nvm-blocks)

[7.4 RTE NvM Blocks [10](#rte-nvm-blocks)](#rte-nvm-blocks)

[8 Compiler Settings [11](#compiler-settings)](#compiler-settings)

[8.1 Preprocessor MACRO [11](#preprocessor-macro)](#preprocessor-macro)

[8.2 Optimization Settings
[11](#optimization-settings)](#optimization-settings)

[9 Appendix [12](#appendix)](#appendix)

# Abbrevations And Acronyms

| **Abbreviation** | **Description**                         |
|------------------|-----------------------------------------|
| DFD              | Design functional diagram               |
| MDD              | Module design Document                  |
|                  | \<ADD more to the table if applicable\> |
|                  |                                         |
|                  |                                         |

# References

This section lists the title & version of all the documents that are
referred for development of this document

| **Sr. No.** | **Title**            | **Version** |
|-------------|----------------------|-------------|
| 1           | SF36 Return Firewall | 005         |

# Dependencies

## SWCs

| **Module** | **Required Feature**                     |
|------------|------------------------------------------|
| **None**   | \<Addition of global data, function\>\*. |

Note : Referencing the external components should be avoided in most
cases. Only in unavoidable circumstance external components should be
referred. Developer should track the references.

## Global Functions(Non RTE) to be provided to Integration Project

None

# Configuration REQUIREMeNTS

## Build Time Config

| **Modules** | **Notes** |     |
|-------------|-----------|-----|
| **None**    |           |     |

## Configuration Files to be provided by Integration Project

Ap_ReturnFirewall_Cfg.h for checkpoint enable

## Da Vinci Parameter Configuration Changes

| **Parameter**                                        | **Notes**             | **SWC**        |
|--------------------------------|-----------------------------|------------|
| **ReturnFirewallGeneral**/**ReturnFirewallCPEnable** | To enable checkpoints | ReturnFirewall |

## DaVinci Interrupt Configuration Changes

| **ISR Name** | **VIM \#** | **Priority Dependency** | **Notes** |
|--------------|------------|-------------------------|-----------|
| **None**     |            |                         |           |

## Manual Configuration Changes

| **Constant** | **Notes** | **SWC** |
|--------------|-----------|---------|
| **None**     |           |         |

# Integration DATAFLOW REQUIREMENTS

## Required Global Data Inputs

<span id="_Toc389222329"
class="anchor"></span>HandwheelPosition_HwDeg_f32

ReturnCmd_MtrNm_f32

VehicleSpeed_Kph_f32

Defeat_Return_Svc_Cnt_lgc

MEC_Counter_Cnt_enum

## Required Global Data Outputs

<span id="_Toc357692829" class="anchor"></span>LimitedReturn_MtrNm_f32

## Specific Include Path present

No

# Runnable Scheduling 

This section specifies the required runnable scheduling.

| **Init** | **Scheduling Requirements** | **Trigger** |
|----------|-----------------------------|-------------|
| **None** |                             |             |

<table style="width:100%;">
<colgroup>
<col style="width: 25%" />
<col style="width: 54%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Runnable</strong></th>
<th><strong>Scheduling Requirements</strong></th>
<th><strong>Trigger</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>ReturnFirewall_Per1</strong></td>
<td><p>triggered on TimingEvent</p>
<p>Disabled in WARMINIT and OFF</p></td>
<td>2ms</td>
</tr>
</tbody>
</table>

**.**

# Memory Map REQUIREMENTS

## Mapping

| **Memory Section**                           | **Contents** | **Notes** |
|----------------------------------------------|--------------|-----------|
| RETURNFIREWALL_START_SEC_VAR_CLEARED_32      |              |           |
| RETURNFIREWALL_START_SEC_VAR_CLEARED_BOOLEAN |              |           |

\* Each …START_SEC… constant is terminated by a …STOP_SEC… constant as
specified in the AUTOSAR Memory Mapping requirements.

## Usage

| **Feature** | **RAM** | **ROM** |
|-------------|---------|---------|
| **None**    |         |         |

Table 1: ARM Cortex R4 Memory Usage

## Non RTE NvM Blocks

| **Block Name** |
|----------------|
| **None**       |

Note : Size of the NVM block if configured in developer

##  RTE NvM Blocks

| **Block Name** |
|----------------|
| **None**       |

Note : Size of the NVM block if configured in developer

# Compiler Settings

##  Preprocessor MACRO

None

## Optimization Settings

None

# Appendix

*\<This section is for appendix\>*

{% endraw %}