---
UID: NF:wdm.RtlUTF8StringToUnicodeString
title: RtlUTF8StringToUnicodeString function
author: windows-driver-content
description: TBD
tech.root: kernel
ms.assetid: ab311f45-8ab8-4360-b3ec-928633dfb020
ms.author: windowsdriverdev
ms.date: 03/24/2020
ms.topic: function
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
product:
 - Windows
f1_keywords:
 - RtlUTF8StringToUnicodeString
 - wdm/RtlUTF8StringToUnicodeString
---

# RtlUTF8StringToUnicodeString function (wdm.h)


## -description

**RtlUTF8StringToUnicodeString** converts the specified UTF8 source string into a Unicode string in accordance with the current system locale information.

## -parameters

### -param DestinationString

Pointer to a <a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure to hold the converted Unicode string.

If <i>AllocateDestinationString</i> is <b>TRUE</b>, the routine allocates a new buffer to hold the string data, updates the <b>Buffer</b> member of <i>DestinationString</i> to point to the new buffer, and set the maximum length field. Otherwise, the routine uses the currently-specified buffer to hold the string.

### -param SourceString

Pointer to the UTF8 string to be converted to Unicode.

### -param AllocateDestinationString

Specifies if this routine should allocate the buffer space for the destination string. If it does, the caller must deallocate the buffer by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfreeunicodestring">RtlFreeUnicodeString</a>.

## -returns

If the conversion succeeds, <b>RtlUTF8StringToUnicodeString</b> returns STATUS_SUCCESS. On failure, the routine does not allocate memory or perform a conversion.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfreeunicodestring">RtlFreeUnicodeString</a>

