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
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 21H1
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - 
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

[out/optional] Pointer to a [**STOR_GROUP_AFFINITY**](ns-storport-stor_group_affinity.md) structure in which this routine writes the group number and affinity mask for the calling thread prior to the call.

## -returns

**StorPortSetSystemGroupAffinityThread** returns one of the following values:

| Return code | Description |
| ----------- | ----------- |
| STOR_STATUS_SUCCESS | The specified group affinity was set successfully. |
| STOR_STATUS_INVALID_PARAMETER | One or more of the provided parameters are invalid. |
| STOR_STATUS_UNSUCCESSFUL | Returned for other internal system reasons. |

## -remarks

A miniport can call this function to change the group number and affinity mask of the calling thread.

If miniport calls this function to temporarily change the group affinity of the thread, then it should call [**StorPortRevertToUserGroupAffinityThread**](nf-storport-storportreverttousergroupaffinitythread.md) to revert thread affinity to its original value before the thread exits.

## -see-also

[**STOR_GROUP_AFFINITY**](ns-storport-stor_group_affinity.md)

[**StorPortCreateSystemThread**](nf-storport-storportcreatesystemthread.md)

[**StorPortRevertToUserGroupAffinityThread**](nf-storport-storportreverttousergroupaffinitythread.md)