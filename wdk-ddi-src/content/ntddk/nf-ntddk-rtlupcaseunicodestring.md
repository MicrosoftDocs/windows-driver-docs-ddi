---
UID: NF:ntddk.RtlUpcaseUnicodeString
title: RtlUpcaseUnicodeString function (ntddk.h)
description: The RtlUpcaseUnicodeString routine converts a copy of the source string to uppercase and writes the converted string in the destination buffer.
old-location: kernel\rtlupcaseunicodestring.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["RtlUpcaseUnicodeString function"]
ms.keywords: RtlUpcaseUnicodeString, RtlUpcaseUnicodeString routine [Kernel-Mode Driver Architecture], k109_617db3d7-18d8-46eb-a555-59f99d9cae78.xml, kernel.rtlupcaseunicodestring, ntddk/RtlUpcaseUnicodeString
req.header: ntddk.h
req.include-header: Ntddk.h
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
req.dll: NtosKrnl.exe (kernel mode); Ntdll.dll (user mode)
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlUpcaseUnicodeString
 - ntddk/RtlUpcaseUnicodeString
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
 - Ntdll.dll
api_name:
 - RtlUpcaseUnicodeString
---

# RtlUpcaseUnicodeString function


## -description

The <b>RtlUpcaseUnicodeString</b> routine converts a copy of the source string to uppercase and writes the converted string in the destination buffer.

## -parameters

### -param DestinationString [in, out]


Pointer to a caller-allocated buffer for the converted Unicode string.

### -param SourceString [in]


Pointer to the source Unicode string to be converted to uppercase.

### -param AllocateDestinationString [in]


Specifies if <b>RtlUpcaseUnicodeString</b> is to allocate the buffer space for the <i>DestinationString</i>. If it does, the buffer must be deallocated by calling <b>RtlFreeUnicodeString</b>.

## -returns

If the operation succeeds, <b>RtlUpcaseUnicodeString</b> returns STATUS_SUCCESS. Otherwise, no storage was allocated, and no conversion was done.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfreeunicodestring">RtlFreeUnicodeString</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlupcaseunicodechar">RtlUpcaseUnicodeChar</a>
