---
UID: NS:ntpoapi._POWER_LIMIT_VALUE
tech.root: kernel
title: POWER_LIMIT_VALUE
ms.date: 03/17/2025
targetos: Windows
description: Describes the specific power limit value to be updated for a certain power limit. 
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntpoapi.h
req.include-header: Ntpoapi.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: POWER_LIMIT_VALUE, *PPOWER_LIMIT_VALUE
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntpoapi.h
api_name:
 - _POWER_LIMIT_VALUE
 - PPOWER_LIMIT_VALUE
 - POWER_LIMIT_VALUE
f1_keywords:
 - _POWER_LIMIT_VALUE
 - ntpoapi/_POWER_LIMIT_VALUE
 - PPOWER_LIMIT_VALUE
 - ntpoapi/PPOWER_LIMIT_VALUE
 - POWER_LIMIT_VALUE
 - ntpoapi/POWER_LIMIT_VALUE
dev_langs:
 - c++
helpviewer_keywords:
 - _POWER_LIMIT_VALUE
---

# POWER_LIMIT_VALUE structure (ntpoapi.h)

## -description

The **POWER_LIMIT_VALUE** structure describes the specific power limit value to be updated for a certain power limit.

## -struct-fields

### -field Type

Type ID of this power limit.

### -field DomainId

Domain ID of this power limit.

### -field TargetValue

The target value of this power limit.

### -field TimeParameter

The time parameter of this power limit.

## -see-also

[PoCreatePowerLimitRequest](../wdm/nf-wdm-pocreatepowerlimitrequest.md)

[PoDeletePowerLimitRequest](../wdm/nf-wdm-podeletepowerlimitrequest.md)

[PoQueryPowerLimitAttributes](../wdm/nf-wdm-poquerypowerlimitattributes.md)

[PoQueryPowerLimitValue](../wdm/nf-wdm-poquerypowerlimitattributes.md)

[PoSetPowerLimitValue](../wdm/nf-wdm-posetpowerlimitvalue.md)

[**POWER_LIMIT_ATTRIBUTES**](ns-ntpoapi-power_limit_attributes.md)

[**POWER_LIMIT_TYPES**](ne-ntpoapi-power_limit_types.md)
