---
UID: NF:wdm.ExReleaseRundownProtection
title: ExReleaseRundownProtection function (wdm.h)
description: The ExReleaseRundownProtection routine releases run-down protection that the caller previously acquired by calling the ExAcquireRundownProtection routine.
old-location: kernel\exreleaserundownprotection.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["ExReleaseRundownProtection function"]
ms.keywords: ExReleaseRundownProtection, ExReleaseRundownProtection routine [Kernel-Mode Driver Architecture], kernel.exreleaserundownprotection, wdm/ExReleaseRundownProtection
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows XP.
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
req.irql: <= DISPATCH_LEVEL (see Remarks)
targetos: Windows
req.typenames: 
f1_keywords:
 - ExReleaseRundownProtection
 - wdm/ExReleaseRundownProtection
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ExReleaseRundownProtection
---

# ExReleaseRundownProtection function


## -description

The <b>ExReleaseRundownProtection</b> routine releases run-down protection that the caller previously acquired by calling the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exacquirerundownprotection">ExAcquireRundownProtection</a> routine.

## -parameters

### -param RunRef 

[in, out]
A pointer to an <a href="/windows-hardware/drivers/kernel/eprocess">EX_RUNDOWN_REF</a> structure that was initialized by a previous call to the  <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializerundownprotection">ExInitializeRundownProtection</a> routine. The run-down protection routines use this structure to track the run-down status of the associated shared object. This structure is opaque to drivers.

## -remarks

A driver that calls <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exacquirerundownprotection">ExAcquireRundownProtection</a> to acquire run-time protection for an object access is responsible for calling <b>ExReleaseRundownProtection</b> to release the run-time protection when the access is finished.

As long as the run-down block itself is nonpaged, this function can be called at DISPATCH_LEVEL.

For more information, see <a href="/windows-hardware/drivers/kernel/run-down-protection">Run-Down Protection</a>.

## -see-also

<a href="/windows-hardware/drivers/kernel/eprocess">EX_RUNDOWN_REF</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exacquirerundownprotection">ExAcquireRundownProtection</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializerundownprotection">ExInitializeRundownProtection</a>
