---
UID: NE:wdm.POOL_EXTENDED_PARAMETER_TYPE
title: POOL_EXTENDED_PARAMETER_TYPE
tech.root: kernel
ms.date: 03/01/2020
ms.topic: language-reference
targetos: Windows
description: 
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
f1_keywords:
 - wdm/POOL_EXTENDED_PARAMETER_TYPE
dev_langs:
 - c++
---

## -description

This enumeration is used in the [**POOL_EXTENDED_PARAMETER**](ns-wdm-pool_extended_parameter.md) structure. 

## -enum-fields

### -field PoolExtendedParameterInvalidType

Invalid extended parameter type. Do not use.

### -field PoolExtendedParameterPriority

The extended parameter specifies the priority of the pool allocation using the **Priority** field of the <a href="ns-wdm-pool_extended_parameter.md"><b>POOL_EXTENDED_PARAMETER</b></a> structure.

### -field PoolExtendedParameterMax

For internal use only.

## -remarks

## -see-also

[**ExAllocatePool3**](nf-wdm-exallocatepool3.md)