---
UID: NF:usbpmapi.UsbPm_RetrieveHubConnectorHandles
title: UsbPm_RetrieveHubConnectorHandles function (usbpmapi.h)
description: Retrieves connector handles for all connectors of a hub. 
ms.assetid: 0c55cc80-ab9d-4302-b350-7c673f9d4abf
ms.date: 09/30/2018
ms.topic: function
f1_keywords:
 - "usbpmapi/UsbPm_RetrieveHubConnectorHandles"
ms.keywords: UsbPm_RetrieveHubConnectorHandles
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
topic_type: 
- apiref
api_type: 
- LibDef
api_location: 
- UsbPmApi.lib
api_name: 
- UsbPm_RetrieveHubConnectorHandles
product:
- Windows
targetos: Windows


ms.custom: RS5
---

# UsbPm_RetrieveHubConnectorHandles function


## -description
Retrieves connector handles for all connectors of a hub.


## -parameters

### -param ClientHandle
[In] The handle that the client driver received in a previous call to [**UsbPm_Register**](nf-usbpmapi-usbpm_register.md).
### -param HubHandle
[In] The handle to the hub.
### -param HubConnectorHandles
[Out] A pointer to a [**USBPM_HUB_CONNECTOR_HANDLES**](nf-usbpmapi-usbpm_retrievehubconnectorhandles.md) structures that contains the connector handles. Intialize this structure by calling [**USBPM_HUB_CONNECTOR_HANDLES_INIT**](nf-usbpmapi-usbpm_hub_connector_handles_init.md). The array is allocated by the Policy Manager is valid during the life time of the hub. The client driver must not change the array or release the array after use.  

## -returns
This function returns NTSTATUS.
## -remarks

## -see-also
