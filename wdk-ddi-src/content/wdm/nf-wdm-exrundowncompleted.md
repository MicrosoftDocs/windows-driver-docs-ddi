---
UID: NF:wdm.ExRundownCompleted
title: ExRundownCompleted function (wdm.h)
description: The ExRundownCompleted routine updates the run-down status of a shared object to indicate that the run down of the object has completed.
old-location: kernel\exrundowncompleted.htm
tech.root: kernel
ms.assetid: CF1650C2-4141-4AD7-A3FC-A800B2281A8A
ms.date: 04/30/2018
ms.keywords: ExRundownCompleted, ExRundownCompleted routine [Kernel-Mode Driver Architecture], kernel.exrundowncompleted, wdm/ExRundownCompleted
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ExRundownCompleted
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExRundownCompleted function


## -description


The <b>ExRundownCompleted</b> routine updates the run-down status of a shared object to indicate that the run down of the object has completed.


## -parameters




### -param RunRef [out]

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/jj569379">EX_RUNDOWN_REF</a> structure that was initialized by a previous call to the  <a href="https://msdn.microsoft.com/library/windows/hardware/jj569373">ExInitializeRundownProtection</a> routine. The run-down protection routines use this structure to track the run-down status of the associated shared object. This structure is opaque to drivers.


## -returns



None.




## -remarks



This routine is called by the driver that owns an object that resides in shared memory and that is accessed by other drivers. The <b>ExRundownCompleted</b> call must be preceded by a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/jj569378">ExWaitForRundownProtectionRelease</a> routine that runs down the object.

After an <b>ExRundownCompleted</b> call, additional calls to <b>ExWaitForRundownProtectionRelease</b> to run down the associated object return immediately without waiting. However, calls to <a href="https://msdn.microsoft.com/library/windows/hardware/jj569371">ExAcquireRundownProtection</a> to acquire run-down protection on the associated object fail (return <b>FALSE</b>).

After an <b>ExRundownCompleted</b> call, the driver can call the <a href="https://msdn.microsoft.com/library/windows/hardware/jj569374">ExReInitializeRundownProtection</a> routine to associate the <a href="https://msdn.microsoft.com/library/windows/hardware/jj569379">EX_RUNDOWN_REF</a> structure with a new object and to initialize run-down protection on this object. After the <b>ExReInitializeRundownProtection</b> call, drivers can call <b>ExAcquireRundownProtection</b> to acquire run-down protection on the new object.

On entry, the status information in the <b>EX_RUNDOWN_REF</b> structure must indicate that the object that was associated with this structure was run down. Otherwise, <b>ExReInitializeRundownProtection</b> bug checks in checked builds.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/jj569382">Run-Down Protection</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/jj569379">EX_RUNDOWN_REF</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj569373">ExInitializeRundownProtection</a>
 

 

