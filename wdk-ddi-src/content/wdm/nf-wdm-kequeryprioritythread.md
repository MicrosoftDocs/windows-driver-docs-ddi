---
UID: NF:wdm.KeQueryPriorityThread
title: KeQueryPriorityThread function
author: windows-driver-content
description: The KeQueryPriorityThread routine returns the current priority of a particular thread.
old-location: kernel\kequeryprioritythread.htm
tech.root: kernel
ms.assetid: 69a8ad3f-641d-4aaf-9184-e56dee6ca347
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: KeQueryPriorityThread, KeQueryPriorityThread routine [Kernel-Mode Driver Architecture], k105_6a330d84-aa5a-4822-a4d3-7b68aa9e8882.xml, kernel.kequeryprioritythread, wdm/KeQueryPriorityThread
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeQueryPriorityThread
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeQueryPriorityThread function


## -description


The <b>KeQueryPriorityThread</b> routine returns the current priority of a particular thread. 


## -parameters




### -param Thread [in]

Pointer to a dispatcher object of type KTHREAD. 


## -returns



<b>KeQueryPriorityThread</b> returns the current priority of the specified thread. 




## -remarks



Thread priorities range from 0 to 31, where 0 is the lowest priority and 31 is the highest. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552084">KeGetCurrentThread</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553246">KeSetBasePriorityThread</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553265">KeSetPriorityThread</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559936">PsGetCurrentThread</a>
 

 

