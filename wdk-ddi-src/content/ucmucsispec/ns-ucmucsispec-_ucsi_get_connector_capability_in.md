---
UID: NS:ucmucsispec._UCSI_GET_CONNECTOR_CAPABILITY_IN
title: _UCSI_GET_CONNECTOR_CAPABILITY_IN (ucmucsispec.h)
description: Used in the GET_CONNECTOR_CAPABILITY command.
tech.root: usbref
ms.date: 01/05/2022
keywords: ["UCSI_GET_CONNECTOR_CAPABILITY_IN structure"]
ms.keywords: _UCSI_GET_CONNECTOR_CAPABILITY_IN, UCSI_GET_CONNECTOR_CAPABILITY_IN, *PUCSI_GET_CONNECTOR_CAPABILITY_IN,
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
req.typenames: UCSI_GET_CONNECTOR_CAPABILITY_IN, *PUCSI_GET_CONNECTOR_CAPABILITY_IN
targetos: Windows
ms.custom: RS5
f1_keywords:
 - _UCSI_GET_CONNECTOR_CAPABILITY_IN
 - ucmucsispec/_UCSI_GET_CONNECTOR_CAPABILITY_IN
 - PUCSI_GET_CONNECTOR_CAPABILITY_IN
 - ucmucsispec/PUCSI_GET_CONNECTOR_CAPABILITY_IN
 - UCSI_GET_CONNECTOR_CAPABILITY_IN
 - ucmucsispec/UCSI_GET_CONNECTOR_CAPABILITY_IN
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ucmucsispec.h
api_name:
 - _UCSI_GET_CONNECTOR_CAPABILITY_IN
 - PUCSI_GET_CONNECTOR_CAPABILITY_IN
 - UCSI_GET_CONNECTOR_CAPABILITY_IN
---

# _UCSI_GET_CONNECTOR_CAPABILITY_IN structure

## -description

Used in the **GET_CONNECTOR_CAPABILITY** command.

## -struct-fields

### -field OperationMode

This field indicates the mode that the connector can support.

### -field OperationMode.AsUInt8

For internal use.

### -field OperationMode.DfpOnly

Indicates that the connector supports only DFP mode.

### -field OperationMode.UfpOnly

Indicates that the connector supports only UFP mode.

### -field OperationMode.Drp

Indicates that the connector supports DRP mode.

### -field OperationMode.AudioAccessoryMode

Indicates that the connector supports audio accessory mode.

### -field OperationMode.DebugAccessoryMode

Indicates that the connector supports debug accessory mode.

### -field OperationMode.Usb2

Indicates that the connector supports USB2 mode.

### -field OperationMode.Usb3

Indicates that the connector supports USB3 mode.

### -field OperationMode.AlternateMode

Indicates that the connector supports an alternate mode.

### -field Provider

Indicates that the connector is capable of providing power.

### -field Consumer

Indicates that the connector is capable of consuming power.

### -field SwapToDfp

Indicates that the connector is capable of accepting swap to DFP.

### -field SwapToUfp

Indicates that the connector is capable of accepting swap to UFP.

### -field SwapToSrc

Indicates that the connector is capable of accepting swap to SRC.

### -field SwapToSnk

Indicates that the connector is capable of accepting swap to SNK.

## -remarks

See Table 4-17 in [UCSI spec version 1.2](https://www.intel.cn/content/dam/www/public/us/en/documents/technical-specifications/usb-type-c-ucsi-spec.pdf).

## -see-also

- [UCSI_GET_CONNECTOR_CAPABILITY_COMMAND](ns-ucmucsispec-_ucsi_get_connector_capability_command.md)
- [UCSI spec version 1.2](https://www.intel.cn/content/dam/www/public/us/en/documents/technical-specifications/usb-type-c-ucsi-spec.pdf)
