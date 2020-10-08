---
UID: NF:netadapteroffload.NetAdapterOffloadSetTxChecksumCapabilities
title: NetAdapterOffloadSetTxChecksumCapabilities function (netadapteroffload.h)
description: The NetAdapterOffloadSetTxChecksumCapabilities function sets the hardware Tx checksum offload capabilities of a network adapter.
tech.root: netvista
ms.assetid: 
ms.date: 10/06/2020
keywords: ["NetAdapterOffloadSetTxChecksumCapabilities function"]
f1_keywords:
 - "netadapteroffload/NetAdapterOffloadSetTxChecksumCapabilities"
ms.keywords: NetAdapterOffloadSetTxChecksumCapabilities
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
ms.custom: Fe
---

# NetAdapterOffloadSetTxChecksumCapabilities function

## -description

The **NetAdapterOffloadSetTxChecksumCapabilities** function sets the hardware Tx checksum offload capabilities of a network adapter.

## -parameters

### -param Adapter

[_In_] A handle to a NETADAPTER object that the client driver obtained from a previous call to [**NetAdapterCreate**](../netadapter/nf-netadapter-netadaptercreate.md).

### -param HardwareCapabilities

[_In_] A pointer to a driver-allocated and initialized [**NET_ADAPTER_OFFLOAD_TX_CHECKSUM_CAPABILITIES**](ns-netadapteroffload-_net_adapter_offload_tx_checksum_capabilities.md) structure that describes the hardware's Tx checksum offload capabilities.

## -remarks

Client drivers typically call this function from within their [*EvtDevicePrepareHardware*](../wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware.md) callback, but **must** call this function before calling [**NetAdapterStart**](../netadapter/nf-netadapter-netadapterstart.md).

## -see-also

[Checksum Offload](/windows-hardware/drivers/netcx/checksum-offload)

[**NetAdapterCreate**](../netadapter/nf-netadapter-netadaptercreate.md)

[**NET_ADAPTER_OFFLOAD_TX_CHECKSUM_CAPABILITIES**](ns-netadapteroffload-_net_adapter_offload_tx_checksum_capabilities.md)

[**NET_ADAPTER_OFFLOAD_TX_CHECKSUM_CAPABILITIES_INIT**](nf-netadapteroffload-net_adapter_offload_tx_checksum_capabilities_init.md)

[*EVT_NET_ADAPTER_OFFLOAD_SET_TX_CHECKSUM*](nc-netadapteroffload-evt_net_adapter_offload_set_tx_checksum.md)

[**NetAdapterStart**](../netadapter/nf-netadapter-netadapterstart.md)
