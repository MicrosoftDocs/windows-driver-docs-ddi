---
UID: NS:wdm._POOL_EXTENDED_PARAMETER
title: POOL_EXTENDED_PARAMETER
tech.root: kernel
ms.date: 03/01/2020
targetos: Windows
description: "Learn more about: POOL_EXTENDED_PARAMETER"
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
req.typenames: POOL_EXTENDED_PARAMETER, *PPOOL_EXTENDED_PARAMETER
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _POOL_EXTENDED_PARAMETER
 - PPOOL_EXTENDED_PARAMETER
 - POOL_EXTENDED_PARAMETER
f1_keywords:
 - _POOL_EXTENDED_PARAMETER
 - wdm/_POOL_EXTENDED_PARAMETER
 - PPOOL_EXTENDED_PARAMETER
 - wdm/PPOOL_EXTENDED_PARAMETER
 - POOL_EXTENDED_PARAMETER
 - wdm/POOL_EXTENDED_PARAMETER
dev_langs:
 - c++
---

## -description

Specifies extended parameter information that the driver provides when calling [**ExAllocatePool3**](nf-wdm-exallocatepool3.md).

## -struct-fields

### -field DUMMYSTRUCTNAME

### -field DUMMYSTRUCTNAME.Type

A [**POOL_EXTENDED_PARAMETER_TYPE**](ne-wdm-pool_extended_parameter_type.md) enumeration value that indicates the type of the parameter.

If this value is set to **PoolExtendedParameterPriority**, then the **Priority** member of this structure must be an [**EX_POOL_PRIORITY**](ne-wdm-ex_pool_priority.md) value indicating the priority of the pool allocation. If there is not enough space for the specified priority the allocation fails.

### -field DUMMYSTRUCTNAME.Optional

If this field is set to 1, the extended parameter is optional. If **Type** is not a valid enumeration value, it is ignored. If **Type** is a valid enumeration, it may still be ignored, for example if it is incompatible with other specified flags.

If this field is set to 0, **Type** must be recognized by the pool allocator or the allocation fails.

### -field DUMMYSTRUCTNAME.Reserved

Reserved for future use.

### -field DUMMYUNIONNAME

### -field DUMMYUNIONNAME.Reserved2

### -field DUMMYUNIONNAME.Reserved3

### -field DUMMYUNIONNAME.Priority

If **Type** is set to **PoolExtendedParameterPriority**, this field must contain a valid [**EX_POOL_PRIORITY**](ne-wdm-ex_pool_priority.md) value.

### -field DUMMYUNIONNAME.SecurePoolParams

### -field DUMMYUNIONNAME.PreferredNode

If **Type** is set to **PoolExtendedParameterNumaNode** this field should contain a valid NUMA node index numbered 0 through N-1.
If the field also contains MM_ANY_NODE_OK, the call prefers the specified NUMA node but tries others if it is unavailable.
If MM_ANY_NODE_OK is not set, the call fails if the requested NUMA node cannot satisfy the allocation.
This parameter is valid only for allocations made with POOL_FLAG_NON_PAGED pool.

## -remarks

## -see-also

[**POOL_EXTENDED_PARAMETER_TYPE**](ne-wdm-pool_extended_parameter_type.md)

[**ExAllocatePool3**](nf-wdm-exallocatepool3.md)

