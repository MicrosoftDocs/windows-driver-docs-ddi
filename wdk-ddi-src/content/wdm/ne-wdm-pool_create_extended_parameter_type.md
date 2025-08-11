---
UID: NE:wdm._POOL_CREATE_EXTENDED_PARAMETER_TYPE
tech.root: kernel
title: POOL_CREATE_EXTENDED_PARAMETER_TYPE
ms.date: 08/08/2025
targetos: Windows
description: Enumerates the types of extended parameters that can be passed to ExCreatePool.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: wdm.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: false
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _POOL_CREATE_EXTENDED_PARAMETER_TYPE
 - PPOOL_CREATE_EXTENDED_PARAMETER_TYPE
 - POOL_CREATE_EXTENDED_PARAMETER_TYPE
f1_keywords:
 - _POOL_CREATE_EXTENDED_PARAMETER_TYPE
 - wdm/_POOL_CREATE_EXTENDED_PARAMETER_TYPE
 - PPOOL_CREATE_EXTENDED_PARAMETER_TYPE
 - wdm/PPOOL_CREATE_EXTENDED_PARAMETER_TYPE
 - POOL_CREATE_EXTENDED_PARAMETER_TYPE
 - wdm/POOL_CREATE_EXTENDED_PARAMETER_TYPE
dev_langs:
 - c++
helpviewer_keywords:
 - _POOL_CREATE_EXTENDED_PARAMETER_TYPE
ai-usage: ai-assisted
---

## -description

The **POOL_CREATE_EXTENDED_PARAMETER_TYPE** enumeration identifies the kind of data present in a [**POOL_CREATE_EXTENDED_PARAMETER**](ns-wdm-pool_create_extended_parameter.md) entry.

## -enum-fields

### -field PoolCreateExtendedParameterInvalidType

Using this value in a parameter causes [**ExCreatePool**](nf-wdm-excreatepool.md) to fail with **STATUS_INVALID_PARAMETER_3**.

### -field PoolCreateExtendedParameterName

Specifies that the parameter supplies a pool name through the **PoolName** member of the union in **POOL_CREATE_EXTENDED_PARAMETER**. Required for paged and nonpaged private pools. Not permitted for secure pools.

## -remarks

Future versions of Windows may introduce additional parameter types. Drivers constructing a parameters array must not include duplicate types.

## -see-also

[**ExCreatePool**](nf-wdm-excreatepool.md)

[**POOL_CREATE_EXTENDED_PARAMETER**](ns-wdm-pool_create_extended_parameter.md)

[**POOL_CREATE_EXTENDED_PARAMS**](ns-wdm-pool_create_extended_params.md)
