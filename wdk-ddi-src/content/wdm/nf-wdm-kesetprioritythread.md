---
UID: NF:wdm.KeSetPriorityThread
title: KeSetPriorityThread function (wdm.h)
description: The KeSetPriorityThread routine sets the run-time priority of a driver-created thread.
old-location: kernel\kesetprioritythread.htm
tech.root: kernel
ms.assetid: 400176a1-9192-424b-be37-9386cc3ffbb2
ms.date: 04/30/2018
keywords: ["KeSetPriorityThread function"]
ms.keywords: KeSetPriorityThread, KeSetPriorityThread routine [Kernel-Mode Driver Architecture], k105_b767dc2c-39ec-41de-8888-177d83de67c4.xml, kernel.kesetprioritythread, wdm/KeSetPriorityThread
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
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - KeSetPriorityThread
 - wdm/KeSetPriorityThread
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - KeSetPriorityThread
---

# KeSetPriorityThread function


## -description

The <b>KeSetPriorityThread</b> routine sets the run-time priority of a driver-created thread.

## -parameters

### -param Thread 

[in, out]
Pointer to the driver-created thread.

### -param Priority 

[in]
Specifies the priority of the driver-created thread, usually to the real-time priority value, LOW_REALTIME_PRIORITY. The value LOW_PRIORITY is reserved for system use.

## -returns

<b>KeSetPriorityThread</b> returns the old priority of the thread.

## -remarks

If a call to <b>KeSetPriorityThread</b> resets the thread's priority to a lower value, execution of the thread can be rescheduled even if it is currently running or is about to be dispatched for execution.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kegetcurrentthread">KeGetCurrentThread</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kequeryprioritythread">KeQueryPriorityThread</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-kesetbaseprioritythread">KeSetBasePriorityThread</a>