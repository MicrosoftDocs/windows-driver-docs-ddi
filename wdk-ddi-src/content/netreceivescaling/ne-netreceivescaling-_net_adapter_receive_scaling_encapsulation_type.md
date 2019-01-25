---
UID: NE:netreceivescaling._NET_ADAPTER_RECEIVE_SCALING_ENCAPSULATION_TYPE
title: _NET_ADAPTER_RECEIVE_SCALING_ENCAPSULATION_TYPE (netreceivescaling.h)
description: The NET_ADAPTER_RECEIVE_SCALING_ENCAPSULATION_TYPE enumeration specifies packet encapsulation technologies an RSS-capable NIC is able to bypass.
tech.root: netvista
ms.assetid: b5225e1b-e077-48b6-8065-40d3805589e2
ms.date: 03/07/2018
ms.topic: enum
ms.keywords: _NET_ADAPTER_RECEIVE_SCALING_ENCAPSULATION_TYPE, NET_ADAPTER_RECEIVE_SCALING_ENCAPSULATION_TYPE, 
req.header: netreceivescaling.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.25
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: NET_ADAPTER_RECEIVE_SCALING_ENCAPSULATION_TYPE
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netreceivescaling.h
apiname: 
-	_NET_ADAPTER_RECEIVE_SCALING_ENCAPSULATION_TYPE
product:
-	Windows
targetos: Windows
---

# _NET_ADAPTER_RECEIVE_SCALING_ENCAPSULATION_TYPE enumeration

## -description
> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The **NET_ADAPTER_RECEIVE_SCALING_ENCAPSULATION_TYPE** enumeration specifies packet encapsulation technologies an RSS-capable NIC is able to bypass.

## -enum-fields

### -field NetAdapterReceiveScalingEncapsulationTypeNone : 
Indicates that the hardware cannot bypass any encapsulation technologies.

### -field NetAdapterReceiveScalingEncapsulationTypeNVGre : 
Indicates that the hardware understands how to bypass [NV-GRE encapsulation](https://docs.microsoft.com/windows-server/networking/sdn/technologies/hyper-v-network-virtualization/hyperv-network-virtualization-technical-details-windows-server#generic-routing-encapsulation-nvgre).

### -field NetAdapterReceiveScalingEncapsulationTypeVXLan : 
Indicates that the hardware understands how to bypass [VXLan encapsulation](https://docs.microsoft.com/windows-server/networking/sdn/technologies/hyper-v-network-virtualization/hyperv-network-virtualization-technical-details-windows-server#virtual-extensible-local-area-network-vxlan).

### -field NetAdapterReceiveScalingEncapsulationTypeVLan : 
Indicates that the hardware understands how to bypass [VLan encapsulation](https://docs.microsoft.com/windows-server/networking/sdn/technologies/hyper-v-network-virtualization/hyperv-network-virtualization-technical-details-windows-server#VirtualNetworks).

## -remarks
The **ReceiveScalingEncapsulationTypes** member of the [NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES](ns-netreceivescaling-_net_adapter_receive_scaling_capabilities.md) structure contains information for both outer (transport) and inner (tunnel) encapsulation types that the NIC is capable of bypassing. These members each contain a bitwise OR of **NET_ADAPTER_RECEIVE_SCALING_ENCAPSULATION_TYPE** constants.



## -see-also
[NetAdapterCx Receive Side Scaling](https://docs.microsoft.com/windows-hardware/drivers/netcx/netadaptercx-receive-side-scaling-rss-)

[Hyper-V Network Virtualization Technical Details in Windows Server 2016](https://docs.microsoft.com/windows-server/networking/sdn/technologies/hyper-v-network-virtualization/hyperv-network-virtualization-technical-details-windows-server)
