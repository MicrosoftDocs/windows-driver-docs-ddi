---
UID: NF:ntifs.RtlFillMemoryUlonglong
title: RtlFillMemoryUlonglong macro
author: windows-driver-content
description: The RtlFillMemoryUlonglong routine fills a given range of memory with one or more repetitions of a given ULONGLONG value.
old-location: ifsk\rtlfillmemoryulonglong.htm
old-project: ifsk
ms.assetid: b5604cdb-084e-431a-b413-020e8213a18f
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , F, M, R, RtlFillMemoryUlonglong, RtlFillMemoryUlonglong routine [Installable File System Drivers], U, e, g, i, ifsk.rtlfillmemoryulonglong, l, m, n, ntifs/RtlFillMemoryUlonglong, o, r, rtlref_5e06d1be-accd-40f6-a5b1-2a3b39caacce.xml, t, y"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: For AMD64 systems, this routine is available on Microsoft Windows 2000 and later. For non-AMD64 systems, this routine is available on Windows 7 and later.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	RtlFillMemoryUlonglong
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlFillMemoryUlonglong macro


## -description


The <b>RtlFillMemoryUlonglong</b> routine fills a given range of memory with one or more repetitions of a given ULONGLONG value. 


## -syntax


````
VOID RtlFillMemoryUlonglong(
  _Out_ PVOID     Destination,
  _In_  SIZE_T    Length,
  _In_  ULONGLONG Pattern
);
````


## -parameters




### -param Destination [out]

Pointer to the start of the range of memory to be filled. This address must be ULONGLONG-aligned.


### -param Length [in]

Number of bytes to fill. This value must be a multiple of <b>sizeof(</b>ULONGLONG<b>)</b>. (Note: SIZE_T is defined in <i>basetsd.h</i>.)


### -param Pattern [in]

ULONGLONG value with which to fill the range starting at <i>Destination</i> and extending for <i>Length</i> bytes.


## -remarks



If the range of memory starting at <i>Destination</i> is nonpaged, the caller can be running at any IRQL. Otherwise, callers of <b>RtlFillMemoryUlonglong</b> must be running at IRQL &lt; DISPATCH_LEVEL.

For more information about managing buffered data and initializing driver-allocated buffers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540656">Buffered Data and Buffer Initialization</a>. 

For AMD64 systems, this routine is a macro.  For non-AMD64 systems, this routine is contained in Ntoskrnl.lib.




## -see-also

<a href="..\smclib\nf-smclib-rtlzeromemory.md">RtlZeroMemory</a>



<a href="..\ntifs\nf-ntifs-rtlfillmemoryulong.md">RtlFillMemoryUlong</a>



<a href="..\wdm\nf-wdm-rtlfillmemory.md">RtlFillMemory</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlFillMemoryUlonglong routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

