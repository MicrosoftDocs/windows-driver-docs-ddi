---
UID: NE:usbpmapi._USBPM_EVENT_TYPE
title: _USBPM_EVENT_TYPE
author: windows-driver-content
description: Defines values for types of events.
ms.assetid: 71d061e8-92bb-4b83-9e77-c576163bb5a1
ms.date: 09/30/2018
ms.topic: enum
ms.keywords: _USBPM_EVENT_TYPE, USBPM_EVENT_TYPE, 
tech.root: usbref
req.header: usbpmapi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver: 1.27
req.umdf-ver: 2.27
req.ddi-compliance:
req.max-support:
req.typenames: USBPM_EVENT_TYPE
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	usbpmapi.h
api_name: 
-	USBPM_EVENT_TYPE
product: Windows
targetos: Windows
---

# _USBPM_EVENT_TYPE enumeration

## -description
Defines values for types of events. This enumeration is used in the [**EVT_USBPM_EVENT_CALLBACK**](nc-usbpmapi-evt_usbpm_event_callback.md) callback function. 

## -enum-fields

### -field UsbPmEventPolicyManagerArrival 
The Policy Manager has arrived. This is the first callback event after client registration. 

### -field UsbPmEventPolicyManagerRemoval 
 The Policy Manager has left.

### -field UsbPmEventHubArrival
A new connector hub has arrived.

### -field UsbPmEventHubRemoval 
A connector hub has been removed.

### -field UsbPmEventConnectorStateChange 
 The connector state has changed.

## -remarks

## -see-also
[**EVT_USBPM_EVENT_CALLBACK**](nc-usbpmapi-evt_usbpm_event_callback.md)

[**USBPM_EVENT_CALLBACK_PARAMS**](ns-usbpmapi-_usbpm_event_callback_params.md)
