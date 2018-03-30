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


## -parameters




### -param Endpoint [in]

A handle to the endpoint object. The client driver retrieved the handle in a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt188039">UcxEndpointCreate</a>.


### -param WdfQueue [in]

A handle to the framework queue object to set on the endpoint.


## -returns



This method does not return a value.




## -remarks



This routine can only get  called from <a href="https://msdn.microsoft.com/library/windows/hardware/mt187843">EVT_UCX_USBDEVICE_ENDPOINT_ADD</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/mt187839">EVT_UCX_USBDEVICE_DEFAULT_ENDPOINT_ADD</a>
     callback functions.
    The client driver must call this routine only once for each endpoint.

For a code example, see <a href="https://msdn.microsoft.com/library/windows/hardware/mt187843">EVT_UCX_USBDEVICE_ENDPOINT_ADD</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt188039">UcxEndpointCreate</a>
 

 

