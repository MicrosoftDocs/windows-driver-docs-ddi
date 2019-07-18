---
UID: NS:d3dkmthk._DXGK_GRAPHICSPOWER_REGISTER_INPUT_V_1_1
title: _DXGK_GRAPHICSPOWER_REGISTER_INPUT_V_1_1 (d3dkmthk.h)
description: Used to register the power state of a new input.
old-location: display\dxgk-graphicspower-register-input-v-1-1.htm
ms.assetid: 5b120f3c-43d2-447a-9959-0788d7decf50
ms.date: 05/10/2018
ms.keywords: "*PDXGK_GRAPHICSPOWER_REGISTER_INPUT, *PDXGK_GRAPHICSPOWER_REGISTER_INPUT_V_1_1, DXGK_GRAPHICSPOWER_REGISTER_INPUT, DXGK_GRAPHICSPOWER_REGISTER_INPUT_V_1_1, DXGK_GRAPHICSPOWER_REGISTER_INPUT_V_1_1 structure [Display Devices], PDXGK_GRAPHICSPOWER_REGISTER_INPUT_V_1_1, PDXGK_GRAPHICSPOWER_REGISTER_INPUT_V_1_1 structure pointer [Display Devices], _DXGK_GRAPHICSPOWER_REGISTER_INPUT_V_1_1, d3dkmthk/DXGK_GRAPHICSPOWER_REGISTER_INPUT_V_1_1, d3dkmthk/PDXGK_GRAPHICSPOWER_REGISTER_INPUT_V_1_1, display.dxgk-graphicspower-register-input-v-1-1"
ms.topic: struct
f1_keywords:
 - "d3dkmthk/DXGK_GRAPHICSPOWER_REGISTER_INPUT_V_1_1"
req.header: d3dkmthk.h
req.include-header:
req.target-type: Windows
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support: Windows 10, version 1709
req.namespace:
req.assembly:
req.type-library:
req.lib:
req.dll:
req.irql:
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmthk.h
api_name:
- DXGK_GRAPHICSPOWER_REGISTER_INPUT_V_1_1
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_GRAPHICSPOWER_REGISTER_INPUT_V_1_1, *PDXGK_GRAPHICSPOWER_REGISTER_INPUT_V_1_1
---

# _DXGK_GRAPHICSPOWER_REGISTER_INPUT_V_1_1 structure


## -description


Used to register the power state of a new input.


## -struct-fields




### -field Version

The current version being used.


### -field PrivateHandle

A private handle to the device.


### -field PowerNotificationCb

Issues a power notification.


### -field RemovalNotificationCb

Issues a removal notification.


### -field FStateNotificationCb

Issues a state notification.

