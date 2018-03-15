---
UID: NC:netadapter.EVT_NET_ADAPTER_SET_CAPABILITIES
title: EVT_NET_ADAPTER_SET_CAPABILITIES
author: windows-driver-content
description: The client driver's implementation of the EVT_NET_ADAPTER_SET_CAPABILITIES event callback function that sets the capabilities of the network adapter.
ms.assetid: fd02cb14-1bf4-4c76-a01a-9f03be87e68a
ms.author: windowsdriverdev
ms.date: 02/05/2018
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: netadapter.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.21
req.umdf-ver:
req.lib:
req.dll:
req.irql: PASSIVE_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topictype: 
-	apiref
apitype: 
-	UserDefined
apilocation: 
-	netadapter.h
apiname: 
-	EVT_NET_ADAPTER_SET_CAPABILITIES
product: Windows
targetos: Windows
req.typenames: 
req.product: Windows 10 or later.
---

# EVT_NET_ADAPTER_SET_CAPABILITIES callback function

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

The client driver's implementation of the **EVT_NET_ADAPTER_SET_CAPABILITIES** event callback function that sets the capabilities of the network adapter.

## -prototype

```c++
//Declaration

EVT_NET_ADAPTER_SET_CAPABILITIES EvtNetAdapterSetCapabilities; 

// Definition

NTSTATUS EvtNetAdapterSetCapabilities 
(
	_In_	NETADAPTER	Adapter
)
{...}

typedef EVT_NET_ADAPTER_SET_CAPABILITIES *PFN_NET_ADAPTER_SET_CAPABILITIES;

```

## -parameters

### -param Adapter: 
The network adapter object that the client created in a prior call to [NetAdapterCreate](nf-netadapter-netadaptercreate.md).


## -returns

If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE.

If this function returns an [NTSTATUS](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values) error code, the device fails to initialize.

## -remarks

To register an *EVT_NET_ADAPTER_SET_CAPABILITIES* callback function, the client driver must call [NetAdapterCreate](nf-netadapter-netadaptercreate.md).

NetAdapterCx calls *EVT_NET_ADAPTER_SET_CAPABILITIES* after [*EVT_WDF_DEVICE_PREPARE_HARDWARE*](../wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware.md) but before [*EVT_WDF_DEVICE_D0_ENTRY*](../wdfdevice/nc-wdfdevice-evt_wdf_device_d0_entry.md).

NetAdapterCx calls *EVT_NET_ADAPTER_SET_CAPABILITIES* once per device start.

In this function, the client typically sets the adapter's link and MAC capabilities, power capabilities and MTU size. To do so, it uses the following methods:

- [NetAdapterSetLinkLayerMtuSize](nf-netadapter-netadaptersetlinklayermtusize.md) 
- [NetAdapterSetLinkLayerCapabilities](nf-netadapter-netadaptersetlinklayercapabilities.md)
- [NetAdapterSetPowerCapabilities](nf-netadapter-netadaptersetpowercapabilities.md)

Optionally, the client can also call:

- [NetAdapterSetCurrentLinkState](nf-netadapter-netadaptersetcurrentlinkstate.md)
- [NetAdapterSetDataPathCapabilities](nf-netadapter-netadaptersetdatapathcapabilities.md)
- [NetAdapterSetReceiveScalingCapabilities](../netreceivescaling/nf-netreceivescaling-netadaptersetreceivescalingcapabilities.md)

To set an attribute that does not have equivalent NetAdapter functionality, for example to report offload capabilities, call [NdisMSetMiniportAttributes](../ndis/nf-ndis-ndismsetminiportattributes.md) from *EvtNetAdapterSetCapabilities*. Use [NetAdapterWdmGetNdisHandle](nf-netadapter-netadapterwdmgetndishandle.md) to get the NDIS handle.

The minimum NetAdapterCx version for *EVT_NET_ADAPTER_SET_CAPABILITIES* is 1.0.

### Example



## -see-also

[NetAdapterSetDataPathCapabilities](nf-netadapter-netadaptersetdatapathcapabilities.md)

[NetAdapterSetLinkLayerCapabilities](nf-netadapter-netadaptersetlinklayercapabilities.md)

[NetAdapterSetPowerCapabilities](nf-netadapter-netadaptersetpowercapabilities.md)