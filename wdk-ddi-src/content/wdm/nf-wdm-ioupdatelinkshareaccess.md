---
UID: NF:wdm.IoUpdateLinkShareAccess
title: IoUpdateLinkShareAccess function (wdm.h)
description: The IoUpdateLinkShareAccess routine updates the share access for the given file object, usually when the file is being opened.
old-location: kernel\ioupdatelinkshareaccess.htm
tech.root: kernel
ms.assetid: C92E53C8-3411-4E6E-B48E-B16F6B815488
ms.date: 04/30/2018
ms.keywords: IoUpdateLinkShareAccess, IoUpdateLinkShareAccess function [Kernel-Mode Driver Architecture], kernel.ioupdatelinkshareaccess, wdm/IoUpdateLinkShareAccess
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoUpdateLinkShareAccess
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoUpdateLinkShareAccess function


## -description


The <b>IoUpdateLinkShareAccess</b> routine updates the share access for the given file object, usually when the file is being opened.


## -parameters




### -param FileObject [in]

Pointer to the file object, which usually is being closed by the current thread.


### -param ShareAccess [in, out]

A pointer to the common share-access data structure that is associated with <i>FileObject</i>. Drivers should treat this structure as opaque.


### -param LinkShareAccess [in, out, optional]

A pointer to the common link share-access data structure (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_link_share_access">LINK_SHARE_ACCESS</a>) that is associated with <i>FileObject</i>. Drivers should treat this structure as opaque.


## -returns



None




## -remarks



<b>IoUpdateLinkShareAccess</b> is not an atomic operation. Therefore, drivers calling this routine must protect the shared file object passed to <b>IoUpdateLinkShareAccess</b> by means of some kind of lock, such as a mutex or a resource lock, in order to prevent corruption of the shared access counts.

Before calling <b>IoUpdateLinkShareAccess</b>, the caller must successfully call <a href="https://msdn.microsoft.com/1C34237E-D4AF-4F12-9FF2-9382BADCC9D3">IoCheckLinkShareAccess</a> with <i>Update</i> set to False. Such a call to <b>IoCheckLinkShareAccess</b> determines whether the requested shared access is compatible with the way the file object is currently being accessed by other opens, but it does not update the <b>SHARE_ACCESS</b> structure. <b>IoUpdateLinkShareAccess</b> actually updates the <b>SHARE_ACCESS</b> structure associated with the file object. 




## -see-also




<a href="https://msdn.microsoft.com/1C34237E-D4AF-4F12-9FF2-9382BADCC9D3">IoCheckLinkShareAccess</a>



<a href="https://msdn.microsoft.com/FFCD4705-4E5D-4D4E-9E6D-D06A7D21DC17">IoRemoveLinkShareAccess</a>



<a href="https://msdn.microsoft.com/206D74F6-09D5-4C04-8A0A-A7765E64BB27">IoSetLinkShareAccess</a>
 

 

