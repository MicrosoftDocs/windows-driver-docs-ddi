---
UID: NS:ntddk._WHEAP_ROW_FAILURE_EVENT
tech.root: kernel
title: WHEAP_ROW_FAILURE_EVENT (ntddk.h)
ms.date: 03/28/2022
targetos: Windows
description: This topic describes the WHEAP_ROW_FAILURE_EVENT structure.
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
req.typenames: WHEAP_ROW_FAILURE_EVENT, *PWHEAP_ROW_FAILURE_EVENT
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _WHEAP_ROW_FAILURE_EVENT
 - PWHEAP_ROW_FAILURE_EVENT
 - WHEAP_ROW_FAILURE_EVENT
f1_keywords:
 - _WHEAP_ROW_FAILURE_EVENT
 - ntddk/_WHEAP_ROW_FAILURE_EVENT
 - PWHEAP_ROW_FAILURE_EVENT
 - ntddk/PWHEAP_ROW_FAILURE_EVENT
 - WHEAP_ROW_FAILURE_EVENT
 - ntddk/WHEAP_ROW_FAILURE_EVENT
dev_langs:
 - c++
helpviewer_keywords:
 - _WHEAP_ROW_FAILURE_EVENT
---

## -description

This topic describes the **WHEAP_ROW_FAILURE_EVENT** structure.

## -struct-fields

### -field WheaEventLogEntry

Defines the **WHEA_EVENT_LOG_ENTRY** member **WheaEventLogEntry**.

### -field LowOrderPage

Defines the **PFN_NUMBER** member **LowOrderPage**.

### -field HighOrderPage

Defines the **PFN_NUMBER** member **HighOrderPage**.

## -remarks

## -see-also
