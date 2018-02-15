---
UID: NF:wdm.KeSetSystemAffinityThreadEx
title: KeSetSystemAffinityThreadEx function
author: windows-driver-content
description: The KeSetSystemAffinityThreadEx routine sets the system affinity of the current thread.
old-location: kernel\kesetsystemaffinitythreadex.htm
old-project: kernel
ms.assetid: db7980c1-3da6-408e-a3a4-509bc9c0ef2e
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: KeSetSystemAffinityThreadEx, KeSetSystemAffinityThreadEx routine [Kernel-Mode Driver Architecture], kernel.kesetsystemaffinitythreadex, wdm/KeSetSystemAffinityThreadEx, k105_7718d4aa-a4f5-44ff-9663-c5f91810644f.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
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
req.irql: "<= DISPATCH_LEVEL (see Remarks section)."
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	KeSetSystemAffinityThreadEx
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeSetSystemAffinityThreadEx function


## -description


The <b>KeSetSystemAffinityThreadEx</b> routine sets the system affinity of the current thread.


## -syntax


````
KAFFINITY KeSetSystemAffinityThreadEx(
  _In_ KAFFINITY Affinity
);
````


## -parameters




### -param Affinity [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff551830">KAFFINITY</a>-typed variable that specifies the new system affinity of the current thread.


## -returns



<b>KeSetSystemAffinityThreadEx</b> returns either the previous system affinity of the current thread, or zero to indicate that there was no previous system affinity.




## -remarks



<b>KeSetSystemAffinityThreadEx</b> changes the affinity mask of the current thread. The affinity mask identifies a set of processors on which the thread can run. If successful, the routine schedules the thread to run on a processor in this set.

Callers of <b>KeSetSystemAffinityThreadEx</b> should save the return value and later pass this value to the <b>KeRevertToUserAffinityThreadEx</b> routine to restore the previous affinity mask.

In a multiprocessor system, a kernel-mode driver routine that runs in the context of a user-mode thread might need to call <b>KeSetSystemAffinityThreadEx</b> to temporarily change the affinity mask of the thread. Before the routine exits, it should call <b>KeRevertToUserAffinityThreadEx</b> to restore the affinity mask of the thread to its original value.

The term <i>user affinity</i> refers to the original affinity of the user-mode thread. The affinity that is set by the kernel-mode driver is referred to as the <i>system affinity</i>. If a call to <b>KeSetSystemAffinityThreadEx</b> replaces the user affinity of a thread with a system affinity, the call returns zero. Later, the driver restores the user affinity by calling <b>KeRevertToUserAffinityThreadEx</b> and passing this return value (zero) as the <i>Affinity</i> value.

Additionally, a kernel-mode driver routine that requires a particular affinity mask might call another kernel-mode routine that requires a different affinity mask. Each routine can call <b>KeSetSystemAffinityThreadEx</b> to set a new affinity mask and then call <b>KeRevertToUserAffinityThreadEx</b> to restore the previous affinity mask before returning.

The <b>KeSetSystemAffinityThreadEx</b> routine changes the affinity mask of the current thread to the <i>Affinity</i> value only if both of the following are true:

<ul>
<li>
The <i>Affinity</i> value is valid (that is, only mask bits that correspond to logical processors are set).

</li>
<li>
At least one of the processors that is specified in the <i>Affinity</i> value is active.

</li>
</ul>
If either of these conditions is not met, the call to <b>KeSetSystemAffinityThreadEx</b> has no effect.

Windows 7 and later versions of Windows support processor groups. Drivers that are designed to handle information about processor groups should use the <a href="..\wdm\nf-wdm-kesetsystemgroupaffinitythread.md">KeSetSystemGroupAffinityThread</a> routine, which specifies a processor group, instead of <b>KeSetSystemAffinityThreadEx</b>, which does not. However, the implementation of <b>KeSetSystemAffinityThreadEx</b> in Windows 7 and later versions of Windows provides compatibility for drivers that were written for earlier versions of Windows, which do not support processor groups. In this implementation, <b>KeSetSystemAffinityThreadEx</b> assigns the thread to group 0, and uses the affinity mask to specify a set of logical processors in this group on which the thread can run. The routine returns the previous group-relative affinity mask, but not the previous group.

If <b>KeSetSystemAffinityThreadEx</b> is called at IRQL &lt;= APC_LEVEL and the call is successful, the new affinity mask takes effect immediately. When the call returns, the calling thread is already running on a processor that is specified in the new affinity mask. If <b>KeSetSystemAffinityThreadEx</b> is called at IRQL = DISPATCH_LEVEL and the call is successful, the pending processor change is deferred until the caller lowers the IRQL below DISPATCH_LEVEL.




## -see-also

<a href="..\wdm\nf-wdm-kereverttouseraffinitythreadex.md">KeRevertToUserAffinityThreadEx</a>



<a href="..\wdm\nf-wdm-kesetsystemgroupaffinitythread.md">KeSetSystemGroupAffinityThread</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551830">KAFFINITY</a>



<a href="..\wdm\nf-wdm-kesetsystemaffinitythread.md">KeSetSystemAffinityThread</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeSetSystemAffinityThreadEx routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

