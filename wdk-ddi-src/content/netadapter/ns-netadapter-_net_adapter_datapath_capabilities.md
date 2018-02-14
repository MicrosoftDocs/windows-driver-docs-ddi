---
UID: NS:netadapter._NET_ADAPTER_DATAPATH_CAPABILITIES
title: _NET_ADAPTER_DATAPATH_CAPABILITIES
author: windows-driver-content
description: Describes the data path capabilities of the adapter.
ms.assetid: af856224-5afb-42f0-868d-99698019a4bf
ms.author: windowsdriverdev
ms.date: 02/06/2018
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _NET_ADAPTER_DATAPATH_CAPABILITIES, *PNET_ADAPTER_DATAPATH_CAPABILITIES, NET_ADAPTER_DATAPATH_CAPABILITIES, 
req.header: netadapter.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.21
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.alt-api:
req.alt-loc:
req.typenames: *PNET_ADAPTER_DATAPATH_CAPABILITIES, NET_ADAPTER_DATAPATH_CAPABILITIES
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netadapter.h
apiname: 
-	NET_ADAPTER_DATAPATH_CAPABILITIES
product: Windows
targetos: Windows
req.product: Windows 10 or later.
---

# _NET_ADAPTER_DATAPATH_CAPABILITIES structure

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

Describes the data path capabilities of the adapter.

## -struct-fields

### -field Size
The size of this structure, in bytes.
 
### -field NumTxQueues
The maximum number of transmit queues supported by the adapter.
 
### -field NumRxQueues
The maximum number of receive queues supported by the adapter.

## -remarks
The client driver passes an initialized **NET_ADAPTER_DATAPATH_CAPABILITIES** structure as an input parameter value to [NetAdapterSetDataPathCapabilities](nf-netadapter-netadaptersetdatapathcapabilities.md).

Call [NET_ADAPTER_DATAPATH_CAPABILITIES_INIT](ns-netadapter-_net_adapter_datapath_capabilities.md) to initialize this structure.

The minimum NetAdapterCx version for **NET_ADAPTER_DATAPATH_CAPABILITIES** is 1.0.

## -see-also