---
UID: NF:netadapteroffload.NetAdapterOffloadSetGsoCapabilities
title: NetAdapterOffloadSetGsoCapabilities function (netadapteroffload.h)
description: The NetAdapterOffloadSetChecksumCapabilities function sets the hardware Generic Segmentation Offload (GSO) capabilities of a network adapter.
tech.root: netvista
ms.date: 10/09/2020
keywords: ["NetAdapterOffloadSetGsoCapabilities function"]
f1_keywords:
 - "netadapteroffload/NetAdapterOffloadSetGsoCapabilities"
ms.keywords: NetAdapterOffloadSetGsoCapabilities
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
- NetAdapterOffloadSetGsoCapabilities
product:
- Windows
targetos: Windows
ms.custom: Fe
---

# NetAdapterOffloadSetGsoCapabilities function


## -description

> [!WARNING]
> Some information in this topic relates to pre-released product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 2004.
>
> Currently, NetAdapterCx client drivers cannot be certified.

The **NetAdapterOffloadSetGsoCapabilities** function sets the hardware [Generic Segmentation Offload (GSO)](/windows-hardware/drivers/netcx/gso-offload) capabilities of a network adapter.

## -parameters

### -param Adapter

[_In_] A handle to a NETADAPTER object that the client driver obtained from a previous call to [**NetAdapterCreate**](../netadapter/nf-netadapter-netadaptercreate.md).

### -param HardwareCapabilities

[_In_] A pointer to a driver-allocated and initialized [**NET_ADAPTER_OFFLOAD_GSO_CAPABILITIES**](ns-netadapteroffload-_net_adapter_offload_gso_capabilities.md) structure that describes the hardware's GSO capabilities.

## -remarks

Client drivers typically call this function from within their [*EvtDevicePrepareHardware*](../wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware.md) callback, but **must** call this function before calling [**NetAdapterStart**](../netadapter/nf-netadapter-netadapterstart.md).

## -see-also

[Generic Segmentation Offload](/windows-hardware/drivers/netcx/gso-offload)

[**NetAdapterCreate**](../netadapter/nf-netadapter-netadaptercreate.md)

[**NET_ADAPTER_OFFLOAD_GSO_CAPABILITIES**](ns-netadapteroffload-_net_adapter_offload_gso_capabilities.md)

[**NET_ADAPTER_OFFLOAD_GSO_CAPABILITIES_INIT**](nf-netadapteroffload-net_adapter_offload_gso_capabilities_init.md)

[*EVT_NET_ADAPTER_OFFLOAD_SET_GSO*](nc-netadapteroffload-evt_net_adapter_offload_set_gso.md)

[**NetAdapterStart**](../netadapter/nf-netadapter-netadapterstart.md)
