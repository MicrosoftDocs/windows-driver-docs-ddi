---
UID: NF:wdm.IoSetShareAccess
title: IoSetShareAccess function (wdm.h)
description: The IoSetShareAccess routine sets the access rights for sharing the given file object.
old-location: kernel\iosetshareaccess.htm
tech.root: kernel
ms.assetid: a686ea04-8a6b-4c4b-be06-73a75c4fc87d
ms.date: 04/30/2018
keywords: ["IoSetShareAccess function"]
ms.keywords: IoSetShareAccess, IoSetShareAccess routine [Kernel-Mode Driver Architecture], k104_c7e9d7db-409a-4385-963b-61b5c96c1ffa.xml, kernel.iosetshareaccess, wdm/IoSetShareAccess
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlIoPassive5, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoSetShareAccess
 - wdm/IoSetShareAccess
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoSetShareAccess
---

# IoSetShareAccess function


## -description

The <b>IoSetShareAccess</b> routine sets the access rights for sharing the given file object.

## -parameters

### -param DesiredAccess 

[in]
Specifies an <a href="/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a> value that represents the type of access requested for the <i>FileObject</i>. See <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocreatefile">IoCreateFile</a> for a complete list of system-defined <i>DesiredAccess </i>flags.

### -param DesiredShareAccess 

[in]
Specifies the type of share access to be set for the file object. This value can be zero, or any combination of the following:

FILE_SHARE_READ

FILE_SHARE_WRITE

FILE_SHARE_DELETE

### -param FileObject 

[in, out]
Pointer to the file object whose share access is being set or reset.

### -param ShareAccess 

[out]
Pointer to the SHARE_ACCESS structure associated with <i>FileObject</i>. Drivers should treat this structure as opaque.

## -remarks

Only highest-level kernel-mode drivers should call this routine. The call must occur in the context of the first thread that attempts to open the <i>FileObject</i>.

This routine sets the access and share access information when the <i>FileObject</i> is first opened. It returns a pointer to the common share-access data structure associated with <i>FileObject</i>. Callers should save this pointer for later use when updating the access or closing the file.

Generally, file system drivers (FSDs) are most likely to call this routine. However, other highest-level drivers can call <b>IoSetShareAccess</b> to control the kind of access allowed to a driver-created device object associated with the given <i>FileObject</i>.

<b>IoSetShareAccess</b> is not an atomic operation. Therefore, drivers calling this routine must protect the shared file object passed to <b>IoSetShareAccess </b>by means of some kind of lock, such as a mutex or a resource lock, in order to prevent corruption of the shared access counts.

## -see-also

<a href="/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocheckshareaccess">IoCheckShareAccess</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocreatefile">IoCreateFile</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iocreatefileex">IoCreateFileEx</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iogetfileobjectgenericmapping">IoGetFileObjectGenericMapping</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetrelateddeviceobject">IoGetRelatedDeviceObject</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ioremoveshareaccess">IoRemoveShareAccess</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ioupdateshareaccess">IoUpdateShareAccess</a>