---
UID: NF:wdm.IoCheckShareAccess
title: IoCheckShareAccess function
author: windows-driver-content
description: The IoCheckShareAccess routine is called by file system drivers (FSDs) or other highest-level drivers to check whether shared access to a file object is permitted.
old-location: kernel\iocheckshareaccess.htm
old-project: kernel
ms.assetid: a249c76b-7389-467f-bfb0-befe06df2fa4
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: IoCheckShareAccess, IoCheckShareAccess routine [Kernel-Mode Driver Architecture], k104_0411033a-da5d-4803-a970-f6e7289a6200.xml, kernel.iocheckshareaccess, wdm/IoCheckShareAccess
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoCheckShareAccess
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoCheckShareAccess function


## -description


The <b>IoCheckShareAccess</b> routine is called by file system drivers (FSDs) or other highest-level drivers to check whether shared access to a file object is permitted.


## -syntax


````
NTSTATUS IoCheckShareAccess(
  _In_    ACCESS_MASK   DesiredAccess,
  _In_    ULONG         DesiredShareAccess,
  _Inout_ PFILE_OBJECT  FileObject,
  _Inout_ PSHARE_ACCESS ShareAccess,
  _In_    BOOLEAN       Update
);
````


## -parameters




### -param DesiredAccess [in]

Specifies an <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> value that indicates the desired type of access to the given <i>FileObject</i> for the current open request. Drivers compute the value of this parameter by taking the requested access in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a> request and then applying <a href="..\wdm\nf-wdm-seaccesscheck.md">SeAccessCheck</a> for each security descriptor to determine the actual access granted. If the granted access is more restrictive than the desired access, then that is an error, and the driver should complete the current IRP with a status of STATUS_ACCESS_DENIED. (Note that <b>SeAccessCheck</b> clears the MAXIMUM_ALLOWED bit in the granted access; be sure to not use that bit when comparing desired access to granted access.) The driver then passes the granted access as the value of <i>DesiredAccess</i>. 


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

<a href="..\wdm\nf-wdm-iocreatefile.md">IoCreateFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>



<a href="..\wdm\nf-wdm-ioupdateshareaccess.md">IoUpdateShareAccess</a>



<a href="..\ntddk\nf-ntddk-iocreatefileex.md">IoCreateFileEx</a>



<a href="..\wdm\nf-wdm-iosetshareaccess.md">IoSetShareAccess</a>



<a href="..\wdm\nf-wdm-ioremoveshareaccess.md">IoRemoveShareAccess</a>



<a href="..\wdm\nf-wdm-iogetrelateddeviceobject.md">IoGetRelatedDeviceObject</a>



 

 


