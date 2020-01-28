---
UID: NC:netadapter.EVT_NET_ADAPTER_CREATE_RXQUEUE
title: EVT_NET_ADAPTER_CREATE_RXQUEUE (netadapter.h)
description: The client driver's implementation of the EvtNetAdapterCreateRxQueue event callback function that sets up a receive (Rx) queue.
tech.root: netvista
ms.assetid: 30a51b5b-5da7-4cfa-aaff-433c39f90bd0
ms.date: 01/18/2019
f1_keywords:
 - "netadapter/EVT_NET_ADAPTER_CREATE_RXQUEUE"
req.header: netadapter.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.29
req.umdf-ver:
req.lib:
req.dll:
req.irql: PASSIVE_LEVEL
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
- UserDefined
api_location:
- netadapter.h
api_name: 
- EVT_NET_ADAPTER_CREATE_RXQUEUE
targetos: Windows
req.typenames: 
product:
- Windows
---

# EVT_NET_ADAPTER_CREATE_RXQUEUE callback function


## -description



The client driver's implementation of the *EvtNetAdapterCreateRxQueue* event callback function that sets up a receive (Rx) queue.

## -prototype

```c++
//Declaration

EVT_NET_ADAPTER_CREATE_RXQUEUE EvtNetAdapterCreateRxqueue; 

// Definition

NTSTATUS EvtNetAdapterCreateRxqueue 
(
	_In_    NETADAPTER          Adapter,
	_Inout_ NETRXQUEUE_INIT *   RxQueueInit
)
{...}

typedef EVT_NET_ADAPTER_CREATE_RXQUEUE *PFN_NET_ADAPTER_CREATE_RXQUEUE;
```

## -parameters

### -param Adapter 

The network adapter object that the client created in a prior call to [**NetAdapterCreate**](nf-netadapter-netadaptercreate.md).

### -param RxQueueInit 

A pointer to a NetAdapterCx-allocated **NETRXQUEUE_INIT** structure. For more information, see the Remarks section.


## -returns

If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise, an appropriate [NTSTATUS](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values) error code.

## -remarks

To register an EVT_NET_ADAPTER_CREATE_RXQUEUE callback function, the client driver must call [**NetAdapterCreate**](nf-netadapter-netadaptercreate.md).

The **NETRXQUEUE_INIT** structure is an opaque structure that is defined and allocated by NetAdapterCx, similar to [**WDFDEVICE_INIT**](https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfdevice_init).

In this callback, the client driver might call [**NetRxQueueInitGetQueueId**](../netrxqueue/nf-netrxqueue-netrxqueueinitgetqueueid.md) to retrieve the identifier of the receive queue to set up. Next, the client calls [**NetRxQueueCreate**](../netrxqueue/nf-netrxqueue-netrxqueuecreate.md) to allocate a queue. If [NetRxQueueCreate](../netrxqueue/nf-netrxqueue-netrxqueuecreate.md) fails, the *EvtNetAdapterCreateRxQueue* callback function should return an error code.

NetAdapterCx calls *EvtNetAdapterCreateRxQueue* at the very end of the [power-up sequence](https://docs.microsoft.com/windows-hardware/drivers/netcx/power-up-sequence-for-a-netadaptercx-client-driver). 

For a code example of implementing this callback function, see [Transmit and receive queues](https://docs.microsoft.com/windows-hardware/drivers/netcx/transmit-and-receive-queues).

## -see-also
