---
UID: NS:ucmucsispec._UCSI_CONTROL
title: _UCSI_CONTROL (ucmucsispec.h)
tech.root: usbref
description: Used in the SET_NOTIFICATION_ENABLE command. See Table 4-9.
ms.date: 09/30/2018
keywords: ["UCSI_CONTROL structure"]
ms.keywords: _UCSI_CONTROL, UCSI_CONTROL, *PUCSI_CONTROL,
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
req.typenames: UCSI_CONTROL, *PUCSI_CONTROL
targetos: Windows
ms.custom: RS5
f1_keywords:
 - _UCSI_CONTROL
 - ucmucsispec/_UCSI_CONTROL
 - PUCSI_CONTROL
 - ucmucsispec/PUCSI_CONTROL
 - UCSI_CONTROL
 - ucmucsispec/UCSI_CONTROL
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ucmucsispec.h
api_name:
 - _UCSI_CONTROL
 - PUCSI_CONTROL
 - UCSI_CONTROL
---

# _UCSI_CONTROL structure


## -description

Used in the SET_NOTIFICATION_ENABLE command. See Table 4-9 in [UCSI spec version 1.2](https://www.intel.com/content/dam/www/public/us/en/documents/technical-specifications/usb-type-c-ucsi-spec.pdf).

## -struct-fields

### -field AsUInt64

### -field Command

### -field DataLength

### -field CommandSpecific

### -field ConnectorReset

### -field AckCcCi

### -field SetNotificationEnable

### -field GetConnectorCapability

### -field SetUom

### -field SetUor

### -field SetPdm

### -field SetPdr

### -field GetAlternateModes

### -field GetCamSupported

### -field GetCurrentCam

### -field SetNewCam

### -field GetPdos

### -field GetCableProperty

### -field GetConnectorStatus

### -field GetErrorStatus

### -field SetPowerLevel

## -remarks

## -see-also

