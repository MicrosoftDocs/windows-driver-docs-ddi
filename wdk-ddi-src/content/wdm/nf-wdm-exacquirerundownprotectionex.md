---
UID: NF:wdm.ExAcquireRundownProtectionEx
title: ExAcquireRundownProtectionEx function (wdm.h)
description: The ExAcquireRundownProtectionEx routine tries to acquire run-down protection on a shared object so the caller can safely access the object.
old-location: kernel\exacquirerundownprotectionex.htm
tech.root: kernel
ms.assetid: AB5939B9-01DD-4F51-BAEB-6C5EC909FAE1
ms.date: 04/30/2018
keywords: ["ExAcquireRundownProtectionEx function"]
ms.keywords: ExAcquireRundownProtectionEx, ExAcquireRundownProtectionEx routine [Kernel-Mode Driver Architecture], kernel.exacquirerundownprotectionex, wdm/ExAcquireRundownProtectionEx
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Server 2003.
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
 - ExAcquireRundownProtectionEx
 - wdm/ExAcquireRundownProtectionEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ExAcquireRundownProtectionEx
---

# ExAcquireRundownProtectionEx function


## -description

The <b>ExAcquireRundownProtectionEx</b> routine tries to acquire run-down protection on a shared object so the caller can safely access the object.

## -parameters

### -param RunRef 

[in, out]
A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">EX_RUNDOWN_REF</a> structure that was initialized by a previous call to the  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializerundownprotection">ExInitializeRundownProtection</a> routine. The run-down protection routines use this structure to track the run-down status of the associated shared object. This structure is opaque to drivers.

### -param Count 

[in]
The amount by which to increment to the run-down instance count of the object. The count is incremented only if the routine returns <b>TRUE</b>. For more information, see Remarks

## -returns

<b>ExAcquireRundownProtectionEx</b> returns <b>TRUE</b> if the routine successfully acquires run-down protection for the caller. Otherwise, it returns <b>FALSE</b>. A return value of <b>FALSE</b> indicates that the run down of the object has started and that the object must be treated as invalid.

## -remarks

To safely access a shared object, a driver calls <b>ExAcquireRundownProtectionEx</b> to acquire run-down protection on the object.

The <i>RunRef</i> parameter points to an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">EX_RUNDOWN_REF</a> structure that tracks the run-down status of the associated object. This status information includes a count of instances of run-down protection that are currently in effect on the object. The <b>ExAcquireRundownProtectionEx</b> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exreleaserundownprotectionex">ExReleaseRundownProtectionEx</a> routines increment and decrement this count by arbitrary amounts. Two related routines,  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exacquirerundownprotection">ExAcquireRundownProtection</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exreleaserundownprotection">ExReleaseRundownProtection</a>, increment and decrement this count by one.

As long as the run-down block itself is nonpaged, this function can be called at DISPATCH_LEVEL.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/run-down-protection">Run-Down Protection</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">EX_RUNDOWN_REF</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exacquirerundownprotection">ExAcquireRundownProtection</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializerundownprotection">ExInitializeRundownProtection</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exreleaserundownprotection">ExReleaseRundownProtection</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exreleaserundownprotectionex">ExReleaseRundownProtectionEx</a>

