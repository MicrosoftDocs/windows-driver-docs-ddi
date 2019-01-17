---
UID: NS:usbpmapi._USBPM_HUB_CONNECTOR_HANDLES
title: _USBPM_HUB_CONNECTOR_HANDLES
description: Stores the connector handles for all connectors on a hub.
ms.assetid: 09998d82-882c-4e6d-83ab-ee356198aff7
ms.date: 09/30/2018
ms.topic: struct
tech.root: usbref
ms.keywords: _USBPM_HUB_CONNECTOR_HANDLES, USBPM_HUB_CONNECTOR_HANDLES, *PUSBPM_HUB_CONNECTOR_HANDLES, 
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
req.typenames: USBPM_HUB_CONNECTOR_HANDLES, *PUSBPM_HUB_CONNECTOR_HANDLES
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	usbpmapi.h
api_name: 
-	_USBPM_HUB_CONNECTOR_HANDLES
product: Windows
targetos: Windows
ms.custom: RS5
---

# _USBPM_HUB_CONNECTOR_HANDLES structure

## -description
Stores the connector handles for all connectors on a hub. This structure is used in the [**UsbPm_RetrieveHubConnectorHandles**](nf-usbpmapi-usbpm_retrievehubconnectorhandles.md) function.

## -struct-fields

### -field HubHandle
The handle of this hub.
 
### -field ConnectorCount
 The number of connectors on this hub.
 
### -field ConnectorHandles
A pointer to a connector handle array of all the connectors on this hub. The array is allocated by the Policy Manager is valid during the life time of the hub. The client driver must not change the array or release the array after use. 

## -remarks

## -see-also
