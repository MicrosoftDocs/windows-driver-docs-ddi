---
UID: NF:wdm.KeRemoveByKeyDeviceQueue
title: KeRemoveByKeyDeviceQueue function
author: windows-driver-content
description: The KeRemoveByKeyDeviceQueue routine removes an entry, selected according to a sort key value, from the specified device queue.
old-location: kernel\keremovebykeydevicequeue.htm
old-project: kernel
ms.assetid: 9819567c-1c79-440c-9bac-f81f23df29ae
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wdm/KeRemoveByKeyDeviceQueue, KeRemoveByKeyDeviceQueue routine [Kernel-Mode Driver Architecture], k105_7ceac4c8-26cc-4dfc-86fa-937d1c63d11b.xml, KeRemoveByKeyDeviceQueue, kernel.keremovebykeydevicequeue
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	KeRemoveByKeyDeviceQueue
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeRemoveByKeyDeviceQueue function


## -description


The <b>KeRemoveByKeyDeviceQueue</b> routine removes an entry, selected according to a sort key value, from the specified device queue. 


## -syntax


````
PKDEVICE_QUEUE_ENTRY KeRemoveByKeyDeviceQueue(
  _Inout_ PKDEVICE_QUEUE DeviceQueue,
  _In_    ULONG          SortKey
);
````


## -parameters




### -param DeviceQueue [in, out]

Pointer to an initialized device queue object for which the caller provides the storage.


### -param SortKey [in]

Specifies the key to be used when searching the <i>DeviceQueue</i>. 


## -returns



<b>KeRemoveByKeyDeviceQueue</b> returns the device queue entry that was removed; returns <b>NULL</b> if the queue was empty.




## -remarks



This routine searches for the first entry in the device queue that has a value greater than or equal to the <i>SortKey</i>. After this entry is found, this routine removes the entry from the device queue and returns it. If no such entry is found, then the first entry in the queue is returned. If the device queue is empty, then the device is set to a not-busy state and a <b>NULL</b> pointer is returned. 

It is an error to call <b>KeRemoveByKeyDeviceQueue</b> when the device queue object is set to a not-busy state. 




## -see-also

<a href="..\wdm\nf-wdm-keinsertdevicequeue.md">KeInsertDeviceQueue</a>



<a href="..\wdm\nf-wdm-keremovedevicequeue.md">KeRemoveDeviceQueue</a>



<a href="..\wdm\nf-wdm-keinsertbykeydevicequeue.md">KeInsertByKeyDeviceQueue</a>



<a href="..\wdm\nf-wdm-keinitializedevicequeue.md">KeInitializeDeviceQueue</a>



<a href="..\wdm\nf-wdm-keremoveentrydevicequeue.md">KeRemoveEntryDeviceQueue</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeRemoveByKeyDeviceQueue routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

