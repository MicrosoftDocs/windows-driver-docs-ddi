---
UID: NF:netadapter.NetAdapterOffloadSetChecksumCapabilities
title: NetAdapterOffloadSetChecksumCapabilities function (netadapter.h)
description: The NetAdapterOffloadSetChecksumCapabilities function sets the hardware checksum offload capabilities of a network adapter.
tech.root: netvista
ms.assetid: 103b7d8e-b6bd-497a-9ee8-18b66e13a9ab
ms.date: 01/18/2019
keywords: ["NetAdapterOffloadSetChecksumCapabilities function"]
ms.keywords: NetAdapterOffloadSetChecksumCapabilities
req.header: netadapter.h
req.include-header: netadaptercx.h 
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.29
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
ms.custom: 19H1
f1_keywords:
 - NetAdapterOffloadSetChecksumCapabilities
 - netadapter/NetAdapterOffloadSetChecksumCapabilities
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - netadaptercxstub.lib
api_name:
 - NetAdapterOffloadSetChecksumCapabilities
---

# NetAdapterOffloadSetChecksumCapabilities function


## -description

The **NetAdapterOffloadSetChecksumCapabilities** function sets the hardware checksum offload capabilities of a network adapter.

## -parameters

### -param Adapter

A handle to a NETADAPTER object that the client driver obtained from a previous call to [**NetAdapterCreate**](nf-netadapter-netadaptercreate.md).

### -param HardwareCapabilities

A pointer to a driver-allocated and initialized [**NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES**](ns-netadapter-_net_adapter_offload_checksum_capabilities.md) structure that describes the hardware's checksum offload capabilities.

## -remarks

Client drivers typically call this function from within their [*EvtDevicePrepareHardware*](../wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware.md) callback, but **must** call this function before calling [**NetAdapterStart**](nf-netadapter-netadapterstart.md).

## -see-also

[NetAdapterCx hardware offloads](/windows-hardware/drivers/netcx/netadaptercx-hardware-offloads)

[**NetAdapterCreate**](nf-netadapter-netadaptercreate.md)

[**NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES**](ns-netadapter-_net_adapter_offload_checksum_capabilities.md)

[**NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES_INIT**](nf-netadapter-net_adapter_offload_checksum_capabilities_init.md)

[*EVT_NET_ADAPTER_OFFLOAD_SET_CHECKSUM*](nc-netadapter-evt_net_adapter_offload_set_checksum.md)

[**NetAdapterStart**](nf-netadapter-netadapterstart.md)