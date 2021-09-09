---
UID: NF:storport.StorPortRevertToUserGroupAffinityThread
tech.root: storage
title: StorPortRevertToUserGroupAffinityThread
ms.date: 05/13/2021
targetos: Windows
description: "Learn more about: StorPortRevertToUserGroupAffinityThread"
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
 - StorPortRevertToUserGroupAffinityThread
f1_keywords:
 - StorPortRevertToUserGroupAffinityThread
 - storport/StorPortRevertToUserGroupAffinityThread
dev_langs:
 - c++
---

## -description

## -parameters

### -param HwDeviceExtension

[in] Pointer to the miniport's hardware device extension.

### -param ThreadContext

[in/optional] Pointer to the thread context received in a prior call to [**StorPortCreateSystemThread**](nf-storport-storportcreatesystemthread.md).

### -param PreviousAffinity

[in] Pointer to a [**STOR_GROUP_AFFINITY**](ns-storport-stor_group_affinity.md) structure with the group affinity to restore. This group affinity was obtained in a prior call to [**StorPortSetSystemGroupAffinityThread**](nf-storport-storportsetprioritythread.md).

## -returns

**StorPortRevertToUserGroupAffinityThread** returns one of the following values:

| Return code | Description |
| ----------- | ----------- |
| STOR_STATUS_SUCCESS | The original group affinity was restored successfully. |
| STOR_STATUS_INVALID_IRQL | IRQL level must be <= DISPATCH_LEVEL. |
| STOR_STATUS_INVALID_PARAMETER | One or more of the provided parameters are invalid. |
| STOR_STATUS_UNSUCCESSFUL | Returned for other internal system reasons. |

## -remarks

If a miniport calls [**StorPortSetSystemGroupAffinityThread**](nf-storport-storportsetsystemgroupaffinitythread.md) to temporarily change the group affinity of the thread, then it should call **StorPortRevertToUserGroupAffinityThread** to revert thread affinity to its original value before the thread exits.

## -see-also

[**STOR_GROUP_AFFINITY**](ns-storport-stor_group_affinity.md)

[**StorPortCreateSystemThread**](nf-storport-storportcreatesystemthread.md)

[**StorPortSetSystemGroupAffinityThread**](nf-storport-storportsetsystemgroupaffinitythread.md)
