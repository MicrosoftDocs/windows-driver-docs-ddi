---
UID: NF:netadapter.NET_ADAPTER_CONFIG_INIT
title: NET_ADAPTER_CONFIG_INIT function
author: windows-driver-content
description: Initializes the NET_ADAPTER_CONFIG structure.
ms.assetid: 3320dda0-8d8d-4c93-b354-045324f57d00
ms.author: windowsdriverdev
ms.date: 02/05/2018
ms.topic: function
ms.keywords: NET_ADAPTER_CONFIG_INIT
req.header: netadapter.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.21
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
req.typenames: NET_ADAPTER_CONFIG_INIT
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netadapter.h
apiname: 
-	NET_ADAPTER_CONFIG_INIT
product: Windows
targetos: Windows
req.product: Windows 10 or later.
---

# NET_ADAPTER_CONFIG_INIT function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

Initializes the NET_ADAPTER_CONFIG structure.

## -parameters

### -param AdapterConfig
A pointer to the driver-allocated [NET_ADAPTER_CONFIG](ns-netadapter-_net_adapter_config.md) structure.

### -param EvtAdapterSetCapabilities
A pointer to the client's implementation of the *[EVT_NET_ADAPTER_SET_CAPABILITIES](nc-netadapter-evt_net_adapter_set_capabilities.md)* event callback.

### -param EvtAdapterCreateTxQueue
A pointer to the client's implementation of the *[EVT_NET_ADAPTER_CREATE_TXQUEUE](nc-netadapter-evt_net_adapter_create_txqueue.md)* event callback.

### -param EvtAdapterCreateRxQueue
A pointer to the client's implementation of the *[EVT_NET_ADAPTER_CREATE_RXQUEUE](nc-netadapter-evt_net_adapter_create_rxqueue.md)* event callback.

## -returns
This method does not return a value.

## -remarks
The client typically calls this method from its *[EVT_WDF_DRIVER_DEVICE_ADD](../wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add.md)* event callback function.



## -see-also