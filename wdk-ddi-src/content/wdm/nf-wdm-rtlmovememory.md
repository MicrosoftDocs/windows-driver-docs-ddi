---
UID: NF:wdm.RtlMoveMemory
title: RtlMoveMemory macro
author: windows-driver-content
description: The RtlMoveMemory routine copies the contents of a source memory block to a destination memory block, and supports overlapping source and destination memory blocks.
old-location: kernel\rtlmovememory.htm
old-project: kernel
ms.assetid: f6727247-e704-42d7-b4f1-ce7d20e317bb
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlMoveMemory, kernel.rtlmovememory, wdm/RtlMoveMemory, k109_5731ba5b-a7a5-4883-87cf-543768a29a93.xml, RtlMoveMemory routine [Kernel-Mode Driver Architecture]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: BufAfterReqCompletedIntIoctlA, BufAfterReqCompletedIoctlA, BufAfterReqCompletedReadA, BufAfterReqCompletedWriteA
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level (See Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	RtlMoveMemory
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlMoveMemory macro


## -description


The <b>RtlMoveMemory</b> routine copies the contents of a source memory block to a destination memory block, and supports overlapping source and destination memory blocks.


## -syntax


````
VOID RtlMoveMemory(
  _Out_       VOID UNALIGNED *Destination,
  _In_  const VOID UNALIGNED *Source,
  _In_        SIZE_T         Length
);
````


## -parameters




### -param Destination [out]

A pointer to the destination memory block to copy the bytes to.


### -param Source [in]

A pointer to the source memory block to copy the bytes from.


### -param Length [in]

The number of bytes to copy from the source to the destination.


## -remarks


The source memory block, which is defined by <i>Source</i> and <i>Length</i>, can overlap the destination memory block, which is defined by <i>Destination</i> and <i>Length</i>.

The <a href="..\wdm\nf-wdm-rtlcopymemory.md">RtlCopyMemory</a> routine runs faster than <b>RtlMoveMemory</b>, but <b>RtlCopyMemory</b> requires that the source and destination memory blocks do not overlap.

Callers of <b>RtlMoveMemory</b> can be running at any IRQL if the source and destination memory blocks are in nonpaged system memory. Otherwise, the caller must be running at IRQL &lt;= APC_LEVEL.



## -see-also

<a href="..\wdm\nf-wdm-rtlcopymemory.md">RtlCopyMemory</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlMoveMemory routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

