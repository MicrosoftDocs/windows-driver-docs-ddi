---
UID: NF:wdmsec.WdmlibRtlInitUnicodeStringEx
title: WdmlibRtlInitUnicodeStringEx function (wdmsec.h)
description: The WdmlibRtlInitUnicodeStringEx function initializes a counted string of Unicode characters.
old-location: kernel\wdmlibrtlinitunicodestringex.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["WdmlibRtlInitUnicodeStringEx function"]
ms.keywords: RtlInitUnicodeString, WdmlibRtlInitUnicodeStringEx, WdmlibRtlInitUnicodeStringEx function [Kernel-Mode Driver Architecture], kernel.wdmlibrtlinitunicodestringex, wdmsec/RtlInitUnicodeString, wdmsec/WdmlibRtlInitUnicodeStringEx
req.header: wdmsec.h
req.include-header: Wdmsec.h, Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: See Remarks section.
targetos: Windows
req.typenames: 
f1_keywords:
 - WdmlibRtlInitUnicodeStringEx
 - wdmsec/WdmlibRtlInitUnicodeStringEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - WdmlibRtlInitUnicodeStringEx
---

# WdmlibRtlInitUnicodeStringEx function


## -description

The **WdmlibRtlInitUnicodeStringEx** function initializes a counted string of Unicode characters.

## -parameters

### -param DestinationString 

[out]
A pointer to the [UNICODE_STRING](/windows/win32/api/ntdef/ns-ntdef-_unicode_string) structure to be initialized.

### -param SourceString 

[in, optional]
A pointer to a null-terminated wide-character string. This string is used to initialize the counted string pointed to by *DestinationString*.

## -remarks

The routine copies the *SourceString* pointer value to the **Buffer** member of the [UNICODE_STRING](/windows/win32/api/ntdef/ns-ntdef-_unicode_string) structure pointed to by *DestinationString*. The **Length** member of this structure is set to the length, in bytes, of the source string, excluding the terminating null. The **MaximumLength** member of the structure is set to the length, in bytes, of the source string, including the terminating null. If *SourceString* is **NULL**, **Length** and **MaximumLength** are both set to zero.

**WdmlibRtlInitUnicodeStringEx** does not alter the source string pointed to by *SourceString*.

> [!NOTE]
>If the source string is longer than MAX_USTRING - 1 bytes, **WdmlibRtlInitUnicodeStringEx** sets the **Length** member of the **UNICODE_STRING** structure pointed to by *DestinationString* to MAX_USTRING - 2, and sets the **MaximumLength** member of this structure to MAX_USTRING.  In this case, the **Length** and **MaximumLength** values misrepresent the length of the null-terminated source string, and relying on the accuracy of these values is potentially dangerous.


Callers of **WdmlibRtlInitUnicodeStringEx** can be running at IRQL <= DISPATCH_LEVEL if the *DestinationString* buffer is nonpageable. Usually, callers run at IRQL = PASSIVE_LEVEL because most other **Rtl*Xxx*String** routines cannot be called at IRQL > PASSIVE_LEVEL.

## -see-also

[RtlUnicodeStringInit](../ntstrsafe/nf-ntstrsafe-rtlunicodestringinit.md) 

[RtlUnicodeStringInitEx](../ntstrsafe/nf-ntstrsafe-rtlunicodestringinitex.md) 

[UNICODE_STRING](/windows/win32/api/ntdef/ns-ntdef-_unicode_string)

