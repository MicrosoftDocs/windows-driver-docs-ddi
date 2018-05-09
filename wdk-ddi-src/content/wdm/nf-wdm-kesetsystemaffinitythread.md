---
UID: NF:wdm.KeSetSystemAffinityThread
title: KeSetSystemAffinityThread function
author: windows-driver-content
description: The KeSetSystemAffinityThread routine sets the system affinity of the current thread.
old-location: kernel\kesetsystemaffinitythread.htm
old-project: kernel
ms.assetid: eb66ed06-356d-4550-8ccf-10854e4ca259
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: KeSetSystemAffinityThread, KeSetSystemAffinityThread routine [Kernel-Mode Driver Architecture], k105_86ff0d26-a53d-4da4-b776-35ed30b950ad.xml, kernel.kesetsystemaffinitythread, wdm/KeSetSystemAffinityThread
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows. Use KeSetSystemAffinityThread only on systems before Windows Vista. In Windows Vista and later versions of the Windows operating system, use KeSetSystemAffinityThreadEx instead.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL (see Remarks section)."
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeSetSystemAffinityThread
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeSetSystemAffinityThread function


## -description


The <b>KeSetSystemAffinityThread</b> routine sets the system affinity of the current thread.


## -parameters




### -param Affinity [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff551830">KAFFINITY</a>-typed variable that specifies the new system affinity of the current thread. 


## -returns



None




## -remarks



The implementation of <b>KeSetSystemAffinityThread</b> in Windows 7 and later versions of Windows provides compatibility for drivers that were written for earlier versions of Windows, which do not support processor groups. In this implementation, <b>KeSetSystemAffinityThread</b> assigns the thread to group 0, and uses the affinity mask to specify a set of logical processors in this group on which the thread can run.

If <b>KeSetSystemAffinityThread</b> is called at IRQL &lt;= APC_LEVEL and the call is successful, the new affinity mask takes effect immediately. When the call returns, the calling thread is already running on a processor that is specified in the new affinity mask. If <b>KeSetSystemAffinityThread</b> is called at IRQL = DISPATCH_LEVEL and the call is successful, the pending processor change is deferred until the caller lowers the IRQL below DISPATCH_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551830">KAFFINITY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553271">KeSetSystemAffinityThreadEx</a>
 

 

