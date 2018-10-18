---
UID: NF:usbpmapi.UsbPm_AssignConnectorPowerLevel
title: UsbPm_AssignConnectorPowerLevel function
author: windows-driver-content
description: Attempts a PD contract renegotiation with the specified voltage/current/power value.
ms.assetid: 92f98419-fa13-44be-9546-939958232033
ms.date: 9/30/2018 
ms.topic: function
ms.keywords: UsbPm_AssignConnectorPowerLevel
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
-	UsbPm_AssignConnectorPowerLevel
product: Windows
targetos: Windows


---

# UsbPm_AssignConnectorPowerLevel function


## -description

Attempts a PD contract renegotiation with the specified voltage/current/power value.

## -parameters

### -param ClientHandle
[In] The handle that the client driver received in a previous call to [**UsbPm_Register**](nf-usbpmapi-usbpm_register.md).

### -param ConnectorHandle
[In] The connector handle provided by Policy Manager when it calls the driver's implementation of [**EVT_USBPM_EVENT_CALLBACK**](nc-usbpmapi-evt_usbpm_event_callback.md). The handle is set in the **EventData.ConnectorStateChange.ConnectorHandle** member of the _Params_ value.

### -param Params
[In] A pointer to a driver-provided [**USBPM_ASSIGN_CONNECTOR_POWER_LEVEL_PARAMS**](ns-usbpmapi-_usbpm_assign_connector_power_level_params.md) structure that contains the voltage/current/power value to negotiate. Initialize the structure by calling [**USBPM_ASSIGN_CONNECTOR_POWER_LEVEL_PARAMS_INIT**](nf-usbpmapi-usbpm_assign_connector_power_level_params_init.md).

Specifying 0 as the voltage/current/power value for a connector in power sink role  causes the connector to stop charging.

## -returns
Returns STATUS_SUCCESS if the operation succeeds. Otherwise, returns an appropriate [NTSTATUS](https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505) value.

## -remarks

The negotiated settings are persistent only as long as the port partner is attached, and is  discarded when the port partner is detached. The client driver is required to call this function based on the current connector state, without assuming the previous setting.  

If this call succeeds, the request was been accepted but PD contract renegotiation might not be complete. The result of PD contract renegotiation can be either success or failure.

As a result of successful PD contract renegotiation, **EVT_USBPM_EVENT_CALLBACK** is invoked with a connector state change event. If PD contract renegotiation request fails, the callback function is not invoked. For example, the request gets rejected by the partner, or is no longer valid because the connector state has changed.  
In Windows 10, version 1809, the driver can only call this function with the power role of UsbCPowerRoleSink and when a partner is attached to the connector.

## -see-also
[**UsbPm_Register**](nf-usbpmapi-usbpm_register.md)

[**EVT_USBPM_EVENT_CALLBACK**](nc-usbpmapi-evt_usbpm_event_callback.md)
