---
UID: NF:ntddk.KeLeaveGuardedRegion
title: KeLeaveGuardedRegion function (ntddk.h)
description: The KeLeaveGuardedRegion routine exits a guarded region entered by KeEnterGuardedRegion.
old-location: kernel\keleaveguardedregion.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["KeLeaveGuardedRegion function"]
ms.keywords: KeLeaveGuardedRegion, KeLeaveGuardedRegion routine [Kernel-Mode Driver Architecture], k105_a2582957-39b0-45dd-810c-7ab03d97d6a6.xml, kernel.keleaveguardedregion, wdm/KeLeaveGuardedRegion
req.header: ntddk.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Server 2003 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: GuardedRegions, IrqlKeApcLte2, WithinCriticalRegion, HwStorPortProhibitedDDIs
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
 - KeLeaveGuardedRegion
 - ntddk/KeLeaveGuardedRegion
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - KeLeaveGuardedRegion
---

# KeLeaveGuardedRegion function (ntddk.h)


## -description

The <b>KeLeaveGuardedRegion</b> routine exits a guarded region entered by <b>KeEnterGuardedRegion</b>.

## -remarks

Guarded regions can be nested, so APCs are only reenabled once the thread exists the outermost guarded region.

For more information about guarded regions, see <a href="/windows-hardware/drivers/kernel/critical-regions-and-guarded-regions">Critical Regions and Guarded Regions</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-keenterguardedregion">KeEnterGuardedRegion</a>
