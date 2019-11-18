---
UID: NF:ntifs.IoUnregisterFileSystem
title: IoUnregisterFileSystem function (ntifs.h)
description: The IoUnregisterFileSystem routine removes a file system's control device object from the global file system queue.
old-location: ifsk\iounregisterfilesystem.htm
tech.root: ifsk
ms.assetid: f6a0bff7-85b6-479a-b952-9a3a637e339e
ms.date: 04/16/2018
ms.keywords: IoUnregisterFileSystem, IoUnregisterFileSystem routine [Installable File System Drivers], ifsk.iounregisterfilesystem, ioref_8799f64d-023b-4a67-8761-0899951596ad.xml, ntifs/IoUnregisterFileSystem
ms.topic: function
f1_keywords:
 - "ntifs/IoUnregisterFileSystem"
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
req.irql: < DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoUnregisterFileSystem
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoUnregisterFileSystem function


## -description


The <b>IoUnregisterFileSystem</b> routine removes a file system's control device object from the global file system queue.


## -parameters




### -param DeviceObject [in]

Pointer to the control device object for the file system.


## -remarks



<b>IoUnregisterFileSystem</b> unregisters the file system as an active file system by removing the file system's control device object from the global file system queue, and decrements the reference count on the file system's control device object. 

<b>IoUnregisterFileSystem</b> calls the notification routines of file system filter drivers that have registered for this notification by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ioregisterfsregistrationchange">IoRegisterFsRegistrationChange</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ioregisterfilesystem">IoRegisterFileSystem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ioregisterfsregistrationchange">IoRegisterFsRegistrationChange</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iounregisterfsregistrationchange">IoUnregisterFsRegistrationChange</a>
 

 

