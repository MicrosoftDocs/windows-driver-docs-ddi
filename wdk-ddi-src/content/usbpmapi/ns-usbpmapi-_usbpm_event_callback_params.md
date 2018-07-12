---
UID: NS:usbpmapi._USBPM_EVENT_CALLBACK_PARAMS
title: _USBPM_EVENT_CALLBACK_PARAMS
author: windows-driver-content
description: Contains the details of the events related to changes in policy manager arrival/removal, hub arrival/removal or connector state change. 
ms.assetid: aa4fb292-590e-486a-af06-d6414892e68c
ms.author: windowsdriverdev
ms.date: 9/30/2018 
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _USBPM_EVENT_CALLBACK_PARAMS, USBPM_EVENT_CALLBACK_PARAMS, *PUSBPM_EVENT_CALLBACK_PARAMS, 
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
req.typenames: USBPM_EVENT_CALLBACK_PARAMS, *PUSBPM_EVENT_CALLBACK_PARAMS
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	usbpmapi.h
api_name: 
-	_USBPM_EVENT_CALLBACK_PARAMS
product: Windows
targetos: Windows
---

# _USBPM_EVENT_CALLBACK_PARAMS structure

## -description
Contains the details of the events related to changes in policy manager arrival/removal, hub arrival/removal or connector state change. This structure is used in the [**EVT_USBPM_EVENT_CALLBACK**](nc-usbpmapi-evt_usbpm_event_callback.md) callback function.

## -struct-fields

### -field EventType
A [**USBPM_EVENT_TYPE**](ne-usbpmapi-_usbpm_event_type.md)-type value that indicates the type of event.
 
### -field EventData
A union that contains the event-specific data. The client driver should set the event data in the inner structure related to the event.
 
### -field EventData.PolicyManagerArrival
Data about the Policy Manager arrival event.
 
### -field EventData.PolicyManagerArrival.AccessGranted
 
### -field EventData.HubArrivalRemoval
Data about the hub arrival or removal event.
 
### -field EventData.HubArrivalRemoval.HubHandle
The handle to the connector hub.
 
### -field EventData.ConnectorStateChange
Data about the connector state change event.
 
### -field EventData.ConnectorStateChange.ConnectorHandle
The handle to the connector.
 
### -field Context
The context which is provided by the client driver in a previous call to [**UsbPm_Register**](nf-usbpmapi-usbpm_register.md).  

## -remarks

## -see-also