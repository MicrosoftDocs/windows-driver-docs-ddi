---
UID: NF:wdm.PoCreatePowerLimitRequest
tech.root: kernel
title: PoCreatePowerLimitRequest
ms.date: 03/17/2025
targetos: Windows
description: This function creates a power limit request object.
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
 - PoCreatePowerLimitRequest
f1_keywords:
 - PoCreatePowerLimitRequest
 - wdm/PoCreatePowerLimitRequest
dev_langs:
 - c++
helpviewer_keywords:
 - PoCreatePowerLimitRequest
---

# PoCreatePowerLimitRequest function (wdm.h)

## -description

This function creates a power limit request object.

## -parameters

### -param PowerLimitRequest

A pointer to receive the power limit request object.

### -param TargetDeviceObject

Supplies the device object of the device to apply power limits.

### -param PolicyDeviceObject

Supplies the device object of the device creating power limit requests.

### -param Context

 A pointer to a [**COUNTED_REASON_CONTEXT**](ns-wdm-_counted_reason_context.md) structure that describes why the caller is creating the power limit request object.

## -returns

Returns an NTSTATUS value.

## -see-also

[PoDeletePowerLimitRequest](nf-wdm-podeletepowerlimitrequest.md)

[PoQueryPowerLimitAttributes](nf-wdm-poquerypowerlimitattributes.md)

[PoQueryPowerLimitValue](nf-wdm-poquerypowerlimitattributes.md)

[PoSetPowerLimitValue](nf-wdm-posetpowerlimitvalue.md)

[**POWER_LIMIT_ATTRIBUTES**](../ntpoapi/ns-ntpoapi-power_limit_attributes.md)

[**POWER_LIMIT_TYPES**](../ntpoapi/ne-ntpoapi-power_limit_types.md)

[**POWER_LIMIT_VALUE**](../ntpoapi/ns-ntpoapi-power_limit_value.md)
