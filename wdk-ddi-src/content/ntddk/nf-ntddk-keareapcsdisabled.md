---
UID: NF:ntddk.KeAreApcsDisabled
title: KeAreApcsDisabled function
author: windows-driver-content
description: The KeAreApcsDisabled routine returns whether the calling thread is within a critical region or a guarded region, which disables normal kernel APC delivery.
old-location: kernel\keareapcsdisabled.htm
old-project: kernel
ms.assetid: 58962146-a16d-4827-9cef-73b3a438be35
ms.author: windowsdriverdev
ms.date: 4/5/2018
ms.keywords: KeAreApcsDisabled, KeAreApcsDisabled routine [Kernel-Mode Driver Architecture], k105_8bdca8e2-6541-4525-b4b6-7fdc26e451ac.xml, kernel.keareapcsdisabled, wdm/KeAreApcsDisabled
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
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
req.typenames: 
---

# KeAreApcsDisabled function


## -description


The <b>KeAreApcsDisabled</b> routine returns whether the calling thread is within a critical region or a guarded region, which disables normal kernel APC delivery.


## -parameters






## -returns



<b>KeAreApcsDisabled</b> returns <b>TRUE</b> if the thread is within a critical region or a guarded region, and <b>FALSE</b> otherwise.




## -remarks



A thread running at IRQL = PASSIVE_LEVEL can use <b>KeAreApcsDisabled</b> to determine if normal kernel APCs are disabled. A thread that is inside a critical region has both user APCs and normal kernel APCs disabled, but not special kernel APCs. A thread that is inside a guarded region has all APCs disabled, including special kernel APCs.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551935">KeAreAllApcsDisabled</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552021">KeEnterCriticalRegion</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552964">KeLeaveCriticalRegion</a>
 

 

