---
UID: NF:wdm.KeRevertToUserGroupAffinityThread
title: KeRevertToUserGroupAffinityThread function (wdm.h)
description: The KeRevertToUserGroupAffinityThread routine restores the group affinity of the calling thread to its original value at the time that the thread was created.
old-location: kernel\kereverttousergroupaffinitythread.htm
tech.root: kernel
ms.assetid: 13a1a106-0c5c-4c0e-964d-27e549e1c699
ms.date: 04/30/2018
keywords: ["KeRevertToUserGroupAffinityThread function"]
ms.keywords: KeRevertToUserGroupAffinityThread, KeRevertToUserGroupAffinityThread routine [Kernel-Mode Driver Architecture], k105_be46d681-835f-40ba-8120-b8699e16ea0b.xml, kernel.kereverttousergroupaffinitythread, wdm/KeRevertToUserGroupAffinityThread
req.header: wdm.h
req.include-header: Ntddk.h, Wdm.h, Ntddk.h
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
req.irql: <= DISPATCH_LEVEL (see Remarks section).
targetos: Windows
req.typenames: 
f1_keywords:
 - KeRevertToUserGroupAffinityThread
 - wdm/KeRevertToUserGroupAffinityThread
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - KeRevertToUserGroupAffinityThread
---

# KeRevertToUserGroupAffinityThread function


## -description

The <b>KeRevertToUserGroupAffinityThread</b> routine restores the group affinity of the calling thread to its original value at the time that the thread was created.

## -parameters

### -param PreviousAffinity 

[in]
A pointer to the group affinity to restore. This parameter points to a <a href="/windows-hardware/drivers/ddi/miniport/ns-miniport-_group_affinity">GROUP_AFFINITY</a> structure that contains a group number and an affinity mask. The affinity mask specifies the set of logical processors that the user thread can run on.

## -remarks

This routine changes the group number and group-relative affinity mask of the calling thread. The group number and affinity mask identify a set of processors on which the thread can run. If successful, the routine schedules the thread to run on a processor in this set.

The <i>PreviousAffinity</i> parameter points to a <b>GROUP_AFFINITY</b> structure that specifies the new group number (<b>Group</b> member) and affinity mask (<b>Mask</b> member) for the thread. If <i>PreviousAffinity</i>-><b>Mask</b> is nonzero, <b>KeRevertToUserGroupAffinityThread</b> sets the group number and affinity mask of the calling thread to the values in the structure. If <i>PreviousAffinity</i>-><b>Mask</b> is zero, the routine restores the group number and affinity mask to their original values at the time that the thread was initialized.

A process can have affinity for more than one group at a time. However, a thread can be assigned to only one group at any time, and that group is always in the affinity of the thread's process.

A thread can change the group to which it is assigned by calling the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kesetsystemgroupaffinitythread">KeSetSystemGroupAffinityThread</a> routine. Following one or more calls to <b>KeSetSystemGroupAffinityThread</b>, the thread can restore the original group affinity that it had when the thread was created by calling <b>KeRevertToUserGroupAffinityThread</b>.

After the thread is created, a call to <b>KeRevertToUserGroupAffinityThread</b> has no effect (that is, the group number and affinity mask of the thread remain unchanged) unless the thread first calls <b>KeSetSystemGroupAffinityThread</b>. Following a call to <b>KeRevertToUserGroupAffinityThread</b>, a second call to <b>KeRevertToUserGroupAffinityThread</b> has no effect unless the thread first calls <b>KeSetSystemGroupAffinityThread</b>.

The routine changes the group number and affinity mask to the values that are specified in *<i>PreviousAffinity</i> only if the following are true:

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
If any of these conditions is not met, the call to <b>KeRevertToUserGroupAffinityThread</b> has no effect.

A related routine, <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kereverttouseraffinitythreadex">KeRevertToUserAffinityThreadEx</a>, changes the affinity mask of the calling thread, but this routine, unlike <b>KeRevertToUserGroupAffinityThread</b>, does not accept a group number as an input parameter. In Windows 7 and later versions of the Windows operating system, <b>KeRevertToUserAffinityThreadEx</b> assumes that the affinity mask refers to processors in group 0, which is compatible with the behavior of this routine in earlier versions of Windows that do not support groups. This behavior ensures that existing drivers that call <b>KeRevertToUserAffinityThreadEx</b> and that use no group-oriented features will run correctly in multiprocessor systems that have two or more groups. However, drivers that use any group-oriented features in Windows 7 and later versions of the Windows operating system should call <b>KeRevertToUserGroupAffinityThread</b> instead of <b>KeRevertToUserAffinityThreadEx</b>.

If <b>KeRevertToUserGroupAffinityThread</b> is called at IRQL <= APC_LEVEL and the call is successful, the new (reverted) group affinity takes effect immediately. When the call returns, the calling thread is already running on a processor that is specified in the new group affinity. If <b>KeRevertToUserGroupAffinityThread</b> is called at IRQL = DISPATCH_LEVEL and the call is successful, the pending processor change is deferred until the caller lowers the IRQL below DISPATCH_LEVEL.

## -see-also

<a href="/windows-hardware/drivers/ddi/miniport/ns-miniport-_group_affinity">GROUP_AFFINITY</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kereverttouseraffinitythreadex">KeRevertToUserAffinityThreadEx</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kesetsystemgroupaffinitythread">KeSetSystemGroupAffinityThread</a>