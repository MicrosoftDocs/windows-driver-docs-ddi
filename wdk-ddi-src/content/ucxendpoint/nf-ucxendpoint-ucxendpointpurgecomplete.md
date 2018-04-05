---
UID: NF:ucxendpoint.UcxEndpointPurgeComplete
title: UcxEndpointPurgeComplete function
author: windows-driver-content
description: Notifies UCX that a purge operation has been completed on the specified endpoint object.
old-location: buses\_ucxendpointpurgecomplete.htm
old-project: usbref
ms.assetid: F640D54B-277F-4382-9478-8A7AFAD242E2
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: UcxEndpointPurgeComplete, UcxEndpointPurgeComplete method [Buses], buses._ucxendpointpurgecomplete, ucxendpoint/UcxEndpointPurgeComplete
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	ucxendpoint.h
api_name:
-	UcxEndpointPurgeComplete
product:
- Windows
targetos: Windows
req.typenames: UCX_ENDPOINT_CHARACTERISTIC_TYPE
req.product: Windows 10 or later.
---

# UcxEndpointPurgeComplete function


## -description


Notifies UCX that a purge operation has been completed  on the specified endpoint object.


## -parameters




### -param Endpoint [in]

A handle to the endpoint object. The client driver retrieved the handle in a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt188039">UcxEndpointCreate</a>.


## -returns



This method does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt188039">UcxEndpointCreate</a>
 

 

