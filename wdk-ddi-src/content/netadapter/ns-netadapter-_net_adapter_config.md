---
UID: NS:netadapter._NET_ADAPTER_CONFIG
title: _NET_ADAPTER_CONFIG
author: windows-driver-content
description: Describes the configuration options for a NetAdapterCx client driver. An initialized NET_ADAPTER_CONFIG structure is an input parameter to NetAdapterCreate.
ms.assetid: a84fa024-91db-4fa1-beb3-30dfd638f63b
ms.author: windowsdriverdev
ms.date: 02/06/2018
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _NET_ADAPTER_CONFIG, *PNET_ADAPTER_CONFIG, NET_ADAPTER_CONFIG, 
req.header: netadapter.h
req.include-header: netadaptercx.h
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.23
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.alt-api:
req.alt-loc:
req.typenames: NET_ADAPTER_CONFIG, *PNET_ADAPTER_CONFIG
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netadapter.h
apiname: 
-	NET_ADAPTER_CONFIG
product: Windows
targetos: Windows
req.product: Windows 10 or later.
---

# _NET_ADAPTER_CONFIG structure

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

Describes the configuration options for a NetAdapterCx client driver. An initialized **NET_ADAPTER_CONFIG** structure is an input parameter to [NetAdapterCreate](nf-netadapter-netadaptercreate.md).

## -struct-fields

### -field Size
The size of the **NET_ADAPTER_CONFIG** structure, in bytes.
 
### -field EvtAdapterSetCapabilities
A pointer to the client's implementation of the *[EVT_NET_ADAPTER_SET_CAPABILITIES](nc-netadapter-evt_net_adapter_set_capabilities.md)* event callback.
 
### -field EvtAdapterCreateTxQueue
A pointer to the client's implementation of the *[EVT_NET_ADAPTER_CREATE_TXQUEUE](nc-netadapter-evt_net_adapter_create_txqueue.md)* event callback.
 
### -field EvtAdapterCreateRxQueue
A pointer to the client's implementation of the *[EVT_NET_ADAPTER_CREATE_RXQUEUE](nc-netadapter-evt_net_adapter_create_rxqueue.md)* event callback.

### -field EvtAdapterCreateRssQueueGroup
An optional pointer to the client's implementation of the *[EVT_NET_ADAPTER_CREATE_RSS_QUEUE_GROUP](nc-netadapter-evt_net_adapter_create_rssqueue_group.md)* event callback. 
 
### -field NetRequestObjectAttributes
Optional WDF object attributes associated with the NETREQUEST objects, or NULL. If non-NULL, all NETREQUESTs created by the framework will have these attributes.
 
### -field NetPowerSettingsObjectAttributes 
Optional WDF object attributes associated with the NETPOWERSETTINGS object, or NULL.

## -remarks
Call [NET_ADAPTER_CONFIG_INIT](nf-netadapter-net_adapter_config_init.md) to initialize this structure.

The minimum NetAdapterCx version for **NET_ADAPTER_CONFIG** is 1.2.

## -see-also