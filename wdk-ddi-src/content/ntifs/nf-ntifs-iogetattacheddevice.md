---
UID: NF:ntifs.IoGetAttachedDevice
title: IoGetAttachedDevice function
author: windows-driver-content
description: The IoGetAttachedDevice routine returns a pointer to the highest-level device object associated with the specified device.
old-location: ifsk\iogetattacheddevice.htm
old-project: ifsk
ms.assetid: 18083431-37b5-49e9-9c69-8b6cd7b5f736
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: IoGetAttachedDevice, ifsk.iogetattacheddevice, ntifs/IoGetAttachedDevice, IoGetAttachedDevice routine [Installable File System Drivers], ioref_5a77f51f-2bea-4991-bf10-965e6b72e9ab.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoGetAttachedDevice
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# IoGetAttachedDevice function


## -description


The <b>IoGetAttachedDevice</b> routine returns a pointer to the highest-level device object associated with the specified device.


## -syntax


````
PDEVICE_OBJECT IoGetAttachedDevice(
  _In_ PDEVICE_OBJECT DeviceObject
);
````


## -parameters




### -param DeviceObject [in]

A pointer to the device object for which the topmost attached device is to be returned.


## -returns


<b>IoGetAttachedDevice</b> returns the highest-level device attached to the specified device. 



## -remarks


If the device object specified by <i>DeviceObject</i> has no other device objects attached to it, <i>DeviceObject</i> and the returned pointer are equal.

<b>IoGetAttachedDevice</b> differs from <a href="..\ntifs\nf-ntifs-iogetattacheddevicereference.md">IoGetAttachedDeviceReference</a> in the following respects:
<ul>
<li>
<b>IoGetAttachedDevice</b> does not increment the reference count on the device object. (Thus no matching call to <a href="..\wdm\nf-wdm-obdereferenceobject.md">ObDereferenceObject</a> is required.)

</li>
<li>
Callers of <b>IoGetAttachedDevice</b> must ensure that no device objects are added to or removed from the stack while <b>IoGetAttachedDevice</b> is executing. Callers that cannot do this must use <a href="..\ntifs\nf-ntifs-iogetattacheddevicereference.md">IoGetAttachedDeviceReference</a> instead.

</li>
</ul>


## -see-also

<a href="..\wdm\nf-wdm-obdereferenceobject.md">ObDereferenceObject</a>

<a href="..\ntifs\nf-ntifs-iogetattacheddevicereference.md">IoGetAttachedDeviceReference</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20IoGetAttachedDevice routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

