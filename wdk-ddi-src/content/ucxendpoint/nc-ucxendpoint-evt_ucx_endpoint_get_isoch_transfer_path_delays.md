---
UID: NC:ucxendpoint.EVT_UCX_ENDPOINT_GET_ISOCH_TRANSFER_PATH_DELAYS
title: EVT_UCX_ENDPOINT_GET_ISOCH_TRANSFER_PATH_DELAYS
author: windows-driver-content
description: UCX invokes this callback function to get information about transfer path delays for an isochronous endpoint.
old-location: buses\evt_ucx_endpoint_get_isoch_transfer_path_delays_.htm
old-project: usbref
ms.assetid: E400CCAE-8F0F-4814-8B63-EB4E116543A2
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: EVT_UCX_ENDPOINT_GET_ISOCH_TRANSFER_PATH_DELAYS, EvtUcxEndpointGetIsochTransferPathDelays, EvtUcxEndpointGetIsochTransferPathDelays callback function [Buses], buses.evt_ucx_endpoint_get_isoch_transfer_path_delays_, ucxendpoint/EvtUcxEndpointGetIsochTransferPathDelays
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ucxendpoint.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ucxendpoint.h
api_name:
-	EvtUcxEndpointGetIsochTransferPathDelays
product: Windows
targetos: Windows
req.typenames: UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS_CHANGE_FLAGS
req.product: Windows 10 or later.
---

# EVT_UCX_ENDPOINT_GET_ISOCH_TRANSFER_PATH_DELAYS callback


## -description


UCX invokes this callback function to get information about transfer path delays for an isochronous endpoint. 


## -prototype


````
EVT_UCX_ENDPOINT_GET_ISOCH_TRANSFER_PATH_DELAYS EvtUcxEndpointGetIsochTransferPathDelays;

NTSTATUS EvtUcxEndpointGetIsochTransferPathDelays(
  _In_    UCXENDPOINT                              Endpoint,
  _Inout_ PUCX_ENDPOINT_ISOCH_TRANSFER_PATH_DELAYS UcxEndpointTransferPathDelays
)
{ ... }
````


## -parameters




### -param UcxEndpoint


### -param UcxEndpointTransferPathDelays [in, out]

A pointer to a <a href="..\ucxendpoint\ns-ucxendpoint-_ucx_endpoint_isoch_transfer_path_delays.md">UCX_ENDPOINT_ISOCH_TRANSFER_PATH_DELAYS</a> structure that contains transfer path delay values.


#### - Endpoint [in]

A handle to a UCXENDPOINT object that represents the isochronous endpoint for which the client driver receives the transfer path delays.


## -returns



If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it must return a status value for which NT_SUCCESS(status) equals FALSE.




## -remarks



The UCX client driver registers this callback function with the USB host controller extension (UCX) by calling the <a href="..\ucxendpoint\nf-ucxendpoint-ucxendpointcreate.md">UcxEndpointCreate</a>
 method.




## -see-also

<a href="..\usb\ns-usb-_urb_get_isoch_pipe_transfer_path_delays.md">_URB_GET_ISOCH_PIPE_TRANSFER_PATH_DELAYS</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/usbcon/usb-client-drivers-for-ma-usb">USB client drivers for Media-Agnostic (MA-USB)</a>



 

 


