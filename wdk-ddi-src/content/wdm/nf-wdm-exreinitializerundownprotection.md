---
UID: NF:wdm.ExReInitializeRundownProtection
title: ExReInitializeRundownProtection function (wdm.h)
description: The ExReInitializeRundownProtection routine reinitializes an EX_RUNDOWN_REF structure after the associated object is run down.
old-location: kernel\exreinitializerundownprotection.htm
tech.root: kernel
ms.assetid: 41B7CE15-8702-49C8-9FD0-450DF6E4798C
ms.date: 04/30/2018
keywords: ["ExReInitializeRundownProtection function"]
ms.keywords: ExReInitializeRundownProtection, ExReInitializeRundownProtection routine [Kernel-Mode Driver Architecture], kernel.exreinitializerundownprotection, wdm/ExReInitializeRundownProtection
f1_keywords:
 - "wdm/ExReInitializeRundownProtection"
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ExReInitializeRundownProtection
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExReInitializeRundownProtection function


## -description


The <b>ExReInitializeRundownProtection</b> routine reinitializes an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">EX_RUNDOWN_REF</a> structure after the associated object is run down.


## -parameters




### -param RunRef [in, out]

A pointer to an <b>EX_RUNDOWN_REF</b> structure that was initialized by a previous call to the  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializerundownprotection">ExInitializeRundownProtection</a> routine. The run-down protection routines use this structure to track the run-down status of the associated shared object. This structure is opaque to drivers.


## -remarks



This routine is called by the driver that owns an object that resides in shared memory and that is accessed by other drivers.

<b>ExReInitializeRundownProtection</b> enables a previously used <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">EX_RUNDOWN_REF</a> structure to be associated with a new object, and initializes run-down protection on this object. After the <b>ExReInitializeRundownProtection</b> call, drivers can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exacquirerundownprotection">ExAcquireRundownProtection</a> to acquire run-down protection on the new object.

An <b>ExReInitializeRundownProtection</b> call must be preceded by a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exwaitforrundownprotectionrelease">ExWaitForRundownProtectionRelease</a> routine that runs down the old object. Between the <b>ExWaitForRundownProtectionRelease</b> and <b>ExReInitializeRundownProtection</b> calls, the driver might call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exrundowncompleted">ExRundownCompleted</a> routine to indicate that the run down of the old object has completed.

On entry, the status information in the <b>EX_RUNDOWN_REF</b> structure must indicate that the old object was run down. 

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/run-down-protection">Run-Down Protection</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">EX_RUNDOWN_REF</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exacquirerundownprotection">ExAcquireRundownProtection</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializerundownprotection">ExInitializeRundownProtection</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exrundowncompleted">ExRundownCompleted</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exwaitforrundownprotectionrelease">ExWaitForRundownProtectionRelease</a>
 

 

