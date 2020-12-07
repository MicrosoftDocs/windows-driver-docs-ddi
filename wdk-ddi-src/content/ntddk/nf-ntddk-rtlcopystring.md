---
UID: NF:ntddk.RtlCopyString
title: RtlCopyString function (ntddk.h)
description: The RtlCopyString routine copies a source string to a destination string.
old-location: kernel\rtlcopystring.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["RtlCopyString function"]
ms.keywords: RtlCopyString, RtlCopyString routine [Kernel-Mode Driver Architecture], k109_c68983f1-ec02-405f-a3a6-d1f3884fe303.xml, kernel.rtlcopystring, ntddk/RtlCopyString
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
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
req.irql: Any level (See Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlCopyString
 - ntddk/RtlCopyString
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlCopyString
---

# RtlCopyString function


## -description

The <b>RtlCopyString</b> routine copies a source string to a destination string.

## -parameters

### -param DestinationString 

[out]
A pointer to the destination string buffer.

### -param SourceString 

[in, optional]
A pointer to the source string buffer.

## -returns

None

## -remarks

The<i> DestinationString </i><b>Length</b> is set to zero if no source string is supplied. The <b>MaximumLength</b> and <b>Buffer</b> members of the <i>DestinationString</i> are not modified by this routine.

The number of bytes copied from the <i>SourceString</i> is either the length of <i>SourceString</i> or the maximum length of <i>DestinationString</i>, whichever is smaller. 

The <i>DestinationString</i> and <i>SourceString</i> buffers must be resident if the caller is running at IRQL >= DISPATCH_LEVEL.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlcopyunicodestring">RtlCopyUnicodeString</a>
