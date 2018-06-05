---
UID: NF:netadapter.NET_ADAPTER_POWER_CAPABILITIES_INIT
title: NET_ADAPTER_POWER_CAPABILITIES_INIT function
author: windows-driver-content
description: Initializes a NET_ADAPTER_POWER_CAPABILITIES structure.
ms.assetid: e5d431f9-fd17-40fd-83df-f5cbd5969770
ms.author: windowsdriverdev
ms.date: 02/06/2018
ms.topic: function
ms.keywords: NET_ADAPTER_POWER_CAPABILITIES_INIT
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
req.typenames: NET_ADAPTER_POWER_CAPABILITIES_INIT
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netadapter.h
apiname: 
-	NET_ADAPTER_POWER_CAPABILITIES_INIT
product: Windows
targetos: Windows
req.product: Windows 10 or later.
---

# NET_ADAPTER_POWER_CAPABILITIES_INIT function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

Initializes a [NET_ADAPTER_POWER_CAPABILITIES](ns-netadapter-_net_adapter_power_capabilities.md) structure.

## -parameters

### -param PowerCapabilities
A pointer to the driver-allocated [NET_ADAPTER_POWER_CAPABILITIES](ns-netadapter-_net_adapter_power_capabilities.md) structure.

## -returns

This method does not return a value.

## -remarks

The **NET_ADAPTER_POWER_CAPABILITIES_INIT** function zeros the specified **NET_ADAPTER_POWER_CAPABILITIES** structure and sets the structure's **Size** member. It also sets the structure's **ManageS0IdlePowerReferences** member to **WdfUseDefault**.



## -see-also

[NetAdapterSetPowerCapabilities](nf-netadapter-netadaptersetpowercapabilities.md)