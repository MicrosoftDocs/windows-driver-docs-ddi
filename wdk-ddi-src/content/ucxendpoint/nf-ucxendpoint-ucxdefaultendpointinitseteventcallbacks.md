---
UID: NF:ucxendpoint.UcxDefaultEndpointInitSetEventCallbacks
title: UcxDefaultEndpointInitSetEventCallbacks function (ucxendpoint.h)
description: Initializes a UCXENDPOINT_INIT structure with client driver's event callback functions related to the default endpoint.
old-location: buses\_ucxdefaultendpointinitseteventcallbacks.htm
tech.root: usbref
ms.assetid: 5CE3F1B5-9C6D-4061-ADF4-B388C81C0674
ms.date: 05/07/2018
ms.keywords: UcxDefaultEndpointInitSetEventCallbacks, UcxDefaultEndpointInitSetEventCallbacks method [Buses], buses._ucxdefaultendpointinitseteventcallbacks
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
-	UcxDefaultEndpointInitSetEventCallbacks
product:
- Windows
targetos: Windows
req.typenames: 
---

# UcxDefaultEndpointInitSetEventCallbacks function


## -description


Initializes a <b>UCXENDPOINT_INIT</b> structure with client driver's event callback functions related to the default endpoint.


## -parameters




### -param EndpointInit

A pointer to a <b>UCXENDPOINT_INIT</b> structure that UCX passes when it invokes the client driver's <a href="https://msdn.microsoft.com/library/windows/hardware/mt187839">EVT_UCX_USBDEVICE_DEFAULT_ENDPOINT_ADD</a> event callback function. 


### -param EventCallbacks

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt188063">UCX_ENDPOINT_EVENT_CALLBACKS</a> structure that contains function pointer to event callback functions related to the endpoint. The  the client driver initializes the structure  by calling <a href="https://msdn.microsoft.com/library/windows/hardware/mt188064">UCX_ENDPOINT_EVENT_CALLBACKS_INIT</a>.


## -returns



This method does not return a value.




## -remarks



The client driver calls this method to set function pointers to its event callback functions just before calling <a href="https://msdn.microsoft.com/library/windows/hardware/mt188039">UcxEndpointCreate</a> to create the default endpoint.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt187839">EVT_UCX_USBDEVICE_DEFAULT_ENDPOINT_ADD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt188039">UcxEndpointCreate</a>
 

 

