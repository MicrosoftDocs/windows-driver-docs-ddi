---
UID: NF:netpoweroffloadlist.NetDeviceGetPowerOffloadList
title: NetDeviceGetPowerOffloadList function (netpoweroffloadlist.h)
author: windows-driver-content
description: The NetDeviceGetPowerOffloadList method gets the list of low power protocol offloads to a net adapter.
tech.root: netvista
ms.assetid: 6ec8df81-ab48-413d-848c-2407385c1da7
ms.author: windowsdriverdev
ms.date: 10/03/2019
ms.topic: function
f1_keywords:
 - "netpoweroffloadlist/NetDeviceGetPowerOffloadList"
ms.keywords: NetDeviceGetPowerOffloadList
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
- NetDeviceGetPowerOffloadList
product: 
- Windows
targetos: Windows
ms.custom: Vb
---

# NetDeviceGetPowerOffloadList function


## -description

The **NetDeviceGetPowerOffloadList** method gets the list of low power protocol offloads to a net adapter.

## -parameters

### -param Device

A handle to the WDFDEVICE object that represents this net adapter.

### -param List

A handle to a driver-allocated and initialized [**NET_POWER_OFFLOAD_LIST**](../netpoweroffloadlist/ns-netpoweroffloadlist-_net_power_offload_list.md) structure.

## -returns

This method does not return a value.

## -remarks

Call [**NET_POWER_OFFLOAD_LIST_INIT**](../netpoweroffloadlist/nf-netpoweroffloadlist-net_power_offload_list_init.md) to initialize the [**NET_POWER_OFFLOAD_LIST**](../netpoweroffloadlist/ns-netpoweroffloadlist-_net_power_offload_list.md) structure, then call this method to retrieve the low power protocol offload list.

For a code sample of working with NETPOWEROFFLOAD objects, see [Configuring power management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management).

## -see-also

[Configuring power management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_POWER_OFFLOAD_LIST_INIT**](../netpoweroffloadlist/nf-netpoweroffloadlist-net_power_offload_list_init.md)

[**NET_POWER_OFFLOAD_LIST**](../netpoweroffloadlist/ns-netpoweroffloadlist-_net_power_offload_list.md)