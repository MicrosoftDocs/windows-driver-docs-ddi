---
UID: NF:netadapteroffload.NetAdapterOffloadSetRscCapabilities
title: NetAdapterOffloadSetRscCapabilities function (netadapteroffload.h)
description: The NetAdapterOffloadSetRscCapabilities function sets the hardware receive segment coalescence (RSC) offload capabilities of a network adapter.
tech.root: netvista
ms.assetid: d3e3c034-55cc-4324-8e03-b158f1ed8b03
ms.date: 11/07/2019
keywords: ["NetAdapterOffloadSetRscCapabilities function"]
ms.keywords: NetAdapterOffloadSetRscCapabilities
req.header: netadapteroffload.h
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
 - NetAdapterOffloadSetRscCapabilities
 - netadapteroffload/NetAdapterOffloadSetRscCapabilities
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - netadaptercxstub.lib
api_name:
 - NetAdapterOffloadSetRscCapabilities
product:
 - Windows
---

# NetAdapterOffloadSetRscCapabilities function


## -description

The **NetAdapterOffloadSetRscCapabilities** function sets the hardware receive segment coalescence (RSC) offload capabilities of a network adapter.

## -parameters

### -param Adapter

A handle to a NETADAPTER object that the client driver obtained from a previous call to [**NetAdapterCreate**](../netadapter/nf-netadapter-netadaptercreate.md).

### -param HardwareCapabilities

A pointer to a driver-allocated and initialized [**NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES**](../netadapteroffload/ns-netadapteroffload-_net_adapter_offload_rsc_capabilities.md) structure that describes the hardware's RSC offload capabilities.

## -returns

This function does not return a value.

## -remarks

Client drivers typically call this function from within their [*EvtDevicePrepareHardware*](../wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware.md) callback, but **must** call this function before calling [**NetAdapterStart**](../netadapter/nf-netadapter-netadapterstart.md).

## -see-also

[Receive Segment Coalescing offload](/windows-hardware/drivers/netcx/rsc-offload)

[**NetAdapterCreate**](../netadapter/nf-netadapter-netadaptercreate.md)

[**NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES**](../netadapteroffload/ns-netadapteroffload-_net_adapter_offload_rsc_capabilities.md)

[**NET_ADAPTER_OFFLOAD_RSC_CAPABILITIES_INIT**](../netadapteroffload/nf-netadapteroffload-net_adapter_offload_rsc_capabilities_init.md)

[*EVT_NET_ADAPTER_OFFLOAD_SET_RSC*](../netadapteroffload/nc-netadapteroffload-evt_net_adapter_offload_set_rsc.md)

[**NetAdapterStart**](../netadapter/nf-netadapter-netadapterstart.md)