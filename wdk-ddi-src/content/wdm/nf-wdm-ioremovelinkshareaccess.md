---
UID: NF:wdm.IoRemoveLinkShareAccess
title: IoRemoveLinkShareAccess function
author: windows-driver-content
description: The IoRemoveLinkShareAccess routine removes the access and link share-access information for a given open instance of a file object.
old-location: kernel\ioremovelinkshareaccess.htm
old-project: kernel
ms.assetid: FFCD4705-4E5D-4D4E-9E6D-D06A7D21DC17
ms.author: windowsdriverdev
ms.date: 4/5/2018
ms.keywords: IoRemoveLinkShareAccess, IoRemoveLinkShareAccess function [Kernel-Mode Driver Architecture], kernel.ioremovelinkshareaccess, wdm/IoRemoveLinkShareAccess
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoRemoveLinkShareAccess
product: Windows
targetos: Windows
req.typenames: 
---

# IoRemoveLinkShareAccess function


## -description


The <b>IoRemoveLinkShareAccess</b> routine removes the access and link share-access information for a given open instance of a file object.


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



This routine is a reciprocal to <a href="https://msdn.microsoft.com/C92E53C8-3411-4E6E-B48E-B16F6B815488">IoUpdateLinkShareAccess</a>.

<b>IoRemoveLinkShareAccess</b> is not an atomic operation. Therefore, drivers calling this routine must protect the shared file object passed to <b>IoRemoveLinkShareAccess</b> by means of some kind of lock, such as a mutex or a resource lock, in order to prevent corruption of the shared access counts.

Callers of <b>IoRemoveLinkShareAccess</b> must be running at IRQL = PASSIVE_LEVEL and in the context of the thread that requested that the <i>FileObject</i> be closed.




## -see-also




<a href="https://msdn.microsoft.com/1C34237E-D4AF-4F12-9FF2-9382BADCC9D3">IoCheckLinkShareAccess</a>



<a href="https://msdn.microsoft.com/206D74F6-09D5-4C04-8A0A-A7765E64BB27">IoSetLinkShareAccess</a>



<a href="https://msdn.microsoft.com/C92E53C8-3411-4E6E-B48E-B16F6B815488">IoUpdateLinkShareAccess</a>
 

 

