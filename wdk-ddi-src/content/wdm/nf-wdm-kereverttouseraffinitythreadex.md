---
UID: NF:wdm.KeRevertToUserAffinityThreadEx
title: KeRevertToUserAffinityThreadEx function
author: windows-driver-content
description: The KeRevertToUserAffinityThreadEx routine restores the previous affinity of the current thread.
old-location: kernel\kereverttouseraffinitythreadex.htm
old-project: kernel
ms.assetid: effda249-3ba0-40e9-914b-4dd33126518c
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: k105_88dc65fe-5379-4b7c-bfa0-6f2bb943b7cc.xml, KeRevertToUserAffinityThreadEx, KeRevertToUserAffinityThreadEx routine [Kernel-Mode Driver Architecture], wdm/KeRevertToUserAffinityThreadEx, kernel.kereverttouseraffinitythreadex
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	KeRevertToUserAffinityThreadEx
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeRevertToUserAffinityThreadEx function


## -description


The <b>KeRevertToUserAffinityThreadEx</b> routine restores the previous affinity of the current thread.


## -syntax


````
VOID KeRevertToUserAffinityThreadEx(
  _In_ KAFFINITY Affinity
);
````


## -parameters




### -param Affinity [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff551830">KAFFINITY</a>-typed variable that specifies the new system affinity of the current thread. Set this parameter to the value that was returned by a previous call to the <a href="..\wdm\nf-wdm-kesetsystemaffinitythreadex.md">KeSetSystemAffinityThreadEx</a> routine.


## -returns



None




## -remarks



<b>KeRevertToUserAffinityThreadEx</b> changes the affinity of the current thread. The affinity value is a mask that identifies a set of processors on which the thread can run. If successful, the routine schedules the thread to run on a processor in this set.

If the <i>Affinity</i> value is nonzero, <b>KeRevertToUserAffinityThreadEx</b> sets the affinity mask of the thread to the <i>Affinity</i> value. If the <i>Affinity</i> value is zero, <b>KeRevertToUserAffinityThreadEx</b> restores the original user affinity mask of the thread. This original user affinity mask was saved in the <a href="https://msdn.microsoft.com/698de86b-1790-42d5-a482-82e4431ce7af">thread object</a> by a previous call to <a href="..\wdm\nf-wdm-kesetsystemaffinitythreadex.md">KeSetSystemAffinityThreadEx</a>. A call to <b>KeRevertToUserAffinityThreadEx</b> has no effect unless it is preceded by a call to <b>KeSetSystemAffinityThreadEx</b>.

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

Windows 7 and later versions of Windows support processor groups. Drivers that are designed to handle information about processor groups should use the <a href="..\wdm\nf-wdm-kereverttousergroupaffinitythread.md">KeRevertToUserGroupAffinityThread</a> routine, which specifies a processor group, instead of <b>KeRevertToUserAffinityThreadEx</b>, which does not. However, the implementation of <b>KeRevertToUserAffinityThreadEx</b> in Windows 7 and later versions of Windows provides compatibility for drivers that were written for earlier versions of Windows, which do not support processor groups. In this implementation, a nonzero <i>Affinity</i> value is an affinity mask that specifies a set of logical processors in group 0 on which the thread can run. If <i>Affinity</i> is zero, the thread reverts to its original user-mode group number and affinity mask.

If <b>KeRevertToUserAffinityThreadEx</b> is called at IRQL &lt;= APC_LEVEL and the call is successful, the new (reverted) affinity mask takes effect immediately. When the call returns, the calling thread is already running on a processor that is specified in the new affinity mask. If <b>KeRevertToUserAffinityThreadEx</b> is called at IRQL = DISPATCH_LEVEL and the call is successful, the pending processor change is deferred until the caller lowers the IRQL below DISPATCH_LEVEL.




## -see-also

<a href="..\wdm\nf-wdm-kesetsystemaffinitythreadex.md">KeSetSystemAffinityThreadEx</a>



<a href="..\wdm\nf-wdm-kereverttousergroupaffinitythread.md">KeRevertToUserGroupAffinityThread</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551830">KAFFINITY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeRevertToUserAffinityThreadEx routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

