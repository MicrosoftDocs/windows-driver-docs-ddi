---
UID: NC:ucxendpoint.EVT_UCX_ENDPOINT_GET_ISOCH_TRANSFER_PATH_DELAYS
title: EVT_UCX_ENDPOINT_GET_ISOCH_TRANSFER_PATH_DELAYS
author: windows-driver-content
description: UCX invokes this callback function to get information about transfer path delays for an isochronous endpoint.
old-location: buses\evt_ucx_endpoint_get_isoch_transfer_path_delays_.htm
old-project: usbref
ms.assetid: E400CCAE-8F0F-4814-8B63-EB4E116543A2
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: buses.evt_ucx_endpoint_get_isoch_transfer_path_delays_, EvtUcxEndpointGetIsochTransferPathDelays callback function [Buses], EvtUcxEndpointGetIsochTransferPathDelays, EVT_UCX_ENDPOINT_GET_ISOCH_TRANSFER_PATH_DELAYS, EVT_UCX_ENDPOINT_GET_ISOCH_TRANSFER_PATH_DELAYS, ucxendpoint/EvtUcxEndpointGetIsochTransferPathDelays
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Ucxendpoint.h
apiname:
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

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20EVT_UCX_ENDPOINT_GET_ISOCH_TRANSFER_PATH_DELAYS callback function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

