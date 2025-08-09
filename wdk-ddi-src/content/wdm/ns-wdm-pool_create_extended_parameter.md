---
UID: NS:wdm._POOL_CREATE_EXTENDED_PARAMETER
tech.root: kernel
title: POOL_CREATE_EXTENDED_PARAMETER
ms.date: 08/08/2025
targetos: Windows
description: Describes an individual extended parameter supplied to ExCreatePool.
prerelease: false
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
req.target-min-winversvr: 
req.target-type: 
req.typenames: POOL_CREATE_EXTENDED_PARAMETER, *PPOOL_CREATE_EXTENDED_PARAMETER
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _POOL_CREATE_EXTENDED_PARAMETER
 - PPOOL_CREATE_EXTENDED_PARAMETER
 - POOL_CREATE_EXTENDED_PARAMETER
f1_keywords:
 - _POOL_CREATE_EXTENDED_PARAMETER
 - wdm/_POOL_CREATE_EXTENDED_PARAMETER
 - PPOOL_CREATE_EXTENDED_PARAMETER
 - wdm/PPOOL_CREATE_EXTENDED_PARAMETER
 - POOL_CREATE_EXTENDED_PARAMETER
 - wdm/POOL_CREATE_EXTENDED_PARAMETER
dev_langs:
 - c++
helpviewer_keywords:
 - _POOL_CREATE_EXTENDED_PARAMETER
ai-usage: ai-assisted
---

## -description

The **POOL_CREATE_EXTENDED_PARAMETER** structure is used within the **Parameters** array of [**POOL_CREATE_EXTENDED_PARAMS**](ns-wdm-pool_create_extended_params.md) when calling [**ExCreatePool**](nf-wdm-excreatepool.md).

## -struct-fields

### -field Type

Specifies the parameter type. Must be a value from [**POOL_CREATE_EXTENDED_PARAMETER_TYPE**](ne-wdm-pool_create_extended_parameter_type.md).

### -field DUMMYUNIONNAME

Anonymous union that contains the data for the parameter. Interpret the active member based on **Type**.

### -field DUMMYUNIONNAME.PoolName

Valid only when **Type** == **PoolCreateExtendedParameterName**. A UNICODE_STRING specifying the name of the pool being created. Required (and must be non-empty) for paged and nonpaged private pools; must be omitted for secure pools. The string buffer must remain valid for the duration of the **ExCreatePool** call. The name is not case-sensitive for uniqueness checks.

## -remarks

Only one parameter with **Type** == **PoolCreateExtendedParameterName** may be supplied in a single **Parameters** array.

Paged and nonpaged private pools must include exactly one name parameter.

Secure pools must not include a name parameter.

The structure does not own the underlying string buffer; the caller is responsible for allocation and freeing after the call returns.

## -see-also

[**ExCreatePool**](nf-wdm-excreatepool.md)

[**POOL_CREATE_EXTENDED_PARAMS**](ns-wdm-pool_create_extended_params.md)

[**POOL_CREATE_EXTENDED_PARAMETER_TYPE**](ne-wdm-pool_create_extended_parameter_type.md)
