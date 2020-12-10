---
UID: NF:wdm.ExIsResourceAcquiredExclusiveLite
title: ExIsResourceAcquiredExclusiveLite function (wdm.h)
description: The ExIsResourceAcquiredExclusiveLite routine returns whether the current thread has exclusive access to a given resource.
old-location: kernel\exisresourceacquiredexclusivelite.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["ExIsResourceAcquiredExclusiveLite function"]
ms.keywords: ExIsResourceAcquiredExclusiveLite, ExIsResourceAcquiredExclusiveLite routine [Kernel-Mode Driver Architecture], k102_ef023047-60ff-42aa-8224-37e2cfbe9f7b.xml, kernel.exisresourceacquiredexclusivelite, wdm/ExIsResourceAcquiredExclusiveLite
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
 - ExIsResourceAcquiredExclusiveLite
 - wdm/ExIsResourceAcquiredExclusiveLite
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ExIsResourceAcquiredExclusiveLite
---

# ExIsResourceAcquiredExclusiveLite function


## -description

The <b>ExIsResourceAcquiredExclusiveLite</b> routine returns whether the current thread has exclusive access to a given resource.

## -parameters

### -param Resource 

[in]
A pointer to the resource to be queried.

## -returns

<b>ExIsResourceAcquiredExclusiveLite</b> returns <b>TRUE</b> if the caller already has exclusive access to the given resource.

## -see-also

<a href="/previous-versions/ff544351(v=vs.85)">ExAcquireResourceExclusiveLite</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exisresourceacquiredsharedlite">ExIsResourceAcquiredSharedLite</a>
