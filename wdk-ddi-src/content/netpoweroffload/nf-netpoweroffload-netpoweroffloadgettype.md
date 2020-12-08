---
UID: NF:netpoweroffload.NetPowerOffloadGetType
title: NetPowerOffloadGetType function (netpoweroffload.h)
description: The NetPowerOffloadGetType function gets the power offload type for a low power protocol offload to a net adapter.
tech.root: netvista
ms.date: 10/03/2019
keywords: ["NetPowerOffloadGetType function"]
ms.keywords: NetPowerOffloadGetType
req.header: netpoweroffload.h
req.include-header: netadaptercx.h 
req.target-type: Universal
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: netadaptercxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: Vb
f1_keywords:
 - NetPowerOffloadGetType
 - netpoweroffload/NetPowerOffloadGetType
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - netadaptercxstub.lib
api_name:
 - NetPowerOffloadGetType
product:
 - Windows
---

# NetPowerOffloadGetType function


## -description

The **NetPowerOffloadGetType** function gets the power offload type for a low power protocol offload to a net adapter.

## -parameters

### -param PowerOffload

The NETPOWEROFFLOAD object that represents this low power protocol offload.

## -returns

Returns a [**NET_POWER_OFFLOAD_TYPE**](../netpoweroffload/ne-netpoweroffload-_net_power_offload_type.md) value that specifies the offload type.

## -remarks

The client driver must only call **NetPowerOffloadGetType** during a power transition, typically from its *[EVT_WDF_DEVICE_ARM_WAKE_FROM_SX](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md)*, *[EVT_WDF_DEVICE_ARM_WAKE_FROM_S0](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_s0.md)*, or *[EVT_NET_DEVICE_PREVIEW_POWER_OFFLOAD](../netdevice/nc-netdevice-evt_net_device_preview_power_offload.md)* callback function. Otherwise, the call results in a system bugcheck.

## -see-also

[Configuring power management](/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_POWER_OFFLOAD_TYPE**](../netpoweroffload/ne-netpoweroffload-_net_power_offload_type.md)

[**NET_POWER_OFFLOAD_LIST**](../netpoweroffloadlist/ns-netpoweroffloadlist-_net_power_offload_list.md)
