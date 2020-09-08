---
UID: NF:wdm.ExWaitForRundownProtectionRelease
title: ExWaitForRundownProtectionRelease function (wdm.h)
description: The ExWaitForRundownProtectionRelease routine waits until all drivers that have already been granted run-down protection complete their accesses of the shared object.
old-location: kernel\exwaitforrundownprotectionrelease.htm
tech.root: kernel
ms.assetid: 96786C19-29C4-4030-9429-0B3CB7F3DF11
ms.date: 04/30/2018
keywords: ["ExWaitForRundownProtectionRelease function"]
ms.keywords: ExWaitForRundownProtectionRelease, ExWaitForRundownProtectionRelease routine [Kernel-Mode Driver Architecture], kernel.exwaitforrundownprotectionrelease, wdm/ExWaitForRundownProtectionRelease
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: HwStorPortProhibitedDDIs, SpNoWait
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
 - ExWaitForRundownProtectionRelease
 - wdm/ExWaitForRundownProtectionRelease
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ExWaitForRundownProtectionRelease
---

# ExWaitForRundownProtectionRelease function


## -description

The <b>ExWaitForRundownProtectionRelease</b> routine waits until all drivers that have already been granted run-down protection complete their accesses of the shared object.

## -parameters

### -param RunRef 

[in, out]
A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">EX_RUNDOWN_REF</a> structure that was initialized by a previous call to the  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializerundownprotection">ExInitializeRundownProtection</a> routine. The run-down protection routines use this structure to track the run-down status of the associated shared object. This structure is opaque to drivers.

## -remarks

This routine is called by the driver that owns an object that resides in shared memory and that is accessed by other drivers. Before deleting this object, the owning driver must call this routine to wait for any outstanding accesses of the object to complete. After <b>ExWaitForRundownProtectionRelease</b> returns, the owning driver can safely delete the object.

After <b>ExWaitForRundownProtectionRelease</b> is called, the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exacquirerundownprotection">ExAcquireRundownProtection</a> routine grants no further requests for run-down protection from drivers that are trying to access the shared object. The routine waits to return until all drivers that were previously granted run-down protection finish accessing the object. As each driver finishes, it calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exreleaserundownprotection">ExReleaseRundownProtection</a> routine to release the previously acquired run-down protection. When all outstanding accesses are completed, <b>ExWaitForRundownProtectionRelease</b> returns and the object can be safely deleted.

If <b>ExWaitForRundownProtectionRelease</b> is called when all drivers that were previously granted run-down protection have already finished accessing the shared object, the routine changes the object status to <i>run down</i>, and returns immediately, without waiting.

If <b>ExWaitForRundownProtectionRelease</b> is called to run down a shared object, but the <i>RunRef</i> parameter indicates that this object is already run down, the call has no effect but is not treated as an error.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/run-down-protection">Run-Down Protection</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">EX_RUNDOWN_REF</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exacquirerundownprotection">ExAcquireRundownProtection</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializerundownprotection">ExInitializeRundownProtection</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exreleaserundownprotection">ExReleaseRundownProtection</a>

