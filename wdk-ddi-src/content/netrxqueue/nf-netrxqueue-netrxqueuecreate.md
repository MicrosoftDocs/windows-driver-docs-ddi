---
UID: NF:netrxqueue.NetRxQueueCreate
title: NetRxQueueCreate function (netrxqueue.h)
description: Creates a net receive queue object.
tech.root: netvista
ms.assetid: 2f5e886c-10c8-42bf-83d3-1902ef628b5a
ms.date: 11/12/2018
keywords: ["NetRxQueueCreate function"]
ms.keywords: NetRxQueueCreate
req.header: netrxqueue.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.27
req.umdf-ver: 
req.lib: NetAdapterCxStub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.alt-api: 
req.alt-loc: 
targetos: Windows
f1_keywords:
 - NetRxQueueCreate
 - netrxqueue/NetRxQueueCreate
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - netrxqueue.h
api_name:
 - NetRxQueueCreate
---

# NetRxQueueCreate function


## -description

Creates a net receive queue object.

## -parameters

### -param NetRxQueueInit

A pointer to the NETRXQUEUE_INIT structure that the client driver received in its *[EVT_NET_ADAPTER_CREATE_RXQUEUE](../netadapter/nc-netadapter-evt_net_adapter_create_rxqueue.md)* callback function.

### -param RxQueueAttributes

A pointer to caller-allocated and initialized [**WDF_OBJECT_ATTRIBUTES**](../wdfobject/ns-wdfobject-_wdf_object_attributes.md) structure. This parameter is optional and can be **WDF_NO_OBJECT_ATTRIBUTES**. However, if the client driver supplies this parameter, the **ParentObject** field must be **NULL**.

### -param Configuration

A pointer to a caller-allocated [**NET_PACKET_QUEUE_CONFIG**](../netpacketqueue/ns-netpacketqueue-_net_packet_queue_config.md) structure.

### -param RxQueue

A pointer to a location that receives a handle to the new net receive queue object.

## -returns

This method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate NTSTATUS error code.

## -remarks

The client calls **NetRxQueueCreate** from within its *[EVT_NET_ADAPTER_CREATE_RXQUEUE](../netadapter/nc-netadapter-evt_net_adapter_create_rxqueue.md)* event callback function. For info on assigning context space to the new object, see [Framework Object Context Space](https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-object-context-space).

The NETPACKETQUEUE object is a standard WDF object. The framework manages its deletion, which occurs when the parent NETADAPTER object is deleted.

## -see-also

