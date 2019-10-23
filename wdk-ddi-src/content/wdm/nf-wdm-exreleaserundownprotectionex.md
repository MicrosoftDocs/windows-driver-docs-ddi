---
UID: NF:wdm.ExReleaseRundownProtectionEx
title: ExReleaseRundownProtectionEx function (wdm.h)
description: The ExReleaseRundownProtectionEx routine releases run-down protection that the caller previously acquired by calling the ExAcquireRundownProtectionEx routine.
old-location: kernel\exreleaserundownprotectionex.htm
tech.root: kernel
ms.assetid: 9CF77F14-93E5-4742-A01C-770BC814507C
ms.date: 04/30/2018
ms.keywords: ExReleaseRundownProtectionEx, ExReleaseRundownProtectionEx routine [Kernel-Mode Driver Architecture], kernel.exreleaserundownprotectionex, wdm/ExReleaseRundownProtectionEx
ms.topic: function
f1_keywords:
 - "wdm/ExReleaseRundownProtectionEx"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ExReleaseRundownProtectionEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExReleaseRundownProtectionEx function


## -description


The <b>ExReleaseRundownProtectionEx</b> routine releases run-down protection that the caller previously acquired by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-exacquirerundownprotectionex">ExAcquireRundownProtectionEx</a> routine.


## -parameters




### -param RunRef [in, out]

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">EX_RUNDOWN_REF</a> structure that was initialized by a previous call to the  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-exinitializerundownprotection">ExInitializeRundownProtection</a> routine. The run-down protection routines use this structure to track the run-down status of the associated shared object. This structure is opaque to drivers.


### -param Count [in]

The amount by which to decrement to the run-down instance count of the object. For more information, see Remarks.


## -returns



None.




## -remarks



The <i>RunRef</i> parameter points to an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">EX_RUNDOWN_REF</a> structure that tracks the run-down status of the associated object. This status information includes a count of the instances of run-down protection that are currently in effect on the object. The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-exacquirerundownprotectionex">ExAcquireRundownProtectionEx</a> and <b>ExReleaseRundownProtectionEx</b> routines increment and decrement this count by arbitrary amounts. Two related routines,  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-exacquirerundownprotection">ExAcquireRundownProtection</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-exreleaserundownprotection">ExReleaseRundownProtection</a>, increment and decrement this count by one.

As long as the run-down block itself is nonpaged, this function can be called at DISPATCH_LEVEL.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/run-down-protection">Run-Down Protection</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">EX_RUNDOWN_REF</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-exacquirerundownprotection">ExAcquireRundownProtection</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-exacquirerundownprotectionex">ExAcquireRundownProtectionEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-exinitializerundownprotection">ExInitializeRundownProtection</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-exreleaserundownprotection">ExReleaseRundownProtection</a>
 

 

