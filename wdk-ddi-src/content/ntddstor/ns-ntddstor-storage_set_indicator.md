---
UID: NS:ntddstor._STORAGE_SET_INDICATOR
title: STORAGE_SET_INDICATOR
author: windows-driver-content
description: 
tech.root: storage
ms.assetid: 8d6df6a0-5449-49ac-a2df-14af2c83ee30
ms.author: windowsdriverdev
ms.date: 11/30/2019
ms.topic: struct
f1_keywords:
 - "ntddstor/STORAGE_SET_INDICATOR"
ms.keywords: STORAGE_SET_INDICATOR, STORAGE_SET_INDICATOR, *PSTORAGE_SET_INDICATOR, 
req.header: ntddstor.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: STORAGE_SET_INDICATOR, *PSTORAGE_SET_INDICATOR
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - ntddstor.h
api_name: 
 - STORAGE_SET_INDICATOR
product: 
 - Windows
targetos: Windows
---

# STORAGE_SET_INDICATOR structure

## -description

The STORAGE_SET_INDICATOR structure identifies the indicator state to manipulate, and whether that state is to be set or cleared, in an [IOCTL_STORAGE_SET_LED](ni-ntddstor-ioctl_storage_set_led.md) request.

## -struct-fields

### -field Version

Version of this structure. Set to **sizeof**(STORAGE_SET_INDICATOR).

### -field Size

Total size in bytes of this structure. Set to **sizeof**(STORAGE_SET_INDICATOR).

### -field IndicatorControl

A [STORAGE_INDICATOR_STATE](ns-ntddstor-storage_indicator_state.md) union that identifies the indicator state to set or clear.

### -field Set

Boolean value. The device should set the LED indicator identified by *IndicatorControl* when *Set* is TRUE, and clear the LED when *Set* is FALSE.

## -remarks

STORAGE_SET_INDICATOR is the input buffer for [IOCTL_STORAGE_SET_LED](ni-ntddstor-ioctl_storage_set_led.md).

## -see-also

[IOCTL_STORAGE_SET_LED](ni-ntddstor-ioctl_storage_set_led.md)

[STORAGE_INDICATOR_STATE](ns-ntddstor-storage_indicator_state.md)
