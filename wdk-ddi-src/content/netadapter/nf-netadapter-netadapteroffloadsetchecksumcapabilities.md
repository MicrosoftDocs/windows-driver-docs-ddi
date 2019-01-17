---
UID: NF:netadapter.NetAdapterOffloadSetChecksumCapabilities
title: NetAdapterOffloadSetChecksumCapabilities function
description: The NetAdapterOffloadSetChecksumCapabilities method sets the hardware checksum offload capabilities of a network adapter.
tech.root: netvista
ms.assetid: 103b7d8e-b6bd-497a-9ee8-18b66e13a9ab
ms.date: 07/19/2018
ms.topic: function
ms.keywords: NetAdapterOffloadSetChecksumCapabilities
req.header: netadapter.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.27
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
topic_type: 
-	apiref
api_type: 
-	LibDef
api_location: 
-	netadaptercxstub.lib
api_name: 
-	NetAdapterOffloadSetChecksumCapabilities
product:
- Windows
targetos: Windows


ms.custom: RS5
---

# NetAdapterOffloadSetChecksumCapabilities function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The **NetAdapterOffloadSetChecksumCapabilities** method sets the hardware checksum offload capabilities of a network adapter.

## -parameters

### -param Adapter

A handle to a NETADAPTER object that the client driver obtained from a previous call to [**NetAdapterCreate**](nf-netadapter-netadaptercreate.md).

### -param HardwareCapabilities

A pointer to a driver-allocated and initialized [**NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES**](ns-netadapter-_net_adapter_offload_checksum_capabilities.md) structure that describes the hardware's checksum offload capabilities.

### -param EvtAdapterOffloadSetChecksum

A pointer to the client driver's implementation of the [*EVT_NET_ADAPTER_OFFLOAD_SET_CHECKSUM*](nc-netadapter-evt_net_adapter_offload_set_checksum.md) callback function.

## -returns

This method does not return a value.

## -remarks

Client drivers typically call this method from within their [*EvtDevicePrepareHardware*](../wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware.md) callback, but **must** call this method before calling [**NetAdapterStart**](nf-netadapter-netadapterstart.md).

## -see-also

[NetAdapterCx hardware offloads](https://docs.microsoft.com/windows-hardware/drivers/netcx/netadaptercx-hardware-offloads)

[**NetAdapterCreate**](nf-netadapter-netadaptercreate.md)

[**NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES**](ns-netadapter-_net_adapter_offload_checksum_capabilities.md)

[**NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES_INIT**](nf-netadapter-net_adapter_offload_checksum_capabilities_init.md)

[*EVT_NET_ADAPTER_OFFLOAD_SET_CHECKSUM*](nc-netadapter-evt_net_adapter_offload_set_checksum.md)

[**NetAdapterStart**](nf-netadapter-netadapterstart.md)
