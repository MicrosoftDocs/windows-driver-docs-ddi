---
UID: NF:nettxqueue.NetTxQueueCreate
title: NetTxQueueCreate function (nettxqueue.h)
description: Creates a net transmit queue object.
tech.root: netvista
ms.assetid: 50a3a979-0699-40d9-9932-3836a3b0b3a0
ms.date: 11/12/2018
ms.topic: function
ms.keywords: NetTxQueueCreate
req.header: nettxqueue.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.27
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
req.alt-api:
req.alt-loc:
topictype: 
- apiref
apitype: 
- HeaderDef
apilocation: 
- nettxqueue.h
apiname: 
- NetTxQueueCreate
product:
- Windows
targetos: Windows
product:
- Windows
---

# NetTxQueueCreate function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

Creates a net transmit queue object.

## -parameters

### -param NetTxQueueInit
A pointer to the **NETTXQUEUE_INIT** structure that the client driver received in *[EVT_NET_ADAPTER_CREATE_TXQUEUE](../netadapter/nc-netadapter-evt_net_adapter_create_txqueue.md)*.

### -param TxQueueAttributes
A pointer to an initialized, caller-allocated [**WDF_OBJECT_ATTRIBUTES**](../wdfobject/ns-wdfobject-_wdf_object_attributes.md) structure. This parameter is optional and can be **WDF_NO_OBJECT_ATTRIBUTES**. However, if the client driver supplies this parameter, the **ParentObject** field must be **NULL**.

### -param Configuration
A pointer to a caller-allocated [**NET_PACKET_QUEUE_CONFIG**](../netpacketqueue/ns-netpacketqueue-_net_packet_queue_config.md) structure.

### -param TxQueue
A pointer to a location that receives a handle to the new net transmit queue object.

## -returns
The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate NTSTATUS error code.

## -remarks
The client calls **NetTxQueueCreate** from within its *[EVT_NET_ADAPTER_CREATE_TXQUEUE](../netadapter/nc-netadapter-evt_net_adapter_create_txqueue.md)* event callback function. For info on assigning context space to the new object, see [Framework Object Context Space](https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-object-context-space).

The NETPACKETQUEUE object is a standard WDF object. The framework manages its deletion, which occurs when the parent NETADAPTER object is deleted.



## -see-also
