---
layout: default
title: AssistFirewall_IntegrationManual
nav_order: 2
parent: Assist Firewall (Safety)
---
{% raw %}
[1 Dependencies [2](#dependencies)](#dependencies)

[1.1 SWCs [2](#swcs)](#swcs)

[1.2 Global Functions(Non RTE) to be provided to Integration Project
[2](#global-functions-non-rte-to-be-provided-to-integration-project)](#global-functions-non-rte-to-be-provided-to-integration-project)

[2 Configuration [3](#configuration)](#configuration)

[2.1 Build Time Config [3](#build-time-config)](#build-time-config)

[2.2 Configuration Files to be provided by Integration Project
[3](#configuration-files-to-be-provided-by-integration-project)](#configuration-files-to-be-provided-by-integration-project)

[2.2.1 Da Vinci Parameter Configuration Changes
[3](#da-vinci-parameter-configuration-changes)](#da-vinci-parameter-configuration-changes)

[2.2.2 DaVinci Interrupt Configuration Changes
[3](#davinci-interrupt-configuration-changes)](#davinci-interrupt-configuration-changes)

[2.2.3 Manual Configuration Changes
[3](#manual-configuration-changes)](#manual-configuration-changes)

[3 Integration Dataflow Requirements
[4](#integration-dataflow-requirements)](#integration-dataflow-requirements)

[3.1 Required Global Data Inputs
[4](#required-global-data-inputs)](#required-global-data-inputs)

[3.2 Required Global Data Outputs
[4](#required-global-data-outputs)](#required-global-data-outputs)

[3.3 Specific Include Path present
[4](#specific-include-path-present)](#specific-include-path-present)

[4 Runnable Scheduling [5](#runnable-scheduling)](#runnable-scheduling)

[5 Memory Mapping [6](#memory-mapping)](#memory-mapping)

[5.1 Mapping [6](#mapping)](#mapping)

[5.2 Usage [6](#usage)](#usage)

[5.3 Non RTE NvM Blocks [6](#non-rte-nvm-blocks)](#non-rte-nvm-blocks)

[5.4 RTE NvM Blocks [6](#rte-nvm-blocks)](#rte-nvm-blocks)

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

Note: Referencing the external components should be avoided in most
cases. Only in unavoidable circumstance external components should be
referred. Developer should track the references.

## Global Functions (Non RTE) to be provided to Integration Project

None

# Configuration

## Build Time Config

| Modules | Notes |     |
|---------|-------|-----|
| None    |       |     |

## Configuration Files to be provided by Integration Project

Ap_AssistFirewall_Cfg.h for checkpoint enable

### Da Vinci Parameter Configuration Changes

| Parameter                                    | Notes                 | SWC            |
|--------------------------------|----------------------------|------------|
| AssistFirewallGeneral/AssistFirewallCPEnable | To enable checkpoints | AssistFirewall |

### DaVinci Interrupt Configuration Changes

| ISR Name | VIM \# | Priority Dependency | Notes |
|----------|--------|---------------------|-------|
| None     |        |                     |       |

### Manual Configuration Changes

| Constant | Notes | SWC |
|----------|-------|-----|
| None     |       |     |

# Integration Dataflow Requirements

## Required Global Data Inputs

BaseAssistCmd_MtrNm_f32

Defeat_AsstTbl_Service_Cnt_lgc

HighFreqAssist_MtrNm_f32

HwTorque_HwNm_f32

HysteresisComp_MtrNm_f32

MEC_Counter_Cnt_enum

VehicleSpeed_Kph_f32

## Required Global Data Outputs

AsstFirewallActive_Uls_f32

CombinedAssist_MtrNm_f32

## Specific Include Path present

No

# Runnable Scheduling 

This section specifies the required runnable scheduling.

| Init                | Scheduling Requirements | Trigger     |
|---------------------|-------------------------|-------------|
| AssistFirewall_Init |                         | On Rte_Init |

<table style="width:100%;">
<colgroup>
<col style="width: 25%" />
<col style="width: 54%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Runnable</th>
<th>Scheduling Requirements</th>
<th>Trigger</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>AssistFirewall_Per1</td>
<td><p>triggered on TimingEvent</p>
<p>Disabled in WARMINIT and OFF</p></td>
<td>2ms</td>
</tr>
</tbody>
</table>

# Memory Mapping

## Mapping

| Memory Section                          | Contents | Notes |
|-----------------------------------------|----------|-------|
| ASSISTFIREWALL_START_SEC_VAR_CLEARED_32 |          |       |

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

Note: Size of the NVM block if configured in developer

##  RTE NvM Blocks

| Block Name |
|------------|
| None       |

Note: Size of the NVM block if configured in developer

# Compiler Settings

##  Preprocessor MACRO

None

## Optimization Settings

None

# Revision Control Log

|            |                        |           |            |
|------------|------------------------|-----------|------------|
| **Rev \#** | **Change Description** | **Date**  | **Author** |
| 1          | Initial version        | 6-Nov-14  | SB         |
| 2          | Updated per SF34 v009  | 15-Jan-15 | SB         |

{% endraw %}