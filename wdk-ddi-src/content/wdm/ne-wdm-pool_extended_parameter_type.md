---
UID: NE:wdm.POOL_EXTENDED_PARAMETER_TYPE
title: POOL_EXTENDED_PARAMETER_TYPE
tech.root: kernel
ms.date: 01/10/2022
targetos: Windows
description: "Learn more about: POOL_EXTENDED_PARAMETER_TYPE"
req.construct-type: enumeration
req.ddi-compliance: 
req.header: wdm.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - POOL_EXTENDED_PARAMETER_TYPE
 - PPOOL_EXTENDED_PARAMETER_TYPE
f1_keywords:
 - POOL_EXTENDED_PARAMETER_TYPE
 - wdm/POOL_EXTENDED_PARAMETER_TYPE
 - PPOOL_EXTENDED_PARAMETER_TYPE
 - wdm/PPOOL_EXTENDED_PARAMETER_TYPE
dev_langs:
 - c++
---

## -description

This enumeration is used in the [**POOL_EXTENDED_PARAMETER**](xref:NS:wdm._POOL_EXTENDED_PARAMETER) structure.

## -enum-fields

### -field PoolExtendedParameterInvalidType:0

Invalid extended parameter type. Do not use.

### -field PoolExtendedParameterPriority

The extended parameter specifies the priority of the pool allocation using the **Priority** field of the <a href="ns-wdm-pool_extended_parameter.md"><b>POOL_EXTENDED_PARAMETER</b></a> structure.

### -field PoolExtendedParameterSecurePool

The extended parameter specifies the secure pool parameters of the pool allocation using the **SecurePoolParams** field of the <a href="ns-wdm-pool_extended_parameter.md"><b>POOL_EXTENDED_PARAMETER</b></a> structure.

### -field PoolExtendedParameterNumaNode

The extended parameter specifies the preferred NUMA node of the pool allocation using the **PreferredNode** field of the <a href="ns-wdm-pool_extended_parameter.md"><b>POOL_EXTENDED_PARAMETER</b></a> structure.

### -field PoolExtendedParameterMax

For internal use only.

## -remarks

## -see-also

[**ExAllocatePool3**](nf-wdm-exallocatepool3.md)

