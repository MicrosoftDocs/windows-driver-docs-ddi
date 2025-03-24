---
UID: NF:wdm.PoQueryPowerLimitValue
tech.root: kernel
title: PoQueryPowerLimitValue
ms.date: 03/17/2025
targetos: Windows
description: This function queries the limit values of a power limit request object.
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
 - PoQueryPowerLimitValue
f1_keywords:
 - PoQueryPowerLimitValue
 - wdm/PoQueryPowerLimitValue
dev_langs:
 - c++
helpviewer_keywords:
 - PoQueryPowerLimitValue
---

## -description

This function queries the limit values of a power limit request object.

## -parameters

### -param PowerLimitRequest

A pointer to the power limit request object returned by [PoCreatePowerLimitRequest](nf-wdm-pocreatepowerlimitrequest.md).

### -param ValueCount

Supplies the number of limit values to query.  

### -param Values

Supplies a pointer to the buffer that contains target limits and stores the readout.

## -returns

Returns an NTSTATUS value.

## -see-also

[PoCreatePowerLimitRequest](nf-wdm-pocreatepowerlimitrequest.md)

[PoDeletePowerLimitRequest](nf-wdm-podeletepowerlimitrequest.md)

[PoQueryPowerLimitAttributes](nf-wdm-poquerypowerlimitattributes.md)

[PoSetPowerLimitValue](nf-wdm-posetpowerlimitvalue.md)

[**POWER_LIMIT_ATTRIBUTES**](../ntpoapi/ns-ntpoapi-power_limit_attributes.md)

[**POWER_LIMIT_TYPES**](../ntpoapi/ne-ntpoapi-power_limit_types.md)

[**POWER_LIMIT_VALUE**](../ntpoapi/ns-ntpoapi-power_limit_value.md)
