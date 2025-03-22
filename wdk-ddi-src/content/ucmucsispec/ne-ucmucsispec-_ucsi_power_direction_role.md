---
UID: NE:ucmucsispec._UCSI_POWER_DIRECTION_ROLE
title: _UCSI_POWER_DIRECTION_ROLE (ucmucsispec.h)
tech.root: usbref
description: Used in the SET_PDR command. The SET_PDR command is used to set the power direction dictated by the OS Policy Manager (OPM), for the current connection.
ms.date: 05/01/2024
keywords: ["UCSI_POWER_DIRECTION_ROLE enumeration"]
ms.keywords: _UCSI_POWER_DIRECTION_ROLE, UCSI_POWER_DIRECTION_ROLE,
req.header: ucmucsispec.h
req.construct-type: enumeration
req.include-header: UcmUcsiCx.h
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.27
req.umdf-ver: N/A
req.ddi-compliance: 
req.max-support: 
req.typenames: UCSI_POWER_DIRECTION_ROLE
targetos: Windows
ms.custom: RS5
f1_keywords:
 - _UCSI_POWER_DIRECTION_ROLE
 - ucmucsispec/_UCSI_POWER_DIRECTION_ROLE
 - UCSI_POWER_DIRECTION_ROLE
 - ucmucsispec/UCSI_POWER_DIRECTION_ROLE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ucmucsispec.h
api_name:
 - _UCSI_POWER_DIRECTION_ROLE
 - UCSI_POWER_DIRECTION_ROLE
---

# UCSI_POWER_DIRECTION_ROLE enumeration (ucmucsispec.h)



## -description

Used in the SET_PDR command. The SET_PDR command is used to set the power direction dictated by the OS Policy Manager (OPM), for the current connection.

## -enum-fields

### -field UcsiPowerDirectionRoleProvider:0x1

The connector initiates swap to source, if not already operating as source.

### -field UcsiPowerDirectionRoleConsumer:0x2

The connector initiates swap to sink, if not already operating as sink.

### -field UcsiPowerDirectionRoleAcceptSwap:0x4

The connector accepts power direction swap requests from the port partner. If this bit is cleared, the connector rejects power direction swap requests from the port partner.

### -field UcsiPowerDirectionRoleProviderAcceptSwap:0x5

This field combines the *UcsiPowerDirectionRoleProvider* and *UcsiPowerDirectionRoleAcceptSwap* values.

### -field UcsiPowerDirectionRoleConsumerAcceptSwap:0x6

This field combines the *UcsiPowerDirectionRoleConsumer* and *UcsiPowerDirectionRoleAcceptSwap* values.

## -remarks

For more information, see section 4.5.10 in the [UCSI spec version 1.2](https://www.intel.com/content/www/us/en/products/docs/io/universal-serial-bus/usb-type-c-ucsi-spec.html).

## -see-also

- [UCSI spec version 1.2](https://www.intel.com/content/www/us/en/products/docs/io/universal-serial-bus/usb-type-c-ucsi-spec.html)
