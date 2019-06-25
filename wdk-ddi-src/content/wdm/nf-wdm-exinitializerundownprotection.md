---
UID: NF:wdm.ExInitializeRundownProtection
title: ExInitializeRundownProtection function (wdm.h)
description: The ExInitializeRundownProtection routine initializes run-down protection on a shared object.
old-location: kernel\exinitializerundownprotection.htm
tech.root: kernel
ms.assetid: 59B9C222-1A03-4C04-9F29-D9EA47E5E298
ms.date: 04/30/2018
ms.keywords: ExInitializeRundownProtection, ExInitializeRundownProtection routine [Kernel-Mode Driver Architecture], kernel.exinitializerundownprotection, wdm/ExInitializeRundownProtection
ms.topic: function
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
req.irql: "<= APC_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ExInitializeRundownProtection
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExInitializeRundownProtection function


## -description


The <b>ExInitializeRundownProtection</b> routine initializes run-down protection on a shared object.


## -parameters




### -param RunRef [out]

A pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">EX_RUNDOWN_REF</a> structure that is to be initialized. The allocation must be 4-byte aligned on 32-bit platforms, and 8-byte aligned on 64-bit platforms. For more information, see Remarks.


## -returns



None.




## -remarks



This routine is called by the driver that owns an object that resides in shared memory and is that accessed by other drivers.

<b>ExInitializeRundownProtection</b> must be called to initialize an <b>EX_RUNDOWN_REF</b> structure before it is passed as a parameter to any other run-down protection routine.

The run-down protection routines use the <b>EX_RUNDOWN_REF</b> structure to track the run-down status of a shared object that is associated with the structure. This status information includes a count of instances of run-down protection that are currently in effect on the object. <b>ExInitializeRundownProtection</b> initializes this count to zero.

After an <b>EX_RUNDOWN_REF</b> structure is initialized, other drivers that access the associated object can call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-exacquirerundownprotection">ExAcquireRundownProtection</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-exreleaserundownprotection">ExReleaseRundownProtection</a> routines to acquire and release run-down protection on the object.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/run-down-protection">Run-Down Protection</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">EX_RUNDOWN_REF</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-exacquirerundownprotection">ExAcquireRundownProtection</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-exreleaserundownprotection">ExReleaseRundownProtection</a>
 

 

