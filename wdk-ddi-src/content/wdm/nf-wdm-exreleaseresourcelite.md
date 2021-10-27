---
UID: NF:wdm.ExReleaseResourceLite
title: ExReleaseResourceLite function (wdm.h)
description: The ExReleaseResourceLite routine releases a specified executive resource owned by the current thread.
old-location: kernel\exreleaseresourcelite.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["ExReleaseResourceLite function"]
ms.keywords: ExReleaseResourceLite, ExReleaseResourceLite routine [Kernel-Mode Driver Architecture], k102_3846f443-1ef7-48f4-a5ce-2dd56f83b9be.xml, kernel.exreleaseresourcelite, wdm/ExReleaseResourceLite
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
req.typenames: 
ms.custom: RS5
f1_keywords:
 - ExReleaseResourceLite
 - wdm/ExReleaseResourceLite
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ExReleaseResourceLite
---

# ExReleaseResourceLite function

## -description

The **ExReleaseResourceLite** routine releases a specified executive resource owned by the current thread.

## -parameters

### -param Resource [in, out]


A pointer to an executive resource owned by the current thread.

## -remarks

Normal kernel APC delivery must be disabled before calling this routine. Disable normal kernel APC delivery by calling [KeEnterCriticalRegion](../ntddk/nf-ntddk-keentercriticalregion.md). Delivery must remain disabled until the resource is released, at which point it can be reenabled by calling [KeLeaveCriticalRegion](../ntddk/nf-ntddk-keleavecriticalregion.md). For more information, see [Disabling APCs](/windows-hardware/drivers/kernel/disabling-apcs).

## -see-also

[ExAcquireResourceExclusiveLite](nf-wdm-exacquireresourceexclusivelite.md)

[ExAcquireResourceSharedLite](nf-wdm-exacquireresourcesharedlite.md)

[ExAcquireSharedStarveExclusive](nf-wdm-exacquiresharedstarveexclusive.md)

[ExAcquireSharedWaitForExclusive](nf-wdm-exacquiresharedwaitforexclusive.md)

[ExGetCurrentResourceThread](/previous-versions/windows/hardware/drivers/ff544614(v=vs.85))

[ExInitializeResourceLite](nf-wdm-exinitializeresourcelite.md)

[ExReinitializeResourceLite](nf-wdm-exreinitializeresourcelite.md)

[ExReleaseResourceForThreadLite](nf-wdm-exreleaseresourceforthreadlite.md)
