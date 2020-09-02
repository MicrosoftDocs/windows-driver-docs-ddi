---
UID: NS:ntddk._WHEA_ERROR_RECORD_HEADER_FLAGS
title: WHEA_ERROR_RECORD_HEADER_FLAGS
author: windows-driver-content
description: 
tech.root: 
ms.assetid: 96520e0c-8a60-419a-97f2-f1fe71019570
ms.author: windowsdriverdev
ms.date: 08/19/2019
keywords: ["WHEA_ERROR_RECORD_HEADER_FLAGS structure"]
ms.keywords: WHEA_ERROR_RECORD_HEADER_FLAGS, WHEA_ERROR_RECORD_HEADER_FLAGS, *PWHEA_ERROR_RECORD_HEADER_FLAGS,
req.header: ntddk.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: WHEA_ERROR_RECORD_HEADER_FLAGS, *PWHEA_ERROR_RECORD_HEADER_FLAGS
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - _WHEA_ERROR_RECORD_HEADER_FLAGS
 - ntddk/_WHEA_ERROR_RECORD_HEADER_FLAGS
 - PWHEA_ERROR_RECORD_HEADER_FLAGS
 - ntddk/PWHEA_ERROR_RECORD_HEADER_FLAGS
 - WHEA_ERROR_RECORD_HEADER_FLAGS
 - ntddk/WHEA_ERROR_RECORD_HEADER_FLAGS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - WHEA_ERROR_RECORD_HEADER_FLAGS
product:
 - Windows
---

# WHEA_ERROR_RECORD_HEADER_FLAGS structure


## -description

Used in the **Flags** member of the [**WHEA_ERROR_RECORD_HEADER**](ns-ntddk-_whea_error_record_header.md) structure.

## -struct-fields

### -field DUMMYSTRUCTNAME

### -field DUMMYSTRUCTNAME.Recovered

A single bit that indicates that the operating system recovered from the error condition.

### -field DUMMYSTRUCTNAME.PreviousError

A single bit that indicates that the error condition occurred in a previous session of the operating system.

### -field DUMMYSTRUCTNAME.Simulated

A single bit that indicates that the error condition was simulated.

### -field DUMMYSTRUCTNAME.DeviceDriver

The error was reported by a device driver.

### -field DUMMYSTRUCTNAME.Reserved

Reserved for system use.

### -field AsULONG

A ULONG representation of the contents of the WHEA_ERROR_RECORD_HEADER_FLAGS union.

## -remarks

## -see-also

