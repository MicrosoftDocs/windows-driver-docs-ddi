---
UID: NF:wdm.ExReleaseResourceLite
title: ExReleaseResourceLite function (wdm.h)
description: The ExReleaseResourceLite routine releases a specified executive resource owned by the current thread.
old-location: kernel\exreleaseresourcelite.htm
tech.root: kernel
ms.assetid: 5ca17587-a84e-432b-9874-4197cc107f64
ms.date: 04/30/2018
ms.keywords: ExReleaseResourceLite, ExReleaseResourceLite routine [Kernel-Mode Driver Architecture], k102_3846f443-1ef7-48f4-a5ce-2dd56f83b9be.xml, kernel.exreleaseresourcelite, wdm/ExReleaseResourceLite
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ExReleaseResourceLite
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# ExReleaseResourceLite function


## -description


The <b>ExReleaseResourceLite</b> routine releases a specified executive resource owned by the current thread.


## -parameters




### -param Resource [in, out]

A pointer to an executive resource owned by the current thread.


## -returns



None




## -remarks



Normal kernel APC delivery must be disabled before calling this routine. Disable normal kernel APC delivery by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff552021">KeEnterCriticalRegion</a>. Delivery must remain disabled until the resource is released, at which point it can be reenabled by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff552964">KeLeaveCriticalRegion</a>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543219">Disabling APCs</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544351">ExAcquireResourceExclusiveLite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544363">ExAcquireResourceSharedLite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544367">ExAcquireSharedStarveExclusive</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544370">ExAcquireSharedWaitForExclusive</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544614">ExGetCurrentResourceThread</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545317">ExInitializeResourceLite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545542">ExReinitializeResourceLite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545597">ExReleaseResourceLite</a>
 

 

