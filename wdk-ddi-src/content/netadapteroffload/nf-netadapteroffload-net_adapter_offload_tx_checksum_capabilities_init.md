---
UID: NF:netadapteroffload.NET_ADAPTER_OFFLOAD_TX_CHECKSUM_CAPABILITIES_INIT
title: NET_ADAPTER_OFFLOAD_TX_CHECKSUM_CAPABILITIES_INIT function (netadapteroffload.h)
description: The NET_ADAPTER_OFFLOAD_TX_CHECKSUM_CAPABILITIES_INIT method initializes a NET_ADAPTER_OFFLOAD_TX_CHECKSUM_CAPABILITIES structure.
tech.root: netvista
ms.assetid: 
ms.date: 08/10/2020
keywords: ["NET_ADAPTER_OFFLOAD_TX_CHECKSUM_CAPABILITIES_INIT function"]
f1_keywords:
 - "netadapteroffload/NET_ADAPTER_OFFLOAD_TX_CHECKSUM_CAPABILITIES_INIT"
ms.keywords: NET_ADAPTER_OFFLOAD_TX_CHECKSUM_CAPABILITIES_INIT
req.header: netadapter.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.29
req.umdf-ver:
req.lib: netadaptercxstub.lib
req.dll:
req.irql: 
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
- NET_ADAPTER_OFFLOAD_TX_CHECKSUM_CAPABILITIES_INIT
product:
- Windows
targetos: Windows
ms.custom: Fe
---

# NET_ADAPTER_OFFLOAD_TX_CHECKSUM_CAPABILITIES_INIT function

## -description

The **NET_ADAPTER_OFFLOAD_TX_CHECKSUM_CAPABILITIES_INIT** method initializes a [**NET_ADAPTER_OFFLOAD_TX_CHECKSUM_CAPABILITIES**](ns-netadapteroffload-_net_adapter_offload_tx_checksum_capabilities.md) structure.

## -parameters

### -param TxChecksumCapabilities

A pointer to a driver-allocated [**NET_ADAPTER_OFFLOAD_TX_CHECKSUM_CAPABILITIES**](ns-netadapteroffload-_net_adapter_offload_tx_checksum_capabilities.md) structure.

### -param Layer3Flags

Flags specifying the layer 3 protocol variations that the NIC can successfully perform Tx checksum on.

### -param EvtAdapterOffloadSetTxChecksum

A pointer to the client driver's implementation of the [*EVT_NET_ADAPTER_OFFLOAD_SET_TX_CHECKSUM*](nc-netadapteroffload-evt_net_adapter_offload_set_tx_checksum.md) callback function.

## -remarks

The client driver calls **NET_ADAPTER_OFFLOAD_TX_CHECKSUM_CAPABILITIES_INIT** to initialize a [**NET_ADAPTER_OFFLOAD_TX_CHECKSUM_CAPABILITIES**](ns-netadapteroffload-_net_adapter_offload_tx_checksum_capabilities.md) structure. The driver then passes the **NET_ADAPTER_OFFLOAD_TX_CHECKSUM_CAPABILITIES** structure as a parameter to the [**NetAdapterOffloadSetTxChecksumCapabilities**](nf-netadapteroffload-netadapteroffloadsettxchecksumcapabilities.md) method to register it.

## -see-also

[NetAdapterCx hardware offloads](/windows-hardware/drivers/netcx/netadaptercx-hardware-offloads)

[Checksum Offload](/windows-hardware/drivers/netcx/checksum-offload)

[**NET_ADAPTER_OFFLOAD_TX_CHECKSUM_CAPABILITIES**](ns-netadapteroffload-_net_adapter_offload_tx_checksum_capabilities.md)

[**NetAdapterOffloadSetTxChecksumCapabilities**](nf-netadapteroffload-netadapteroffloadsettxchecksumcapabilities.md)

[*EVT_NET_ADAPTER_OFFLOAD_SET_TX_CHECKSUM*](nc-netadapteroffload-evt_net_adapter_offload_set_tx_checksum.md)
