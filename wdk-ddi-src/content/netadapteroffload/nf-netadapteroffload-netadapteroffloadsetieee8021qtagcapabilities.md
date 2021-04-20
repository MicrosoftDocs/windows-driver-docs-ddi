---
UID: NF:netadapteroffload.NetAdapterOffloadSetIeee8021qTagCapabilities
tech.root: netvista
title: NetAdapterOffloadSetIeee8021qTagCapabilities
ms.date: 04/15/2021
ms.topic: language-reference
targetos: Windows
description: NetAdapterOffloadSetIeee8021qTagCapabilities sets the IEEE 802.1 priority and VLAN tagging capabilities of a network adapter.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: netadapteroffload.h
req.idl: 
req.include-header: netadaptercx.h
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - netadapteroffload.h
api_name:
 - NetAdapterOffloadSetIeee8021qTagCapabilities
f1_keywords:
 - NetAdapterOffloadSetIeee8021qTagCapabilities
 - netadapteroffload/NetAdapterOffloadSetIeee8021qTagCapabilities
dev_langs:
 - c++
---

## -description

The **NetAdapterOffloadSetIeee8021qTagCapabilities** function sets the IEEE 802.1 priority tagging and virtual LAN (VLAN) tagging capabilities of a network adapter.

## -parameters

### -param Adapter

[_In_] A handle to a NETADAPTER object that the client driver obtained from a previous call to [**NetAdapterCreate**](../netadapter/nf-netadapter-netadaptercreate.md).

### -param HardwareCapabilities

[In_] A pointer to a driver-allocated and initialized [**NET_ADAPTER_OFFLOAD_IEEE8021Q_TAG_CAPABILITIES**](ns-netadapteroffload-net_adapter_offload_ieee8021q_tag_capabilities.md) structure that describes the hardware's 802.1 priority tagging and VLAN tagging capabilities.

## -remarks

Client drivers typically call this function from within their [*EvtDevicePrepareHardware*](../wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware.md) callback, but **must** call this function before calling [**NetAdapterStart**](../netadapter/nf-netadapter-netadapterstart.md).

## -see-also

[**NET_ADAPTER_OFFLOAD_IEEE8021Q_TAG_CAPABILITIES**](ns-netadapteroffload-net_adapter_offload_ieee8021q_tag_capabilities.md)

[**NET_ADAPTER_OFFLOAD_TX_CHECKSUM_CAPABILITIES_INIT**](nf-netadapteroffload-net_adapter_offload_ieee8021q_tag_capabilities_init.md)

