---
UID: NF:ucxendpoint.UcxEndpointSetWdfIoQueue
title: UcxEndpointSetWdfIoQueue function
author: windows-driver-content
description: Sets a framework queue on the specified endpoint object.
old-location: buses\_ucxendpointsetwdfioqueue.htm
old-project: usbref
ms.assetid: DC23B286-8A52-4642-B345-D76802C83C55
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UcxEndpointSetWdfIoQueue, UcxEndpointSetWdfIoQueue method [Buses], buses._ucxendpointsetwdfioqueue
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
-	UcxEndpointSetWdfIoQueue
product: Windows
targetos: Windows
req.typenames: UCX_ENDPOINT_CHARACTERISTIC_TYPE
req.product: Windows 10 or later.
---

# UcxEndpointSetWdfIoQueue function


## -description


Sets a framework queue  on the specified endpoint object.


## -syntax


````
void UcxEndpointSetWdfIoQueue(
  [in] UCXENDPOINT Endpoint,
  [in] WDFQUEUE    WdfQueue
);
````


## -parameters




### -param Endpoint [in]

A handle to the endpoint object. The client driver retrieved the handle in a previous call to <a href="..\ucxendpoint\nf-ucxendpoint-ucxendpointcreate.md">UcxEndpointCreate</a>.


### -param WdfQueue [in]

A handle to the framework queue object to set on the endpoint.


## -returns



This method does not return a value.




## -remarks



This routine can only get  called from <a href="..\ucxusbdevice\nc-ucxusbdevice-evt_ucx_usbdevice_endpoint_add.md">EVT_UCX_USBDEVICE_ENDPOINT_ADD</a> and <a href="..\ucxusbdevice\nc-ucxusbdevice-evt_ucx_usbdevice_default_endpoint_add.md">EVT_UCX_USBDEVICE_DEFAULT_ENDPOINT_ADD</a>
     callback functions.
    The client driver must call this routine only once for each endpoint.

For a code example, see <a href="..\ucxusbdevice\nc-ucxusbdevice-evt_ucx_usbdevice_endpoint_add.md">EVT_UCX_USBDEVICE_ENDPOINT_ADD</a>.




## -see-also

<a href="..\ucxendpoint\nf-ucxendpoint-ucxendpointcreate.md">UcxEndpointCreate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UcxEndpointSetWdfIoQueue method%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

