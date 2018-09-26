---
UID: NF:usbpmapi.USBPM_ASSIGN_CONNECTOR_POWER_LEVEL_PARAMS_INIT
title: USBPM_ASSIGN_CONNECTOR_POWER_LEVEL_PARAMS_INIT function
author: windows-driver-content
description: Initializes a **USBPM_ASSIGN_CONNECTOR_POWER_LEVEL_PARAMS** structure.
ms.assetid: b95baed4-5f1d-4e0c-a6eb-a68ee5c462a5
ms.author: windowsdriverdev
ms.date: 9/30/2018 
ms.topic: function
ms.keywords: USBPM_ASSIGN_CONNECTOR_POWER_LEVEL_PARAMS_INIT
tech.root: usbref
req.header: usbpmapi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver: 1.27
req.umdf-ver: 2.27
req.lib: 
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	usbpmapi.h
api_name: 
-	USBPM_ASSIGN_CONNECTOR_POWER_LEVEL_PARAMS_INIT
product: Windows
targetos: Windows


---

# USBPM_ASSIGN_CONNECTOR_POWER_LEVEL_PARAMS_INIT function


## -description

Initializes a [**USBPM_ASSIGN_CONNECTOR_POWER_LEVEL_PARAMS**](nf-usbpmapi-usbpm_assign_connector_power_level_params_init.md) structure. The client driver must call this function before calling [**UsbPm_AssignConnectorPowerLevel**](nf-usbpmapi-usbpm_assignconnectorpowerlevel.md).

## -parameters

### -param Params
[Out] A pointer to a [**USBPM_ASSIGN_CONNECTOR_POWER_LEVEL_PARAMS**](nf-usbpmapi-usbpm_assign_connector_power_level_params_init.md) structure to initialize.
### -param PowerRole
[In] The USB Type-C power role of the connector to set. The values are defined in the [**USBC_POWER_ROLE**](../usbctypes/ne-usbctypes-_usbc_power_role.md) enumeration.
### -param Format
[In] The USB Type-C format, defined in [**USBPM_ASSIGN_POWER_LEVEL_PARAMS_FORMAT**](ne-usbpmapi-_usbpm_assign_power_level_params_format.md)

## -returns

## -remarks

## -see-also