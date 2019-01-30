---
UID: NF:wdm.ExInitializeResourceLite
title: ExInitializeResourceLite function (wdm.h)
description: The ExInitializeResourceLite routine initializes a resource variable.
old-location: kernel\exinitializeresourcelite.htm
tech.root: kernel
ms.assetid: be18a6e6-863d-4a0c-9bcd-a36ace0b54fe
ms.date: 04/30/2018
ms.keywords: ExInitializeResourceLite, ExInitializeResourceLite routine [Kernel-Mode Driver Architecture], k102_3264d595-09fb-4165-8147-4f805fb55557.xml, kernel.exinitializeresourcelite, wdm/ExInitializeResourceLite
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: HwStorPortProhibitedDDIs
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
-	ExInitializeResourceLite
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExInitializeResourceLite function


## -description


The <b>ExInitializeResourceLite</b> routine initializes a resource variable. 


## -parameters




### -param Resource [out]

A pointer to the caller-supplied storage, which must be at least <b>sizeof</b>(<b>ERESOURCE</b>), for the resource variable being initialized. The storage must be 4-byte aligned on 32-bit platforms, and 8-byte aligned on 64-bit platforms.


## -returns



<b>ExInitializeResourceLite</b> returns STATUS_SUCCESS.




## -remarks



The storage for <b>ERESOURCE</b> must be allocated from nonpaged pool.

The resource variable can be used for synchronization by a set of threads. Although the caller provides the storage for the resource variable, the <b>ERESOURCE</b> structure is opaque: that is, its members are reserved for system use.

Call <b>ExDeleteResourceLite</b> before freeing the memory for the resource.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544351">ExAcquireResourceExclusiveLite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544363">ExAcquireResourceSharedLite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544367">ExAcquireSharedStarveExclusive</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544370">ExAcquireSharedWaitForExclusive</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544558">ExConvertExclusiveToSharedLite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544578">ExDeleteResourceLite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545458">ExIsResourceAcquiredExclusiveLite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545477">ExIsResourceAcquiredSharedLite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545542">ExReinitializeResourceLite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545585">ExReleaseResourceForThreadLite</a>
 

 

