---
UID: NC:ucxroothub.EVT_UCX_ROOTHUB_INTERRUPT_TX
title: EVT_UCX_ROOTHUB_INTERRUPT_TX (ucxroothub.h)
description: The client driver's implementation that UCX calls when it receives a request for information about changed ports.
old-location: buses\evt_ucx_roothub_interrupt_tx.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["EVT_UCX_ROOTHUB_INTERRUPT_TX callback function"]
ms.keywords: EVT_UCX_ROOTHUB_INTERRUPT_TX, EVT_UCX_ROOTHUB_INTERRUPT_TX callback, EvtUcxInterruptTransferTx, EvtUcxInterruptTransferTx callback function [Buses], PEVT_UCX_ROOTHUB_INTERRUPT_TX, PEVT_UCX_ROOTHUB_INTERRUPT_TX callback function pointer [Buses], buses.evt_ucx_roothub_interrupt_tx, ucxroothub/EvtUcxInterruptTransferTx
req.header: ucxroothub.h
req.include-header: Ucxclass.h
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
 - EVT_UCX_ROOTHUB_INTERRUPT_TX
 - ucxroothub/EVT_UCX_ROOTHUB_INTERRUPT_TX
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ucxroothub.h
api_name:
 - EVT_UCX_ROOTHUB_INTERRUPT_TX
---

# EVT_UCX_ROOTHUB_INTERRUPT_TX callback function


## -description

The client driver's implementation that UCX calls when it receives a request for information about changed ports.

## -parameters

### -param UcxRootHub [in]


A handle to a UCX object that represents the root hub.

### -param Request [in]


Contains the <a href="/windows-hardware/drivers/ddi/usb/ns-usb-_urb">URB</a> for the root hub interrupt transfer request.

## -remarks

The UCX client driver registers this callback function with the USB host controller extension (UCX) by calling the <a href="/previous-versions/windows/hardware/drivers/mt188048(v=vs.85)">UcxRootHubCreate</a>
 method.

 The <i>Request</i> parameter contains a buffer in which each bit corresponds to a root
    hub port, with the first bit corresponding to the first port.  The
    client driver sets the corresponding bit if any port has changed, and then completes the request.

The client driver returns completion status in <i>Request</i>.


#### Examples

This snippet shows how the callback extracts the root hub interrupt transfer request.


```
        WDF_REQUEST_PARAMETERS_INIT(&wdfRequestParams);
        WdfRequestGetParameters(WdfRequest, &wdfRequestParams);

        urb = (PURB)wdfRequestParams.Parameters.Others.Arg1;
        transferBuffer = urb->UrbBulkOrInterruptTransfer.TransferBuffer;
        transferBufferLength = urb->UrbBulkOrInterruptTransfer.TransferBufferLength;

```

