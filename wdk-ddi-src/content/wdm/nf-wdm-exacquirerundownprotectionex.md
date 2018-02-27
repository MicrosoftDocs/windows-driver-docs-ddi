---
UID: NF:wdm.ExAcquireRundownProtectionEx
title: ExAcquireRundownProtectionEx function
author: windows-driver-content
description: The ExAcquireRundownProtectionEx routine tries to acquire run-down protection on a shared object so the caller can safely access the object.
old-location: kernel\exacquirerundownprotectionex.htm
old-project: kernel
ms.assetid: AB5939B9-01DD-4F51-BAEB-6C5EC909FAE1
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ExAcquireRundownProtectionEx, ExAcquireRundownProtectionEx routine [Kernel-Mode Driver Architecture], kernel.exacquirerundownprotectionex, wdm/ExAcquireRundownProtectionEx
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
-	ExAcquireRundownProtectionEx
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExAcquireRundownProtectionEx function


## -description


The <b>ExAcquireRundownProtectionEx</b> routine tries to acquire run-down protection on a shared object so the caller can safely access the object.


## -syntax


````
BOOLEAN ExAcquireRundownProtectionEx(
  _Inout_ PEX_RUNDOWN_REF RunRef,
  _In_    ULONG           Count
);
````


## -parameters




### -param RunRef [in, out]

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/jj569379">EX_RUNDOWN_REF</a> structure that was initialized by a previous call to the  <a href="..\wdm\nf-wdm-exinitializerundownprotection.md">ExInitializeRundownProtection</a> routine. The run-down protection routines use this structure to track the run-down status of the associated shared object. This structure is opaque to drivers.


### -param Count [in]

The amount by which to increment to the run-down instance count of the object. The count is incremented only if the routine returns <b>TRUE</b>. For more information, see Remarks


## -returns



<b>ExAcquireRundownProtectionEx</b> returns <b>TRUE</b> if the routine successfully acquires run-down protection for the caller. Otherwise, it returns <b>FALSE</b>. A return value of <b>FALSE</b> indicates that the run down of the object has started and that the object must be treated as invalid.




## -remarks



To safely access a shared object, a driver calls <b>ExAcquireRundownProtectionEx</b> to acquire run-down protection on the object.

The <i>RunRef</i> parameter points to an <a href="https://msdn.microsoft.com/library/windows/hardware/jj569379">EX_RUNDOWN_REF</a> structure that tracks the run-down status of the associated object. This status information includes a count of instances of run-down protection that are currently in effect on the object. The <b>ExAcquireRundownProtectionEx</b> and <a href="..\wdm\nf-wdm-exreleaserundownprotectionex.md">ExReleaseRundownProtectionEx</a> routines increment and decrement this count by arbitrary amounts. Two related routines,  <a href="..\wdm\nf-wdm-exacquirerundownprotection.md">ExAcquireRundownProtection</a> and <a href="..\wdm\nf-wdm-exreleaserundownprotection.md">ExReleaseRundownProtection</a>, increment and decrement this count by one.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/jj569382">Run-Down Protection</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/jj569379">EX_RUNDOWN_REF</a>



<a href="..\wdm\nf-wdm-exreleaserundownprotectionex.md">ExReleaseRundownProtectionEx</a>



<a href="..\wdm\nf-wdm-exinitializerundownprotection.md">ExInitializeRundownProtection</a>



<a href="..\wdm\nf-wdm-exreleaserundownprotection.md">ExReleaseRundownProtection</a>



<a href="..\wdm\nf-wdm-exacquirerundownprotection.md">ExAcquireRundownProtection</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExAcquireRundownProtectionEx routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

