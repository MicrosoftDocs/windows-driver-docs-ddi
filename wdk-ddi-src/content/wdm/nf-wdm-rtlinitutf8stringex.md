---
UID: NF:wdm.RtlInitUTF8StringEx
title: RtlInitUTF8StringEx function
author: windows-driver-content
description: TBD
tech.root: kernel
ms.assetid: 5d8f81aa-6ba6-4181-973f-a5e6dc868f74
ms.author: windowsdriverdev
ms.date: 03/24/2020
ms.topic: function
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
topic_type: 
- apiref
api_type: 
- 
api_location: 
- 
api_name: 
- RtlInitUTF8StringEx
product: 
- Windows
targetos: Windows

---

# RtlInitUTF8StringEx function



## -description

The <b>RtlInitUTF8StringEx</b> routine initializes a counted string of UTF-8 characters.

## -parameters

### -param DestinationString

A pointer to the <b>UTF8_STRING</b> structure to be initialized. The Ntdef.h header file defines this structure to be identical to the <a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-string">STRING</a> structure.

### -param SourceString

A pointer to a null-terminated character string. This string is used to initialize the counted string pointed to by <i>DestinationString</i>.


## -returns

Returns STATUS_NAME_TOO_LONG if the SourceString is too long. Otherwise, this routine returns STATUS_SUCCESS.

## -remarks

The routine copies the <i>SourceString</i> pointer value to the <b>Buffer</b> member of the <b>UTF8_STRING</b> structure pointed to by <i>DestinationString</i>. The <b>Length</b> member of this structure is set to the length, in bytes, of the source string, excluding the terminating null. The <b>MaximumLength</b> member of the structure is set to the length, in bytes, of the source string, including the terminating null. If <i>SourceString</i> is <b>NULL</b>, <b>Length</b> and <b>MaximumLength</b> are both set to zero.

<b>RtlInitUTF8StringEx</b> does not alter the source string pointed to by <i>SourceString</i>.

Callers of <b>RtlInitUTF8StringEx</b> can be running at IRQL <= DISPATCH_LEVEL if the <i>DestinationString</i> buffer is nonpageable. Usually, callers run at IRQL = PASSIVE_LEVEL because most other <b>Rtl<i>Xxx</i>String</b> routines cannot be called at IRQL > PASSIVE_LEVEL.

## -see-also

[**RtlInitAnsiString**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlinitansistring)