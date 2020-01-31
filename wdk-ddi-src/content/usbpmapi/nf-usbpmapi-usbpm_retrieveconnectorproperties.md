---
UID: NF:usbpmapi.UsbPm_RetrieveConnectorProperties
title: UsbPm_RetrieveConnectorProperties function (usbpmapi.h)
description: Retrieves the properties of a connector. The properties are static information that do not change during the lifecycle of a connector.
ms.assetid: 69060bba-873e-41ff-a00f-5632de227735
ms.date: 09/30/2018
f1_keywords:
 - "usbpmapi/UsbPm_RetrieveConnectorProperties"
ms.keywords: UsbPm_RetrieveConnectorProperties
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
- UsbPm_RetrieveConnectorProperties
product:
- Windows
targetos: Windows


ms.custom: RS5
---

# UsbPm_RetrieveConnectorProperties function


## -description

Retrieves the properties of a connector. The properties are static, which do not change during the lifecycle of a connector.

## -parameters

### -param ClientHandle
[In] The handle that the client driver received in a previous call to [**UsbPm_Register**](nf-usbpmapi-usbpm_register.md).

### -param ConnectorHandle
[In] The connector handle provided by Policy Manager when it calls the driver's implementation of [**EVT_USBPM_EVENT_CALLBACK**](nc-usbpmapi-evt_usbpm_event_callback.md). The handle is set in the **EventData.ConnectorStateChange.ConnectorHandle** member of the _Params_ value.

### -param ConnectorProperties
[Out] A pointer to a driver-provided [**USBPM_CONNECTOR_PROPERTIES**](ns-usbpmapi-_usbpm_connector_properties.md) structure that receives the connector properties. Initialize the structure by calling  [**USBPM_CONNECTOR_PROPERTIES_INIT**](nf-usbpmapi-usbpm_connector_properties_init.md).

## -returns
Returns STATUS_SUCCESS if the operation succeeds. Otherwise, returns an appropriate [NTSTATUS](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values) value.

## -remarks

## -see-also
[**UsbPm_Register**](nf-usbpmapi-usbpm_register.md)

[**EVT_USBPM_EVENT_CALLBACK**](nc-usbpmapi-evt_usbpm_event_callback.md)
