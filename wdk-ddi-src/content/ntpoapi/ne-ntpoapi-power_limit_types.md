---
UID: NE:ntpoapi._POWER_LIMIT_TYPES
tech.root: kernel
title: POWER_LIMIT_TYPES
ms.date: 03/21/2025
targetos: Windows
description: Enumerates power limit types that describe a throttled object (power or battery discharge current) and how long the throttled object can last.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: ntpoapi.h
req.include-header: Ntpoapi.h
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
 - ntpoapi.h
api_name:
 - _POWER_LIMIT_TYPES
 - PPOWER_LIMIT_TYPES
 - POWER_LIMIT_TYPES
f1_keywords:
 - _POWER_LIMIT_TYPES
 - ntpoapi/_POWER_LIMIT_TYPES
 - PPOWER_LIMIT_TYPES
 - ntpoapi/PPOWER_LIMIT_TYPES
 - POWER_LIMIT_TYPES
 - ntpoapi/POWER_LIMIT_TYPES
dev_langs:
 - c++
helpviewer_keywords:
 - _POWER_LIMIT_TYPES
---

## -description

Enumerates power limit types that describe a throttled object (power or battery discharge current) and how long the throttled object can last.

## -enum-fields

### -field PowerLimitContinuous

The platform could sustain infinitely if the average power is under this limit.

### -field PowerLimitBurst

The platform could typically sustain at seconds level if the average power is higher than **PowerLimitContinuous** but lower than this limit.  

### -field PowerLimitRapid

The platform starts associated algorithm to throttle the domain reactively once the power peaks above this limit.

### -field PowerLimitPreemptive

A limit that will not be exceeded, the platform will be preemptively throttled to prevent spikes above this limit.

### -field PowerLimitPreemptiveOffset

The sum of peak power of specified devices, which is used to adjust **PowerLimitPreemptive** at runtime.

## -see-also

[PoCreatePowerLimitRequest](../wdm/nf-wdm-pocreatepowerlimitrequest.md)

[PoDeletePowerLimitRequest](../wdm/nf-wdm-podeletepowerlimitrequest.md)

[PoQueryPowerLimitAttributes](../wdm/nf-wdm-poquerypowerlimitattributes.md)

[PoQueryPowerLimitValue](../wdm/nf-wdm-poquerypowerlimitvalue.md)

[PoSetPowerLimitValue](../wdm/nf-wdm-posetpowerlimitvalue.md)

[**POWER_LIMIT_ATTRIBUTES**](ns-ntpoapi-power_limit_attributes.md)

[**POWER_LIMIT_VALUE**](ns-ntpoapi-power_limit_value.md)
