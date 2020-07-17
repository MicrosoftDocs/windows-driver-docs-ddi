---
UID: NF:netadapteroffload.NetAdapterOffloadSetTxChecksumCapabilities
title: NetAdapterOffloadSetTxChecksumCapabilities function (netadapteroffload.h)
description: The NetAdapterOffloadSetChecksumCapabilities method sets the hardware Tx checksum offload capabilities of a network adapter.
tech.root: netvista
ms.assetid: 03dd8b75-0284-4c7a-8102-6ab0e12f3163
ms.date: 01/17/2019
keywords: ["NetAdapterOffloadSetTxChecksumCapabilities function"]
f1_keywords:
 - "netadapteroffload/NetAdapterOffloadSetTxChecksumCapabilities"
ms.keywords: NetAdapterOffloadSetTxChecksumCapabilities
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
- NetAdapterOffloadSetTxChecksumCapabilities
product:
- Windows
targetos: Windows
ms.custom: 19H1
---

# NetAdapterOffloadSetTxChecksumCapabilities function


## -description



The **NetAdapterOffloadSetTxChecksumCapabilities** method sets the hardware Tx checksum offload capabilities of a network adapter.

## -parameters

### -param Adapter

A handle to a NETADAPTER object that the client driver obtained from a previous call to [**NetAdapterCreate**](../netadapter/nf-netadapter-netadaptercreate.md).

### -param HardwareCapabilities

A pointer to a driver-allocated and initialized [**NET_ADAPTER_OFFLOAD_TX_CHECKSUM_CAPABILITIES**](../netadapteroffload/ns-netadapteroffload-_net_adapter_offload_tx_checksum_capabilities.md) structure that describes the hardware's Tx checksum offload capabilities.

## -remarks

Client drivers typically call this method from within their [*EvtDevicePrepareHardware*](../wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware.md) callback, but **must** call this method before calling [**NetAdapterStart**](../netadapter/nf-netadapter-netadapterstart.md).

## -see-also

[NetAdapterCx hardware offloads](https://docs.microsoft.com/windows-hardware/drivers/netcx/netadaptercx-hardware-offloads)

[**NetAdapterCreate**](../netadapter/nf-netadapter-netadaptercreate.md)

[**NET_ADAPTER_OFFLOAD_TX_CHECKSUM_CAPABILITIES**](../netadapteroffload/ns-netadapteroffload-_net_adapter_offload_tx_checksum_capabilities.md)

[**NET_ADAPTER_OFFLOAD_TX_CHECKSUM_CAPABILITIES_INIT**](../netadapteroffload/nf-netadapteroffload-net_adapter_offload_tx_checksum_capabilities_init.md)

[*EVT_NET_ADAPTER_OFFLOAD_SET_TX_CHECKSUM*](../netadapteroffload/nc-netadapteroffload-evt_net_adapter_offload_set_tx_checksum.md)

[**NetAdapterStart**](../netadapter/nf-netadapter-netadapterstart.md)
