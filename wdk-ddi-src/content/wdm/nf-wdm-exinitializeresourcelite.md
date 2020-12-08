---
UID: NF:wdm.ExInitializeResourceLite
title: ExInitializeResourceLite function (wdm.h)
description: The ExInitializeResourceLite routine initializes a resource variable.
old-location: kernel\exinitializeresourcelite.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["ExInitializeResourceLite function"]
ms.keywords: ExInitializeResourceLite, ExInitializeResourceLite routine [Kernel-Mode Driver Architecture], k102_3264d595-09fb-4165-8147-4f805fb55557.xml, kernel.exinitializeresourcelite, wdm/ExInitializeResourceLite
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
targetos: Windows
req.typenames: 
f1_keywords:
 - ExInitializeResourceLite
 - wdm/ExInitializeResourceLite
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ExInitializeResourceLite
---

# ExInitializeResourceLite function


## -description

The <b>ExInitializeResourceLite</b> routine initializes a resource variable.

## -parameters

### -param Resource 

[out]
A pointer to the caller-supplied storage, which must be at least <b>sizeof</b>(<b>ERESOURCE</b>), for the resource variable being initialized. The storage must be 4-byte aligned on 32-bit platforms, and 8-byte aligned on 64-bit platforms.

## -returns

<b>ExInitializeResourceLite</b> returns STATUS_SUCCESS.

## -remarks

The storage for <b>ERESOURCE</b> must be allocated from nonpaged pool.

The resource variable can be used for synchronization by a set of threads. Although the caller provides the storage for the resource variable, the <b>ERESOURCE</b> structure is opaque: that is, its members are reserved for system use.

Call <b>ExDeleteResourceLite</b> before freeing the memory for the resource.

## -see-also

<a href="/previous-versions/ff544351(v=vs.85)">ExAcquireResourceExclusiveLite</a>



<a href="/previous-versions/ff544363(v=vs.85)">ExAcquireResourceSharedLite</a>



<a href="/previous-versions/ff544367(v=vs.85)">ExAcquireSharedStarveExclusive</a>



<a href="/previous-versions/ff544370(v=vs.85)">ExAcquireSharedWaitForExclusive</a>



<a href="/previous-versions/ff544558(v=vs.85)">ExConvertExclusiveToSharedLite</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exdeleteresourcelite">ExDeleteResourceLite</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exisresourceacquiredexclusivelite">ExIsResourceAcquiredExclusiveLite</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exisresourceacquiredsharedlite">ExIsResourceAcquiredSharedLite</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exreinitializeresourcelite">ExReinitializeResourceLite</a>



<a href="/previous-versions/ff545585(v=vs.85)">ExReleaseResourceForThreadLite</a>
