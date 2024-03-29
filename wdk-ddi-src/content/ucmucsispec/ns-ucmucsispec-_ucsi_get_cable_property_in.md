---
UID: NS:ucmucsispec._UCSI_GET_CABLE_PROPERTY_IN
title: _UCSI_GET_CABLE_PROPERTY_IN (ucmucsispec.h)
tech.root: usbref
description: Used in the GET_CABLE_PROPERTY command. See Table 4-39.
ms.date: 09/30/2018
keywords: ["UCSI_GET_CABLE_PROPERTY_IN structure"]
ms.keywords: _UCSI_GET_CABLE_PROPERTY_IN, UCSI_GET_CABLE_PROPERTY_IN, *PUCSI_GET_CABLE_PROPERTY_IN,
req.header: ucmucsispec.h
req.include-header: UcmUcsiCx.h
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.27
req.umdf-ver: N/A
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: UCSI_GET_CABLE_PROPERTY_IN, *PUCSI_GET_CABLE_PROPERTY_IN
targetos: Windows
ms.custom: RS5
f1_keywords:
 - _UCSI_GET_CABLE_PROPERTY_IN
 - ucmucsispec/_UCSI_GET_CABLE_PROPERTY_IN
 - PUCSI_GET_CABLE_PROPERTY_IN
 - ucmucsispec/PUCSI_GET_CABLE_PROPERTY_IN
 - UCSI_GET_CABLE_PROPERTY_IN
 - ucmucsispec/UCSI_GET_CABLE_PROPERTY_IN
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ucmucsispec.h
api_name:
 - _UCSI_GET_CABLE_PROPERTY_IN
 - PUCSI_GET_CABLE_PROPERTY_IN
 - UCSI_GET_CABLE_PROPERTY_IN
---

# _UCSI_GET_CABLE_PROPERTY_IN structure


## -description

Used in the GET_CABLE_PROPERTY command. See Table 4-39 in [UCSI spec version 1.2](https://www.intel.com/content/dam/www/public/us/en/documents/technical-specifications/usb-type-c-ucsi-spec.pdf).

## -struct-fields

### -field bmSpeedSupported

### -field bmSpeedSupported.AsUInt16

### -field bmSpeedSupported.SpeedExponent

### -field bmSpeedSupported.Mantissa

### -field bCurrentCapability

### -field VBusInCable

### -field CableType

### -field Directionality

### -field PlugEndType

### -field ModeSupport

### -field Latency

## -remarks

## -see-also

