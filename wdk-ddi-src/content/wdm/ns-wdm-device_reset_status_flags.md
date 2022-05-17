---
UID: NS:wdm._DEVICE_RESET_STATUS_FLAGS
tech.root: kernel
title: DEVICE_RESET_STATUS_FLAGS (wdm.h)
ms.date: 03/11/2022
targetos: Windows
description: This topic describes the DEVICE_RESET_STATUS_FLAGS union.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.include-header: Wdm.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 22H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: DEVICE_RESET_STATUS_FLAGS, *PDEVICE_RESET_STATUS_FLAGS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _DEVICE_RESET_STATUS_FLAGS
 - PDEVICE_RESET_STATUS_FLAGS
 - DEVICE_RESET_STATUS_FLAGS
f1_keywords:
 - _DEVICE_RESET_STATUS_FLAGS
 - wdm/_DEVICE_RESET_STATUS_FLAGS
 - PDEVICE_RESET_STATUS_FLAGS
 - wdm/PDEVICE_RESET_STATUS_FLAGS
 - DEVICE_RESET_STATUS_FLAGS
 - wdm/DEVICE_RESET_STATUS_FLAGS
dev_langs:
 - c++
helpviewer_keywords:
 - _DEVICE_RESET_STATUS_FLAGS
---

## -description

This topic describes the **DEVICE_RESET_STATUS_FLAGS** union.

## -struct-fields

### -field u

Defines the **u** structure.

### -field u.KeepStackReset

Defines the **ULONGLONG** member **KeepStackReset**.

### -field u.RecoveringFromBusError

Defines the **ULONGLONG** member **RecoveringFromBusError**.

### -field u.Reserved

Reserved for future use.

### -field AsUlonglong

Defines the **ULONGLONG** member **AsUlonglong**.

## -remarks

## -see-also
