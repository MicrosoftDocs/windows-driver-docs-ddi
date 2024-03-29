---
UID: NS:ucmucsispec._UCSI_CCI
title: _UCSI_CCI (ucmucsispec.h)
tech.root: usbref
description: Used in GET_CONNECTOR_CAPABILITY command. See Table 4-16.
ms.date: 09/30/2018
keywords: ["UCSI_CCI structure"]
ms.keywords: _UCSI_CCI, UCSI_CCI, *PUCSI_CCI,
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
req.typenames: UCSI_CCI, *PUCSI_CCI
targetos: Windows
ms.custom: RS5
f1_keywords:
 - _UCSI_CCI
 - ucmucsispec/_UCSI_CCI
 - PUCSI_CCI
 - ucmucsispec/PUCSI_CCI
 - UCSI_CCI
 - ucmucsispec/UCSI_CCI
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ucmucsispec.h
api_name:
 - _UCSI_CCI
 - PUCSI_CCI
 - UCSI_CCI
---

# _UCSI_CCI structure


## -description

Used in the GET_CONNECTOR_CAPABILITY command. See Table 4-16 in [UCSI spec version 1.2](https://www.intel.com/content/dam/www/public/us/en/documents/technical-specifications/usb-type-c-ucsi-spec.pdf).

## -struct-fields

### -field AsUInt32

### -field ConnectorChangeIndicator

### -field DataLength

### -field NotSupportedIndicator

### -field CancelCompletedIndicator

### -field ResetCompletedIndicator

### -field BusyIndicator

### -field AcknowledgeCommandIndicator

### -field ErrorIndicator

### -field CommandCompletedIndicator

## -remarks

## -see-also

