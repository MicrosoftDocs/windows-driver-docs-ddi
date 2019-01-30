---
UID: NE:netadapter._NET_ADAPTER_POWER_FLAGS
title: _NET_ADAPTER_POWER_FLAGS (netadapter.h)
description: Specifies a client driver's power capabilities.
tech.root: netvista
ms.assetid: 880a2606-f7cb-4552-b89b-238abd062e3d
ms.date: 02/05/2018
ms.topic: enum
ms.keywords: _NET_ADAPTER_POWER_FLAGS, NET_ADAPTER_POWER_FLAGS, 
req.header: netadapter.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.21
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.alt-api:
req.alt-loc:
req.typenames: NET_ADAPTER_POWER_FLAGS
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netadapter.h
apiname: 
-	NET_ADAPTER_POWER_FLAGS
product:
-	Windows
targetos: Windows
product:
- Windows
---

# _NET_ADAPTER_POWER_FLAGS enumeration

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

Specifies a client driver's power capabilities.

## -enum-fields

### -field NET_ADAPTER_POWER_WAKE_PACKET_INDICATION : 
If this flag is set, the network adapter must be able to save the received packet that caused the adapter to generate a wake-up event.

If this flag is set, the client driver must be able to do the following with this packet after the network adapter transitions to a full-power state:

- The client driver must be able to indicate the packet by calling [NdisMIndicateReceiveNetBufferLists](../ndis/nf-ndis-ndismindicatereceivenetbufferlists.md). 
- The client driver must be able to issue an NDIS_STATUS_PM_WAKE_REASON status indication and must pass the packet with the indication. To indicate the received packet, the client calls [NetAdapterWdmGetNdisHandle](nf-netadapter-netadapterwdmgetndishandle.md), then calls [NdisMIndicateReceiveNetBufferLists](../ndis/nf-ndis-ndismindicatereceivenetbufferlists.md).

For more information about this power management capability, see [NDIS Wake Reason Status Indications](https://docs.microsoft.com/windows-hardware/drivers/network/ndis-wake-reason-status-indications).

### -field NET_ADAPTER_POWER_SELECTIVE_SUSPEND : 
Specifies that NetAdapterCx should suspend an idle network adapter by transitioning the adapter to a low-power state.

## -remarks

The **NET_ADAPTER_POWER_FLAGS** enumeration is used to specify power capabilities in the [NET_ADAPTER_POWER_CAPABILITIES](ns-netadapter-_net_adapter_power_capabilities.md) structure.

The client driver passes an initialized [NET_ADAPTER_POWER_CAPABILITIES](ns-netadapter-_net_adapter_power_capabilities.md) structure as an input parameter value to [NetAdapterSetPowerCapabilities](nf-netadapter-netadaptersetpowercapabilities.md).



## -see-also

[NET_ADAPTER_POWER_CAPABILITIES](ns-netadapter-_net_adapter_power_capabilities.md)

[NDIS_PM_CAPABILITIES](../ntddndis/ns-ntddndis-_ndis_pm_capabilities.md)
