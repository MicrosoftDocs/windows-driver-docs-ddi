---
UID: NS:ntddstor._STORAGE_INDICATOR_STATE
title: STORAGE_INDICATOR_STATE
description: 
tech.root: storage
ms.date: 11/30/2019
ms.topic: struct
f1_keywords:
 - "ntddstor/STORAGE_INDICATOR_STATE"
 - "STORAGE_INDICATOR_STATE"
ms.keywords: STORAGE_INDICATOR_STATE, STORAGE_INDICATOR_STATE, *PSTORAGE_INDICATOR_STATE, 
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
req.typenames: STORAGE_INDICATOR_STATE, *PSTORAGE_INDICATOR_STATE
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - ntddstor.h
api_name: 
 - STORAGE_INDICATOR_STATE
product: 
 - Windows
targetos: Windows
---

# STORAGE_INDICATOR_STATE structure

## -description

The STORAGE_INDICATOR_STATE union identifies the indicator state to set or clear during an [IOCTL_STORAGE_SET_LED](ni-ntddstor-ioctl_storage_set_led.md) request.

## -struct-fields

### -field State

### -field State.Ok

OK State

### -field State.Locate

### -field State.Fail

### -field State.Rebuild

### -field State.PFA

Predict Failure Analysis (PFA)

### -field State.HotSpare

### -field State.InACriticalArray

### -field State.InAFailedArray

### -field State.InvalidDevice

### -field State.Disabled

### -field State.Reserved

Reserved; do not use.

### -field AsUlong

????????????????????

## -remarks

STORAGE_INDICATOR_STATE is a member of the STORAGE_SET_INDICATOR](ns-storage_set_indicator.md) structure, which is the input buffer for [IOCTL_STORAGE_SET_LED](ni-ntddstor-ioctl_storage_set_led.md).

See the SCSI specification for more information.

## -see-also

[IOCTL_STORAGE_SET_LED](ni-ntddstor-ioctl_storage_set_led.md)
