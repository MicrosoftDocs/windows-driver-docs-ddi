---
UID: NF:wdm.ExAcquireRundownProtection
title: ExAcquireRundownProtection function (wdm.h)
description: The ExAcquireRundownProtection routine tries to acquire run-down protection on a shared object so the caller can safely access the object.
old-location: kernel\exacquirerundownprotection.htm
tech.root: kernel
ms.assetid: DA4C7FBC-F5D5-48EA-90D6-F2249AF6401E
ms.date: 04/30/2018
ms.keywords: ExAcquireRundownProtection, ExAcquireRundownProtection routine [Kernel-Mode Driver Architecture], kernel.exacquirerundownprotection, wdm/ExAcquireRundownProtection
f1_keywords:
 - "wdm/ExAcquireRundownProtection"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ExAcquireRundownProtection
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExAcquireRundownProtection function


## -description


The <b>ExAcquireRundownProtection</b> routine tries to acquire run-down protection on a shared object so the caller can safely access the object.


## -parameters




### -param RunRef [in, out]

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">EX_RUNDOWN_REF</a> structure that was initialized by a previous call to the  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializerundownprotection">ExInitializeRundownProtection</a> routine. The run-down protection routines use this structure to track the run-down status of the associated shared object. This structure is opaque to drivers.


## -returns



<b>ExAcquireRundownProtection</b> returns <b>TRUE</b> if the routine successfully acquires run-down protection for the caller. Otherwise, it returns <b>FALSE</b>. A return value of <b>FALSE</b> indicates that the run down of the object has started and that the object must be treated as invalid.




## -remarks



To safely access a shared object, a driver calls <b>ExAcquireRundownProtection</b> to acquire run-down protection on the object. The routine returns <b>TRUE</b> to indicate that run-down protection is in effect. When run-down protection is in effect, the driver can safely access the object without risk that the object will be deleted before the access completes.

As long as the run-down block itself is nonpaged, this function can be called at DISPATCH_LEVEL.

After completing the access, the driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exreleaserundownprotection">ExReleaseRundownProtection</a> to release the previously acquired run-down protection.

If <b>ExAcquireRundownProtection</b> returns <b>FALSE</b>, the object is no longer accessible. For example, if the object is to be replaced with a new one, the caller must wait for the object owner to create the new object, and then negotiate access to the new object.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/run-down-protection">Run-Down Protection</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">EX_RUNDOWN_REF</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializerundownprotection">ExInitializeRundownProtection</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exreleaserundownprotection">ExReleaseRundownProtection</a>
 

 

