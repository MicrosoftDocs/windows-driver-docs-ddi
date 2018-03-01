---
UID: NF:wdm.KeInitializeDeviceQueue
title: KeInitializeDeviceQueue function
author: windows-driver-content
description: The KeInitializeDeviceQueue routine initializes a device queue object to a not-busy state.
old-location: kernel\keinitializedevicequeue.htm
old-project: kernel
ms.assetid: 0df0fcba-9ae8-4c69-957a-5685ea40c378
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: KeInitializeDeviceQueue, KeInitializeDeviceQueue routine [Kernel-Mode Driver Architecture], k105_5d7ea571-8c88-45f7-917c-e42e6caac514.xml, kernel.keinitializedevicequeue, wdm/KeInitializeDeviceQueue
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
-	KeInitializeDeviceQueue
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeInitializeDeviceQueue function


## -description


The <b>KeInitializeDeviceQueue</b> routine initializes a device queue object to a not-busy state.


## -syntax


````
VOID KeInitializeDeviceQueue(
  _Out_ PKDEVICE_QUEUE DeviceQueue
);
````


## -parameters




### -param DeviceQueue [out]

Pointer to a device queue object for which the caller provides the storage. 


## -returns



None




## -remarks



<b>KeInitializeDeviceQueue</b> initializes the specified device queue and sets its state to not-busy.

A driver should call <b>KeInitializeDeviceQueue</b> from its <i>AddDevice</i> routine after creating the device object for the associated device. Storage for the device queue object must be resident: in the device extension of a driver-created device object, in the controller extension of a driver-created controller object, or in nonpaged pool allocated by the caller. 




## -see-also

<a href="..\wdm\nf-wdm-keremoveentrydevicequeue.md">KeRemoveEntryDeviceQueue</a>



<a href="..\wdm\nf-wdm-keinsertdevicequeue.md">KeInsertDeviceQueue</a>



<a href="..\wdm\nf-wdm-keinsertbykeydevicequeue.md">KeInsertByKeyDeviceQueue</a>



<a href="..\wdm\nf-wdm-keremovedevicequeue.md">KeRemoveDeviceQueue</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeInitializeDeviceQueue routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

