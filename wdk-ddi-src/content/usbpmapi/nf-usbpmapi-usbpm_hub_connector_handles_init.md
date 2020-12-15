---
UID: NF:usbpmapi.USBPM_HUB_CONNECTOR_HANDLES_INIT
title: USBPM_HUB_CONNECTOR_HANDLES_INIT function (usbpmapi.h)
description: Initializes a **USBPM_HUB_CONNECTOR_HANDLES** structure.
ms.date: 09/30/2018
keywords: ["USBPM_HUB_CONNECTOR_HANDLES_INIT function"]
ms.keywords: USBPM_HUB_CONNECTOR_HANDLES_INIT
tech.root: usbref
req.header: usbpmapi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr: 
req.kmdf-ver: 1.27
req.umdf-ver: 2.27
req.lib: UsbPmApi.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: RS5
f1_keywords:
 - USBPM_HUB_CONNECTOR_HANDLES_INIT
 - usbpmapi/USBPM_HUB_CONNECTOR_HANDLES_INIT
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - UsbPmApi.lib
api_name:
 - USBPM_HUB_CONNECTOR_HANDLES_INIT
---

# USBPM_HUB_CONNECTOR_HANDLES_INIT function


## -description

Initializes a [**USBPM_HUB_CONNECTOR_HANDLES**](ns-usbpmapi-_usbpm_hub_connector_handles.md) structure.

## -parameters

### -param HubConnectorHandles

[Out] A pointer to a [**USBPM_HUB_CONNECTOR_HANDLES**](ns-usbpmapi-_usbpm_hub_connector_handles.md) structure to initialize.

### -param ConnectorCount

[In] The number of connectors on this hub.

### -param ConnectorHandlesBuffer

[Out] A pointer to a connector handle array of all the connectors on this hub.

## -remarks

## -see-also

