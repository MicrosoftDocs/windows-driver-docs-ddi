---
UID: NF:wdm.KeSetSystemGroupAffinityThread
title: KeSetSystemGroupAffinityThread function (wdm.h)
description: The KeSetSystemGroupAffinityThread routine changes the group number and affinity mask of the calling thread.
old-location: kernel\kesetsystemgroupaffinitythread.htm
tech.root: kernel
ms.assetid: 8ccc097d-f997-43c1-a068-f2f532afa0d6
ms.date: 04/30/2018
keywords: ["KeSetSystemGroupAffinityThread function"]
ms.keywords: KeSetSystemGroupAffinityThread, KeSetSystemGroupAffinityThread routine [Kernel-Mode Driver Architecture], k105_3930c7d1-9295-4f62-867e-5e68729c45f3.xml, kernel.kesetsystemgroupaffinitythread, wdm/KeSetSystemGroupAffinityThread
req.header: wdm.h
req.include-header: Wdm.h, Wdm.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 7.
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
req.irql: <= DISPATCH_LEVEL (see Remarks section).
targetos: Windows
req.typenames: 
f1_keywords:
 - KeSetSystemGroupAffinityThread
 - wdm/KeSetSystemGroupAffinityThread
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - KeSetSystemGroupAffinityThread
---

# KeSetSystemGroupAffinityThread function


## -description

The <b>KeSetSystemGroupAffinityThread</b> routine changes the group number and affinity mask of the calling thread.

## -parameters

### -param Affinity 

[in]
A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/miniport/ns-miniport-_group_affinity">GROUP_AFFINITY</a> structure that specifies the new group number and group-relative affinity mask for the calling thread.

### -param PreviousAffinity 

[out, optional]
A pointer to a caller-allocated <b>GROUP_AFFINITY</b> structure into which the routine writes information about the previous group affinity of the calling thread. The caller can later use this pointer as an input parameter to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kereverttousergroupaffinitythread">KeRevertToUserGroupAffinityThread</a> routine to restore the previous thread affinity. Frequently, <b>KeSetSystemGroupAffinityThread</b> writes values to this structure that are not valid group affinities but that have special meaning to <b>KeRevertToUserGroupAffinityThread</b>. Do not supply pointers to these special values as <i>Affinity</i> parameters in subsequent <b>KeSetSystemGroupAffinityThread</b> calls.

If necessary, the caller can change the thread affinity more than once by calling <b>KeSetSystemGroupAffinityThread</b> multiple times. During the first of these calls, the caller should specify a non-<b>NULL</b> value for <i>PreviousAffinity</i> so that the original thread affinity can be captured and later restored. However, the later calls to <b>KeSetSystemGroupAffinityThread</b> can, as an option, set <i>PreviousAffinity</i> = <b>NULL</b>. For more information, see Remarks.

## -remarks

This routine changes the group number and group-relative affinity mask of the calling thread. The <i>Affinity</i> parameter points to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/miniport/ns-miniport-_group_affinity">GROUP_AFFINITY</a> structure. The group number and affinity mask in this structure identify a set of processors on which the thread can run. If successful, the routine schedules the thread to run on a processor in this set.

If the <i>PreviousAffinity</i> parameter is non-<b>NULL</b>, the routine saves information about the previous group affinity, which were in effect at the start of the call, in the <b>GROUP_AFFINITY</b> structure that <i>PreviousAffinity</i> points to. To restore the previous thread affinity, the caller can supply the pointer to this structure as an input parameter to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kereverttousergroupaffinitythread">KeRevertToUserGroupAffinityThread</a> routine.

In a multiprocessor system, a kernel-mode driver routine that runs in the context of a user-mode thread might need to call <b>KeSetSystemGroupAffinityThread</b> to temporarily change the group affinity of the thread. Before the routine exits, it should call <b>KeRevertToUserGroupAffinityThread</b> to restore the affinity mask of the thread to its original value.

A process can have affinity for more than one group at a time. However, a thread can be assigned to only one group at any time. That group is always in the affinity of the thread's process. A thread can change the group to which it is assigned by calling <b>KeSetSystemGroupAffinityThread</b>.

<b>KeSetSystemGroupAffinityThread</b> changes the group number and affinity mask to the values that are specified in *<i>Affinity</i> only if the following are true:

<ul>
<li>
The group number is valid.

</li>
<li>
The affinity mask is valid (that is, only mask bits that correspond to logical processors in the group are set).

</li>
<li>
At least one of the processors that is specified in the affinity mask is active. 

</li>
</ul>
If any of these conditions is not met, the group number and affinity mask of the thread remain unchanged. If <i>PreviousAffinity</i> is non-<b>NULL</b>, the routine writes zero to both the group number and the affinity mask in *<i>PreviousAffinity</i>.

