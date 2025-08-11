---
UID: NS:wdm._POOL_CREATE_EXTENDED_PARAMS
tech.root: kernel
title: POOL_CREATE_EXTENDED_PARAMS
ms.date: 08/17/2023
targetos: Windows
description: Defines the POOL_CREATE_EXTENDED_PARAMS structure.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.include-header: Wdm.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: POOL_CREATE_EXTENDED_PARAMS, *PPOOL_CREATE_EXTENDED_PARAMS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _POOL_CREATE_EXTENDED_PARAMS
 - PPOOL_CREATE_EXTENDED_PARAMS
 - POOL_CREATE_EXTENDED_PARAMS
f1_keywords:
 - _POOL_CREATE_EXTENDED_PARAMS
 - wdm/_POOL_CREATE_EXTENDED_PARAMS
 - PPOOL_CREATE_EXTENDED_PARAMS
 - wdm/PPOOL_CREATE_EXTENDED_PARAMS
 - POOL_CREATE_EXTENDED_PARAMS
 - wdm/POOL_CREATE_EXTENDED_PARAMS
dev_langs:
 - c++
ai-usage: ai-assisted
---

## -description

Defines the **POOL_CREATE_EXTENDED_PARAMS** structure.

## -struct-fields

### -field Version

ULONG that specifies the version of this structure. Set to **POOL_CREATE_PARAMS_VERSION** (currently 1). Any other value causes **ExCreatePool** to fail with **STATUS_INVALID_PARAMETER**. Future versions may extend this structure; drivers must always initialize this field explicitly.

### -field ParameterCount

Number of elements in the array pointed to by **Parameters**. Must be 0 if no extended parameters are supplied.

### -field Parameters

Pointer to an array of [**POOL_CREATE_EXTENDED_PARAMETER**](ns-wdm-pool_create_extended_parameter.md) entries that provide additional creation parameters. Must be NULL when **ParameterCount** is 0. Each entry's **Type** field identifies the parameter kind. Currently the only valid type is **PoolCreateExtendedParameterName**, which supplies the pool's Unicode name in the **PoolName** member. The name must be unique within the creating driver context and follow any internal naming constraints. Unsupported or duplicate parameter types are rejected.

## -remarks

Use this structure to pass optional (or required) extended creation data to [**ExCreatePool**](nf-wdm-excreatepool.md) via its **Params** argument.

Paged and nonpaged private pools must specify exactly one name parameter. Secure pools must not specify a name parameter.

If **ParameterCount** is non-zero, **Parameters** must point to a valid, readable array of that many entries.

Parameter types not recognized by the kernel or appearing more than once cause **ExCreatePool** to return **STATUS_INVALID_PARAMETER_3**.

The structure is versioned to allow forward compatibility; drivers should not assume additional fields remain zero across future releases—always check the version before interpreting unrecognized extensions (if reading a buffer originated elsewhere).

## -see-also

[**ExCreatePool**](nf-wdm-excreatepool.md)

[**ExDestroyPool**](nf-wdm-exdestroypool.md)
