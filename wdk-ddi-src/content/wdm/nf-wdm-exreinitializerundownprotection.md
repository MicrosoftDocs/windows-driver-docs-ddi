---
UID: NF:wdm.ExReInitializeRundownProtection
title: ExReInitializeRundownProtection function
author: windows-driver-content
description: The ExReInitializeRundownProtection routine reinitializes an EX_RUNDOWN_REF structure after the associated object is run down.
old-location: kernel\exreinitializerundownprotection.htm
old-project: kernel
ms.assetid: 41B7CE15-8702-49C8-9FD0-450DF6E4798C
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ExReInitializeRundownProtection, kernel.exreinitializerundownprotection, wdm/ExReInitializeRundownProtection, ExReInitializeRundownProtection routine [Kernel-Mode Driver Architecture]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	ExReInitializeRundownProtection
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExReInitializeRundownProtection function


## -description


The <b>ExReInitializeRundownProtection</b> routine reinitializes an <a href="https://msdn.microsoft.com/library/windows/hardware/jj569379">EX_RUNDOWN_REF</a> structure after the associated object is run down.


## -syntax


````
VOID ExReInitializeRundownProtection(
  _Inout_ PEX_RUNDOWN_REF RunRef
);
````


## -parameters




### -param RunRef [in, out]

A pointer to an <b>EX_RUNDOWN_REF</b> structure that was initialized by a previous call to the  <a href="..\wdm\nf-wdm-exinitializerundownprotection.md">ExInitializeRundownProtection</a> routine. The run-down protection routines use this structure to track the run-down status of the associated shared object. This structure is opaque to drivers.


## -returns



None.




## -remarks



This routine is called by the driver that owns an object that resides in shared memory and that is accessed by other drivers.

<b>ExReInitializeRundownProtection</b> enables a previously used <a href="https://msdn.microsoft.com/library/windows/hardware/jj569379">EX_RUNDOWN_REF</a> structure to be associated with a new object, and initializes run-down protection on this object. After the <b>ExReInitializeRundownProtection</b> call, drivers can call <a href="..\wdm\nf-wdm-exacquirerundownprotection.md">ExAcquireRundownProtection</a> to acquire run-down protection on the new object.

An <b>ExReInitializeRundownProtection</b> call must be preceded by a call to the <a href="..\wdm\nf-wdm-exwaitforrundownprotectionrelease.md">ExWaitForRundownProtectionRelease</a> routine that runs down the old object. Between the <b>ExWaitForRundownProtectionRelease</b> and <b>ExReInitializeRundownProtection</b> calls, the driver might call the <a href="..\wdm\nf-wdm-exrundowncompleted.md">ExRundownCompleted</a> routine to indicate that the run down of the old object has completed.

On entry, the status information in the <b>EX_RUNDOWN_REF</b> structure must indicate that the old object was run down. Otherwise, <b>ExReInitializeRundownProtection</b> bug checks in checked builds.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/jj569382">Run-Down Protection</a>.




## -see-also

<a href="..\wdm\nf-wdm-exwaitforrundownprotectionrelease.md">ExWaitForRundownProtectionRelease</a>



<a href="..\wdm\nf-wdm-exrundowncompleted.md">ExRundownCompleted</a>



<a href="..\wdm\nf-wdm-exinitializerundownprotection.md">ExInitializeRundownProtection</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj569379">EX_RUNDOWN_REF</a>



<a href="..\wdm\nf-wdm-exacquirerundownprotection.md">ExAcquireRundownProtection</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExReInitializeRundownProtection routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

