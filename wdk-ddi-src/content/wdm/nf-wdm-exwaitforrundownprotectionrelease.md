---
UID: NF:wdm.ExWaitForRundownProtectionRelease
title: ExWaitForRundownProtectionRelease function
author: windows-driver-content
description: The ExWaitForRundownProtectionRelease routine waits until all drivers that have already been granted run-down protection complete their accesses of the shared object.
old-location: kernel\exwaitforrundownprotectionrelease.htm
old-project: kernel
ms.assetid: 96786C19-29C4-4030-9429-0B3CB7F3DF11
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , E, ExWaitForRundownProtectionRelease, ExWaitForRundownProtectionRelease routine [Kernel-Mode Driver Architecture], F, P, R, W, a, c, d, e, i, kernel.exwaitforrundownprotectionrelease, l, n, o, r, s, t, u, w, wdm/ExWaitForRundownProtectionRelease, x"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	ExWaitForRundownProtectionRelease
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExWaitForRundownProtectionRelease function


## -description


The <b>ExWaitForRundownProtectionRelease</b> routine waits until all drivers that have already been granted run-down protection complete their accesses of the shared object.


## -syntax


````
VOID ExWaitForRundownProtectionRelease(
  _Inout_ PEX_RUNDOWN_REF RunRef
);
````


## -parameters




### -param RunRef [in, out]

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/jj569379">EX_RUNDOWN_REF</a> structure that was initialized by a previous call to the  <a href="..\wdm\nf-wdm-exinitializerundownprotection.md">ExInitializeRundownProtection</a> routine. The run-down protection routines use this structure to track the run-down status of the associated shared object. This structure is opaque to drivers.


## -returns



None.




## -remarks



This routine is called by the driver that owns an object that resides in shared memory and that is accessed by other drivers. Before deleting this object, the owning driver must call this routine to wait for any outstanding accesses of the object to complete. After <b>ExWaitForRundownProtectionRelease</b> returns, the owning driver can safely delete the object.

After <b>ExWaitForRundownProtectionRelease</b> is called, the <a href="..\wdm\nf-wdm-exacquirerundownprotection.md">ExAcquireRundownProtection</a> routine grants no further requests for run-down protection from drivers that are trying to access the shared object. The routine waits to return until all drivers that were previously granted run-down protection finish accessing the object. As each driver finishes, it calls the <a href="..\wdm\nf-wdm-exreleaserundownprotection.md">ExReleaseRundownProtection</a> routine to release the previously acquired run-down protection. When all outstanding accesses are completed, <b>ExWaitForRundownProtectionRelease</b> returns and the object can be safely deleted.

If <b>ExWaitForRundownProtectionRelease</b> is called when all drivers that were previously granted run-down protection have already finished accessing the shared object, the routine changes the object status to <i>run down</i>, and returns immediately, without waiting.

If <b>ExWaitForRundownProtectionRelease</b> is called to run down a shared object, but the <i>RunRef</i> parameter indicates that this object is already run down, the call has no effect but is not treated as an error.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/jj569382">Run-Down Protection</a>.




## -see-also

<a href="..\wdm\nf-wdm-exinitializerundownprotection.md">ExInitializeRundownProtection</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj569379">EX_RUNDOWN_REF</a>



<a href="..\wdm\nf-wdm-exacquirerundownprotection.md">ExAcquireRundownProtection</a>



<a href="..\wdm\nf-wdm-exreleaserundownprotection.md">ExReleaseRundownProtection</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExWaitForRundownProtectionRelease routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

