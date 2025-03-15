---
UID: NS:ntddvdeo.VIDEO_BRIGHTNESS_POLICY
tech.root: display
title: VIDEO_BRIGHTNESS_POLICY
ms.date: 11/01/2024
targetos: Windows
description: Learn more about the VIDEO_BRIGHTNESS_POLICY structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntddvdeo.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: VIDEO_BRIGHTNESS_POLICY, *PVIDEO_BRIGHTNESS_POLICY
typedef_isUnnamed: true
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddvdeo.h
api_name:
 - VIDEO_BRIGHTNESS_POLICY
 - PVIDEO_BRIGHTNESS_POLICY
f1_keywords:
 - VIDEO_BRIGHTNESS_POLICY
 - ntddvdeo/VIDEO_BRIGHTNESS_POLICY
 - PVIDEO_BRIGHTNESS_POLICY
 - ntddvdeo/PVIDEO_BRIGHTNESS_POLICY
dev_langs:
 - c++
helpviewer_keywords:
 - VIDEO_BRIGHTNESS_POLICY
---

## -description

The **VIDEO_BRIGHTNESS_POLICY** structure is used for setting brightness policy through the [Device Power Policy Manager](/windows-hardware/drivers/kernel/managing-device-power-policy).

## -struct-fields

### -field DefaultToBiosPolicy

Boolean value that specifies whether the brightness values should be adjusted to reflect the suggestions made by the system BIOS.

### -field LevelCount

Number of brightness levels specified in the **Levels** array; that is, the number of **BatteryLevel** and **Brightness** pairs specified.

### -field BatteryLevel

Value that specifies the level below which the **Brightness** value applies.

### -field Brightness

Value that expresses the percentage of how bright the screen should be at or below the **BatteryLevel**.

### -field Level[1]

Array of **BatteryLevel** and **Brightness** pairs that specify the brightness levels.
