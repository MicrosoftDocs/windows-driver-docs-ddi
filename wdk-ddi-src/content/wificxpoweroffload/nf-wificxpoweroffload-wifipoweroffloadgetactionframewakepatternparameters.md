---
UID: NF:wificxpoweroffload.WifiPowerOffloadGetActionFrameWakePatternParameters
tech.root: netvista
title: WifiPowerOffloadGetActionFrameWakePatternParameters
ms.date: 03/04/2024
targetos: Windows
description: The WifiPowerOffloadGetActionFrameWakePatternParameters function gets the parameters for an action frame wake pattern low power protocol offload to a WiFiCx network adapter.
prerelease:
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wificxpoweroffload.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
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
 - WifiPowerOffloadGetActionFrameWakePatternParameters
f1_keywords:
 - WifiPowerOffloadGetActionFrameWakePatternParameters
 - wificxpoweroffload/WifiPowerOffloadGetActionFrameWakePatternParameters
dev_langs:
 - c++
helpviewer_keywords:
 - WifiPowerOffloadGetActionFrameWakePatternParameters
---

## -description

The **WifiPowerOffloadGetActionFrameWakePatternParameters** function gets the parameters for an action frame wake pattern low power protocol offload to a WiFiCx network adapter.

## -parameters

### -param WifiPowerOffload [in]

The WIFIPOWEROFFLOAD object that represents this protocol offload.

### -param Parameters [inout]

A pointer to a driver-allocated and initialized [**WIFI_POWER_OFFLOAD_ACTION_FRAME_WAKE_PATTERN_PARAMETERS**](ns-wificxpoweroffload-wifi_power_offload_action_frame_wake_pattern_parameters.md) structure that receives the action frame wake pattern parameter information.

## -remarks

Drivers must call [**WIFI_POWER_OFFLOAD_ACTION_FRAME_WAKE_PATTERN_PARAMETERS_INIT**](nf-wificxpoweroffload-wifi_power_offload_action_frame_wake_pattern_parameters_init.md) to initialize the [**WIFI_POWER_OFFLOAD_ACTION_FRAME_WAKE_PATTERN_PARAMETERS**](ns-wificxpoweroffload-wifi_power_offload_action_frame_wake_pattern_parameters.md) structure before calling this function.

## -see-also

[**WIFI_POWER_OFFLOAD_ACTION_FRAME_WAKE_PATTERN_PARAMETERS**](ns-wificxpoweroffload-wifi_power_offload_action_frame_wake_pattern_parameters.md)

[**WIFI_POWER_OFFLOAD_ACTION_FRAME_WAKE_PATTERN_PARAMETERS_INIT**](nf-wificxpoweroffload-wifi_power_offload_action_frame_wake_pattern_parameters_init.md)

