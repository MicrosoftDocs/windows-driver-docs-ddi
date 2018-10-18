---
UID: NF:usbpmapi.USBPM_CONNECTOR_STATE_INIT
title: USBPM_CONNECTOR_STATE_INIT function
author: windows-driver-content
description: Initializes a **USBPM_CONNECTOR_STATE_INIT** structure.
ms.assetid: 2f0924ce-22d0-4bea-b368-6f5974441658
ms.date: 9/30/2018 
ms.topic: function
ms.keywords: USBPM_CONNECTOR_STATE_INIT
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
-	USBPM_CONNECTOR_STATE_INIT
product: Windows
targetos: Windows


---

# USBPM_CONNECTOR_STATE_INIT function


## -description

Initializes a [**USBPM_CONNECTOR_STATE_INIT**](ns-usbpmapi-_usbpm_connector_state.md) structure. The client driver must call this function before calling  [**UsbPm_RetrieveConnectorState**](nf-usbpmapi-usbpm_retrieveconnectorstate.md).

## -parameters

### -param ConnectorState
[Out] A pointer a [**USBPM_CONNECTOR_STATE_INIT**](ns-usbpmapi-_usbpm_connector_state.md) structure to initialize.

## -returns

## -remarks

## -see-also
