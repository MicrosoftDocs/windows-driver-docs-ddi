---
UID: NF:wdm.IoSetLinkShareAccess
title: IoSetLinkShareAccess function
author: windows-driver-content
description: The IoSetLinkShareAccess routine sets the access rights for link sharing the specified file object.
old-location: kernel\iosetlinkshareaccess.htm
tech.root: kernel
ms.assetid: 206D74F6-09D5-4C04-8A0A-A7765E64BB27
ms.date: 04/30/2018
ms.keywords: IoSetLinkShareAccess, IoSetLinkShareAccess function [Kernel-Mode Driver Architecture], kernel.iosetlinkshareaccess, wdm/IoSetLinkShareAccess
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ntoskrnl.lib
-	ntoskrnl.dll
api_name:
-	IoSetLinkShareAccess
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoSetLinkShareAccess function


## -description


The <b>IoSetLinkShareAccess</b> routine sets the access rights for link sharing the specified file object.


## -parameters




### -param DesiredAccess [in]

Specifies an <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> value that indicates the desired type of access to the given file object.


### -param DesiredShareAccess [in]

Specifies the desired type of shared access to the file object for the current open request. The value of this parameter is usually the same as the <i>ShareAccess</i> parameter that is passed to the file system or highest-level driver by the I/O manager when the open request was made. This value can be zero, or any combination of the following:

FILE_SHARE_READ

FILE_SHARE_WRITE

FILE_SHARE_DELETE


### -param FileObject [in, out]

A pointer to the file object for which to check access for the current open request.


### -param ShareAccess [in, out]

A pointer to the common share-access data structure that is associated with <i>FileObject</i>. Drivers should treat this structure as opaque.


### -param LinkShareAccess [in, out, optional]

A pointer to the common link share-access data structure (<a href="https://msdn.microsoft.com/CD9E3356-45C3-4F56-9EB3-45FB4B3F054B">LINK_SHARE_ACCESS</a>) that is associated with <i>FileObject</i>. Drivers should treat this structure as opaque.


### -param IoShareAccessFlags [in]

A bitmask of these flags:

IO_SHARE_ACCESS_NO_WRITE_PERMISSION        (0x80000000) specifies that the user has no write permission for the file. This flag is used to prevent opening a file for exclusive read access 
when the user does not have appropriate permissions. 

IO_CHECK_SHARE_ACCESS_UPDATE_SHARE_ACCESS  (0x00000001) indicates whether the SHARE_ACCESS structure
is updated.


## -returns



This function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/1C34237E-D4AF-4F12-9FF2-9382BADCC9D3">IoCheckLinkShareAccess</a>



<a href="https://msdn.microsoft.com/FFCD4705-4E5D-4D4E-9E6D-D06A7D21DC17">IoRemoveLinkShareAccess</a>



<a href="https://msdn.microsoft.com/C92E53C8-3411-4E6E-B48E-B16F6B815488">IoUpdateLinkShareAccess</a>
 

 

