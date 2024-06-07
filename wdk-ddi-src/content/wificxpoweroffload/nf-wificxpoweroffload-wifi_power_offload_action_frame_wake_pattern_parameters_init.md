---
UID: NF:wificxpoweroffload.WIFI_POWER_OFFLOAD_ACTION_FRAME_WAKE_PATTERN_PARAMETERS_INIT
tech.root: netvista
title: WIFI_POWER_OFFLOAD_ACTION_FRAME_WAKE_PATTERN_PARAMETERS_INIT
ms.date: 03/04/2024
targetos: Windows
description: The WIFI_POWER_OFFLOAD_ACTION_FRAME_WAKE_PATTERN_PARAMETERS_INIT function initializes a WIFI_POWER_OFFLOAD_ACTION_FRAME_WAKE_PATTERN_PARAMETERS structure.
prerelease:
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wificxpoweroffload.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wificxpoweroffload.h
api_name:
 - WIFI_POWER_OFFLOAD_ACTION_FRAME_WAKE_PATTERN_PARAMETERS_INIT
f1_keywords:
 - WIFI_POWER_OFFLOAD_ACTION_FRAME_WAKE_PATTERN_PARAMETERS_INIT
 - wificxpoweroffload/WIFI_POWER_OFFLOAD_ACTION_FRAME_WAKE_PATTERN_PARAMETERS_INIT
dev_langs:
 - c++
helpviewer_keywords:
 - WIFI_POWER_OFFLOAD_ACTION_FRAME_WAKE_PATTERN_PARAMETERS_INIT
---

## -description

The **WIFI_POWER_OFFLOAD_ACTION_FRAME_WAKE_PATTERN_PARAMETERS_INIT** function initializes a [**WIFI_POWER_OFFLOAD_ACTION_FRAME_WAKE_PATTERN_PARAMETERS**](ns-wificxpoweroffload-wifi_power_offload_action_frame_wake_pattern_parameters.md) structure.

## -parameters

### -param Parameters

[_Out_] A pointer to a client driver-allocated [**WIFI_POWER_OFFLOAD_ACTION_FRAME_WAKE_PATTERN_PARAMETERS**](ns-wificxpoweroffload-wifi_power_offload_action_frame_wake_pattern_parameters.md) structure.

## -remarks

This function zeroes out the memory of the WIFI_POWER_OFFLOAD_ACTION_FRAME_WAKE_PATTERN_PARAMETERS structure, then fills in the **Size** member. Client drivers must then call [**WifiPowerOffloadGetActionFrameWakePatternParameters**](nf-wificxpoweroffload-wifipoweroffloadgetactionframewakepatternparameters.md) to fill in the remaining members of the structure.

The client driver must only call **WIFI_POWER_OFFLOAD_ACTION_FRAME_WAKE_PATTERN_PARAMETERS_INIT** during a power transition, typically from its *[EVT_WDF_DEVICE_ARM_WAKE_FROM_SX](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md)*, *[EVT_WDF_DEVICE_ARM_WAKE_FROM_S0](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_s0.md)*, or *[EVT_NET_DEVICE_PREVIEW_POWER_OFFLOAD](../netdevice/nc-netdevice-evt_net_device_preview_power_offload.md)* callback function. Otherwise, the call results in a system bugcheck.

## -see-also

[**WIFI_POWER_OFFLOAD_ACTION_FRAME_WAKE_PATTERN_PARAMETERS**](ns-wificxpoweroffload-wifi_power_offload_action_frame_wake_pattern_parameters.md)

[**WifiPowerOffloadGetActionFrameWakePatternParameters**](nf-wificxpoweroffload-wifipoweroffloadgetactionframewakepatternparameters.md)