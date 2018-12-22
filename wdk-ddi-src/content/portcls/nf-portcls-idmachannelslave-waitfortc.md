---
UID: NF:portcls.IDmaChannelSlave.WaitForTC
title: IDmaChannelSlave::WaitForTC
description: The WaitForTC method waits for the DMA-transfer terminal count to complete, or it times out if the time-out interval expires.
tech.root: audio
ms.assetid: 9e022d50-5bdd-4eb9-a6b4-86c93eca8527
ms.author: windowsdriverdev
ms.date: 10/30/2018
ms.topic: method
ms.keywords: IDmaChannelSlave::WaitForTC, WaitForTC, IDmaChannelSlave.WaitForTC, IDmaChannelSlave::WaitForTC, IDmaChannelSlave.WaitForTC
req.header: portcls.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: PASSIVE_LEVEL (See Remarks section.)
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
 - apiref
api_type: 
 - COM
api_location: 
 - portcls.h
api_name: 
 - IDmaChannelSlave.WaitForTC
product: 
 - Windows
targetos: Windows

---

# IDmaChannelSlave::WaitForTC


## -description

The WaitForTC method waits for the DMA-transfer terminal count to complete, or it times out if the specified time-out interval expires first.

## -parameters

### -param Timeout

Specifies the time-out interval in microseconds. This interval is the length of time that the method waits for the transfer to complete before timing out. The specified time-out interval is rounded down to the nearest ten-microsecond increment.

## -returns
The WaitForTC method returns NTSTATUS. It returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.

## -remarks
This method should be called in only two situations:

1. After sending a request to the hardware to stop, the miniport driver calls WaitForTC in order to wait for the DMA to complete before continuing execution.

2. In the case of DMA hardware that is not auto-initialized, the miniport driver can call WaitForTC at any time to wait until a DMA transfer completes.

Because this method simply waits until the DMA transfer either completes or times out, callers of WaitForTC must be running at IRQL PASSIVE_LEVEL.


## -see-also

[IDmaChannelSlave interface](nn-portcls-idmachannelslave.md)
