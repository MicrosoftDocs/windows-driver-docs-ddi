---
UID: NS:usbpmapi._USBPM_CONNECTOR_PROPERTIES
title: _USBPM_CONNECTOR_PROPERTIES (usbpmapi.h)
description: Describes the properties of a connector.
ms.assetid: f07a2985-d569-4fe2-9a37-c95e7d664d28
ms.date: 09/30/2018
ms.topic: struct
tech.root: usbref
ms.keywords: _USBPM_CONNECTOR_PROPERTIES, USBPM_CONNECTOR_PROPERTIES, *PUSBPM_CONNECTOR_PROPERTIES, 
req.header: usbpmapi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver: 1.27
req.umdf-ver: 2.27
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: USBPM_CONNECTOR_PROPERTIES, *PUSBPM_CONNECTOR_PROPERTIES
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	usbpmapi.h
api_name: 
-	USBPM_CONNECTOR_PROPERTIES
product: Windows
targetos: Windows
ms.custom: RS5
---

# _USBPM_CONNECTOR_PROPERTIES structure

## -description

Describes the properties of a connector. This structure is used in the [**UsbPm_RetrieveCoonnectorProperties**](nf-usbpmapi-usbpm_retrieveconnectorproperties.md) call.

## -struct-fields

### -field ConnectorHandle
A handle of this connector.
 
### -field ParentHubHandle
The handle of the parent hub to which this connector belongs.
 
### -field ConnectorId
A system-assigned identifier.
 
### -field SupportedTypeCOperatingModes
A bitwise OR of the values defined in the [**USBC_TYPEC_OPERATING_MODE**](../usbctypes/ne-usbctypes-_usbc_typec_operating_mode.md) enumeration.

### -field SupportedTypeCSourceCurrentAdvertisements
A bitwise OR of the values defined in the [**USBC_CURRENT**](../usbctypes/ne-usbctypes-_usbc_current.md) enumeration.
 
### -field IsTypeCAudioAccessorySupported
Indicates whether audio accessories are supported by this connector.
 
### -field IsPdSupported
Indicates whether PD is supported on this connector.
 
### -field SupportedPowerRoles
A bitwise OR of the values defined in the [**USBC_POWER_ROLE**](../usbctypes/ne-usbctypes-_usbc_power_role.md) enumeration.

## -remarks

## -see-also
