---
UID: NF:wdm.ExInitializeRundownProtection
title: ExInitializeRundownProtection function
author: windows-driver-content
description: The ExInitializeRundownProtection routine initializes run-down protection on a shared object.
old-location: kernel\exinitializerundownprotection.htm
old-project: kernel
ms.assetid: 59B9C222-1A03-4C04-9F29-D9EA47E5E298
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: kernel.exinitializerundownprotection, ExInitializeRundownProtection, wdm/ExInitializeRundownProtection, ExInitializeRundownProtection routine [Kernel-Mode Driver Architecture]
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
-	ExInitializeRundownProtection
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExInitializeRundownProtection function


## -description


The <b>ExInitializeRundownProtection</b> routine initializes run-down protection on a shared object.


## -syntax


````
VOID ExInitializeRundownProtection(
  _Out_ PEX_RUNDOWN_REF RunRef
);
````


## -parameters




### -param RunRef [out]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/jj569379">EX_RUNDOWN_REF</a> structure that is to be initialized. The allocation must be 4-byte aligned on 32-bit platforms, and 8-byte aligned on 64-bit platforms. For more information, see Remarks.


## -returns



None.




## -remarks



This routine is called by the driver that owns an object that resides in shared memory and is that accessed by other drivers.

<b>ExInitializeRundownProtection</b> must be called to initialize an <b>EX_RUNDOWN_REF</b> structure before it is passed as a parameter to any other run-down protection routine.

The run-down protection routines use the <b>EX_RUNDOWN_REF</b> structure to track the run-down status of a shared object that is associated with the structure. This status information includes a count of instances of run-down protection that are currently in effect on the object. <b>ExInitializeRundownProtection</b> initializes this count to zero.

After an <b>EX_RUNDOWN_REF</b> structure is initialized, other drivers that access the associated object can call the <a href="..\wdm\nf-wdm-exacquirerundownprotection.md">ExAcquireRundownProtection</a> and <a href="..\wdm\nf-wdm-exreleaserundownprotection.md">ExReleaseRundownProtection</a> routines to acquire and release run-down protection on the object.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/jj569382">Run-Down Protection</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/jj569379">EX_RUNDOWN_REF</a>



<a href="..\wdm\nf-wdm-exacquirerundownprotection.md">ExAcquireRundownProtection</a>



<a href="..\wdm\nf-wdm-exreleaserundownprotection.md">ExReleaseRundownProtection</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExInitializeRundownProtection routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

