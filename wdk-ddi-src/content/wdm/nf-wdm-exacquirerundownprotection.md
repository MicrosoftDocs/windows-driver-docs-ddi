---
UID: NF:wdm.ExAcquireRundownProtection
title: ExAcquireRundownProtection function
author: windows-driver-content
description: The ExAcquireRundownProtection routine tries to acquire run-down protection on a shared object so the caller can safely access the object.
old-location: kernel\exacquirerundownprotection.htm
old-project: kernel
ms.assetid: DA4C7FBC-F5D5-48EA-90D6-F2249AF6401E
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ExAcquireRundownProtection, ExAcquireRundownProtection routine [Kernel-Mode Driver Architecture], kernel.exacquirerundownprotection, wdm/ExAcquireRundownProtection
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	ExAcquireRundownProtection
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExAcquireRundownProtection function


## -description


The <b>ExAcquireRundownProtection</b> routine tries to acquire run-down protection on a shared object so the caller can safely access the object.


## -syntax


````
BOOLEAN ExAcquireRundownProtection(
  _Inout_ PEX_RUNDOWN_REF RunRef
);
````


## -parameters




### -param RunRef [in, out]

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/jj569379">EX_RUNDOWN_REF</a> structure that was initialized by a previous call to the  <a href="..\wdm\nf-wdm-exinitializerundownprotection.md">ExInitializeRundownProtection</a> routine. The run-down protection routines use this structure to track the run-down status of the associated shared object. This structure is opaque to drivers.


## -returns



<b>ExAcquireRundownProtection</b> returns <b>TRUE</b> if the routine successfully acquires run-down protection for the caller. Otherwise, it returns <b>FALSE</b>. A return value of <b>FALSE</b> indicates that the run down of the object has started and that the object must be treated as invalid.




## -remarks



To safely access a shared object, a driver calls <b>ExAcquireRundownProtection</b> to acquire run-down protection on the object. The routine returns <b>TRUE</b> to indicate that run-down  protection is in effect. When run-down protection is in effect, the driver can safely access the object without risk that the object will be deleted before the access completes.

After completing the access, the driver calls <a href="..\wdm\nf-wdm-exreleaserundownprotection.md">ExReleaseRundownProtection</a> to release the previously acquired run-down protection.

If <b>ExAcquireRundownProtection</b> returns <b>FALSE</b>, the object is no longer accessible. For example, if the object is to be replaced with a new one, the caller must wait for the object owner to create the new object, and then negotiate access to the new object.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/jj569382">Run-Down Protection</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/jj569379">EX_RUNDOWN_REF</a>



<a href="..\wdm\nf-wdm-exreleaserundownprotection.md">ExReleaseRundownProtection</a>



<a href="..\wdm\nf-wdm-exinitializerundownprotection.md">ExInitializeRundownProtection</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExAcquireRundownProtection routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

