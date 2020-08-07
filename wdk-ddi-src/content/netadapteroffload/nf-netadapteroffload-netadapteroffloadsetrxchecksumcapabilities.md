---
UID: NF:netadapteroffload.NetAdapterOffloadSetRxChecksumCapabilities
title: NetAdapterOffloadSetRxChecksumCapabilities function (netadapteroffload.h)
description: The NetAdapterOffloadSetChecksumCapabilities method sets the hardware Rx checksum offload capabilities of a network adapter.
tech.root: netvista
ms.assetid: 
ms.date: 08/10/2020
keywords: ["NetAdapterOffloadSetRxChecksumCapabilities function"]
f1_keywords:
 - "netadapteroffload/NetAdapterOffloadSetRxChecksumCapabilities"
ms.keywords: NetAdapterOffloadSetRxChecksumCapabilities
req.header: netadapter.h
req.include-header:
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
topic_type: 
- apiref
api_type: 
- LibDef
api_location: 
- netadaptercxstub.lib
api_name: 
- NetAdapterOffloadSetRxChecksumCapabilities
product:
- Windows
targetos: Windows
ms.custom: Fe
---

# NetAdapterOffloadSetRxChecksumCapabilities function

## -description

The **NetAdapterOffloadSetRxChecksumCapabilities** method sets the hardware Rx checksum offload capabilities of a network adapter.

## -parameters

### -param Adapter

A handle to a NETADAPTER object that the client driver obtained from a previous call to [**NetAdapterCreate**](../netadapter/nf-netadapter-netadaptercreate.md).

### -param HardwareCapabilities

A pointer to a driver-allocated and initialized [**NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES**](ns-netadapteroffload-_net_adapter_offload_rx_checksum_capabilities.md) structure that describes the hardware's Rx checksum offload capabilities.

## -remarks

Client drivers typically call this method from within their [*EvtDevicePrepareHardware*](../wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware.md) callback, but **must** call this method before calling [**NetAdapterStart**](../netadapter/nf-netadapter-netadapterstart.md).

## -see-also

[NetAdapterCx hardware offloads](/windows-hardware/drivers/netcx/netadaptercx-hardware-offloads)

[Checksum Offload](/windows-hardware/drivers/netcx/checksum-offload)

[**NetAdapterCreate**](../netadapter/nf-netadapter-netadaptercreate.md)

[**NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES**](ns-netadapteroffload-_net_adapter_offload_rx_checksum_capabilities.md)

[**NET_ADAPTER_OFFLOAD_RX_CHECKSUM_CAPABILITIES_INIT**](nf-netadapteroffload-net_adapter_offload_rx_checksum_capabilities_init.md)

[*EVT_NET_ADAPTER_OFFLOAD_SET_RX_CHECKSUM*](nc-netadapteroffload-evt_net_adapter_offload_set_rx_checksum.md)

[**NetAdapterStart**](../netadapter/nf-netadapter-netadapterstart.md)
