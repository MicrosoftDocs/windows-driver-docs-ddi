---
UID: NE:ucmucsispec._UCSI_COMMAND
title: _UCSI_COMMAND (ucmucsispec.h)
tech.root: usbref
description: See Table 4-51, Command Code.
ms.assetid: d2570837-3a83-4bc4-a222-bfa867826837
ms.date: 09/30/2018
ms.topic: enum
f1_keywords:
 - "ucmucsispec/_UCSI_COMMAND"
ms.keywords: _UCSI_COMMAND, UCSI_COMMAND, 
req.header: ucmucsispec.h
req.include-header: UcmUcsiCx.h 
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.27
req.umdf-ver: N/A
req.ddi-compliance:
req.max-support:
req.typenames: UCSI_COMMAND
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- ucmucsispec.h
api_name: 
- _UCSI_COMMAND
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# _UCSI_COMMAND enumeration

## -description
See Table 4-51: Command Code, in [UCSI spec version 1.1](https://www.intel.com/content/dam/www/public/us/en/documents/technical-specifications/usb-type-c-ucsi-spec.pdf).



## -enum-fields

### -field UcsiCommandPpmReset
See PPM_RESET described in section 4.5.1 of the specification.

### -field UcsiCommandCancel
See CANCEL described in section 4.5.2 of the specification.

### -field UcsiCommandConnectorReset
See CONNECTOR_RESET described in section 4.5.3 of the specification.

### -field UcsiCommandAckCcCi
See ACK_CC_CI described in section 4.5.4 of the specification.
 
### -field UcsiCommandSetNotificationEnable
See SET_NOTIFICATION_ENABLE described in section 4.5.5 of the specification.

### -field UcsiCommandGetCapability 
See GET_CAPABILITY described in section 4.5.6 of the specification.

### -field UcsiCommandGetConnectorCapability 
See GET_CONNECTOR_CAPABILITY described in section 4.5.7 of the specification.

### -field UcsiCommandSetUom 
See SET_CCOM described in section 4.5.8 of the specification.

### -field UcsiCommandSetUor 
See SET_UOR described in section 4.5.9 of the specification.

### -field UcsiCommandSetPdm 
See SET_PDM described in section 4.5.10 of the specification.

### -field UcsiCommandSetPdr 
See SET_PDR described in section 4.5.10 of the specification.

### -field UcsiCommandGetAlternateModes 
See GET_ALTERNATE_MODES described in section 4.5.11 of the specification.

### -field UcsiCommandGetCamSupported 
See GET_CAM_SUPPORTED described in section 4.5.12 of the specification.

### -field UcsiCommandGetCurrentCam 
See GET_CURRENT_CAM described in section 4.5.13 of the specification.

### -field UcsiCommandSetNewCam 
See SET_NEW_CAM described in section 4.5.14 of the specification.

### -field UcsiCommandGetPdos 
See GET_PDOS described in section 4.5.15 of the specification.

### -field UcsiCommandGetCableProperty 
See GET_CABLE_PROPERTY described in section 4.5.16 of the specification.

### -field UcsiCommandGetConnectorStatus 
See GET_CONNECTOR_STATUS described in section 4.5.17 of the specification.

### -field UcsiCommandGetErrorStatus 
See GET_ERROR_STATUS described in section 4.5.18 of the specification.

### -field UcsiCommandSetPowerLevel 
See SET_POWER_LEVEL described in section 4.5.19 of the specification.

### -field UcsiCommandMax 
Reserved.

## -remarks

## -see-also
