---
UID: NF:netadapter.NET_ADAPTER_DATAPATH_CALLBACKS_INIT
title: NET_ADAPTER_DATAPATH_CALLBACKS_INIT function (netadapter.h)
description: The NET_ADAPTER_DATAPATH_CALLBACKS_INIT function initializes a NET_ADAPTER_DATAPATH_CALLBACKS structure.
tech.root: netvista
ms.assetid: bc15c768-b5ba-48b0-ad78-fb33cc577407
ms.date: 07/27/2018
keywords: ["NET_ADAPTER_DATAPATH_CALLBACKS_INIT function"]
ms.keywords: NET_ADAPTER_DATAPATH_CALLBACKS_INIT
req.header: netadapter.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.27
req.umdf-ver: 
req.lib: netadaptercxstub.lib
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: RS5
f1_keywords:
 - NET_ADAPTER_DATAPATH_CALLBACKS_INIT
 - netadapter/NET_ADAPTER_DATAPATH_CALLBACKS_INIT
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - netadaptercxstub.lib
api_name:
 - NET_ADAPTER_DATAPATH_CALLBACKS_INIT
---

# NET_ADAPTER_DATAPATH_CALLBACKS_INIT function


## -description

The **NET_ADAPTER_DATAPATH_CALLBACKS_INIT** function initializes a [**NET_ADAPTER_DATAPATH_CALLBACKS**](ns-netadapter-_net_adapter_datapath_callbacks.md) structure.

## -parameters

### -param DatapathCallbacks

A pointer to a driver-allocated [**NET_ADAPTER_DATAPATH_CALLBACKS**](ns-netadapter-_net_adapter_datapath_callbacks.md) structure.

### -param EvtAdapterCreateTxQueue

A pointer to the client driver's implementation of the [*EVT_NET_ADAPTER_CREATE_TXQUEUE*](nc-netadapter-evt_net_adapter_create_txqueue.md) callback function.

### -param EvtAdapterCreateRxQueue

A pointer to the client driver's implementation of the [*EVT_NET_ADAPTER_CREATE_RXQUEUE*](nc-netadapter-evt_net_adapter_create_rxqueue.md) callback function.

## -remarks

Call this function to initialize the [**NET_ADAPTER_DATAPATH_CALLBACKS**](ns-netadapter-_net_adapter_datapath_callbacks.md) structure before calling [**NetAdapterInitSetDatapathCallbacks**](nf-netadapter-netadapterinitsetdatapathcallbacks.md).

## -see-also

[**NET_ADAPTER_DATAPATH_CALLBACKS**](ns-netadapter-_net_adapter_datapath_callbacks.md)

[**NetAdapterInitSetDatapathCallbacks**](nf-netadapter-netadapterinitsetdatapathcallbacks.md)

