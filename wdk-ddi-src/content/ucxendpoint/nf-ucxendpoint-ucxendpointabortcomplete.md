---
UID: NF:ucxendpoint.UcxEndpointAbortComplete
title: UcxEndpointAbortComplete function (ucxendpoint.h)
description: Notifies UCX that a transfer abort operation has been completed on the specified endpoint object.
old-location: buses\_ucxendpointabortcomplete.htm
tech.root: usbref
ms.assetid: 754BCC74-1EC2-429E-A711-E8958665A5A8
ms.date: 05/07/2018
keywords: ["UcxEndpointAbortComplete function"]
ms.keywords: UcxEndpointAbortComplete, UcxEndpointAbortComplete method [Buses], buses._ucxendpointabortcomplete, ucxendpoint/UcxEndpointAbortComplete
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
 - UcxEndpointAbortComplete
 - ucxendpoint/UcxEndpointAbortComplete
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - ucxendpoint.h
api_name:
 - UcxEndpointAbortComplete
---

# UcxEndpointAbortComplete function


## -description

Notifies UCX that a transfer abort operation has been completed  on the specified endpoint object.

## -parameters

### -param Endpoint 

[in]
A handle to the endpoint object. The client driver retrieved the handle in a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxendpoint/nf-ucxendpoint-ucxendpointcreate">UcxEndpointCreate</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxendpoint/nf-ucxendpoint-ucxendpointcreate">UcxEndpointCreate</a>

