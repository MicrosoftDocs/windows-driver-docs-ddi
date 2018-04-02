---
UID: NF:wdm.MmProbeAndLockSelectedPages
title: MmProbeAndLockSelectedPages function
author: windows-driver-content
description: The MmProbeAndLockSelectedPages routine probes the selected virtual memory pages, makes them resident, and locks them in memory.
old-location: kernel\mmprobeandlockselectedpages_.htm
old-project: kernel
ms.assetid: 1DA632FF-FD5F-4C4C-8B8E-5AC26069094A
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: MmProbeAndLockSelectedPages, MmProbeAndLockSelectedPages routine [Kernel-Mode Driver Architecture], kernel.mmprobeandlockselectedpages_, wdm/MmProbeAndLockSelectedPages
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: 
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
req.lib: 
req.dll: 
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	MmProbeAndLockSelectedPages
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# MmProbeAndLockSelectedPages function


## -description


The <b>MmProbeAndLockSelectedPages</b> routine probes the selected virtual memory pages, makes them resident, and locks them in memory.


## -parameters




### -param MemoryDescriptorList [in, out]

A pointer to a memory descriptor list (MDL) that specifies a virtual memory buffer. If the routine successfully locks the pages in memory, the MDL is updated to describe the underlying physical pages.


### -param SegmentArray [in]

A pointer to an array of buffer segments that contain the virtual memory pages.


### -param AccessMode [in]

Specifies the access mode in which to probe the arguments, either KernelMode or UserMode.


### -param Operation [in]

Specifies the type of operation for which the caller wants the access rights probed and the pages locked. Set this parameter to IoReadAccess, IoWriteAccess, or IoModifyAccess. IoReadAccess indicates that the driver can examine the contents of the buffer but cannot change the contents. IoWriteAccess and IoModifyAccess, which are equivalent, indicate that the driver has both read and write access to the buffer. 


## -returns



None




## -remarks



Calls to <b>MmProbeAndLockSelectedPages</b> must be enclosed in a <b>try/except</b> block. If the pages do not support the specified operation, the routine raises the STATUS_ACCESS_VIOLATION or other exceptions. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546823">Handling Exceptions</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554664">MmProbeAndLockPages</a>
 

 

