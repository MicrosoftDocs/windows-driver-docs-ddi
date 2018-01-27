---
UID: NC:ucxendpoint.EVT_UCX_ENDPOINT_PURGE
title: EVT_UCX_ENDPOINT_PURGE
author: windows-driver-content
description: The client driver's implementation that completes all outstanding I/O requests on the endpoint.
old-location: buses\evt_ucx_endpoint_purge.htm
old-project: usbref
ms.assetid: e4ceb597-ebfe-4016-ba83-e5246a70f566
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: buses.evt_ucx_endpoint_purge, EvtUcxEndpointPurge callback function [Buses], EvtUcxEndpointPurge, EVT_UCX_ENDPOINT_PURGE, EVT_UCX_ENDPOINT_PURGE, ucxendpoint/EvtUcxEndpointPurge, PEVT_UCX_ENDPOINT_PURGE callback function pointer [Buses], PEVT_UCX_ENDPOINT_PURGE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ucxendpoint.h
req.include-header: Ucxclass.h, Ucxendpoint.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: DISPATCH_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	ucxendpoint.h
apiname: 
-	PEVT_UCX_ENDPOINT_PURGE
product: Windows
targetos: Windows
req.typenames: UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS_CHANGE_FLAGS
req.product: Windows 10 or later.
---

# EVT_UCX_ENDPOINT_PURGE callback


## -description


The client driver's implementation that completes all outstanding I/O requests on the endpoint.


## -prototype


````
EVT_UCX_ENDPOINT_PURGE EvtUcxEndpointPurge;

VOID EvtUcxEndpointPurge(
  _In_ UCXCONTROLLER UcxController,
  _In_ UCXENDPOINT   Endpoint
)
{ ... }

typedef EVT_UCX_ENDPOINT_PURGE PEVT_UCX_ENDPOINT_PURGE;
````


## -parameters




### -param UcxController [in]

 A handle to the UCX controller that the client driver received in a previous call to  the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a> method.


### -param UcxEndpoint






#### - Endpoint [in]

A handle to a UCXENDPOINT object that represents the endpoint.


## -returns


This callback function does not return a value.



## -remarks


The UCX client driver registers this callback function with the USB host controller extension (UCX) by calling the <a href="..\ucxendpoint\nf-ucxendpoint-ucxendpointcreate.md">UcxEndpointCreate</a>
 method.

Typically, this function calls <a href="..\wdfio\nf-wdfio-wdfioqueuepurge.md">WdfIoQueuePurge</a>.

After UCX calls this function, the client driver fails subsequent I/O requests until UCX calls the client driver's <a href="..\ucxendpoint\nc-ucxendpoint-evt_ucx_endpoint_start.md">EVT_UCX_ENDPOINT_START</a> callback function.



## -see-also

<a href="..\wdfio\nf-wdfio-wdfioqueuepurge.md">WdfIoQueuePurge</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20EVT_UCX_ENDPOINT_PURGE callback function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

