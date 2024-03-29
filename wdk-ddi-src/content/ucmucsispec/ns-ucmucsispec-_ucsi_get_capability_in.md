---
UID: NS:ucmucsispec._UCSI_GET_CAPABILITY_IN
title: _UCSI_GET_CAPABILITY_IN (ucmucsispec.h)
description: Used in the GET_CAPABILITY command. See Table 4-13.
tech.root: usbref
ms.date: 09/30/2018
keywords: ["UCSI_GET_CAPABILITY_IN structure"]
ms.keywords: _UCSI_GET_CAPABILITY_IN, UCSI_GET_CAPABILITY_IN, *PUCSI_GET_CAPABILITY_IN,
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
req.typenames: UCSI_GET_CAPABILITY_IN, *PUCSI_GET_CAPABILITY_IN
targetos: Windows
ms.custom: RS5
f1_keywords:
 - _UCSI_GET_CAPABILITY_IN
 - ucmucsispec/_UCSI_GET_CAPABILITY_IN
 - PUCSI_GET_CAPABILITY_IN
 - ucmucsispec/PUCSI_GET_CAPABILITY_IN
 - UCSI_GET_CAPABILITY_IN
 - ucmucsispec/UCSI_GET_CAPABILITY_IN
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ucmucsispec.h
api_name:
 - _UCSI_GET_CAPABILITY_IN
 - PUCSI_GET_CAPABILITY_IN
 - UCSI_GET_CAPABILITY_IN
---

# _UCSI_GET_CAPABILITY_IN structure


## -description

Used in the GET_CAPABILITY command. See Table 4-13 in [UCSI spec version 1.2](https://www.intel.com/content/dam/www/public/us/en/documents/technical-specifications/usb-type-c-ucsi-spec.pdf).

## -struct-fields

### -field bmAttributes

### -field bmAttributes.AsUInt32

### -field bmAttributes.DisabledStateSupport

### -field bmAttributes.BatteryCharging

### -field bmAttributes.UsbPowerDelivery

### -field bmAttributes.UsbTypeCCurrent

### -field bmAttributes.bmPowerSource

### -field bNumConnectors

### -field bmOptionalFeatures

### -field bmOptionalFeatures.SetUomSupported

### -field bmOptionalFeatures.SetPdmSupported

### -field bmOptionalFeatures.AlternateModeDetailsAvailable

### -field bmOptionalFeatures.AlternateModeOverrideSupported

### -field bmOptionalFeatures.PdoDetailsAvailable

### -field bmOptionalFeatures.CableDetailsAvailable

### -field bmOptionalFeatures.ExternalSupplyNotificationSupported

### -field bmOptionalFeatures.PdResetNotificationSupported

### -field OptionalFeatures

### -field bNumAltModes

### -field bcdBcVersion

### -field bcdPdVersion

### -field bcdUsbTypeCVersion

## -remarks

## -see-also

