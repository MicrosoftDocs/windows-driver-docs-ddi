---
UID: NF:wdm.IoWithinStackLimits
title: IoWithinStackLimits function
author: windows-driver-content
description: The IoWithinStackLimits routine determines whether a region of memory is within the stack limit of the current thread.
old-location: kernel\iowithinstacklimits.htm
old-project: kernel
ms.assetid: af182cd5-23b5-4d5b-b3d4-ec65ec087d0b
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: IoWithinStackLimits, IoWithinStackLimits routine [Kernel-Mode Driver Architecture], k104_631648cb-6ba2-47b1-8745-e6314e17be30.xml, kernel.iowithinstacklimits, wdm/IoWithinStackLimits
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available on Windows Vista and later versions of the Windows operating system.
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoWithinStackLimits
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoWithinStackLimits function


## -description


The <b>IoWithinStackLimits</b> routine determines whether a region of memory is within the stack limit of the current thread.


## -parameters




### -param RegionStart [in]

A pointer to the start of the region.


### -param RegionSize [in]

The size of the region.


## -returns



<b>IoWithinStackLimits</b> returns <b>TRUE</b> is the current thread's stack contains the region completely and <b>FALSE</b> otherwise.




## -remarks



The <b>IoWithinStackLimits</b> routine considers all possible stack segments and the DPC stack, if necessary.

<div class="alert"><b>Note</b>    For drivers that use <a href="https://msdn.microsoft.com/library/windows/hardware/ff552030">KeExpandKernelStackAndCallout</a>, <b>IoWithinStackLimits</b> considers only the current thread.</div>
<div> </div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549247">IoGetInitialStack</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549286">IoGetRemainingStackSize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549299">IoGetStackLimits</a>
 

 

