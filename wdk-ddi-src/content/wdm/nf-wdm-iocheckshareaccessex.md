---
UID: NF:wdm.IoCheckShareAccessEx
title: IoCheckShareAccessEx function (wdm.h)
description: The IoCheckShareAccessEx routine is called by file system drivers (FSDs) or other highest-level drivers to check whether shared access to a file object is permitted.
old-location: kernel\iocheckshareaccessex.htm
tech.root: kernel
ms.assetid: E6CDE415-FCC2-4039-B6DD-168113D9A490
ms.date: 04/30/2018
ms.keywords: IoCheckShareAccessEx, IoCheckShareAccessEx routine [Kernel-Mode Driver Architecture], kernel.iocheckshareaccessex, wdm/IoCheckShareAccessEx
ms.topic: function
req.header: wdm.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
req.lib: Ntoskrnl.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ntoskrnl.lib
- ntoskrnl.dll
api_name:
- IoCheckShareAccessEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoCheckShareAccessEx function


## -description


The <b>IoCheckShareAccessEx</b> routine is called by file system drivers (FSDs) or other highest-level drivers to check whether shared access to a file object is permitted.


## -parameters




### -param DesiredAccess [in]

Specifies an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a> value that indicates the desired type of access to the given file object.


### -param DesiredShareAccess [in]

Specifies the desired type of shared access to the file object for the current open request. The value of this parameter is usually the same as the <i>ShareAccess</i> parameter that is passed to the file system or highest-level driver by the I/O manager when the open request was made. This value can be zero, or any combination of the following:

FILE_SHARE_READ

FILE_SHARE_WRITE

FILE_SHARE_DELETE


### -param FileObject [in, out]

A pointer to the file object for which to check access for the current open request.


### -param ShareAccess [in, out]

A pointer to the common share-access data structure that is associated with <i>FileObject</i>. Drivers should treat this structure as opaque.


### -param Update [in]

Specifies whether to update the share-access status for <i>FileObject</i>. A Boolean value of <b>TRUE</b> means this routine will update the share access information for the file object if the open request is permitted. 


### -param WritePermission [in]

Specifies whether the share access has write permission. This value is TRUE if the share has write permission; otherwise, FALSE. If  the value is FALSE and the share access has write permission and the caller attempts to take exclusive read access, the write permission is downgraded to FILE_SHARE_READ. This value is NULL if  a write permission check is not done on the share access. 


## -returns



The <b>IoCheckShareAccessEx</b> routine returns STATUS_SUCCESS if the requester's access to the file object is compatible with the way in which it is currently open. If the request is denied because of a sharing violation, then STATUS_SHARING_VIOLATION is returned. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">I/O Manager Routines</a>
 

 

