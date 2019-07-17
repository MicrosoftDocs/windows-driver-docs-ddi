---
UID: NF:usbpmapi.UsbPm_RetrieveConnectorState
title: UsbPm_RetrieveConnectorState function (usbpmapi.h)
description: Retrieves the current state of a connector. Unlike connector properties, state information is dynamic, which can change at runtime.
ms.assetid: dc7c8d73-70bc-4021-83b3-1519fab014fa
ms.date: 09/30/2018
ms.topic: function
f1_keywords:
 - "usbpmapi/UsbPm_RetrieveConnectorState"
ms.keywords: UsbPm_RetrieveConnectorState
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
- UsbPm_RetrieveConnectorState
product:
- Windows
targetos: Windows


ms.custom: RS5
---

# UsbPm_RetrieveConnectorState function


## -description

Retrieves the current state of a connector. Unlike connector properties, state information is dynamic, which can change at runtime.

## -parameters

### -param ClientHandle
[In] The handle that the client driver received in a previous call to [**UsbPm_Register**](nf-usbpmapi-usbpm_register.md).

### -param ConnectorHandle
[In] The connector handle provided by Policy Manager when it calls the driver's implementation of [**EVT_USBPM_EVENT_CALLBACK**](nc-usbpmapi-evt_usbpm_event_callback.md). The handle is set in the **EventData.ConnectorStateChange.ConnectorHandle** member of the _Params_ value.

### -param ConnectorState
[Out] A pointer to a driver-provided [**USBPM_CONNECTOR_STATE**](ns-usbpmapi-_usbpm_connector_state.md) structure that receives the connector state. Initialize the structure by calling  [**USBPM_CONNECTOR_STATE_INIT**](nf-usbpmapi-usbpm_connector_state_init.md).

## -returns
Returns STATUS_SUCCESS if the operation succeeds. Otherwise, returns an appropriate [NTSTATUS](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values) value.

## -remarks

## -see-also
[**UsbPm_Register**](nf-usbpmapi-usbpm_register.md)

[**EVT_USBPM_EVENT_CALLBACK**](nc-usbpmapi-evt_usbpm_event_callback.md)
