---
UID: NF:wdm.KeInsertDeviceQueue
title: KeInsertDeviceQueue function
author: windows-driver-content
description: The KeInsertDeviceQueue routine acquires the spin lock for the specified device queue object and, if the device queue is set to a busy state, queues the specified entry.
old-location: kernel\keinsertdevicequeue.htm
old-project: kernel
ms.assetid: d0e634e0-f0b4-49a7-9df5-7af0842154f4
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: KeInsertDeviceQueue, k105_a527fbb6-bb60-4051-9983-e960d9406abe.xml, wdm/KeInsertDeviceQueue, KeInsertDeviceQueue routine [Kernel-Mode Driver Architecture], kernel.keinsertdevicequeue
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	KeInsertDeviceQueue
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeInsertDeviceQueue function


## -description


The <b>KeInsertDeviceQueue</b> routine acquires the spin lock for the specified device queue object and, if the device queue is set to a busy state, queues the specified entry.


## -syntax


````
BOOLEAN KeInsertDeviceQueue(
  _Inout_ PKDEVICE_QUEUE       DeviceQueue,
  _Inout_ PKDEVICE_QUEUE_ENTRY DeviceQueueEntry
);
````


## -parameters




### -param DeviceQueue [in, out]

Pointer to a control object of type device queue for which the caller provides the storage.


### -param DeviceQueueEntry [in, out]

Pointer to the device queue entry that is to be inserted. 


## -returns


If the device queue is empty, <b>FALSE</b> is returned and the <i>DeviceQueueEntry</i> is not inserted in the device queue.



## -remarks


If the device queue is set to a busy state, the specified <i>DeviceQueueEntry</i> is inserted at the tail of the device queue and the device queue spin lock is released.

If <b>KeInsertDeviceQueue</b> returns <b>FALSE</b>, the entry was not queued and the caller must begin processing the IRP. A call to <b>KeInsertDeviceQueue</b> or <a href="..\wdm\nf-wdm-keinsertbykeydevicequeue.md">KeInsertByKeyDeviceQueue</a> when the queue is empty causes the device queue to change from a not-busy state to a busy state.

This routine is for code that queues an I/O request to a device driver. 



## -see-also

<a href="..\wdm\nf-wdm-keremoveentrydevicequeue.md">KeRemoveEntryDeviceQueue</a>

<a href="..\wdm\nf-wdm-keinsertbykeydevicequeue.md">KeInsertByKeyDeviceQueue</a>

<a href="..\wdm\nf-wdm-keremovedevicequeue.md">KeRemoveDeviceQueue</a>

<a href="..\wdm\nf-wdm-keinitializedevicequeue.md">KeInitializeDeviceQueue</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeInsertDeviceQueue routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

