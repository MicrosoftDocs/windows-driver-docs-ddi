---
UID: NF:ucxendpoint.UcxEndpointPurgeComplete
title: UcxEndpointPurgeComplete function (ucxendpoint.h)
description: Notifies UCX that a purge operation has been completed on the specified endpoint object.
old-location: buses\_ucxendpointpurgecomplete.htm
tech.root: usbref
ms.assetid: F640D54B-277F-4382-9478-8A7AFAD242E2
ms.date: 05/07/2018
keywords: ["UcxEndpointPurgeComplete function"]
ms.keywords: UcxEndpointPurgeComplete, UcxEndpointPurgeComplete method [Buses], buses._ucxendpointpurgecomplete, ucxendpoint/UcxEndpointPurgeComplete
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
targetos: Windows
req.typenames: 
f1_keywords:
 - UcxEndpointPurgeComplete
 - ucxendpoint/UcxEndpointPurgeComplete
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - ucxendpoint.h
api_name:
 - UcxEndpointPurgeComplete
---

# UcxEndpointPurgeComplete function


## -description

Notifies UCX that a purge operation has been completed  on the specified endpoint object.

## -parameters

### -param Endpoint 

[in]
A handle to the endpoint object. The client driver retrieved the handle in a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxendpoint/nf-ucxendpoint-ucxendpointcreate">UcxEndpointCreate</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxendpoint/nf-ucxendpoint-ucxendpointcreate">UcxEndpointCreate</a>

