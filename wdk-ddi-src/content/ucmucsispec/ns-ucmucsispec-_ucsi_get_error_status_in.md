---
UID: NS:ucmucsispec._UCSI_GET_ERROR_STATUS_IN
title: _UCSI_GET_ERROR_STATUS_IN
author: windows-driver-content
description: Used in the GET_ERROR_STATUS command. See Table 4-47.
ms.assetid: 94622279-e077-4ded-a143-32223bcc23fb
tech.root: usbref
ms.date: 09/30/2018
ms.topic: struct
ms.keywords: _UCSI_GET_ERROR_STATUS_IN, UCSI_GET_ERROR_STATUS_IN, *PUCSI_GET_ERROR_STATUS_IN, 
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
req.typenames: UCSI_GET_ERROR_STATUS_IN, *PUCSI_GET_ERROR_STATUS_IN
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	ucmucsispec.h
api_name: 
-	_UCSI_GET_ERROR_STATUS_IN
product: Windows
targetos: Windows
---

# _UCSI_GET_ERROR_STATUS_IN structure

## -description
Used in the GET_ERROR_STATUS command. See Table 4-47 in [UCSI spec version 1.1](https://www.intel.com/content/dam/www/public/us/en/documents/technical-specifications/usb-type-c-ucsi-spec.pdf).

## -struct-fields

### -field ErrorInformation
 
### -field ErrorInformation.AsUInt16
 
### -field ErrorInformation.UnrecognizedCommandError
 
### -field ErrorInformation.NonExistentConnectorNumberError
 
### -field ErrorInformation.InvalidCommandParametersError
 
### -field ErrorInformation.IncompatibleConnectorPartnerError
 
### -field ErrorInformation.CcCommunicationError
 
### -field ErrorInformation.CommandFailureDueToDeadBattery
 
### -field ErrorInformation.ContractNegotiationFailure
 
### -field VendorDefined
 

## -remarks

## -see-also
