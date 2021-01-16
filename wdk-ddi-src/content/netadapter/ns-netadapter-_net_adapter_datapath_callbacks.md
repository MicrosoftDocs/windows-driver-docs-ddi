---
UID: NS:netadapter._NET_ADAPTER_DATAPATH_CALLBACKS
title: _NET_ADAPTER_DATAPATH_CALLBACKS (netadapter.h)
description: The NET_ADAPTER_DATAPATH_CALLBACKS structure describes a net adapter's callback functions for creating its datapath queues.
tech.root: netvista
ms.date: 07/27/2018
keywords: ["NET_ADAPTER_DATAPATH_CALLBACKS structure"]
ms.keywords: _NET_ADAPTER_DATAPATH_CALLBACKS, NET_ADAPTER_DATAPATH_CALLBACKS, *PNET_ADAPTER_DATAPATH_CALLBACKS,
req.header: netadapter.h
req.include-header: netadaptercx.h
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
targetos: Windows
ms.custom: RS5
f1_keywords:
 - _NET_ADAPTER_DATAPATH_CALLBACKS
 - netadapter/_NET_ADAPTER_DATAPATH_CALLBACKS
 - NET_ADAPTER_DATAPATH_CALLBACKS
 - netadapter/NET_ADAPTER_DATAPATH_CALLBACKS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - netadapter.h
api_name:
 - _NET_ADAPTER_DATAPATH_CALLBACKS
 - NET_ADAPTER_DATAPATH_CALLBACKS
---

# _NET_ADAPTER_DATAPATH_CALLBACKS structure


## -description

The NET_ADAPTER_DATAPATH_CALLBACKS structure describes a net adapter's callback functions for creating its datapath queues.

## -struct-fields

### -field Size

The size of this structure, in bytes.

### -field EvtAdapterCreateTxQueue

A pointer to the client driver's implementation of the [*EVT_NET_ADAPTER_CREATE_TXQUEUE*](nc-netadapter-evt_net_adapter_create_txqueue.md) callback function.

### -field EvtAdapterCreateRxQueue

A pointer to the client driver's implementation of the [*EVT_NET_ADAPTER_CREATE_RXQUEUE*](nc-netadapter-evt_net_adapter_create_rxqueue.md) callback function.

## -remarks

Call [**NET_ADAPTER_DATAPATH_CALLBACKS_INIT**](nf-netadapter-net_adapter_datapath_callbacks_init.md) to initialize this structure. An initialized **NET_ADAPTER_DATAPATH_CALLBACKS** structure is passed as a parameter to the [**NetAdapterInitSetDatapathCallbacks**](nf-netadapter-netadapterinitsetdatapathcallbacks.md) function.

## -see-also

[**NET_ADAPTER_DATAPATH_CALLBACKS_INIT**](nf-netadapter-net_adapter_datapath_callbacks_init.md)

[**NetAdapterInitSetDatapathCallbacks**](nf-netadapter-netadapterinitsetdatapathcallbacks.md)

