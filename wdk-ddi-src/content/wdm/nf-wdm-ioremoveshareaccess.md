---
UID: NF:wdm.IoRemoveShareAccess
title: IoRemoveShareAccess function
author: windows-driver-content
description: The IoRemoveShareAccess routine removes the access and share-access information for a given open instance of a file object.
old-location: kernel\ioremoveshareaccess.htm
old-project: kernel
ms.assetid: 999ee9cc-13c7-4e6b-a294-7e7d28272384
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: IoRemoveShareAccess, IoRemoveShareAccess routine [Kernel-Mode Driver Architecture], k104_0034e41b-0320-40e0-8dea-847db6b6dc58.xml, kernel.ioremoveshareaccess, wdm/IoRemoveShareAccess
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
req.ddi-compliance: IrqlIoPassive5, PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoRemoveShareAccess
product: Windows
targetos: Windows
req.typenames: 
---

# IoRemoveShareAccess function


## -description


The <b>IoRemoveShareAccess</b> routine removes the access and share-access information for a given open instance of a file object.


## -parameters




### -param FileObject [in]

Pointer to the file object, which usually is being closed by the current thread.


### -param ShareAccess [in, out]

Pointer to the share-access structure that describes how the open file object is currently being accessed. 


## -returns



None




## -remarks



This routine is a reciprocal to <a href="https://msdn.microsoft.com/library/windows/hardware/ff550412">IoUpdateShareAccess</a>.

<b>IoRemoveShareAccess</b> is not an atomic operation. Therefore, drivers calling this routine must protect the shared file object passed to <b>IoRemoveShareAccess</b> by means of some kind of lock, such as a mutex or a resource lock, in order to prevent corruption of the shared access counts.

Callers of <b>IoRemoveShareAccess</b> must be running at IRQL = PASSIVE_LEVEL and in the context of the thread that requested that the <i>FileObject</i> be closed.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548341">IoCheckShareAccess</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550324">IoSetShareAccess</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550412">IoUpdateShareAccess</a>
 

 

