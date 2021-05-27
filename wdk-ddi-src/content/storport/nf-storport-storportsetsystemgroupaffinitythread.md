---
UID: NF:storport.StorPortSetSystemGroupAffinityThread
tech.root: storage
title: StorPortSetSystemGroupAffinityThread
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: StorPortSetSystemGroupAffinityThread changes the group number and affinity mask of the calling thread.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: storport.h
req.idl: 
req.include-header: 
req.irql: <= DISPATCH_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt:
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - StorPortSetSystemGroupAffinityThread
f1_keywords:
 - StorPortSetSystemGroupAffinityThread
 - storport/StorPortSetSystemGroupAffinityThread
dev_langs:
 - c++
---

## -description

**StorPortSetSystemGroupAffinityThread** changes the group number and affinity mask of the calling thread.

## -parameters

### -param HwDeviceExtension

[in] Pointer to the miniport's hardware device extension.

### -param ThreadContext

[in/optional] Pointer to the thread context received in a prior call to [**StorPortCreateSystemThread**](nf-storport-storportcreatesystemthread.md).

### -param Affinity

[in] Pointer to a caller-allocated [**STOR_GROUP_AFFINITY**](ns-storport-stor_group_affinity.md) structure that specifies the new group number and group-relative affinity mask for the calling thread.

### -param PreviousAffinity

[out/optional] Pointer to a [**STOR_GROUP_AFFINITY**](ns-storport-stor_group_affinity.md) structure in which this routine writes the group number and affinity mask for the calling thread prior to the call. This parameter is optional and can be NULL.

## -returns

**StorPortSetSystemGroupAffinityThread** returns one of the following values:

| Return code | Description |
| ----------- | ----------- |
| STOR_STATUS_SUCCESS | The specified group affinity was set successfully. |
| STOR_STATUS_INVALID_PARAMETER | One or more of the provided parameters are invalid. |
| STOR_STATUS_UNSUCCESSFUL | Returned for other internal system reasons. |

## -remarks

A miniport can call **StorPortSetSystemGroupAffinityThread** to change the group number and group-level affinity mask of the calling thread.

The group number and affinity mask in the [**STOR_GROUP_AFFINITY**](ns-storport-stor_group_affinity.md) structure pointed to by **Affinity** identify a set of processors on which the thread can run. If successful, **StorPortSetSystemGroupAffinityThread** schedules the thread to run on a processor in this set.

If the **PreviousAffinity** parameter is non-NULL, **StorPortSetSystemGroupAffinityThread** saves information about the previous group affinity, which were in effect at the start of the call, in the [**STOR_GROUP_AFFINITY**](ns-storport-stor_group_affinity.md) structure that **PreviousAffinity** points to. To restore the previous thread affinity, the caller can supply the pointer to this structure as an input parameter to the [**StorPortRevertToUserGroupAffinityThread**](nf-storport-storportreverttousergroupaffinitythread.md) routine.

If a miniport calls this function to temporarily change the group affinity of the thread, then it should call [**StorPortRevertToUserGroupAffinityThread**](nf-storport-storportreverttousergroupaffinitythread.md) to revert thread affinity to its original value before the thread exits.

A thread can be assigned to only one group affinity at any time. That group is always in the affinity of the thread's process. A thread can change the group to which it is assigned by calling this routine.

**StorPortSetSystemGroupAffinityThread** changes the group number and affinity mask to the values that are specified in **Affinity** only if the following are true:

- The group number is valid.
- The affinity mask is valid (that is, only mask bits that correspond to logical processors in the group are set).
- At least one of the processors that is specified in the affinity mask is active.

If any of these conditions is not met, the group number and affinity mask of the thread remain unchanged. If **PreviousAffinity** is non-NULL, the routine writes zero to both the group number and the affinity mask in **PreviousAffinity**.

Before the new affinity mask in **Affinity** takes effect, **StorPortSetSystemGroupAffinityThread** removes (sets to zero) any affinity mask bits that correspond to processors that are not currently active. In a subsequent **StorPortSetSystemGroupAffinityThread** call, the value that the routine writes to **PreviousAffinity** might contain an affinity mask that has been modified in this way.

If **StorPortSetSystemGroupAffinityThread** is called at IRQL <= APC_LEVEL and the call is successful, the new group affinity takes effect immediately. When the call returns, the calling thread is already running on a processor that is specified in the new group affinity. If **StorPortSetSystemGroupAffinityThread** is called at IRQL = DISPATCH_LEVEL and the call is successful, the pending processor change is deferred until the caller lowers the IRQL below DISPATCH_LEVEL.

## -see-also

[**KeSetSystemGroupAffinityThread **](../wdm/nf-wdm-kesetsystemgroupaffinitythread.md)

[**STOR_GROUP_AFFINITY**](ns-storport-stor_group_affinity.md)

[**StorPortCreateSystemThread**](nf-storport-storportcreatesystemthread.md)

[**StorPortGetCurrentIrql**](nf-storport-storportgetcurrentirql.md)

[**StorPortRevertToUserGroupAffinityThread**](nf-storport-storportreverttousergroupaffinitythread.md)