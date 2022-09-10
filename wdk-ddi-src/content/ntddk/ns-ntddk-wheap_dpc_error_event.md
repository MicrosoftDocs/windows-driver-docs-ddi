---
UID: NS:ntddk._WHEAP_DPC_ERROR_EVENT
tech.root: kernel
title: WHEAP_DPC_ERROR_EVENT (ntddk.h)
ms.date: 03/28/2022
targetos: Windows
description: This topic describes the WHEAP_DPC_ERROR_EVENT structure.
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
req.typenames: WHEAP_DPC_ERROR_EVENT, *PWHEAP_DPC_ERROR_EVENT
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _WHEAP_DPC_ERROR_EVENT
 - PWHEAP_DPC_ERROR_EVENT
 - WHEAP_DPC_ERROR_EVENT
f1_keywords:
 - _WHEAP_DPC_ERROR_EVENT
 - ntddk/_WHEAP_DPC_ERROR_EVENT
 - PWHEAP_DPC_ERROR_EVENT
 - ntddk/PWHEAP_DPC_ERROR_EVENT
 - WHEAP_DPC_ERROR_EVENT
 - ntddk/WHEAP_DPC_ERROR_EVENT
dev_langs:
 - c++
helpviewer_keywords:
 - _WHEAP_DPC_ERROR_EVENT
---

## -description

This topic describes the **WHEAP_DPC_ERROR_EVENT** structure.

## -struct-fields

### -field WheaEventLogEntry

Defines the **WHEA_EVENT_LOG_ENTRY** member **WheaEventLogEntry**.

### -field ErrType

Defines the **WHEAP_DPC_ERROR_EVENT_TYPE** member **ErrType**.

### -field Bus

Defines the **ULONG** member **Bus**.

### -field Device

Defines the **ULONG** member **Device**.

### -field Function

Defines the **ULONG** member **Function**.

### -field DeviceId

Defines the **USHORT** member **DeviceId**.

### -field VendorId

Defines the **USHORT** member **VendorId**.

## -remarks

## -see-also
