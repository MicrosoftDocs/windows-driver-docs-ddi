---
UID: NF:wdm.KeRemoveQueueDpc
title: KeRemoveQueueDpc function (wdm.h)
description: The KeRemoveQueueDpc routine removes the specified DPC object from the system DPC queue.
old-location: kernel\keremovequeuedpc.htm
tech.root: kernel
ms.assetid: 9f4b076f-006b-47cd-b970-8beed8d7e804
ms.date: 04/30/2018
keywords: ["KeRemoveQueueDpc function"]
ms.keywords: KeRemoveQueueDpc, KeRemoveQueueDpc routine [Kernel-Mode Driver Architecture], k105_b07492b0-b6b2-4d15-b62c-437a4b33c0b6.xml, kernel.keremovequeuedpc, wdm/KeRemoveQueueDpc
f1_keywords:
 - "wdm/KeRemoveQueueDpc"
 - "KeRemoveQueueDpc"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- KeRemoveQueueDpc
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeRemoveQueueDpc function


## -description


The <b>KeRemoveQueueDpc</b> routine removes the specified DPC object from the system DPC queue.


## -parameters




### -param Dpc [in, out]

A pointer to an initialized DPC object that was queued by a previous call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinsertqueuedpc">KeInsertQueueDpc</a> routine.


## -returns



<b>KeRemoveQueueDpc</b> returns <b>TRUE</b> if the DPC object is in the DPC queue. If the specified DPC object is not currently in the DPC queue, no operation is performed and <b>FALSE</b> is returned.




## -remarks



If the specified DPC object is currently queued, it is removed from the queue, canceling a call to the associated DPC routine.

Starting with Windows Vista with Service Pack 1 (SP1) and Windows Server 2008, a return value of <b>TRUE</b> always means that <b>KeRemoveQueueDpc</b> successfully removed the DPC object from the DPC queue before the DPC routine started to run. In earlier versions of Windows, the DPC routine might occasionally run even if <b>KeRemoveQueueDpc</b> returns <b>TRUE</b>. In these earlier versions of Windows, drivers that cannot tolerate ambiguity in the <b>TRUE</b> return value should treat return values of <b>TRUE</b> and <b>FALSE</b> identically.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializedpc">KeInitializeDpc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinsertqueuedpc">KeInsertQueueDpc</a>
 

 

