---
UID: NF:ntifs.IoGetLowerDeviceObject
title: IoGetLowerDeviceObject function
author: windows-driver-content
description: The IoGetLowerDeviceObject routine returns a pointer to the next-lower-level device object on the driver stack.
old-location: ifsk\iogetlowerdeviceobject.htm
old-project: ifsk
ms.assetid: 2446dfee-baa4-4f7b-a5a0-ff13bf45ce4b
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: IoGetLowerDeviceObject, IoGetLowerDeviceObject routine [Installable File System Drivers], ifsk.iogetlowerdeviceobject, ioref_0739069f-c14d-4b35-accd-8d65954bbc3d.xml, ntifs/IoGetLowerDeviceObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Update Rollup for Windows 2000 Service Pack 4 (SP4) and on Windows XP and later.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoGetLowerDeviceObject
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# IoGetLowerDeviceObject function


## -description


The <b>IoGetLowerDeviceObject</b> routine returns a pointer to the next-lower-level device object on the driver stack.


## -parameters




### -param DeviceObject [in]

A pointer to the device object in the stack for which the next-lower-level device object is to be returned. 


## -returns



<b>IoGetLowerDeviceObject</b> returns a pointer to the next-lower-level device object on the driver stack. 




## -remarks



Given a pointer to a device object in a file system or device driver stack, <b>IoGetLowerDeviceObject</b> returns a pointer to the next-lower-level device object on the stack.

<b>IoGetLowerDeviceObject</b> returns <b>NULL</b> if: 

<ul>
<li>
The next-lower-level driver is not loaded. 

</li>
<li>
The next-lower-level driver is currently being unloaded, removed, or deleted. 

</li>
<li>
The device object pointed to by <i>DeviceObject</i> is the lowest device object in the driver stack. 

</li>
</ul>
A file system filter driver typically uses <b>IoGetLowerDeviceObject</b> to determine whether it is already attached to the filter driver stack that is chained above a given file system device object. First, the filter calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff549145">IoGetAttachedDeviceReference</a> to get a pointer to the topmost device object in the stack. Then it calls <b>IoGetLowerDeviceObject</b> repeatedly to walk the driver stack, checking each device object to see whether the object belongs to the filter driver. 

<b>IoGetLowerDeviceObject</b> increments the reference count on the next-lower-level device object. Thus every successful call to <b>IoGetLowerDeviceObject</b> must be matched by a subsequent call <a href="https://msdn.microsoft.com/library/windows/hardware/ff557724">ObDereferenceObject</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548359">IoGetAttachedDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549145">IoGetAttachedDeviceReference</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557724">ObDereferenceObject</a>
 

 

