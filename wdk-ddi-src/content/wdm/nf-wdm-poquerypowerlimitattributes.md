---
UID: NF:wdm.PoQueryPowerLimitAttributes
tech.root: kernel
title: PoQueryPowerLimitAttributes
ms.date: 04/28/2025
targetos: Windows
description: This function queries the attributes of a power limit request object.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: Wdm.h
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
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
 - wdm.h
api_name:
 - PoQueryPowerLimitAttributes
f1_keywords:
 - PoQueryPowerLimitAttributes
 - wdm/PoQueryPowerLimitAttributes
dev_langs:
 - c++
helpviewer_keywords:
 - PoQueryPowerLimitAttributes
---

## -description

This function queries the attributes of a power limit request object.

## -parameters

### -param PowerLimitRequest

A pointer to the power limit request object returned by [PoCreatePowerLimitRequest](nf-wdm-pocreatepowerlimitrequest.md).

### -param BufferCount

Entries of the parameter *Buffer*.

### -param Buffer

A pre-allocated buffer to save [**POWER_LIMIT_ATTRIBUTES**](../ntpoapi/ns-ntpoapi-power_limit_attributes.md) of each power limit types of power limit domains.

### -param AttributeCount

A pointer to save the number of attributes this platform supports. It should be the sum of power limit types of all domains.

## -returns

Returns an NTSTATUS value.

## -remarks

The policy calls this interface twice and allocates a buffer in between:

1. Call with *BufferCount = 0*, *Buffer = NULL*, the OS will update AttributeCount.

1. Allocate continuous memory for *AttributeCount* of [**POWER_LIMIT_ATTRIBUTES**](../ntpoapi/ns-ntpoapi-power_limit_attributes.md).

1. Call with updated *BufferCount* and *Buffer*.

## -see-also

[PoCreatePowerLimitRequest](nf-wdm-pocreatepowerlimitrequest.md)

[PoDeletePowerLimitRequest](nf-wdm-podeletepowerlimitrequest.md)

[PoQueryPowerLimitValue](nf-wdm-poquerypowerlimitvalue.md)

[PoSetPowerLimitValue](nf-wdm-posetpowerlimitvalue.md)

[**POWER_LIMIT_ATTRIBUTES**](../ntpoapi/ns-ntpoapi-power_limit_attributes.md)

[**POWER_LIMIT_TYPES**](../ntpoapi/ne-ntpoapi-power_limit_types.md)

[**POWER_LIMIT_VALUE**](../ntpoapi/ns-ntpoapi-power_limit_value.md)
