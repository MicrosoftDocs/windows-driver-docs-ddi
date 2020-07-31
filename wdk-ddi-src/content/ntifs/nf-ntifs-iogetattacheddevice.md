---
UID: NF:ntifs.IoGetAttachedDevice
title: IoGetAttachedDevice function (ntifs.h)
description: The IoGetAttachedDevice routine returns a pointer to the highest-level device object associated with the specified device.
old-location: ifsk\iogetattacheddevice.htm
tech.root: ifsk
ms.assetid: 18083431-37b5-49e9-9c69-8b6cd7b5f736
ms.date: 04/16/2018
keywords: ["IoGetAttachedDevice function"]
ms.keywords: IoGetAttachedDevice, IoGetAttachedDevice routine [Installable File System Drivers], ifsk.iogetattacheddevice, ioref_5a77f51f-2bea-4991-bf10-965e6b72e9ab.xml, ntifs/IoGetAttachedDevice
f1_keywords:
 - "ntifs/IoGetAttachedDevice"
 - "IoGetAttachedDevice"
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoGetAttachedDevice
targetos: Windows
req.typenames: 
---

# IoGetAttachedDevice function


## -description


The <b>IoGetAttachedDevice</b> routine returns a pointer to the highest-level device object associated with the specified device.


## -parameters




### -param DeviceObject [in]

A pointer to the device object for which the topmost attached device is to be returned.


## -returns



<b>IoGetAttachedDevice</b> returns the highest-level device attached to the specified device. 




## -remarks



If the device object specified by <i>DeviceObject</i> has no other device objects attached to it, <i>DeviceObject</i> and the returned pointer are equal.

<b>IoGetAttachedDevice</b> differs from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iogetattacheddevicereference">IoGetAttachedDeviceReference</a> in the following respects:

<ul>
<li>
<b>IoGetAttachedDevice</b> does not increment the reference count on the device object. (Thus no matching call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobject">ObDereferenceObject</a> is required.)

</li>
<li>
Callers of <b>IoGetAttachedDevice</b> must ensure that no device objects are added to or removed from the stack while <b>IoGetAttachedDevice</b> is executing. Callers that cannot do this must use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iogetattacheddevicereference">IoGetAttachedDeviceReference</a> instead.

</li>
</ul>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iogetattacheddevicereference">IoGetAttachedDeviceReference</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobject">ObDereferenceObject</a>
 

 

