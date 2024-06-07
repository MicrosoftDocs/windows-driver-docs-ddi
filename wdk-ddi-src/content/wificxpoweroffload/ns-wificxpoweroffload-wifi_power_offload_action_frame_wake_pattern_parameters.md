---
UID: NS:wificxpoweroffload._WIFI_POWER_OFFLOAD_ACTION_FRAME_WAKE_PATTERN_PARAMETERS
tech.root: netvista
title: WIFI_POWER_OFFLOAD_ACTION_FRAME_WAKE_PATTERN_PARAMETERS
ms.date: 03/04/2024
targetos: Windows
description: The WIFI_POWER_OFFLOAD_ACTION_FRAME_WAKE_PATTERN_PARAMETERS structure contains parameters for an action frame wake pattern low power protocol offload to a WiFiCx network adapter.
prerelease:
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wificxpoweroffload.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2 
req.target-min-winversvr: 
req.target-type: 
req.typenames: WIFI_POWER_OFFLOAD_ACTION_FRAME_WAKE_PATTERN_PARAMETERS
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wificxpoweroffload.h
api_name:
 - _WIFI_POWER_OFFLOAD_ACTION_FRAME_WAKE_PATTERN_PARAMETERS
 - WIFI_POWER_OFFLOAD_ACTION_FRAME_WAKE_PATTERN_PARAMETERS
f1_keywords:
 - _WIFI_POWER_OFFLOAD_ACTION_FRAME_WAKE_PATTERN_PARAMETERS
 - wificxpoweroffload/_WIFI_POWER_OFFLOAD_ACTION_FRAME_WAKE_PATTERN_PARAMETERS
 - WIFI_POWER_OFFLOAD_ACTION_FRAME_WAKE_PATTERN_PARAMETERS
 - wificxpoweroffload/WIFI_POWER_OFFLOAD_ACTION_FRAME_WAKE_PATTERN_PARAMETERS
dev_langs:
 - c++
helpviewer_keywords:
 - _WIFI_POWER_OFFLOAD_ACTION_FRAME_WAKE_PATTERN_PARAMETERS
---

## -description

The **WIFI_POWER_OFFLOAD_ACTION_FRAME_WAKE_PATTERN_PARAMETERS** structure contains parameters for an action frame wake pattern low power protocol offload to a WiFiCx network adapter.

## -struct-fields

### -field Size

The size of the **WIFI_POWER_OFFLOAD_ACTION_FRAME_WAKE_PATTERN_PARAMETERS** structure in bytes.

### -field FilterOnFrameAction

**FilterOnFrameAction** can have the following values:
* **0**: The IHV driver should indicate all incoming action frames that match **ActionFrameCategory**.
* **1**: The IHV driver should indicate all incoming action frames that match both **ActionFrameCategory** and **ActionFrameAction**.

### -field ActionFrameCategory

A UINT8 representing the Action Frame Category.

### -field ActionFrameAction

A UINT8 representing the Action Frame Action. The driver ignores **ActionFrameAction** if it isn't filtering by action type.

## -remarks

The IHV driver must call [**WIFI_POWER_OFFLOAD_ACTION_FRAME_WAKE_PATTERN_PARAMETERS_INIT**](nf-wificxpoweroffload-wifi_power_offload_action_frame_wake_pattern_parameters_init.md) to initialize this structure and fill in its **Size** field. Then the driver must call [**WifiPowerOffloadGetActionFrameWakePatternParameters**](nf-wificxpoweroffload-wifipoweroffloadgetactionframewakepatternparameters.md) to fill in the remaining members of the structure.

## -see-also

[**WIFI_POWER_OFFLOAD_ACTION_FRAME_WAKE_PATTERN_PARAMETERS_INIT**](nf-wificxpoweroffload-wifi_power_offload_action_frame_wake_pattern_parameters_init.md)

[**WifiPowerOffloadGetActionFrameWakePatternParameters**](nf-wificxpoweroffload-wifipoweroffloadgetactionframewakepatternparameters.md)