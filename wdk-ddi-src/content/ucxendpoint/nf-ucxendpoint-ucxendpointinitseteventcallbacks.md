---
UID: NF:ucxendpoint.UcxEndpointInitSetEventCallbacks
title: UcxEndpointInitSetEventCallbacks function
author: windows-driver-content
description: Initializes a UCXENDPOINT_INIT structure with client driver's event callback functions related to endpoints on the device.
old-location: buses\_ucxendpointinitseteventcallbacks.htm
old-project: usbref
ms.assetid: 4F5FB073-0803-4112-964E-431930D14A88
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: UcxEndpointInitSetEventCallbacks, UcxEndpointInitSetEventCallbacks method [Buses], buses._ucxendpointinitseteventcallbacks
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	ucxendpoint.h
api_name:
-	UcxEndpointInitSetEventCallbacks
product:
- Windows
targetos: Windows
req.typenames: 
---

# UcxEndpointInitSetEventCallbacks function


## -description


Initializes a <b>UCXENDPOINT_INIT</b> structure with client driver's event callback functions related to endpoints on the device.


## -parameters




### -param EndpointInit

A pointer to a <b>UCXENDPOINT_INIT</b> structure that UCX passes when it invokes the client driver's <a href="https://msdn.microsoft.com/library/windows/hardware/mt187843">EVT_UCX_USBDEVICE_ENDPOINT_ADD</a> event callback function. 


### -param EventCallbacks

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt188063">UCX_ENDPOINT_EVENT_CALLBACKS</a> structure that contains function pointer to event callback functions related to the endpoint. The  the client driver initializes the structure  by calling <a href="https://msdn.microsoft.com/library/windows/hardware/mt188064">UCX_ENDPOINT_EVENT_CALLBACKS_INIT</a>.


## -returns



This method does not return a value.




## -remarks



The client driver calls this method to set function pointers to its event callback functions just before calling <a href="https://msdn.microsoft.com/library/windows/hardware/mt188039">UcxEndpointCreate</a> to create an endpoint.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt188063">UCX_ENDPOINT_EVENT_CALLBACKS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt188039">UcxEndpointCreate</a>
 

 