Additionally, <b>KeSetSystemGroupAffinityThread</b> writes zero to both the group number and the affinity mask in *<i>PreviousAffinity</i> if the previous group affinity was assigned to the thread in user mode. In response to a <b>GROUP_AFFINITY</b> structure in which the group number and affinity mask are both zero, <b>KeRevertToUserGroupAffinityThread</b> restores the current user-mode thread affinity. If the user-mode thread affinity changes between the <b>KeSetSystemGroupAffinityThread</b> and <b>KeRevertToUserGroupAffinityThread</b> calls, the most recent user-mode affinity is assigned to the thread. (An application can call a function such as <a href="https://docs.microsoft.com/windows/desktop/api/processtopologyapi/nf-processtopologyapi-setthreadgroupaffinity">SetThreadGroupAffinity</a> to change the user-mode group affinity of a thread.)

Before the new affinity mask in *<i>Affinity</i> takes effect, <b>KeSetSystemGroupAffinityThread</b> removes (sets to zero) any affinity mask bits that correspond to processors that are not currently active. In a subsequent <b>KeSetSystemGroupAffinityThread</b> call, the value that the routine writes to *<i>PreviousAffinity</i> might contain an affinity mask that has been modified in this way.

A related routine, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kesetsystemaffinitythreadex">KeSetSystemAffinityThreadEx</a>, changes the affinity mask of the calling thread, but this routine, unlike <b>KeSetSystemGroupAffinityThread</b>, does not accept a group number as an input parameter. Starting with Windows 7, <b>KeSetSystemAffinityThreadEx</b> assumes that the affinity mask refers to processors in group 0, which is compatible with the behavior of this routine in earlier versions of Windows that do not support groups. This behavior ensures that existing drivers that call <b>KeSetSystemAffinityThreadEx</b> and that use no group-oriented features will run correctly in multiprocessor systems that have two or more groups. However, drivers that use any group-oriented features in Windows 7 and later versions of the Windows operating system should call <b>KeSetSystemGroupAffinityThread</b> instead of <b>KeSetSystemAffinityThreadEx</b>.

<b>KeSetSystemGroupAffinityThread</b> and <b>KeRevertToUserGroupAffinityThread</b> support a variety of calling patterns. Two examples are shown in the following diagrams.

The following diagram represents a driver thread that calls <b>KeSetSystemGroupAffinityThread</b> three times to change the thread affinity, and then calls <b>KeRevertToUserGroupAffinityThread</b> to restore the original thread affinity.

![Diagram illustrating multiple calls to set affinity.](images/affinity1.png)

In the preceding diagram, the three boxes labeled "Set affinity" are calls to <b>KeSetSystemGroupAffinityThread</b>, and the box labeled "Revert affinity" is a call to <b>KeRevertToUserGroupAffinityThread</b>. The first <b>KeSetSystemGroupAffinityThread</b> call uses the <i>PreviousAffinity</i> output pointer to save the original thread affinity. In the next two calls to <b>KeSetSystemGroupAffinityThread</b> (marked with asterisks), the caller sets <i>PreviousAffinity</i> to <b>NULL</b>. Before the thread exits, it calls <b>KeRevertToUserGroupAffinityThread</b> to restore the thread affinity that was saved by the first <b>KeSetSystemGroupAffinityThread</b> call.

The following diagram shows a somewhat different calling pattern in which pairs of <b>KeSetSystemGroupAffinityThread</b> and <b>KeRevertToUserGroupAffinityThread</b> calls are nested. In this diagram, each call to <b>KeSetSystemGroupAffinityThread</b> in the driver thread uses the <i>PreviousAffinity</i> output parameter to save the previous thread affinity, and each of these calls is paired with a call to <b>KeRevertToUserGroupAffinityThread</b> that restores the saved thread affinity.

![Diagram illustrating nested calls to set and restore affinity.](images/affinity2.png)

In the preceding diagram, function A in the driver thread calls function B twice. Assume that on entry to function A, the thread still has the affinity assigned to it by the user-mode application. Thus, the <b>KeSetSystemGroupAffinityThread</b> call in function A saves the original, user-mode thread affinity. During the first call to function B, the <b>KeSetSystemGroupAffinityThread</b> saves the thread affinity assigned by the driver in function A, and the corresponding call to <b>KeRevertToUserGroupAffinityThread</b> restores this affinity. After B returns, the <b>KeRevertToUserGroupAffinityThread</b> in A restores the original, user-mode thread affinity. During the second call to B, the <b>KeSetSystemGroupAffinityThread</b> call saves the original, user-mode thread affinity, and the corresponding call to <b>KeRevertToUserGroupAffinityThread</b> restores this affinity. The point of this example is that function B does not need to know whether the caller (function A) changed the thread affinity to a driver-defined value before calling B.

If <b>KeSetSystemGroupAffinityThread</b> is called at IRQL <= APC_LEVEL and the call is successful, the new group affinity takes effect immediately. When the call returns, the calling thread is already running on a processor that is specified in the new group affinity. If <b>KeSetSystemGroupAffinityThread</b> is called at IRQL = DISPATCH_LEVEL and the call is successful, the pending processor change is deferred until the caller lowers the IRQL below DISPATCH_LEVEL.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/miniport/ns-miniport-_group_affinity">GROUP_AFFINITY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kereverttousergroupaffinitythread">KeRevertToUserGroupAffinityThread</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kesetsystemaffinitythreadex">KeSetSystemAffinityThreadEx</a>

