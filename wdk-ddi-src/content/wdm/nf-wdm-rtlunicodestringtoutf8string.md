---
UID: NF:wdm.RtlUnicodeStringToUTF8String
title: RtlUnicodeStringToUTF8String function
author: windows-driver-content
description: TBD
tech.root: kernel
ms.assetid: 1a433bcd-c772-414c-9614-397e3da52cef
ms.author: windowsdriverdev
ms.date: 03/24/2020
ms.topic: function
ms.keywords: RtlUnicodeStringToUTF8String
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
topic_type: 
- apiref
api_type:
- DllExport
api_location: 
- wdm.h
api_name: 
- RtlUnicodeStringToUTF8String
product: 
- Windows
targetos: Windows

---

# RtlUnicodeStringToUTF8String function



## -description

**RtlUnicodeStringToUTF8String** converts the specified Unicode source string into an UTF8 string

## -parameters

### -param DestinationString

Pointer to a <a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-string">UTF8_STRING</a> structure to hold the converted UTF8 string.  If <i>AllocateDestinationString</i> is <b>TRUE</b>, the routine allocates a new buffer to hold the string data, and updates the <b>Buffer</b> member of <i>DestinationString</i> to point to the new buffer. Otherwise, the routine uses the currently specified buffer to hold the string.  The maximum length field is only set if *AllocateDestinationString* is TRUE.

### -param SourceString

Pointer to the Unicode source string to be converted to UTF8.

### -param AllocateDestinationString

<b>TRUE</b> if this routine is to allocate the buffer space for the <i>DestinationString</i>. If it does, the buffer must be deallocated by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfreeutf8string">RtlFreeUTF8String</a>.


## -returns

If the conversion succeeds, <b>RtlUnicodeStringToUTF8String</b> returns STATUS_SUCCESS. On failure, the routine does not allocate memory or perform a conversion.


## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfreeutf8string">RtlFreeUTF8String</a>