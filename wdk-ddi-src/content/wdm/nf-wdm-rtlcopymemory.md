---
UID: NF:wdm.RtlCopyMemory
title: RtlCopyMemory macro
author: windows-driver-content
description: The RtlCopyMemory routine copies the contents of a source memory block to a destination memory block.
old-location: kernel\rtlcopymemory.htm
old-project: kernel
ms.assetid: d204eeb4-e109-4a86-986f-0fccdda3f8f8
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: RtlCopyBytes, RtlCopyMemory, RtlCopyMemory routine [Kernel-Mode Driver Architecture], k109_f4bb1fef-aae6-4086-b95a-ae4dc220c04b.xml, kernel.rtlcopymemory, wdm/RtlCopyMemory
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtDll.dll (user mode); NtosKrnl.exe (kernel mode)
req.irql: Any level (See Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtDll.dll
-	NtosKrnl.exe
-	API-MS-Win-Core-Rtlsupport-l1-1-0.dll
api_name:
-	RtlCopyMemory
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlCopyMemory macro


## -description


The <b>RtlCopyMemory</b> routine copies the contents of a source memory block to a destination memory block.


## -parameters




### -param Destination [out]

A pointer to the destination memory block to copy the bytes to.


### -param Source [in]

A pointer to the source memory block to copy the bytes from.


### -param Length [in]

The number of bytes to copy from the source to the destination.


## -remarks



<b>RtlCopyMemory</b> runs faster than <b>RtlMoveMemory</b>. However, <b>RtlCopyMemory</b> requires that the source memory block, which is defined by <i>Source</i> and <i>Length</i>, cannot overlap the destination memory block, which is defined by <i>Destination</i> and <i>Length</i>. In contrast, <b>RtlMoveMemory</b> correctly handles the case in which the source and destination memory blocks overlap.

New drivers should use the <b>RtlCopyMemory</b> routine instead of <b>RtlCopyBytes</b>.

Callers of <b>RtlCopyMemory</b> can be running at any IRQL if the source and destination memory blocks are in nonpaged system memory. Otherwise, the caller must be running at IRQL &lt;= APC_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562030">RtlMoveMemory</a>
 

 

