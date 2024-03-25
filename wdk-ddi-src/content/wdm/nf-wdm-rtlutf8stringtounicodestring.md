---
UID: NF:wdm.RtlUTF8StringToUnicodeString
title: RtlUTF8StringToUnicodeString function
description: The RtlUTF8StringToUnicodeString function converts the specified UTF8 source string into a Unicode string in accordance with the current system locale information.
tech.root: kernel
ms.date: 05/27/2021
ms.keywords: RtlUTF8StringToUnicodeString
req.header: wdm.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
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
 - RtlUTF8StringToUnicodeString
f1_keywords:
 - RtlUTF8StringToUnicodeString
 - wdm/RtlUTF8StringToUnicodeString
---

# RtlUTF8StringToUnicodeString function (wdm.h)

## -description

The **RtlUTF8StringToUnicodeString** function converts the specified UTF8 source string into a Unicode string in accordance with the current system locale information.

## -parameters

### -param DestinationString

Pointer to a [**UNICODE_STRING**](/windows/win32/api/ntdef/ns-ntdef-_unicode_string) structure to hold the converted Unicode string.

If *AllocateDestinationString* is **TRUE**, the routine allocates a new buffer to hold the string data, updates the **Buffer** member of *DestinationString* to point to the new buffer, and set the maximum length field. Otherwise, the routine uses the currently-specified buffer to hold the string.

### -param SourceString

Pointer to the UTF8 string to be converted to Unicode.

### -param AllocateDestinationString

Specifies if this routine should allocate the buffer space for the destination string. If it does, the caller must deallocate the buffer by calling [**RtlFreeUnicodeString**](./nf-wdm-rtlfreeunicodestring.md).

## -returns

If the conversion succeeds, **RtlUTF8StringToUnicodeString** returns STATUS_SUCCESS. On failure, the routine does not allocate memory or perform a conversion.

## -see-also

[**RtlFreeUnicodeString**](./nf-wdm-rtlfreeunicodestring.md)
