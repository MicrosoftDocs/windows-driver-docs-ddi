---
UID: NF:ntifs.IoUnregisterFileSystem
title: IoUnregisterFileSystem function (ntifs.h)
description: The IoUnregisterFileSystem routine removes a file system's control device object from the global file system queue.
old-location: ifsk\iounregisterfilesystem.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["IoUnregisterFileSystem function"]
ms.keywords: IoUnregisterFileSystem, IoUnregisterFileSystem routine [Installable File System Drivers], ifsk.iounregisterfilesystem, ioref_8799f64d-023b-4a67-8761-0899951596ad.xml, ntifs/IoUnregisterFileSystem
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IoUnregisterFileSystem
 - ntifs/IoUnregisterFileSystem
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoUnregisterFileSystem
---

# IoUnregisterFileSystem function


## -description

The <b>IoUnregisterFileSystem</b> routine removes a file system's control device object from the global file system queue.

## -parameters

### -param DeviceObject [in]


Pointer to the control device object for the file system.

## -remarks

<b>IoUnregisterFileSystem</b> unregisters the file system as an active file system by removing the file system's control device object from the global file system queue, and decrements the reference count on the file system's control device object. 

<b>IoUnregisterFileSystem</b> calls the notification routines of file system filter drivers that have registered for this notification by calling <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ioregisterfsregistrationchange">IoRegisterFsRegistrationChange</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ioregisterfilesystem">IoRegisterFileSystem</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ioregisterfsregistrationchange">IoRegisterFsRegistrationChange</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iounregisterfsregistrationchange">IoUnregisterFsRegistrationChange</a>
