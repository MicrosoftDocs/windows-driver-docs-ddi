---
UID: NF:wdm.KeInsertDeviceQueue
title: KeInsertDeviceQueue function (wdm.h)
description: The KeInsertDeviceQueue routine acquires the spin lock for the specified device queue object and, if the device queue is set to a busy state, queues the specified entry.
old-location: kernel\keinsertdevicequeue.htm
tech.root: kernel
ms.assetid: d0e634e0-f0b4-49a7-9df5-7af0842154f4
ms.date: 04/30/2018
keywords: ["KeInsertDeviceQueue function"]
ms.keywords: KeInsertDeviceQueue, KeInsertDeviceQueue routine [Kernel-Mode Driver Architecture], k105_a527fbb6-bb60-4051-9983-e960d9406abe.xml, kernel.keinsertdevicequeue, wdm/KeInsertDeviceQueue
f1_keywords:
 - "wdm/KeInsertDeviceQueue"
 - "KeInsertDeviceQueue"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlDispatch, MarkingQueuedIrps, HwStorPortProhibitedDDIs, IrqlDispatch(storport)
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
- KeInsertDeviceQueue
targetos: Windows
req.typenames: 
---

# KeInsertDeviceQueue function


## -description


The <b>KeInsertDeviceQueue</b> routine acquires the spin lock for the specified device queue object and, if the device queue is set to a busy state, queues the specified entry.


## -parameters




### -param DeviceQueue 
[in, out]
Pointer to a control object of type device queue for which the caller provides the storage.


### -param DeviceQueueEntry 
[in, out]
Pointer to the device queue entry that is to be inserted. 


## -returns



If the device queue is empty, <b>FALSE</b> is returned and the <i>DeviceQueueEntry</i> is not inserted in the device queue.




## -remarks



If the device queue is set to a busy state, the specified <i>DeviceQueueEntry</i> is inserted at the tail of the device queue and the device queue spin lock is released.

If <b>KeInsertDeviceQueue</b> returns <b>FALSE</b>, the entry was not queued and the caller must begin processing the IRP. A call to <b>KeInsertDeviceQueue</b> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinsertbykeydevicequeue">KeInsertByKeyDeviceQueue</a> when the queue is empty causes the device queue to change from a not-busy state to a busy state.

This routine is for code that queues an I/O request to a device driver. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializedevicequeue">KeInitializeDeviceQueue</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinsertbykeydevicequeue">KeInsertByKeyDeviceQueue</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keremovedevicequeue">KeRemoveDeviceQueue</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keremoveentrydevicequeue">KeRemoveEntryDeviceQueue</a>
 

 

