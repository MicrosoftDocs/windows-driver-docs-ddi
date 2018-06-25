---
UID: NS:ucmucsispec._UCSI_GET_CONNECTOR_CAPABILITY_IN
title: _UCSI_GET_CONNECTOR_CAPABILITY_IN
author: windows-driver-content
description: Used in the GET_CONNECTOR_CAPABILITY command. See Table 4-17.
ms.assetid: 2cbd9c0e-f5a8-4b63-9879-3e8d775717b5
ms.author: windowsdriverdev
ms.date: 09/30/2018 
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _UCSI_GET_CONNECTOR_CAPABILITY_IN, UCSI_GET_CONNECTOR_CAPABILITY_IN, *PUCSI_GET_CONNECTOR_CAPABILITY_IN, 
req.header: ucmucsispec.h
req.include-header: UcmucsiCx.h 
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
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	ucmucsispec.h
api_name: 
-	_UCSI_GET_CONNECTOR_CAPABILITY_IN
product: Windows
targetos: Windows
---

# _UCSI_GET_CONNECTOR_CAPABILITY_IN structure

## -description
Used in the GET_CONNECTOR_CAPABILITY command. See Table 4-17 in [UCSI spec version 1.1](https://www.intel.com/content/dam/www/public/us/en/documents/technical-specifications/usb-type-c-ucsi-spec.pdf).


## -struct-fields

### -field OperationMode
 
### -field OperationMode.AsUInt8
 
### -field OperationMode.DfpOnly
 
### -field OperationMode.UfpOnly
 
### -field OperationMode.Drp
 
### -field OperationMode.AudioAccessoryMode
 
### -field OperationMode.DebugAccessoryMode
 
### -field OperationMode.Usb2
 
### -field OperationMode.Usb3
 
### -field OperationMode.AlternateMode
 
### -field Provider
 
### -field Consumer
 

## -remarks

## -see-also