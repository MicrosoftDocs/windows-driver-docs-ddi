---
UID: NF:wdm.RtlInitUTF8StringEx
title: RtlInitUTF8StringEx function (wdm.h)
description: The RtlInitUTF8StringEx routine initializes a counted string of UTF-8 characters.
tech.root: kernel
ms.date: 03/24/2020
ms.keywords: RtlInitUTF8StringEx
req.header: wdm.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - wdm.h
api_name:
 - RtlInitUTF8StringEx
f1_keywords:
 - RtlInitUTF8StringEx
 - wdm/RtlInitUTF8StringEx
---

# RtlInitUTF8StringEx function (wdm.h)

## -description

The **RtlInitUTF8StringEx** routine initializes a counted string of UTF-8 characters.

## -parameters

### -param DestinationString

A pointer to the **UTF8_STRING** structure to be initialized. The Ntdef.h header file defines this structure to be identical to the [**STRING**](/windows/win32/api/ntdef/ns-ntdef-string) structure.

### -param SourceString

A pointer to a null-terminated character string. This string is used to initialize the counted string pointed to by *DestinationString*.

## -returns

Returns STATUS_NAME_TOO_LONG if the SourceString is too long. Otherwise, this routine returns STATUS_SUCCESS.

## -remarks

The routine copies the *SourceString* pointer value to the **Buffer** member of the **UTF8_STRING** structure pointed to by *DestinationString*. The **Length** member of this structure is set to the length, in bytes, of the source string, excluding the terminating null. The **MaximumLength** member of the structure is set to the length, in bytes, of the source string, including the terminating null. If *SourceString* is **NULL**, **Length** and **MaximumLength** are both set to zero.

**RtlInitUTF8StringEx** does not alter the source string pointed to by *SourceString*.

Callers of **RtlInitUTF8StringEx** can be running at IRQL <= DISPATCH_LEVEL if the *DestinationString* buffer is nonpageable. Usually, callers run at IRQL = PASSIVE_LEVEL because most other **Rtl*Xxx*String** routines cannot be called at IRQL > PASSIVE_LEVEL.

## -see-also

[**RtlInitAnsiString**](./nf-wdm-rtlinitansistring.md)
