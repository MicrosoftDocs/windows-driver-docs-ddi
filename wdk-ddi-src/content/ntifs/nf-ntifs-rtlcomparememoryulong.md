---
UID: NF:ntifs.RtlCompareMemoryUlong
title: RtlCompareMemoryUlong function
author: windows-driver-content
description: The RtlCompareMemoryUlong routine returns how many bytes in a block of memory match a specified pattern.
old-location: ifsk\rtlcomparememoryulong.htm
old-project: ifsk
ms.assetid: 78ff21da-be0f-4b57-9162-1052a6c12b5c
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ntifs/RtlCompareMemoryUlong, RtlCompareMemoryUlong routine [Installable File System Drivers], rtlref_a220e168-945b-46d1-9aa7-7750bdfc39bd.xml, ifsk.rtlcomparememoryulong, RtlCompareMemoryUlong
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.irql: Any level (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
-	Ntdll.dll
apiname:
-	RtlCompareMemoryUlong
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlCompareMemoryUlong function


## -description


The <b>RtlCompareMemoryUlong</b> routine returns how many bytes in a block of memory match a specified pattern. 


## -syntax


````
SIZE_T RtlCompareMemoryUlong(
  _In_ PVOID  Source,
  _In_ SIZE_T Length,
  _In_ ULONG  Pattern
);
````


## -parameters




#### - Source [in]

Pointer to a block of memory. Must be aligned on a ULONG boundary. 


#### - Length [in]

Number of bytes over which the comparison should be done. Must be a multiple of <b>sizeof(</b>ULONG<b>)</b>. 


#### - Pattern [in]

Pattern to be compared byte by byte, repeatedly, through the specified memory range. 


## -returns


<b>RtlCompareMemoryUlong</b> returns the number of bytes that were compared and found to be equal. If all bytes compare as equal, the input <i>Length</i> is returned. <b>RtlCompareMemoryUlong</b> returns zero if <i>Source</i> is not ULONG-aligned or if <i>Length</i> is not a multiple of <b>sizeof(</b>ULONG<b>)</b>. 



## -remarks


If the block of memory at <i>Source</i> is nonpaged, the caller can be running at any IRQL. Otherwise, callers of <b>RtlCompareMemoryUlong</b> must be running at IRQL &lt; DISPATCH_LEVEL. 

For more information about managing buffered data and initializing driver-allocated buffers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540656">Buffered Data and Buffer Initialization</a>. 



## -see-also

<a href="..\wdm\nf-wdm-rtlcomparememory.md">RtlCompareMemory</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlCompareMemoryUlong routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

