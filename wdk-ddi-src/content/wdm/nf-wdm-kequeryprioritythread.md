---
UID: NF:wdm.KeQueryPriorityThread
title: KeQueryPriorityThread function (wdm.h)
description: The KeQueryPriorityThread routine returns the current priority of a particular thread.
old-location: kernel\kequeryprioritythread.htm
tech.root: kernel
ms.assetid: 69a8ad3f-641d-4aaf-9184-e56dee6ca347
ms.date: 04/30/2018
ms.keywords: KeQueryPriorityThread, KeQueryPriorityThread routine [Kernel-Mode Driver Architecture], k105_6a330d84-aa5a-4822-a4d3-7b68aa9e8882.xml, kernel.kequeryprioritythread, wdm/KeQueryPriorityThread
f1_keywords:
 - "wdm/KeQueryPriorityThread"
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- KeQueryPriorityThread
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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kegetcurrentthread">KeGetCurrentThread</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-kesetbaseprioritythread">KeSetBasePriorityThread</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kesetprioritythread">KeSetPriorityThread</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-psgetcurrentthread">PsGetCurrentThread</a>
 

 

