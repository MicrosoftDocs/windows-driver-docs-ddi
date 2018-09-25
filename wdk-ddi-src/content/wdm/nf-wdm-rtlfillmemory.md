---
UID: NF:wdm.RtlFillMemory
title: RtlFillMemory macro
author: windows-driver-content
description: The RtlFillMemory routine fills a block of memory with the specified fill value.
old-location: kernel\rtlfillmemory.htm
tech.root: kernel
ms.assetid: 9a73331a-cc73-4a47-948b-a821600ca6a6
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: RtlFillMemory, RtlFillMemory routine [Kernel-Mode Driver Architecture], k109_db7a2a9f-c7b5-40c3-9755-e386bbaf5353.xml, kernel.rtlfillmemory, wdm/RtlFillMemory
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
req.lib: NtDll.lib (user mode); NtosKrnl.lib (kernel mode)
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
-	API-MS-Win-Core-rtlsupport-l1-1-0.dll
api_name:
-	RtlFillMemory
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlFillMemory macro


## -description


The <b>RtlFillMemory</b> routine fills a block of memory with the specified fill value.


## -parameters




### -param Destination [out]

Datatype: void*. A pointer to the block of memory to be filled.


### -param Length [in]

Datatype: size_t. The number of bytes in the block of memory to be filled.


### -param Fill [in]

Datatype: int. The value to fill the destination memory block with. This value is copied to every byte in the memory block that is defined by <i>Destination</i> and <i>Length</i>.


## -remarks



Callers of <b>RtlFillMemory</b> can be running at any IRQL if the destination memory block is in nonpaged system memory. Otherwise, the caller must be running at IRQL &lt;= APC_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563610">RtlZeroMemory</a>
 

 

