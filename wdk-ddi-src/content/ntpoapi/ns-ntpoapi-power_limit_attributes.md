---
UID: NS:ntpoapi._POWER_LIMIT_ATTRIBUTES
tech.root: kernel
title: POWER_LIMIT_ATTRIBUTES
ms.date: 03/17/2025
targetos: Windows
description: Describes the attributes of each power limit type.
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
req.typenames: POWER_LIMIT_ATTRIBUTES, *PPOWER_LIMIT_ATTRIBUTES
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
 - _POWER_LIMIT_ATTRIBUTES
 - PPOWER_LIMIT_ATTRIBUTES
 - POWER_LIMIT_ATTRIBUTES
f1_keywords:
 - _POWER_LIMIT_ATTRIBUTES
 - ntpoapi/_POWER_LIMIT_ATTRIBUTES
 - PPOWER_LIMIT_ATTRIBUTES
 - ntpoapi/PPOWER_LIMIT_ATTRIBUTES
 - POWER_LIMIT_ATTRIBUTES
 - ntpoapi/POWER_LIMIT_ATTRIBUTES
dev_langs:
 - c++
helpviewer_keywords:
 - _POWER_LIMIT_ATTRIBUTES
---

# POWER_LIMIT_ATTRIBUTES structure (ntpoapi.h)

## -description

 The **POWER_LIMIT_ATTRIBUTES** structure describes the attributes of each power limit type.

## -struct-fields

### -field Type

Indicates which [**POWER_LIMIT_TYPES**](ne-ntpoapi-power_limit_types.md) this attribute is associated with.

### -field DomainId

Indicates which domain this attribute is associated with.

### -field MaxValue

The maximum supported value (inclusive), unit is mW for power, mA for current.

### -field MinValue

The minimum supported value (inclusive), unit is mW for power, mA for current.

### -field MinTimeParameter

The minimum supported time parameter (inclusive), unit is microsecond.

### -field MaxTimeParameter

The maximum supported time parameter (inclusive), unit is microsecond.

### -field DefaultACValue

The default AC value, unit is mW for power, mA for current, microsecond for time parameters.

### -field DefaultDCValue

The default DC value, unit is mW for power, mA for current, microsecond for time parameters.

### -field Flags

Defines the Flags union.

### -field Flags.SupportTimeParameter

Set to 1 if this limit supports time parameter.

### -field Flags.Reserved

Reserved

### -field Flags.AsUlong

Defines the AsULong member of the Flags union.

## -remarks

Each instance of **POWER_LIMIT_ATTRIBUTES** is associated with one domain and one type. For example, if one power limit device has 2 domains: domain 0 supports PowerLimitContinuous, domain 1 supports PowerLimitContinuous and PowerLimitPreemptive.

## -see-also

[PoCreatePowerLimitRequest](../wdm/nf-wdm-pocreatepowerlimitrequest.md)

[PoDeletePowerLimitRequest](../wdm/nf-wdm-podeletepowerlimitrequest.md)

[PoQueryPowerLimitAttributes](../wdm/nf-wdm-poquerypowerlimitattributes.md)

[PoQueryPowerLimitValue](../wdm/nf-wdm-poquerypowerlimitattributes.md)

[PoSetPowerLimitValue](../wdm/nf-wdm-posetpowerlimitvalue.md)

[**POWER_LIMIT_TYPES**](ne-ntpoapi-power_limit_types.md)

[**POWER_LIMIT_VALUE**](ns-ntpoapi-power_limit_value.md)
