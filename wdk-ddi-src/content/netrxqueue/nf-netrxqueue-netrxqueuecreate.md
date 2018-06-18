---
UID: NF:netrxqueue.NetRxQueueCreate
title: NetRxQueueCreate function
author: windows-driver-content
description: Creates a net receive queue object.
ms.assetid: 2f5e886c-10c8-42bf-83d3-1902ef628b5a
ms.author: windowsdriverdev
ms.date: 02/09/2018
ms.topic: function
ms.keywords: NetRxQueueCreate
req.header: netrxqueue.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.21
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
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netrxqueue.h
apiname: 
-	NetRxQueueCreate
product: Windows
targetos: Windows
req.product: Windows 10 or later.
---

# NetRxQueueCreate function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

Creates a net receive queue object.

## -parameters

### -param NetRxQueueInit
A pointer to the NETRXQUEUE_INIT structure that the client driver received in *[EVT_NET_ADAPTER_CREATE_RXQUEUE](../netadapter/nc-netadapter-evt_net_adapter_create_rxqueue.md)*.

### -param RxQueueAttributes
A pointer to caller-allocated and initialized [WDF_OBJECT_ATTRIBUTES](../wdfobject/ns-wdfobject-_wdf_object_attributes.md) structure. The structure’s **ParentObject** member must be NULL. The parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.

### -param Configuration
A pointer to a caller-allocated [NET_RXQUEUE_CONFIG](ns-netrxqueue-_net_rxqueue_config.md) structure.

### -param RxQueue
A pointer to a location that receives a handle to the new net receive queue object.

## -returns
This method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate NTSTATUS error code.

## -remarks
The client calls **NetRxQueueCreate** from within its *[EVT_NET_ADAPTER_CREATE_RXQUEUE](../netadapter/nc-netadapter-evt_net_adapter_create_rxqueue.md)* event callback function. For info on assigning context space to the new object, see [Framework Object Context Space](https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-object-context-space).

The NETRXQUEUE object is a standard WDF object. The framework manages its deletion, which occurs when the parent WDFDEVICE is deleted.



## -see-also