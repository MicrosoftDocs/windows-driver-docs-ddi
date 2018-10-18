---
UID: NF:wdm.KeRemoveEntryDeviceQueue
title: KeRemoveEntryDeviceQueue function
author: windows-driver-content
description: The KeRemoveEntryDeviceQueue routine returns whether the specified entry is in the device queue and removes it, if it was queued, from the device queue.
old-location: kernel\keremoveentrydevicequeue.htm
tech.root: kernel
ms.assetid: 2dc32517-3730-4a1c-a59a-f5036d6f54ef
ms.date: 04/30/2018
ms.keywords: KeRemoveEntryDeviceQueue, KeRemoveEntryDeviceQueue routine [Kernel-Mode Driver Architecture], k105_351b5540-c341-46d1-b2da-1ea88f78b7b2.xml, kernel.keremoveentrydevicequeue, wdm/KeRemoveEntryDeviceQueue
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlKeDispatchLte, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeRemoveEntryDeviceQueue
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeRemoveEntryDeviceQueue function


## -description


The <b>KeRemoveEntryDeviceQueue</b> routine returns whether the specified entry is in the device queue and removes it, if it was queued, from the device queue.


## -parameters




### -param DeviceQueue [in, out]

Pointer to an initialized device queue object for which the caller provides the storage.


### -param DeviceQueueEntry [in, out]

Pointer to the entry to be removed from the specified <i>DeviceQueue</i>.


## -returns



If the <i>DeviceQueueEntry</i> is queued, it is removed and <b>KeRemoveEntryDeviceQueue</b> returns <b>TRUE</b>.




## -remarks



The IRQL is set to DISPATCH_LEVEL and the <i>DeviceQueue</i> spin lock is acquired.

If the specified <i>DeviceQueueEntry</i> is not in the queue, the IRP either is already being processed, or the IRP has been canceled. In this case, <b>KeRemoveEntryDeviceQueue</b> simply returns <b>FALSE</b>.

The specified <i>DeviceQueue</i> spin lock is released and IRQL is restored to its previous value. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552126">KeInitializeDeviceQueue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552178">KeInsertByKeyDeviceQueue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552180">KeInsertDeviceQueue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553152">KeRemoveByKeyDeviceQueue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553156">KeRemoveDeviceQueue</a>
 

 

