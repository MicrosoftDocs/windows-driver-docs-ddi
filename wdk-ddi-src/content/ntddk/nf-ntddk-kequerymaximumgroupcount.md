---
UID: NF:ntddk.KeQueryMaximumGroupCount
title: KeQueryMaximumGroupCount function
description: The KeQueryMaximumGroupCount routine returns the maximum number of groups in a multiprocessor system.
old-location: kernel\kequerymaximumgroupcount.htm
tech.root: kernel
ms.assetid: b5cf231b-1a78-485f-bf26-fe50fbe63d08
ms.date: 04/30/2018
ms.keywords: KeQueryMaximumGroupCount, KeQueryMaximumGroupCount routine [Kernel-Mode Driver Architecture], k105_c1e0cc3e-f9d0-4570-8a56-b799d2ca5d14.xml, kernel.kequerymaximumgroupcount, wdm/KeQueryMaximumGroupCount
ms.topic: function
req.header: ntddk.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeQueryMaximumGroupCount
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeQueryMaximumGroupCount function


## -description


The <b>KeQueryMaximumGroupCount</b> routine returns the maximum number of groups in a multiprocessor system.


## -parameters






## -returns



<b>KeQueryMaximumGroupCount</b> returns the maximum number of groups. 




## -remarks



The value that is returned by <b>KeQueryMaximumGroupCount</b> remains constant during runtime. This value depends on the hardware configuration of the multiprocessor system, but it can never exceed a fixed limit that is set by the Windows operating system.

In Windows 7, the maximum number of groups in a multiprocessor system is four, but this value might change in future versions of Windows. The safest way to determine the maximum number of groups in Windows 7 or a later versions of the Windows operating system is to call <b>KeQueryMaximumGroupCount</b>. Kernel-mode drivers that call <b>KeQueryMaximumGroupCount</b> will not require code changes if the formula that is used to calculate the maximum number of groups changes in a future version of Windows.

To obtain the number of active groups in a multiprocessor system, call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552981">KeQueryActiveGroupCount</a> routine.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552981">KeQueryActiveGroupCount</a>
 

 

