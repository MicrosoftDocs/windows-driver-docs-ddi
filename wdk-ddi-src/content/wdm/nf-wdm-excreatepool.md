---
UID: NF:wdm.ExCreatePool
tech.root: kernel
title: ExCreatePool
ms.date: 08/08/2025
targetos: Windows
description: Creates a pool instance of the requested type.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: Wdm.h
req.irql: PASSIVE_LEVEL
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
 - wdm.h
api_name:
 - ExCreatePool
f1_keywords:
 - ExCreatePool
 - wdm/ExCreatePool
dev_langs:
 - c++
ai-usage: ai-assisted
---

## -description

**ExCreatePool** creates a pool instance of the requested type.

## -parameters

### -param Flags

[in] Bitmask specifying the pool type and optional creation options. Exactly one pool type flag must be specified. The following values are mutually exclusive:

| Value | Description |
|-------|-------------|
| POOL_CREATE_FLG_SECURE_POOL | Creates a secure pool instance. A pool name must NOT be supplied when this flag is used. |
| POOL_CREATE_FLG_PAGED_POOL | Creates a private paged pool instance. A pool name MUST be supplied via an extended parameter. Allocations may reside in pageable memory. |
| POOL_CREATE_FLG_NONPAGED_POOL | Creates a private nonpaged pool instance. A pool name MUST be supplied via an extended parameter. Allocations remain resident in nonpaged memory. |

### -param Tag

[in] Tag (four-character value, stored in little-endian form) to associate with the pool.

### -param Params

[in, optional] Pointer to a [**POOL_CREATE_EXTENDED_PARAMS**](ns-wdm-pool_create_extended_params.md) structure that supplies extended creation parameters for the given pool type. This parameter can be NULL. A name parameter may be supplied subject to these rules: required for paged and nonpaged pools; not permitted for secure pools; only one name parameter allowed; unsupported parameter types are rejected.

### -param PoolHandle

[out] Receives the opaque handle to the newly created pool on success.

## -returns

Returns an NTSTATUS value such as one of the following values.

| Return code | Description |
|-------------|-------------|
| **STATUS_SUCCESS** | Pool created successfully and **PoolHandle** is valid. |
| **STATUS_INVALID_PARAMETER_1** | Pool type specification in **Flags** was invalid. |
| **STATUS_INVALID_PARAMETER_3** | Extended parameters invalid (missing required name, disallowed name, duplicate name, or unsupported parameter type). |
| Other status codes | An error occurred during creation. |

## -remarks

**ExCreatePool** creates a pool instance of the requested type (secure, paged, or nonpaged) and returns an opaque handle that can be used with pool management routines. The caller specifies a pool type via flags and may supply optional extended parameters.

Exactly one pool type flag must be present in **Flags**. A pool name is required for paged and nonpaged pools and must be omitted for secure pools.

Extended parameters are optional when no name is required by the chosen pool type. The handle returned should be released using the appropriate pool management routine when no longer needed.

Pool allocation is done by calling [**ExAllocatePool2**](nf-wdm-exallocatepool2.md).

## -see-also

`POOL_CREATE_EXTENDED_PARAMS`

[**ExAllocatePool2**](nf-wdm-exallocatepool2.md)

[**ExFreePool2**](nf-wdm-exfreepool2.md)
