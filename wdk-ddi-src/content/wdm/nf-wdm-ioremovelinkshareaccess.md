---
UID: NF:wdm.IoRemoveLinkShareAccess
title: IoRemoveLinkShareAccess function (wdm.h)
description: The IoRemoveLinkShareAccess routine removes the access and link share-access information for a given open instance of a file object.
old-location: kernel\ioremovelinkshareaccess.htm
tech.root: kernel
ms.assetid: FFCD4705-4E5D-4D4E-9E6D-D06A7D21DC17
ms.date: 04/30/2018
keywords: ["IoRemoveLinkShareAccess function"]
ms.keywords: IoRemoveLinkShareAccess, IoRemoveLinkShareAccess function [Kernel-Mode Driver Architecture], kernel.ioremovelinkshareaccess, wdm/IoRemoveLinkShareAccess
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
targetos: Windows
req.typenames: 
ms.custom: 19H1
f1_keywords:
 - IoRemoveLinkShareAccess
 - wdm/IoRemoveLinkShareAccess
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoRemoveLinkShareAccess
---

# IoRemoveLinkShareAccess function


## -description

The <b>IoRemoveLinkShareAccess</b> routine removes the access and link share-access information for a given open instance of a file object.

## -parameters

### -param FileObject 

[in]
Pointer to the file object, which usually is being closed by the current thread.

### -param ShareAccess 

[in, out]
A pointer to the common share-access data structure that is associated with <i>FileObject</i>. Drivers should treat this structure as opaque.

### -param LinkShareAccess 

[in, out, optional]
A pointer to the common link share-access data structure (<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_link_share_access">LINK_SHARE_ACCESS</a>) that is associated with <i>FileObject</i>. Drivers should treat this structure as opaque.

## -remarks

This routine is a reciprocal to <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ioupdatelinkshareaccess">IoUpdateLinkShareAccess</a>.

<b>IoRemoveLinkShareAccess</b> is not an atomic operation. Therefore, drivers calling this routine must protect the shared file object passed to <b>IoRemoveLinkShareAccess</b> by means of some kind of lock, such as a mutex or a resource lock, in order to prevent corruption of the shared access counts.

Callers of <b>IoRemoveLinkShareAccess</b> must be running at IRQL = PASSIVE_LEVEL and in the context of the thread that requested that the <i>FileObject</i> be closed.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iochecklinkshareaccess">IoCheckLinkShareAccess</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iosetlinkshareaccess">IoSetLinkShareAccess</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ioupdatelinkshareaccess">IoUpdateLinkShareAccess</a>