---
UID: NS:netadapter._NET_ADAPTER_DATAPATH_CALLBACKS
title: _NET_ADAPTER_DATAPATH_CALLBACKS
author: windows-driver-content
description: The NET_ADAPTER_DATAPATH_CALLBACKS structure describes a net adapter's callback functions for creating its datapath queues.
ms.assetid: 831e94ef-28ba-4681-b0b6-07a8a38238fc
ms.author: windowsdriverdev
ms.date: 07/27/2018
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _NET_ADAPTER_DATAPATH_CALLBACKS, NET_ADAPTER_DATAPATH_CALLBACKS, *PNET_ADAPTER_DATAPATH_CALLBACKS, 
req.header: netadapter.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.27
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: NET_ADAPTER_DATAPATH_CALLBACKS, *PNET_ADAPTER_DATAPATH_CALLBACKS
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	netadapter.h
api_name: 
-	_NET_ADAPTER_DATAPATH_CALLBACKS
product: Windows
targetos: Windows
---

# _NET_ADAPTER_DATAPATH_CALLBACKS structure

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The NET_ADAPTER_DATAPATH_CALLBACKS structure describes a net adapter's callback functions for creating its datapath queues.

## -struct-fields

### -field Size

The size of this structure, in bytes.
 
### -field EvtAdapterCreateTxQueue

A pointer to the client driver's implementation of the [*EVT_NET_ADAPTER_CREATE_TXQUEUE*](nc-netadapter-evt_net_adapter_create_txqueue.md) callback function.
 
### -field EvtAdapterCreateRxQueue

A pointer to the client driver's implementation of the [*EVT_NET_ADAPTER_CREATE_RXQUEUE*](nc-netadapter-evt_net_adapter_create_rxqueue.md) callback function. 

## -remarks

Call [**NET_ADAPTER_DATAPATH_CALLBACKS_INIT**](nf-netadapter-net_adapter_datapath_callbacks_init.md) to initialize this structure. An initialized **NET_ADAPTER_DATAPATH_CALLBACKS** structure is passed as a parameter to the [**NetAdapterInitSetDatapathCallbacks**](nf-netadapter-netadapterinitsetdatapathcallbacks.md) method.

## -see-also

[**NET_ADAPTER_DATAPATH_CALLBACKS_INIT**](nf-netadapter-net_adapter_datapath_callbacks_init.md)

[**NetAdapterInitSetDatapathCallbacks**](nf-netadapter-netadapterinitsetdatapathcallbacks.md)