---
UID: NF:wdm.IoRemoveLinkShareAccess
title: IoRemoveLinkShareAccess function
author: windows-driver-content
description: The IoRemoveLinkShareAccess routine removes the access and link share-access information for a given open instance of a file object.
old-location: kernel\ioremovelinkshareaccess.htm
old-project: kernel
ms.assetid: FFCD4705-4E5D-4D4E-9E6D-D06A7D21DC17
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: IoRemoveLinkShareAccess, wdm/IoRemoveLinkShareAccess, IoRemoveLinkShareAccess function [Kernel-Mode Driver Architecture], kernel.ioremovelinkshareaccess
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	DllExport
apilocation: 
-	NtosKrnl.exe
apiname: 
-	IoRemoveLinkShareAccess
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoRemoveLinkShareAccess function


## -description


The <b>IoRemoveLinkShareAccess</b> routine removes the access and link share-access information for a given open instance of a file object.


## -syntax


````
VOID IoRemoveLinkShareAccess(
  _In_        PFILE_OBJECT       FileObject,
  _Inout_     PSHARE_ACCESS      ShareAccess,
  _Inout_opt_ PLINK_SHARE_ACCESS LinkShareAccess
);
````


## -parameters




### -param FileObject [in]

Pointer to the file object, which usually is being closed by the current thread.


### -param ShareAccess [in, out]

Pointer to the share-access structure that describes how the open file object is currently being accessed. 


### -param LinkShareAccess [in, out, optional]

Pointer to the share-access structure that describes how the open file object is currently being accessed. 


## -returns


None



## -remarks


This routine is a reciprocal to <a href="..\wdm\nf-wdm-ioupdatelinkshareaccess.md">IoUpdateLinkShareAccess</a>.

<b>IoRemoveLinkShareAccess</b> is not an atomic operation. Therefore, drivers calling this routine must protect the shared file object passed to <b>IoRemoveLinkShareAccess</b> by means of some kind of lock, such as a mutex or a resource lock, in order to prevent corruption of the shared access counts.

Callers of <b>IoRemoveLinkShareAccess</b> must be running at IRQL = PASSIVE_LEVEL and in the context of the thread that requested that the <i>FileObject</i> be closed.



## -see-also

<a href="..\wdm\nf-wdm-iochecklinkshareaccess.md">IoCheckLinkShareAccess</a>

<a href="..\wdm\nf-wdm-ioupdatelinkshareaccess.md">IoUpdateLinkShareAccess</a>

<a href="..\wdm\nf-wdm-iosetlinkshareaccess.md">IoSetLinkShareAccess</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoRemoveLinkShareAccess function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

