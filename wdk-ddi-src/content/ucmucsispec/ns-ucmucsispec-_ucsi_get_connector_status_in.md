---
UID: NS:ucmucsispec._UCSI_GET_CONNECTOR_STATUS_IN
title: _UCSI_GET_CONNECTOR_STATUS_IN (ucmucsispec.h)
description: Used in the GET_CONNECTOR_STATUS command. See Table 4-42.
ms.assetid: 09365116-affe-4b3e-9b31-e98bcf6c3518
tech.root: usbref
ms.date: 09/30/2018
ms.topic: struct
ms.keywords: _UCSI_GET_CONNECTOR_STATUS_IN, UCSI_GET_CONNECTOR_STATUS_IN, *PUCSI_GET_CONNECTOR_STATUS_IN, 
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
req.typenames: UCSI_GET_CONNECTOR_STATUS_IN, *PUCSI_GET_CONNECTOR_STATUS_IN
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	ucmucsispec.h
api_name: 
-	_UCSI_GET_CONNECTOR_STATUS_IN
product: Windows
targetos: Windows
ms.custom: RS5
---

# _UCSI_GET_CONNECTOR_STATUS_IN structure

## -description
Used in the GET_CONNECTOR_STATUS command. See Table 4-42 in [UCSI spec version 1.1](https://www.intel.com/content/dam/www/public/us/en/documents/technical-specifications/usb-type-c-ucsi-spec.pdf).

## -struct-fields

### -field ConnectorStatusChange
 
### -field ConnectorStatusChange.AsUInt16
 
### -field ConnectorStatusChange.ExternalSupplyChange
 
### -field ConnectorStatusChange.PowerOperationModeChange
 
### -field ConnectorStatusChange.SupportedProviderCapabilitiesChange
 
### -field ConnectorStatusChange.NegotiatedPowerLevelChange
 
### -field ConnectorStatusChange.PdResetComplete
 
### -field ConnectorStatusChange.SupportedCamChange
 
### -field ConnectorStatusChange.BatteryChargingStatusChange
 
### -field ConnectorStatusChange.ConnectorPartnerChange
 
### -field ConnectorStatusChange.PowerDirectionChange
 
### -field ConnectorStatusChange.ConnectChange
 
### -field ConnectorStatusChange.Error
 
### -field PowerOperationMode
 
### -field ConnectStatus
 
### -field PowerDirection
 
### -field ConnectorPartnerFlags
 
### -field ConnectorPartnerType
 
### -field RequestDataObject
 
### -field BatteryChargingStatus
 
### -field PowerBudgetLimitedReason
 
### -field bmPowerBudgetLimitedReason
 
### -field bmPowerBudgetLimitedReason.PowerBudgetLowered
 
### -field bmPowerBudgetLimitedReason.ReachingPowerBudgetLimit
 

## -remarks

## -see-also
