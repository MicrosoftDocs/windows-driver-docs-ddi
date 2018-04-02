---
UID: NF:wdm.ExReleaseResourceForThreadLite
title: ExReleaseResourceForThreadLite function
author: windows-driver-content
description: The ExReleaseResourceForThreadLite routine releases the input resource of the indicated thread.
old-location: kernel\exreleaseresourceforthreadlite.htm
old-project: kernel
ms.assetid: 840e7f50-644c-49b9-a40b-d504e19b0db2
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: ExReleaseResourceForThreadLite, ExReleaseResourceForThreadLite routine [Kernel-Mode Driver Architecture], k102_799a8ff7-3996-470d-97b2-e1c18bbcb486.xml, kernel.exreleaseresourceforthreadlite, wdm/ExReleaseResourceForThreadLite
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
req.ddi-compliance: ExclusiveResourceAccess, WithinCriticalRegion, HwStorPortProhibitedDDIs, WithinCriticalRegion(storport)
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ExReleaseResourceForThreadLite
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExReleaseResourceForThreadLite function


## -description


The <b>ExReleaseResourceForThreadLite</b> routine releases the input resource of the indicated thread.


## -parameters




### -param param

TBD


### -param ResourceThreadId [in]

Identifies the thread that originally acquired the resource. If this is not the currently executing thread, the caller must have transferred ownership of the resource by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545606">ExSetResourceOwnerPointerEx</a> routine first on the thread that originally acquired the resource.


#### - Resource [in, out]

A pointer to the resource to release.


## -returns



None




## -remarks



If this is not the currently executing thread, the caller must have transferred ownership of the resource by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545606">ExSetResourceOwnerPointerEx</a> routine first on the thread that originally acquired the resource. This is to ensure that thread A does not get terminated or deleted before thread B has a chance to release the resource.

Unless the caller is running in a system thread, the caller must explicitly disable the delivery of normal kernel APCs before calling this routine. This requirement prevents threads from being suspended while they manipulate or hold a resource. The caller can disable normal kernel APC delivery by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552021">KeEnterCriticalRegion</a> routine. Delivery must remain disabled until the resource is released, at which point it can be reenabled by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552964">KeLeaveCriticalRegion</a> routine. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543219">Disabling APCs</a>.

This requirement does not apply to calls made to <b>ExReleaseResourceForThreadLite</b> from a system thread. A caller running in a system thread does not need to explicitly disable APCs before calling this routine.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544351">ExAcquireResourceExclusiveLite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544363">ExAcquireResourceSharedLite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544367">ExAcquireSharedStarveExclusive</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544370">ExAcquireSharedWaitForExclusive</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544614">ExGetCurrentResourceThread</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545317">ExInitializeResourceLite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545542">ExReinitializeResourceLite</a>
 

 

