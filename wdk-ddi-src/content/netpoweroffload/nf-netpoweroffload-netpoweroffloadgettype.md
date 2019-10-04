---
UID: NF:netpoweroffload.NetPowerOffloadGetType
title: NetPowerOffloadGetType function (netpoweroffload.h)
author: windows-driver-content
description: The NetPowerOffloadGetType method gets the power offload type for a low power protocol offload to a net adapter.
tech.root: netvista
ms.assetid: 04e24520-1ccd-4c27-8bad-ff4cac890e2e
ms.author: windowsdriverdev
ms.date: 10/03/2019
ms.topic: function
f1_keywords:
 - "netpoweroffload/NetPowerOffloadGetType"
ms.keywords: NetPowerOffloadGetType
req.header: netpoweroffload.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt: The next version of Windows 10
req.target-min-winversvr:
req.kmdf-ver:
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
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- netpoweroffload.h
api_name: 
- NetPowerOffloadGetType
product: 
- Windows
targetos: Windows
ms.custom: Vb
---

# NetPowerOffloadGetType function


## -description

The **NetPowerOffloadGetType** method gets the power offload type for a low power protocol offload to a net adapter.

## -parameters

### -param PowerOffload

The NETPOWEROFFLOAD object that represents this low power protocol offload.

## -returns

Returns a [**NET_POWER_OFFLOAD_TYPE**](../netpoweroffload/ne-netpoweroffload-_net_power_offload_type.md) value that specifies the offload type.

## -remarks

## -see-also

[Configuring power management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_POWER_OFFLOAD_TYPE**](../netpoweroffload/ne-netpoweroffload-_net_power_offload_type.md)