---
UID: NF:storport.StorPortGetNodeAffinity2
tech.root: storage
title: StorPortGetNodeAffinity2
ms.date: 05/24/2022
targetos: Windows
description: Learn more about the StorPortGetNodeAffinity2 function.
prerelease: true
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
req.target-min-winverclnt: Windows 11, version 22H2
req.target-min-winversvr: 
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
 - StorPortGetNodeAffinity2
f1_keywords:
 - StorPortGetNodeAffinity2
 - storport/StorPortGetNodeAffinity2
dev_langs:
 - c++
helpviewer_keywords:
 - StorPortGetNodeAffinity2
---

## -description

 A miniport can call **StorPortGetNodeAffinity2** to get the current multi-group processor affinity of the given NUMA node.

## -parameters

### -param HwDeviceExtension

[in] Pointer to the miniport's device extension.

### -param NodeNumber

[in] The node number of the node to query.

### -param GroupAffinities

[out] Pointer to an array of [**GROUP_AFFINITY**](../miniport/ns-miniport-_group_affinity.md) structures that, upon success, receive a group number and the affinity mask of the identified group.

### -param GroupAffinitiesCount

[in] The number of elements in the array that **GroupAffinities** points to. If the array is too small to hold the node affinity then STATUS_BUFFER_TOO_SMALL is returned and the number of elements required is returned in **GroupAffinitiesRequired**.

### -param GroupAffinitiesCountRequired

[out] Pointer to a value that receives the number of group affinities required to represent the node affinity.

## -returns

**StorPortGetNodeAffinity2** returns STOR_STATUS_SUCCESS if the node affinity was queried successfully. Possible error return values include the following.

| Return code | Description |
| ----------- | ----------- |
| STOR_STATUS_INVALID_PARAMETER | There is an invalid parameter, such as an invalid **NodeNumber** value. |
| STOR_STATUS_BUFFER_TOO_SMALL  | The supplied array is too small. |
| STOR_STATUS_UNSUCCESSFUL      | An error occurred for internal reasons. |

## -remarks

See the *Remarks* section of [**KeQueryNodeActiveAffinity2**](..//wdm/nf-wdm-kequerynodeactiveaffinity2.md) for details.

## -see-also

[**GROUP_AFFINITY**](../miniport/ns-miniport-_group_affinity.md)
