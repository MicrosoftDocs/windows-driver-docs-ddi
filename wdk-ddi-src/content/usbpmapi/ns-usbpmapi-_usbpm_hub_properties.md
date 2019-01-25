---
UID: NS:usbpmapi._USBPM_HUB_PROPERTIES
title: _USBPM_HUB_PROPERTIES (usbpmapi.h)
description: Properties of a connector hub.
ms.assetid: f5579381-05a0-42e2-890c-9970a94ca7b4
ms.date: 09/30/2018
ms.topic: struct
tech.root: usbref
ms.keywords: _USBPM_HUB_PROPERTIES, USBPM_HUB_PROPERTIES, *PUSBPM_HUB_PROPERTIES, 
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
req.typenames: USBPM_HUB_PROPERTIES, *PUSBPM_HUB_PROPERTIES
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	usbpmapi.h
api_name: 
-	USBPM_HUB_PROPERTIES
product: Windows
targetos: Windows
ms.custom: RS5
---

# _USBPM_HUB_PROPERTIES structure

## -description
Properties of a connector hub.

## -struct-fields

### -field ParentHubHandle
The handle of the parent hub of this hub. This value is NULL when this hub has no parent hub.
 
### -field HubHandle
The handle of this hub.
 
### -field ConnectorCount
The number of connectors on this hub.


## -remarks

## -see-also
