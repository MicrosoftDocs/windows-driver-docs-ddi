---
UID: NC:netadapter.EVT_NET_ADAPTER_CREATE_TXQUEUE
title: EVT_NET_ADAPTER_CREATE_TXQUEUE (netadapter.h)
description: The client driver's implementation of the *EvtNetAdapterCreateTxQueue* event callback function that sets up a transmit (Tx) queue.
tech.root: netvista
ms.date: 01/18/2019
keywords: ["EVT_NET_ADAPTER_CREATE_TXQUEUE callback function"]
req.header: netadapter.h
req.include-header: netadaptercx.h 
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
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_NET_ADAPTER_CREATE_TXQUEUE
 - netadapter/EVT_NET_ADAPTER_CREATE_TXQUEUE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - netadapter.h
api_name:
 - EVT_NET_ADAPTER_CREATE_TXQUEUE
---

# EVT_NET_ADAPTER_CREATE_TXQUEUE callback function


## -description

The client driver's implementation of the *EvtNetAdapterCreateTxQueue* event callback function that sets up a transmit (Tx) queue.

## -parameters

### -param Adapter 

The network adapter object that the client created in a prior call to [**NetAdapterCreate**](nf-netadapter-netadaptercreate.md).

### -param TxQueueInit 

A pointer to a NetAdapterCx-allocated **NETTXQUEUE_INIT** structure. For more information, see the Remarks section.

## -returns

If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise, an appropriate [NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values) error code.

## -prototype

```C++
//Declaration

EVT_NET_ADAPTER_CREATE_TXQUEUE EvtNetAdapterCreateTxqueue; 

// Definition

NTSTATUS EvtNetAdapterCreateTxqueue 
(
	_In_    NETADAPTER          Adapter,
	_Inout_ NETTXQUEUE_INIT *   TxQueueInit
)
{...}

typedef EVT_NET_ADAPTER_CREATE_TXQUEUE *PFN_NET_ADAPTER_CREATE_TXQUEUE;
```

## -remarks

To register an *EVT_NET_ADAPTER_CREATE_TXQUEUE* callback function, the client driver must call [**NetAdapterCreate**](nf-netadapter-netadaptercreate.md).

The **NETTXQUEUE_INIT** structure is an opaque structure that is defined and allocated by NetAdapterCx, similar to [WDFDEVICE_INIT](/windows-hardware/drivers/wdf/wdfdevice_init).

In this callback, the client driver might call [NetTxQueueInitGetQueueId](../nettxqueue/nf-nettxqueue-nettxqueueinitgetqueueid.md) to retrieve the identifier of the transmit queue to set up. Next, the client calls [**NetTxQueueCreate**](../nettxqueue/nf-nettxqueue-nettxqueuecreate.md) to allocate a queue. If [**NetTxQueueCreate**](../nettxqueue/nf-nettxqueue-nettxqueuecreate.md) fails, the *EvtNetAdapterCreateTxQueue* callback function should return an error code.

NetAdapterCx calls *EvtNetAdapterCreateTxQueue* at the very end of the [power-up sequence](/windows-hardware/drivers/netcx/power-up-sequence-for-a-netadaptercx-client-driver). 

For a code example of implementing this callback function, see [Transmit and receive queues](/windows-hardware/drivers/netcx/transmit-and-receive-queues).

## -see-also
