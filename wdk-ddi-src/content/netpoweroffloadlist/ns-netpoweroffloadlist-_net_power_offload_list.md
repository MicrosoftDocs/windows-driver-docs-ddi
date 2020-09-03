---
UID: NS:netpoweroffloadlist._NET_POWER_OFFLOAD_LIST
title: NET_POWER_OFFLOAD_LIST (netpoweroffloadlist.h)
author: windows-driver-content
description: The NET_POWER_OFFLOAD_LIST structure represents a list of low power protocol offloads to a net adapter.
tech.root: netvista
ms.assetid: a8cc5703-68a3-4adf-97b5-ec3271c1fdc3
ms.author: windowsdriverdev
ms.date: 10/03/2019
keywords: ["NET_POWER_OFFLOAD_LIST structure"]
ms.keywords: NET_POWER_OFFLOAD_LIST, NET_POWER_OFFLOAD_LIST,
req.header: netpoweroffloadlist.h
req.include-header: netadaptercx.h 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: NET_POWER_OFFLOAD_LIST
targetos: Windows
ms.custom: Vb
f1_keywords:
 - _NET_POWER_OFFLOAD_LIST
 - netpoweroffloadlist/_NET_POWER_OFFLOAD_LIST
 - NET_POWER_OFFLOAD_LIST
 - netpoweroffloadlist/NET_POWER_OFFLOAD_LIST
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - netpoweroffloadlist.h
api_name:
 - NET_POWER_OFFLOAD_LIST
product:
 - Windows
---

# NET_POWER_OFFLOAD_LIST structure


## -description

The **NET_POWER_OFFLOAD_LIST** structure represents a list of low power protocol offloads to a net adapter.

## -struct-fields

### -field Size

The size of this structure, in bytes.

### -field Reserved

Reserved. Client drivers must not read or write to this value directly.

## -remarks

Call [**NET_POWER_OFFLOAD_LIST_INIT**](../netpoweroffloadlist/nf-netpoweroffloadlist-net_power_offload_list_init.md) to initialize this structure, then call [**NetDeviceGetPowerOffloadList**](../netpoweroffloadlist/nf-netpoweroffloadlist-netdevicegetpoweroffloadlist.md) to get the list of low power offloads to this net adapter. After you obtain the list, call [**NetPowerOffloadListGetCount**](../netpoweroffloadlist/nf-netpoweroffloadlist-netpoweroffloadlistgetcount.md) with this structure to get the number of NETPOWEROFFLOAD objects that represents the offloads, then loop over the objects and call [**NetPowerOffloadListGetElement**](../netpoweroffloadlist/nf-netpoweroffloadlist-netpoweroffloadlistgetelement.md) to retrieve each one. Once you have obtained a NETPOWEROFFLOAD object, call [**NetPowerOffloadGetType**](../netpoweroffload/nf-netpoweroffload-netpoweroffloadgettype.md) to get the type of that offload so you can call the appropriate function to get the offload's parameters.

The client driver must only call power offload-related functions during a power transition, typically from its *[EVT_WDF_DEVICE_ARM_WAKE_FROM_SX](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md)*, *[EVT_WDF_DEVICE_ARM_WAKE_FROM_S0](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_s0.md)*, or *[EVT_NET_DEVICE_PREVIEW_POWER_OFFLOAD](../netdevice/nc-netdevice-evt_net_device_preview_power_offload.md)* callback function. Otherwise, the call results in a system bugcheck.

For a code sample of working with NETPOWEROFFLOAD objects, see [Configuring power management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management).

## -see-also

[Configuring power management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_POWER_OFFLOAD_LIST_INIT**](../netpoweroffloadlist/nf-netpoweroffloadlist-net_power_offload_list_init.md)

[**NetDeviceGetPowerOffloadList**](../netpoweroffloadlist/nf-netpoweroffloadlist-netdevicegetpoweroffloadlist.md)

[**NetPowerOffloadListGetCount**](../netpoweroffloadlist/nf-netpoweroffloadlist-netpoweroffloadlistgetcount.md)

[**NetPowerOffloadListGetElement**](../netpoweroffloadlist/nf-netpoweroffloadlist-netpoweroffloadlistgetelement.md)

[**NetPowerOffloadGetType**](../netpoweroffload/nf-netpoweroffload-netpoweroffloadgettype.md)

