---
UID: NF:wdm.IoGetAttachedDeviceReference
title: IoGetAttachedDeviceReference function
author: windows-driver-content
description: The IoGetAttachedDeviceReference routine returns a pointer to the highest level device object in a driver stack and increments the reference count on that object.
old-location: kernel\iogetattacheddevicereference.htm
old-project: kernel
ms.assetid: 540a4e5c-8d7b-4ba8-a9a6-6e13d9b85f23
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: wdm/IoGetAttachedDeviceReference, IoGetAttachedDeviceReference routine [Kernel-Mode Driver Architecture], IoGetAttachedDeviceReference, kernel.iogetattacheddevicereference, k104_f7fa8878-306a-4de2-b418-8102754306f7.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoGetAttachedDeviceReference
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoGetAttachedDeviceReference function


## -description


The <b>IoGetAttachedDeviceReference</b> routine returns a pointer to the highest level device object in a driver stack and increments the reference count on that object.


## -syntax


````
PDEVICE_OBJECT IoGetAttachedDeviceReference(
  _In_ PDEVICE_OBJECT DeviceObject
);
````


## -parameters




### -param DeviceObject [in]

Pointer to the device object for which the topmost attached device object is retrieved. 


## -returns



<b>IoGetAttachedDeviceReference</b> returns a pointer to the highest level device object in a stack of attached device objects after incrementing the reference count on the object.




## -remarks



If the device object at <i>DeviceObject</i> has no device objects attached to it, <i>DeviceObject</i> and the returned pointer are equal.

Device driver writers must ensure that when they have completed all operations that required them to make this call, that they call <a href="..\wdm\nf-wdm-obdereferenceobject.md">ObDereferenceObject</a> with the device object pointer returned by this routine. Failure to do so will prevent the system from freeing or deleting the device object because of an outstanding reference count.




## -see-also

<a href="..\wdm\nf-wdm-obdereferenceobject.md">ObDereferenceObject</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoGetAttachedDeviceReference routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

