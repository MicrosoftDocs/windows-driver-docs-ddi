---
UID: NF:netadapter.NET_ADAPTER_DATAPATH_CAPABILITIES_INIT
title: NET_ADAPTER_DATAPATH_CAPABILITIES_INIT function
author: windows-driver-content
description: Initializes the NET_ADAPTER_DATAPATH_CAPABILITIES structure.
ms.assetid: 90d1bf1d-3f84-48a0-9849-b5aeb246df61
ms.author: windowsdriverdev
ms.date: 02/05/2018
ms.topic: function
ms.keywords: NET_ADAPTER_DATAPATH_CAPABILITIES_INIT
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
req.typenames: NET_ADAPTER_DATAPATH_CAPABILITIES_INIT
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netadapter.h
apiname: 
-	NET_ADAPTER_DATAPATH_CAPABILITIES_INIT
product: Windows
targetos: Windows
req.product: Windows 10 or later.
---

# NET_ADAPTER_DATAPATH_CAPABILITIES_INIT function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

Initializes the [NET_ADAPTER_DATAPATH_CAPABILITIES](ns-netadapter-_net_adapter_datapath_capabilities.md) structure.

## -parameters

### -param DataPathCapabilities
A pointer to the driver-allocated [NET_ADAPTER_DATAPATH_CAPABILITIES](ns-netadapter-_net_adapter_datapath_capabilities.md) structure.

## -returns
This method does not return a value.

## -remarks

The minimum NetAdapterCx version for **NET_ADAPTER_DATAPATH_CAPABILITIES_INIT** is 1.0.

## -see-also

[NetAdapterSetDatapathCapabilities](nf-netadapter-netadaptersetdatapathcapabilities.md)