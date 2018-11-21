---
UID: NF:usbpmapi.UsbPm_RetrieveHubProperties
title: UsbPm_RetrieveHubProperties function
author: windows-driver-content
description: Retrieves the properties of a hub. Properties are static information that do not change during the lifecycle of a hub.
ms.assetid: 341977b0-e13f-431e-8b11-5407662bdb8e
ms.date: 09/30/2018
ms.topic: function
ms.keywords: UsbPm_RetrieveHubProperties
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
-	apiref
api_type: 
-	LibDef
api_location: 
-	UsbPmApi.lib
api_name: 
-	UsbPm_RetrieveHubProperties
product: Windows
targetos: Windows


ms.custom: RS5
---

# UsbPm_RetrieveHubProperties function


## -description

Retrieves the properties of a hub. The properties are static, which do not change during the lifecycle of a hub.

## -parameters

### -param ClientHandle
[In] The handle that the client driver received in a previous call to [**UsbPm_Register**](nf-usbpmapi-usbpm_register.md).

### -param HubHandle
[In] The hub handle provided by Policy Manager when it calls the driver's implementation of [**EVT_USBPM_EVENT_CALLBACK**](nc-usbpmapi-evt_usbpm_event_callback.md). The handle is set in the **EventData.HubArrivalRemoval.HubHandle** member of the _Params_ value. 

### -param HubProperties
[Out] A pointer to a driver-provided [**USBPM_HUB_PROPERTIES**](ns-usbpmapi-_usbpm_hub_properties.md) structure that receives the hub properties. Initialize the structure by calling  [**USBPM_HUB_PROPERTIES_INIT**](nf-usbpmapi-usbpm_hub_properties_init.md).

## -returns

Returns STATUS_SUCCESS if the operation succeeds. Otherwise, returns an appropriate [NTSTATUS](https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505) value.


## -remarks



## -see-also
[**UsbPm_Register**](nf-usbpmapi-usbpm_register.md)

[**EVT_USBPM_EVENT_CALLBACK**](nc-usbpmapi-evt_usbpm_event_callback.md)
