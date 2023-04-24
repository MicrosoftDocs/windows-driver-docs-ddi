---
UID: NS:ntddk.DEBUG_DEVICE_ADDRESS
tech.root: kernel
title: DEBUG_DEVICE_ADDRESS (ntddk.h)
ms.date: 04/17/2023
targetos: Windows
description: This topic describes the DEBUG_DEVICE_ADDRESS structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntddk.h
req.include-header: Ntddk.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 22H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: DEBUG_DEVICE_ADDRESS, *PDEBUG_DEVICE_ADDRESS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - PDEBUG_DEVICE_ADDRESS
 - DEBUG_DEVICE_ADDRESS
f1_keywords:
 - PDEBUG_DEVICE_ADDRESS
 - ntddk/PDEBUG_DEVICE_ADDRESS
 - DEBUG_DEVICE_ADDRESS
 - ntddk/DEBUG_DEVICE_ADDRESS
dev_langs:
 - c++
helpviewer_keywords:
 - DEBUG_DEVICE_ADDRESS
---

## -description

This topic describes the **DEBUG_DEVICE_ADDRESS** structure.

## -struct-fields

### -field Type

Defines the **UCHAR** member **Type** (the CmResourceType).

### -field Valid

Defines the **BOOLEAN** member **Valid**.

### -field Reserved

Reserved for future use.

### -field BitWidth

Defines the **UCHAR** member **BitWidth**.

### -field AccessSize

Defines the **UCHAR** member **AccessSize**.

### -field TranslatedAddress

Defines the **PUCHAR** member **TranslatedAddress**.

### -field Length

Defines the **UCHAR** member **Length**.

## -remarks

## -see-also
