---
UID: NF:netpoweroffload.NetPowerOffloadGetNSParameters
title: NetPowerOffloadGetNSParameters function (netpoweroffload.h)
author: windows-driver-content
description: The NetPowerOffloadGetNSParameters method gets parameters for an IPv6 Neighbor Solicitation (NS) low power protocol offload to a net adapter.
tech.root: netvista
ms.assetid: 4434a42f-2f3a-4d19-979c-52de51133b44
ms.author: windowsdriverdev
ms.date: 10/03/2019
ms.topic: function
f1_keywords:
 - "netpoweroffload/NetPowerOffloadGetNSParameters"
ms.keywords: NetPowerOffloadGetNSParameters
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
- NetPowerOffloadGetNSParameters
product: 
- Windows
targetos: Windows
ms.custom: Vb
---

# NetPowerOffloadGetNSParameters function


## -description

The **NetPowerOffloadGetNSParameters** method gets parameters for an IPv6 Neighbor Solicitation (NS) low power protocol offload to a net adapter.

## -parameters

### -param PowerOffload

A handle to a NETPOWEROFFLOAD object that represents this NS protocol offload.

### -param Parameters

A handle to a driver-allocated [**NET_POWER_OFFLOAD_NS_PARAMETERS**](../netpoweroffload/ns-netpoweroffload-_net_power_offload_ns_parameters.md) structure that receives the ARP parameter information.

## -returns

This method does not return a value.

## -remarks

## -see-also

[Configuring power management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_POWER_OFFLOAD_NS_PARAMETERS**](../netpoweroffload/ns-netpoweroffload-_net_power_offload_ns_parameters.md)