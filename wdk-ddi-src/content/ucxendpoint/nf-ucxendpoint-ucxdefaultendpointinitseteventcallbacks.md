---
UID: NF:ucxendpoint.UcxDefaultEndpointInitSetEventCallbacks
title: UcxDefaultEndpointInitSetEventCallbacks function
author: windows-driver-content
description: Initializes a UCXENDPOINT_INIT structure with client driver's event callback functions related to the default endpoint.
old-location: buses\_ucxdefaultendpointinitseteventcallbacks.htm
old-project: usbref
ms.assetid: 5CE3F1B5-9C6D-4061-ADF4-B388C81C0674
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: buses._ucxdefaultendpointinitseteventcallbacks, UcxDefaultEndpointInitSetEventCallbacks, UcxDefaultEndpointInitSetEventCallbacks method [Buses]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ucxendpoint.h
req.include-header: Ucxclass.h, Ucxendpoint.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	ucxendpoint.h
apiname:
-	UcxDefaultEndpointInitSetEventCallbacks
product: Windows
targetos: Windows
req.typenames: UCX_ENDPOINT_CHARACTERISTIC_TYPE
req.product: Windows 10 or later.
---

# UcxDefaultEndpointInitSetEventCallbacks function


## -description


Initializes a <b>UCXENDPOINT_INIT</b> structure with client driver's event callback functions related to the default endpoint.


## -syntax


````
void UcxDefaultEndpointInitSetEventCallbacks(
   PUCXENDPOINT_INIT             EndpointInit,
   PUCX_ENDPOINT_EVENT_CALLBACKS EventCallbacks
);
````


## -parameters




### -param EndpointInit

A pointer to a <b>UCXENDPOINT_INIT</b> structure that UCX passes when it invokes the client driver's <a href="..\ucxusbdevice\nc-ucxusbdevice-evt_ucx_usbdevice_default_endpoint_add.md">EVT_UCX_USBDEVICE_DEFAULT_ENDPOINT_ADD</a> event callback function. 


### -param EventCallbacks

A pointer to a <a href="..\ucxendpoint\ns-ucxendpoint-_ucx_endpoint_event_callbacks.md">UCX_ENDPOINT_EVENT_CALLBACKS</a> structure that contains function pointer to event callback functions related to the endpoint. The  the client driver initializes the structure  by calling <a href="..\ucxendpoint\nf-ucxendpoint-ucx_endpoint_event_callbacks_init.md">UCX_ENDPOINT_EVENT_CALLBACKS_INIT</a>.


## -returns


This method does not return a value.



## -remarks


The client driver calls this method to set function pointers to its event callback functions just before calling <a href="..\ucxendpoint\nf-ucxendpoint-ucxendpointcreate.md">UcxEndpointCreate</a> to create the default endpoint.



## -see-also

<a href="..\ucxendpoint\nf-ucxendpoint-ucxendpointcreate.md">UcxEndpointCreate</a>

<a href="..\ucxusbdevice\nc-ucxusbdevice-evt_ucx_usbdevice_default_endpoint_add.md">EVT_UCX_USBDEVICE_DEFAULT_ENDPOINT_ADD</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UcxDefaultEndpointInitSetEventCallbacks method%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

