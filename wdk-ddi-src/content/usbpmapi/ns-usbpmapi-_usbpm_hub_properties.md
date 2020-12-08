---
UID: NS:usbpmapi._USBPM_HUB_PROPERTIES
title: _USBPM_HUB_PROPERTIES (usbpmapi.h)
description: Properties of a connector hub.
ms.date: 09/30/2018
keywords: ["USBPM_HUB_PROPERTIES structure"]
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
targetos: Windows
ms.custom: RS5
f1_keywords:
 - _USBPM_HUB_PROPERTIES
 - usbpmapi/_USBPM_HUB_PROPERTIES
 - PUSBPM_HUB_PROPERTIES
 - usbpmapi/PUSBPM_HUB_PROPERTIES
 - USBPM_HUB_PROPERTIES
 - usbpmapi/USBPM_HUB_PROPERTIES
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - usbpmapi.h
api_name:
 - USBPM_HUB_PROPERTIES
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

