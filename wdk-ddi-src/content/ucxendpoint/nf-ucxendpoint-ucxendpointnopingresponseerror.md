---
UID: NF:ucxendpoint.UcxEndpointNoPingResponseError
title: UcxEndpointNoPingResponseError function (ucxendpoint.h)
description: Notifies UCX about a &#0034;No Ping Response&#0034; error for a transfer on the specified endpoint object.
old-location: buses\_ucxendpointnopingresponseerror.htm
tech.root: usbref
ms.assetid: 0EDC524E-12BB-49AD-AA12-A7D9CF7D2F9C
ms.date: 05/07/2018
ms.keywords: UcxEndpointNoPingResponseError, UcxEndpointNoPingResponseError method [Buses], buses._ucxendpointnopingresponseerror, ucxendpoint/UcxEndpointNoPingResponseError
ms.topic: function
f1_keywords:
 - "ucxendpoint/UcxEndpointNoPingResponseError"
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
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- ucxendpoint.h
api_name:
- UcxEndpointNoPingResponseError
product:
- Windows
targetos: Windows
req.typenames: 
---

# UcxEndpointNoPingResponseError function


## -description


Notifies UCX about a "No Ping Response" error for a transfer on
    the specified endpoint object


## -parameters




### -param Endpoint [in]

A handle to the endpoint object. The client driver retrieved the handle in a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxendpoint/nf-ucxendpoint-ucxendpointcreate">UcxEndpointCreate</a>.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxendpoint/nf-ucxendpoint-ucxendpointcreate">UcxEndpointCreate</a>
 

 

