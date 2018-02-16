---
UID: NF:wdm.IoSetLinkShareAccess
title: IoSetLinkShareAccess function
author: windows-driver-content
description: The IoSetLinkShareAccess routine sets the access rights for link sharing the specified file object.
old-location: kernel\iosetlinkshareaccess.htm
old-project: kernel
ms.assetid: 206D74F6-09D5-4C04-8A0A-A7765E64BB27
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: IoSetLinkShareAccess function [Kernel-Mode Driver Architecture], wdm/IoSetLinkShareAccess, kernel.iosetlinkshareaccess, IoSetLinkShareAccess
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ntoskrnl.lib
-	ntoskrnl.dll
apiname:
-	IoSetLinkShareAccess
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoSetLinkShareAccess function


## -description


The <b>IoSetLinkShareAccess</b> routine sets the access rights for link sharing the specified file object.


## -syntax


````
void IoSetLinkShareAccess(
  _In_        ACCESS_MASK        DesiredAccess,
  _In_        ULONG              DesiredShareAccess,
  _Inout_     PFILE_OBJECT       FileObject,
  _Inout_     PSHARE_ACCESS      ShareAccess,
  _Inout_opt_ PLINK_SHARE_ACCESS LinkShareAccess,
  _In_        ULONG              IoShareAccessFlags
);
````


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

A pointer to the common link share-access data structure (<a href="..\wdm\ns-wdm-_link_share_access.md">LINK_SHARE_ACCESS</a>) that is associated with <i>FileObject</i>. Drivers should treat this structure as opaque.


### -param IoShareAccessFlags [in]

A bitmask of these flags:

IO_SHARE_ACCESS_NO_WRITE_PERMISSION        (0x80000000) specifies that the user has no write permission for the file. This flag is used to prevent opening a file for exclusive read access 
when the user does not have appropriate permissions. 

IO_CHECK_SHARE_ACCESS_UPDATE_SHARE_ACCESS  (0x00000001) indicates whether the SHARE_ACCESS structure
is updated.


## -returns



This function does not return a value.




## -see-also

<a href="..\wdm\nf-wdm-iochecklinkshareaccess.md">IoCheckLinkShareAccess</a>



<a href="..\wdm\nf-wdm-ioremovelinkshareaccess.md">IoRemoveLinkShareAccess</a>



<a href="..\wdm\nf-wdm-ioupdatelinkshareaccess.md">IoUpdateLinkShareAccess</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoSetLinkShareAccess function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

