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

The **ExInitializeResourceLite** routine initializes a resource variable.

## -parameters

### -param Resource

[out]
A pointer to the caller-supplied storage, which must be at least **sizeof**(**ERESOURCE**), for the resource variable being initialized. The storage must be 4-byte aligned on 32-bit platforms, and 8-byte aligned on 64-bit platforms.

## -returns

**ExInitializeResourceLite** returns STATUS_SUCCESS.

## -remarks

The storage for **ERESOURCE** must be allocated from nonpaged pool.

The resource variable can be used for synchronization by a set of threads. Although the caller provides the storage for the resource variable, the **ERESOURCE** structure is opaque: that is, its members are reserved for system use.

Call **ExDeleteResourceLite** before freeing the memory for the resource.

## -see-also

[ExAcquireResourceExclusiveLite](nf-wdm-exacquireresourceexclusivelite.md)

[ExAcquireResourceSharedLite](nf-wdm-exacquireresourcesharedlite.md)

[ExAcquireSharedStarveExclusive](nf-wdm-exacquiresharedstarveexclusive.md)

[ExAcquireSharedWaitForExclusive](nf-wdm-exacquiresharedwaitforexclusive.md)

[ExConvertExclusiveToSharedLite](nf-wdm-exconvertexclusivetosharedlite.md)

[ExDeleteResourceLite](nf-wdm-exdeleteresourcelite.md)

[ExIsResourceAcquiredExclusiveLite](nf-wdm-exisresourceacquiredexclusivelite.md)

[ExIsResourceAcquiredSharedLite](nf-wdm-exisresourceacquiredsharedlite.md)

[ExReinitializeResourceLite](nf-wdm-exreinitializeresourcelite.md)

[ExReleaseResourceForThreadLite](nf-wdm-exreleaseresourceforthreadlite.md)
