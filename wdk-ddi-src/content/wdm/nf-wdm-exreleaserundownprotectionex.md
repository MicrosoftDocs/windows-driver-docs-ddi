---
UID: NF:wdm.ExReleaseRundownProtectionEx
title: ExReleaseRundownProtectionEx function
author: windows-driver-content
description: The ExReleaseRundownProtectionEx routine releases run-down protection that the caller previously acquired by calling the ExAcquireRundownProtectionEx routine.
old-location: kernel\exreleaserundownprotectionex.htm
old-project: kernel
ms.assetid: 9CF77F14-93E5-4742-A01C-770BC814507C
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: ExReleaseRundownProtectionEx, ExReleaseRundownProtectionEx routine [Kernel-Mode Driver Architecture], kernel.exreleaserundownprotectionex, wdm/ExReleaseRundownProtectionEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ExReleaseRundownProtectionEx
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExReleaseRundownProtectionEx function


## -description


The <b>ExReleaseRundownProtectionEx</b> routine releases run-down protection that the caller previously acquired by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/jj569372">ExAcquireRundownProtectionEx</a> routine.


## -parameters




### -param RunRef [in, out]

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/jj569379">EX_RUNDOWN_REF</a> structure that was initialized by a previous call to the  <a href="https://msdn.microsoft.com/library/windows/hardware/jj569373">ExInitializeRundownProtection</a> routine. The run-down protection routines use this structure to track the run-down status of the associated shared object. This structure is opaque to drivers.


### -param Count [in]

The amount by which to decrement to the run-down instance count of the object. For more information, see Remarks.


## -returns



None.




## -remarks



The <i>RunRef</i> parameter points to an <a href="https://msdn.microsoft.com/library/windows/hardware/jj569379">EX_RUNDOWN_REF</a> structure that tracks the run-down status of the associated object. This status information includes a count of the instances of run-down protection that are currently in effect on the object. The <a href="https://msdn.microsoft.com/library/windows/hardware/jj569372">ExAcquireRundownProtectionEx</a> and <b>ExReleaseRundownProtectionEx</b> routines increment and decrement this count by arbitrary amounts. Two related routines,  <a href="https://msdn.microsoft.com/library/windows/hardware/jj569371">ExAcquireRundownProtection</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/jj569375">ExReleaseRundownProtection</a>, increment and decrement this count by one.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/jj569382">Run-Down Protection</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/jj569379">EX_RUNDOWN_REF</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj569371">ExAcquireRundownProtection</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj569372">ExAcquireRundownProtectionEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj569373">ExInitializeRundownProtection</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj569375">ExReleaseRundownProtection</a>
 

 

