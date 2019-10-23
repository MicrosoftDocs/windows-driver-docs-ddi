---
UID: NF:wdm.ExReinitializeResourceLite
title: ExReinitializeResourceLite function (wdm.h)
description: The ExReinitializeResourceLite routine reinitializes an existing resource variable.
old-location: kernel\exreinitializeresourcelite.htm
tech.root: kernel
ms.assetid: 5713edfd-0b73-4274-862d-23c97f991a68
ms.date: 04/30/2018
ms.keywords: ExReinitializeResourceLite, ExReinitializeResourceLite routine [Kernel-Mode Driver Architecture], k102_dc743b18-db19-4536-a862-e313e201d4d8.xml, kernel.exreinitializeresourcelite, wdm/ExReinitializeResourceLite
ms.topic: function
f1_keywords:
 - "wdm/ExReinitializeResourceLite"
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ExReinitializeResourceLite
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExReinitializeResourceLite function


## -description


The <b>ExReinitializeResourceLite</b> routine reinitializes an existing resource variable.


## -parameters




### -param Resource [in, out]

A pointer to the caller-supplied resource variable to be reinitialized.


## -returns



<b>ExReinitializeResourceLite</b> returns STATUS_SUCCESS.




## -remarks



With a single call to <b>ExReinitializeResource</b>, a driver writer can replace three calls: one to <b>ExDeleteResourceLite</b>, another to <b>ExAllocatePool</b>, and a third to <b>ExInitializeResourceLite</b>. As contention for a resource variable increases, memory is dynamically allocated and attached to the resource in order to track this contention. As an optimization, <b>ExReinitializeResourceLite</b> retains and zeros this previously allocated memory.

The <b>ERESOURCE</b> structure is opaque; that is, the members are reserved for system use.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544351">ExAcquireResourceExclusiveLite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544363">ExAcquireResourceSharedLite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544367">ExAcquireSharedStarveExclusive</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544370">ExAcquireSharedWaitForExclusive</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544558">ExConvertExclusiveToSharedLite</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exdeleteresourcelite">ExDeleteResourceLite</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializeresourcelite">ExInitializeResourceLite</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exisresourceacquiredexclusivelite">ExIsResourceAcquiredExclusiveLite</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exisresourceacquiredsharedlite">ExIsResourceAcquiredSharedLite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545585">ExReleaseResourceForThreadLite</a>
 

 

