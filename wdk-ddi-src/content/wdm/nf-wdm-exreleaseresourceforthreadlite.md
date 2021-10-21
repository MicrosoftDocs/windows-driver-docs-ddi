---
UID: NF:wdm.ExReleaseResourceForThreadLite
title: ExReleaseResourceForThreadLite function (wdm.h)
description: The ExReleaseResourceForThreadLite routine releases the input resource of the indicated thread.
old-location: kernel\exreleaseresourceforthreadlite.htm
tech.root: kernel
ms.date: 03/28/2018
keywords: ["ExReleaseResourceForThreadLite function"]
ms.keywords: ExReleaseResourceForThreadLite, ExReleaseResourceForThreadLite routine [Kernel-Mode Driver Architecture], k102_799a8ff7-3996-470d-97b2-e1c18bbcb486.xml, kernel.exreleaseresourceforthreadlite, wdm/ExReleaseResourceForThreadLite
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
f1_keywords:
 - ExReleaseResourceForThreadLite
 - wdm/ExReleaseResourceForThreadLite
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ExReleaseResourceForThreadLite
---

# ExReleaseResourceForThreadLite function

## -description

The **ExReleaseResourceForThreadLite** routine releases the input resource of the indicated thread.

## -parameters

### -param param [in, out]


A pointer to the resource to release.

### -param ResourceThreadId [in]


Identifies the thread that originally acquired the resource. If this is not the currently executing thread, the caller must have transferred ownership of the resource by calling the [ExSetResourceOwnerPointerEx](nf-wdm-exsetresourceownerpointerex.md) routine first on the thread that originally acquired the resource.

## -remarks

If this is not the currently executing thread, the caller must have transferred ownership of the resource by calling the [ExSetResourceOwnerPointerEx](nf-wdm-exsetresourceownerpointerex.md) routine first on the thread that originally acquired the resource. This is to ensure that thread A does not get terminated or deleted before thread B has a chance to release the resource.

Unless the caller is running in a system thread, the caller must explicitly disable the delivery of normal kernel APCs before calling this routine. This requirement prevents threads from being suspended while they manipulate or hold a resource. The caller can disable normal kernel APC delivery by calling the [KeEnterCriticalRegion](../ntddk/nf-ntddk-keentercriticalregion.md) routine. Delivery must remain disabled until the resource is released, at which point it can be reenabled by calling the [KeLeaveCriticalRegion](../ntddk/nf-ntddk-keleavecriticalregion.md) routine. For more information, see [Disabling APCs](/windows-hardware/drivers/kernel/disabling-apcs).

This requirement does not apply to calls made to **ExReleaseResourceForThreadLite** from a system thread. A caller running in a system thread does not need to explicitly disable APCs before calling this routine.

## -see-also

[ExAcquireResourceExclusiveLite](nf-wdm-exacquireresourceexclusivelite.md)

[ExAcquireResourceSharedLite](nf-wdm-exacquireresourcesharedlite.md)

[ExAcquireSharedStarveExclusive](nf-wdm-exacquiresharedstarveexclusive.md)

[ExAcquireSharedWaitForExclusive](nf-wdm-exacquiresharedwaitforexclusive.md)

[ExGetCurrentResourceThread](/previous-versions/windows/hardware/drivers/ff544614(v=vs.85))

[ExInitializeResourceLite](nf-wdm-exinitializeresourcelite.md)

[ExReinitializeResourceLite](nf-wdm-exreinitializeresourcelite.md)
