---
UID: NF:wdm.IoCheckShareAccess
title: IoCheckShareAccess function (wdm.h)
description: The IoCheckShareAccess routine is called by file system drivers (FSDs) or other highest-level drivers to check whether shared access to a file object is permitted.
old-location: kernel\iocheckshareaccess.htm
tech.root: kernel
ms.assetid: a249c76b-7389-467f-bfb0-befe06df2fa4
ms.date: 04/30/2018
ms.keywords: IoCheckShareAccess, IoCheckShareAccess routine [Kernel-Mode Driver Architecture], k104_0411033a-da5d-4803-a970-f6e7289a6200.xml, kernel.iocheckshareaccess, wdm/IoCheckShareAccess
ms.topic: function
f1_keywords:
 - "wdm/IoCheckShareAccess"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlIoPassive2, PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoCheckShareAccess
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoCheckShareAccess function


## -description


The <b>IoCheckShareAccess</b> routine is called by file system drivers (FSDs) or other highest-level drivers to check whether shared access to a file object is permitted.


## -parameters




### -param DesiredAccess [in]

Specifies an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a> value that indicates the desired type of access to the given <i>FileObject</i> for the current open request. Drivers compute the value of this parameter by taking the requested access in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-create">IRP_MJ_CREATE</a> request and then applying <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-seaccesscheck">SeAccessCheck</a> for each security descriptor to determine the actual access granted. If the granted access is more restrictive than the desired access, then that is an error, and the driver should complete the current IRP with a status of STATUS_ACCESS_DENIED. (Note that <b>SeAccessCheck</b> clears the MAXIMUM_ALLOWED bit in the granted access; be sure to not use that bit when comparing desired access to granted access.) The driver then passes the granted access as the value of <i>DesiredAccess</i>. 


### -param DesiredShareAccess [in]

Specifies the desired type of shared access to <i>FileObject</i> for the current open request. The value of this parameter is usually the same as the <i>ShareAccess</i> passed to the file system or highest-level driver by the I/O manager when the open request was made. This value can be zero, or any combination of the following:

FILE_SHARE_READ

FILE_SHARE_WRITE

FILE_SHARE_DELETE


### -param FileObject [in, out]

Pointer to the file object for which to check access for the current open request.


### -param ShareAccess [in, out]

Pointer to the common share-access data structure associated with <i>FileObject</i>. Drivers should treat this structure as opaque.


### -param Update [in]

Specifies whether to update the share-access status for <i>FileObject</i>. A Boolean value of <b>TRUE</b> means this routine will update the share access information for the file object if the open request is permitted. 


## -returns



<b>IoCheckShareAccess</b> returns STATUS_SUCCESS if the requester's access to the file object is compatible with the way in which it is currently open. If the request is denied because of a sharing violation, then STATUS_SHARING_VIOLATION is returned.




## -remarks



<b>IoCheckShareAccess</b> checks a file object open request to determine whether the types of desired and shared accesses specified are compatible with the way in which the file object is currently being accessed by other opens.

File systems maintain state about files through structures called file control blocks (FCBs). The SHARE_ACCESS is a structure describing how the file is currently accessed by all opens. This state is contained in the FCB as part of the open state for each file object. Each file object should have only one share access structure. Other highest-level drivers might call this routine to check the access requested when a file object representing such a driver's device object is opened.

<b>IoCheckShareAccess</b> is not an atomic operation. Therefore, drivers calling this routine must protect the shared file object passed to <b>IoCheckShareAccess </b>by means of some kind of lock, such as a mutex or a resource lock, in order to prevent corruption of the shared access counts. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iocreatefile">IoCreateFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-iocreatefileex">IoCreateFileEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iogetrelateddeviceobject">IoGetRelatedDeviceObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ioremoveshareaccess">IoRemoveShareAccess</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iosetshareaccess">IoSetShareAccess</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ioupdateshareaccess">IoUpdateShareAccess</a>
 

 

