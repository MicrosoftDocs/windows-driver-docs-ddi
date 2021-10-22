---
UID: NF:wdm.ExDeleteResourceLite
title: ExDeleteResourceLite function (wdm.h)
description: The ExDeleteResourceLite routine deletes a given resource from the system's resource list.
old-location: kernel\exdeleteresourcelite.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["ExDeleteResourceLite function"]
ms.keywords: ExDeleteResourceLite, ExDeleteResourceLite routine [Kernel-Mode Driver Architecture], k102_92907ac3-1391-4ede-8ffa-71a211c7634e.xml, kernel.exdeleteresourcelite, wdm/ExDeleteResourceLite
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlExApcLte3, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - ExDeleteResourceLite
 - wdm/ExDeleteResourceLite
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ExDeleteResourceLite
---

# ExDeleteResourceLite function

## -description

The **ExDeleteResourceLite** routine deletes a given resource from the system's resource list.

## -parameters

### -param Resource [in, out]


A pointer to the caller-supplied storage for the initialized resource variable to be deleted.

## -returns

**ExDeleteResourceLite** returns STATUS_SUCCESS if the resource was deleted.

## -remarks

After calling **ExDeleteResourceLite**, the caller can free the memory it allocated for its resource.

## -see-also

[ExFreePool](../ntddk/nf-ntddk-exfreepool.md)

[ExInitializeResourceLite](nf-wdm-exinitializeresourcelite.md)

[ExReinitializeResourceLite](nf-wdm-exreinitializeresourcelite.md)
