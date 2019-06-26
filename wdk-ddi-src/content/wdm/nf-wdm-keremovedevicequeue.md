---
UID: NF:wdm.KeRemoveDeviceQueue
title: KeRemoveDeviceQueue function (wdm.h)
description: The KeRemoveDeviceQueue routine removes an entry from the head of a specified device queue.
old-location: kernel\keremovedevicequeue.htm
tech.root: kernel
ms.assetid: 9cad7d89-bcaa-47d6-b3e5-51653cbef318
ms.date: 04/30/2018
ms.keywords: KeRemoveDeviceQueue, KeRemoveDeviceQueue routine [Kernel-Mode Driver Architecture], k105_3e26b41e-7e9c-4fc9-8496-f107f3450dd7.xml, kernel.keremovedevicequeue, wdm/KeRemoveDeviceQueue
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlDispatch, HwStorPortProhibitedDDIs, IrqlDispatch(storport)
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- KeRemoveDeviceQueue
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeRemoveDeviceQueue function


## -description


The <b>KeRemoveDeviceQueue</b> routine removes an entry from the head of a specified device queue.


## -parameters




### -param DeviceQueue [in, out]

Pointer to an initialized device queue object for which the caller provides the storage. 


## -returns



If the device queue is empty but is set to a busy state, <b>KeRemoveDeviceQueue</b> returns <b>NULL</b>.




## -remarks



The specified device queue spin lock is acquired and the state of the device queue is checked. If the device queue is set to a busy state and an IRP is queued, this routine dequeues the entry and returns a pointer to the IRP. A call to <b>KeRemoveDeviceQueue</b> when the device queue object is set to a busy state but no IRPs are queued causes a state change to not-busy. The specified device queue's spin lock is released.

It is an error to call <b>KeRemoveDeviceQueue</b> when the device queue object is set to a not-busy state. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-keinitializedevicequeue">KeInitializeDeviceQueue</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-keinsertbykeydevicequeue">KeInsertByKeyDeviceQueue</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-keinsertdevicequeue">KeInsertDeviceQueue</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-keremovebykeydevicequeue">KeRemoveByKeyDeviceQueue</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-keremoveentrydevicequeue">KeRemoveEntryDeviceQueue</a>
 

 

