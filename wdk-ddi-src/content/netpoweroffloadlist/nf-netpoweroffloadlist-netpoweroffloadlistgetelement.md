---
UID: NF:netpoweroffloadlist.NetPowerOffloadListGetElement
title: NetPowerOffloadListGetElement function (netpoweroffloadlist.h)
author: windows-driver-content
description: The NetPowerOffloadListGetElement method gets a NETPOWEROFFLOAD object from a list of low power protocol offloads to a net adapter.
tech.root: netvista
ms.assetid: a93ff9b6-6415-4d3f-8443-9a2479d88453
ms.author: windowsdriverdev
ms.date: 10/03/2019
ms.topic: function
f1_keywords:
 - "netpoweroffloadlist/NetPowerOffloadListGetElement"
ms.keywords: NetPowerOffloadListGetElement
req.header: netpoweroffloadlist.h
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
- netpoweroffloadlist.h
api_name: 
- NetPowerOffloadListGetElement
product: 
- Windows
targetos: Windows
ms.custom: Vb
---

# NetPowerOffloadListGetElement function


## -description

The **NetPowerOffloadListGetElement** method gets a NETPOWEROFFLOAD object from a list of low power protocol offloads to a net adapter.

## -parameters

### -param List

A handle to a driver-allocated and initialized [**NET_POWER_OFFLOAD_LIST**](../netpoweroffloadlist/ns-netpoweroffloadlist-_net_power_offload_list.md) structure.

### -param Index

The zero-based index in the list for the target NETPOWEROFFLOAD object. **Index** must be between **0** inclusive and the number of NETPOWEROFFLOAD objects in the list exclusive. For example, if there are three NETPOWEROFFLOAD objects, then **Index** must be in the range of **[0, 3)**.

## -returns

Returns the NETPOWEROFFLOAD object at the specified index in the list.

## -remarks

Call [**NetPowerOffloadListGetCount**](../netpoweroffloadlist/nf-netpoweroffloadlist-netpoweroffloadlistgetcount.md) to get the number of low power protocol offloads before calling this method.

For a code sample of working with NETPOWEROFFLOAD objects, see [Configuring power management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management).

## -see-also

[Configuring power management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_POWER_OFFLOAD_LIST**](../netpoweroffloadlist/ns-netpoweroffloadlist-_net_power_offload_list.md)