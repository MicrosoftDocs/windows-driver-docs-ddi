---
UID: NF:ntddk.RtlCopyString
title: RtlCopyString function
description: The RtlCopyString routine copies a source string to a destination string.
old-location: kernel\rtlcopystring.htm
tech.root: kernel
ms.assetid: 5295be15-b42e-4e5b-8257-434fb9ed6c83
ms.date: 04/30/2018
ms.keywords: RtlCopyString, RtlCopyString routine [Kernel-Mode Driver Architecture], k109_c68983f1-ec02-405f-a3a6-d1f3884fe303.xml, kernel.rtlcopystring, ntddk/RtlCopyString
ms.topic: function
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlCopyString
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlCopyString function


## -description


The <b>RtlCopyString</b> routine copies a source string to a destination string.


## -parameters




### -param DestinationString [out]

A pointer to the destination string buffer. 


### -param SourceString [in, optional]

A pointer to the source string buffer. 


## -returns



None




## -remarks



The<i> DestinationString </i><b>Length</b> is set to zero if no source string is supplied. The <b>MaximumLength</b> and <b>Buffer</b> members of the <i>DestinationString</i> are not modified by this routine.

The number of bytes copied from the <i>SourceString</i> is either the length of <i>SourceString</i> or the maximum length of <i>DestinationString</i>, whichever is smaller. 

The <i>DestinationString</i> and <i>SourceString</i> buffers must be resident if the caller is running at IRQL &gt;= DISPATCH_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561817">RtlCopyUnicodeString</a>
 

 

