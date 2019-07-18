---
UID: NF:wdm.IoCheckLinkShareAccess
title: IoCheckLinkShareAccess function (wdm.h)
description: The IoCheckLinkShareAccess routine is called by file system drivers (FSDs) or other highest-level drivers to check whether link shared access to a file object is permitted.
old-location: kernel\iochecklinkshareaccess.htm
tech.root: kernel
ms.assetid: 1C34237E-D4AF-4F12-9FF2-9382BADCC9D3
ms.date: 04/30/2018
ms.keywords: IoCheckLinkShareAccess, IoCheckLinkShareAccess function [Kernel-Mode Driver Architecture], kernel.iochecklinkshareaccess, wdm/IoCheckLinkShareAccess
ms.topic: function
f1_keywords:
 - "wdm/IoCheckLinkShareAccess"
req.header: wdm.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
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
- IoCheckLinkShareAccess
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: 19H1
---

# IoCheckLinkShareAccess function


## -description


The <b>IoCheckLinkShareAccess</b> routine is called by file system drivers (FSDs) or other highest-level drivers to check whether link shared access to a file object is permitted.


## -parameters




### -param DesiredAccess [in]

Specifies an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a> value that indicates the desired type of access to the given file object.


### -param DesiredShareAccess [in]

Specifies the desired type of shared access to the file object for the current open request. The value of this parameter is usually the same as the <i>ShareAccess</i> parameter that is passed to the file system or highest-level driver by the I/O manager when the open request was made. This value can be zero, or any combination of the following:

FILE_SHARE_READ

FILE_SHARE_WRITE

FILE_SHARE_DELETE


### -param FileObject [in, out, optional]

A pointer to the file object for which to check access for the current open request.


### -param ShareAccess [in, out, optional]

A pointer to the common share-access data structure that is associated with <i>FileObject</i>. Drivers should treat this structure as opaque.


### -param LinkShareAccess [in, out, optional]

A pointer to the common link share-access data structure (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_link_share_access">LINK_SHARE_ACCESS</a>) that is associated with <i>FileObject</i>. Drivers should treat this structure as opaque.


### -param IoShareAccessFlags [in]

A bitmask of these flags:

IO_SHARE_ACCESS_NO_WRITE_PERMISSION        (0x80000000) specifies that the user has no write permission for the file. This flag is used to prevent opening a file for exclusive read access when the user does not have appropriate permissions.

IO_SHARE_ACCESS_NON_PRIMARY_STREAM         (0x00000080) specifies that the stream is neither the primary data stream nor a directory stream.

IO_CHECK_SHARE_ACCESS_UPDATE_SHARE_ACCESS  (0x00000001) indicates whether the **SHARE_ACCESS** structure is updated.

IO_CHECK_SHARE_ACCESS_DONT_UPDATE_FILE_OBJECT (0x00000002) indicates to not update **FILE_OBJECT** structure.

IO_CHECK_SHARE_ACCESS_DONT_CHECK_READ      (0x00000004) indicates to not check read share access.

IO_CHECK_SHARE_ACCESS_DONT_CHECK_WRITE     (0x00000008) indicates to not check write share access.

IO_CHECK_SHARE_ACCESS_DONT_CHECK_DELETE    (0x00000010) indicates to not check delete share access.

IO_CHECK_SHARE_ACCESS_FORCE_CHECK          (0x00000020) indicate to force check share access even if the request is not read/write/delete access.

IO_CHECK_SHARE_ACCESS_FORCE_USING_SCB      (0x00000040) indicates to force check delete share access using ShareAccess regardless of whether LinkShareAccess is present or not.


## -returns



The <b>IoCheckLinkShareAccess</b> routine returns STATUS_SUCCESS if the requester's access to the file object is compatible with the way in which it is currently open. If the request is denied because of a sharing violation, then STATUS_SHARING_VIOLATION is returned. 




## -remarks



    The <i>ShareAccess</i> parameter must be locked against other accesses
    from other threads while this routine is executing.  Otherwise the counts
    can be synchronization.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">I/O Manager Routines</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ioremovelinkshareaccess">IoRemoveLinkShareAccess</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iosetlinkshareaccess">IoSetLinkShareAccess</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ioupdatelinkshareaccess">IoUpdateLinkShareAccess</a>
 

 

