---
UID: NC:ucxendpoint.EVT_UCX_ENDPOINT_OK_TO_CANCEL_TRANSFERS
title: EVT_UCX_ENDPOINT_OK_TO_CANCEL_TRANSFERS (ucxendpoint.h)
description: The client driver's implementation that UCX calls to notify the controller driver that it can complete cancelled transfers on the endpoint.
old-location: buses\evt_ucx_endpoint_ok_to_cancel_transfers.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["EVT_UCX_ENDPOINT_OK_TO_CANCEL_TRANSFERS callback function"]
ms.keywords: EVT_UCX_ENDPOINT_OK_TO_CANCEL_TRANSFERS, EVT_UCX_ENDPOINT_OK_TO_CANCEL_TRANSFERS callback, EvtUcxEndpointOkToCancelTransfers, EvtUcxEndpointOkToCancelTransfers callback function [Buses], PEVT_UCX_ENDPOINT_OK_TO_CANCEL_TRANSFERS, PEVT_UCX_ENDPOINT_OK_TO_CANCEL_TRANSFERS callback function pointer [Buses], buses.evt_ucx_endpoint_ok_to_cancel_transfers, ucxendpoint/EvtUcxEndpointOkToCancelTransfers
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
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_UCX_ENDPOINT_OK_TO_CANCEL_TRANSFERS
 - ucxendpoint/EVT_UCX_ENDPOINT_OK_TO_CANCEL_TRANSFERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ucxendpoint.h
api_name:
 - EVT_UCX_ENDPOINT_OK_TO_CANCEL_TRANSFERS
---

# EVT_UCX_ENDPOINT_OK_TO_CANCEL_TRANSFERS callback function


## -description

The client driver's implementation that UCX calls to notify the controller driver that it can complete cancelled transfers on the
    endpoint.

## -parameters

### -param UcxEndpoint

#### - Endpoint [in]

A handle to a UCXENDPOINT object that represents the endpoint.

## -remarks

The UCX client driver registers this callback function with the USB host controller extension (UCX) by calling the [UcxEndpointCreate](./nf-ucxendpoint-ucxendpointcreate.md) method.

Before completing the URB associated with the transfer, the client driver calls [UcxEndpointNeedToCancelTransfers](./nf-ucxendpoint-ucxendpointneedtocanceltransfers.md) and then waits for UCX to call this function. Then the client driver can complete the URB with **STATUS_CANCELLED**.

> [!NOTE]
> If GUID_USB_CAPABILITY_CLEAR_TT_BUFFER_ON_ASYNC_TRANSFER_CANCEL capability is supported, the hub driver may send a control transfer to clear the TT (Transaction Translator) buffer before UCX calls this function.

