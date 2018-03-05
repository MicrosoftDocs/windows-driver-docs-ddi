---
UID: NF:wdm.KeAreApcsDisabled
title: KeAreApcsDisabled function
author: windows-driver-content
description: The KeAreApcsDisabled routine returns whether the calling thread is within a critical region or a guarded region, which disables normal kernel APC delivery.
old-location: kernel\keareapcsdisabled.htm
old-project: kernel
ms.assetid: 58962146-a16d-4827-9cef-73b3a438be35
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: KeAreApcsDisabled, KeAreApcsDisabled routine [Kernel-Mode Driver Architecture], k105_8bdca8e2-6541-4525-b4b6-7fdc26e451ac.xml, kernel.keareapcsdisabled, wdm/KeAreApcsDisabled
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeAreApcsDisabled
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeAreApcsDisabled function


## -description


The <b>KeAreApcsDisabled</b> routine returns whether the calling thread is within a critical region or a guarded region, which disables normal kernel APC delivery.


## -syntax


````
BOOLEAN KeAreApcsDisabled(void);
````


## -parameters






## -returns



<b>KeAreApcsDisabled</b> returns <b>TRUE</b> if the thread is within a critical region or a guarded region, and <b>FALSE</b> otherwise.




## -remarks



A thread running at IRQL = PASSIVE_LEVEL can use <b>KeAreApcsDisabled</b> to determine if normal kernel APCs are disabled. A thread that is inside a critical region has both user APCs and normal kernel APCs disabled, but not special kernel APCs. A thread that is inside a guarded region has all APCs disabled, including special kernel APCs.




## -see-also

<a href="..\ntddk\nf-ntddk-keentercriticalregion.md">KeEnterCriticalRegion</a>



<a href="..\ntddk\nf-ntddk-keleavecriticalregion.md">KeLeaveCriticalRegion</a>



<a href="..\wdm\nf-wdm-keareallapcsdisabled.md">KeAreAllApcsDisabled</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeAreApcsDisabled routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

