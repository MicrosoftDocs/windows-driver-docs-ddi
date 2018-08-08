---
UID: NF:ntifs.IoGetAttachedDeviceReference
title: IoGetAttachedDeviceReference function
author: windows-driver-content
description: The IoGetAttachedDeviceReference routine returns a pointer to the highest level device object in a driver stack and increments the reference count on that object.
old-location: kernel\iogetattacheddevicereference.htm
tech.root: kernel
ms.assetid: 540a4e5c-8d7b-4ba8-a9a6-6e13d9b85f23
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: IoGetAttachedDeviceReference, IoGetAttachedDeviceReference routine [Kernel-Mode Driver Architecture], k104_f7fa8878-306a-4de2-b418-8102754306f7.xml, kernel.iogetattacheddevicereference, wdm/IoGetAttachedDeviceReference
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: DanglingDeviceObjectReference, HwStorPortProhibitedDDIs
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
-	IoGetAttachedDeviceReference
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoGetAttachedDeviceReference function


## -description


The <b>IoGetAttachedDeviceReference</b> routine returns a pointer to the highest level device object in a driver stack and increments the reference count on that object.


## -parameters




### -param DeviceObject [in]

Pointer to the device object for which the topmost attached device object is retrieved. 


## -returns



<b>IoGetAttachedDeviceReference</b> returns a pointer to the highest level device object in a stack of attached device objects after incrementing the reference count on the object.




## -remarks



If the device object at <i>DeviceObject</i> has no device objects attached to it, <i>DeviceObject</i> and the returned pointer are equal.

Device driver writers must ensure that when they have completed all operations that required them to make this call, that they call <a href="https://msdn.microsoft.com/library/windows/hardware/ff557724">ObDereferenceObject</a> with the device object pointer returned by this routine. Failure to do so will prevent the system from freeing or deleting the device object because of an outstanding reference count.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557724">ObDereferenceObject</a>
 

 

