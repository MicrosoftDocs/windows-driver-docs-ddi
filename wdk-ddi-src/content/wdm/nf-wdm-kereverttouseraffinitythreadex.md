---
UID: NF:wdm.KeRevertToUserAffinityThreadEx
title: KeRevertToUserAffinityThreadEx function
author: windows-driver-content
description: The KeRevertToUserAffinityThreadEx routine restores the previous affinity of the current thread.
old-location: kernel\kereverttouseraffinitythreadex.htm
old-project: kernel
ms.assetid: effda249-3ba0-40e9-914b-4dd33126518c
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: KeRevertToUserAffinityThreadEx, KeRevertToUserAffinityThreadEx routine [Kernel-Mode Driver Architecture], k105_88dc65fe-5379-4b7c-bfa0-6f2bb943b7cc.xml, kernel.kereverttouseraffinitythreadex, wdm/KeRevertToUserAffinityThreadEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
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
-	KeRevertToUserAffinityThreadEx
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeRevertToUserAffinityThreadEx function


## -description


The <b>KeRevertToUserAffinityThreadEx</b> routine restores the previous affinity of the current thread.


## -parameters




### -param Affinity [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff551830">KAFFINITY</a>-typed variable that specifies the new system affinity of the current thread. Set this parameter to the value that was returned by a previous call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553271">KeSetSystemAffinityThreadEx</a> routine.


## -returns



None




## -remarks



<b>KeRevertToUserAffinityThreadEx</b> changes the affinity of the current thread. The affinity value is a mask that identifies a set of processors on which the thread can run. If successful, the routine schedules the thread to run on a processor in this set.

If the <i>Affinity</i> value is nonzero, <b>KeRevertToUserAffinityThreadEx</b> sets the affinity mask of the thread to the <i>Affinity</i> value. If the <i>Affinity</i> value is zero, <b>KeRevertToUserAffinityThreadEx</b> restores the original user affinity mask of the thread. This original user affinity mask was saved in the <a href="https://msdn.microsoft.com/698de86b-1790-42d5-a482-82e4431ce7af">thread object</a> by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff553271">KeSetSystemAffinityThreadEx</a>. A call to <b>KeRevertToUserAffinityThreadEx</b> has no effect unless it is preceded by a call to <b>KeSetSystemAffinityThreadEx</b>.

If the <i>Affinity</i> value is nonzero, the routine changes the affinity mask of the current thread to the <i>Affinity</i> value only if both of the following are true:

<ul>
<li>
The <i>Affinity</i> value is valid (that is, only mask bits that correspond to logical processors are set).

</li>
<li>
At least one of the processors that is specified in the <i>Affinity</i> value is active.

</li>
</ul>
If either of these conditions is not met, the call to <b>KeRevertToUserAffinityThreadEx</b> has no effect.

Windows 7 and later versions of Windows support processor groups. Drivers that are designed to handle information about processor groups should use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553195">KeRevertToUserGroupAffinityThread</a> routine, which specifies a processor group, instead of <b>KeRevertToUserAffinityThreadEx</b>, which does not. However, the implementation of <b>KeRevertToUserAffinityThreadEx</b> in Windows 7 and later versions of Windows provides compatibility for drivers that were written for earlier versions of Windows, which do not support processor groups. In this implementation, a nonzero <i>Affinity</i> value is an affinity mask that specifies a set of logical processors in group 0 on which the thread can run. If <i>Affinity</i> is zero, the thread reverts to its original user-mode group number and affinity mask.

If <b>KeRevertToUserAffinityThreadEx</b> is called at IRQL &lt;= APC_LEVEL and the call is successful, the new (reverted) affinity mask takes effect immediately. When the call returns, the calling thread is already running on a processor that is specified in the new affinity mask. If <b>KeRevertToUserAffinityThreadEx</b> is called at IRQL = DISPATCH_LEVEL and the call is successful, the pending processor change is deferred until the caller lowers the IRQL below DISPATCH_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551830">KAFFINITY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553195">KeRevertToUserGroupAffinityThread</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553271">KeSetSystemAffinityThreadEx</a>
 

 

