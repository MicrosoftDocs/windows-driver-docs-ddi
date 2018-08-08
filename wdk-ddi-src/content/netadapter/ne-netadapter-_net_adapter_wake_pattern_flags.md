---
UID: NE:netadapter._NET_ADAPTER_WAKE_PATTERN_FLAGS
title: _NET_ADAPTER_WAKE_PATTERN_FLAGS
author: windows-driver-content
description: Specifies wake patterns that an adapter supports.
ms.assetid: ef1fc7e0-e739-4915-a5ac-924bdfd78cb8
ms.author: windowsdriverdev
ms.date: 02/05/2018
ms.topic: enum
ms.keywords: _NET_ADAPTER_WAKE_PATTERN_FLAGS, NET_ADAPTER_WAKE_PATTERN_FLAGS, 
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.typenames: NET_ADAPTER_WAKE_PATTERN_FLAGS
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netadapter.h
apiname: 
-	NET_ADAPTER_WAKE_PATTERN_FLAGS
product:
-	Windows
targetos: Windows
req.product: Windows 10 or later.
---

# _NET_ADAPTER_WAKE_PATTERN_FLAGS enumeration

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

Specifies wake patterns that an adapter supports.

## -enum-fields

### -field NET_ADAPTER_WAKE_BITMAP_PATTERN : 
If this flag is set, the network adapter is enabled to generate a wake-up event when it receives a packet that matches a configured bitmap pattern.

### -field NET_ADAPTER_WAKE_MAGIC_PACKET : 
If this flag is set, the network adapter is enabled to generate a wake-up event when it receives a WOL magic packet. A *magic packet* contains within its payload a string of six bytes with a value of 0xFF, followed immediately by 16 contiguous copies of the receiving network adapter's media access control (MAC) address.

### -field NET_ADAPTER_WAKE_IPV4_TCP_SYN : 
If this flag is set, the network adapter is enabled to generate a wake-up event when it receives an IPv4 TCP SYN packet. Remote hosts send TCP SYN packets to initiate a TCP connection to the local computer.

### -field NET_ADAPTER_WAKE_IPV6_TCP_SYN : 
If this flag is set, the network adapter is enabled to generate a wake-up event when it receives an IPv6 TCP SYN packet.

### -field NET_ADAPTER_WAKE_IPV4_DEST_ADDR_WILDCARD : 
If this flag is set, the network adapter must treat as wildcard values any zero-filled, or unspecified, values for IPv4 addresses and TCP/UDP ports in a WOL pattern. In this way, the wildcard value matches any IPv4 address and any port value of the incoming packet in the location specified by the WOL pattern.

If this flag is set, the network adapter is enabled to generate a wake-up event if the following pattern-matching conditions are true:

- Any value from the incoming packet in the location specified by the WOL pattern is a match, if the WOL pattern for that location contains a wildcard value.
- A value from the incoming packet in the location specified by the WOL pattern is a match if the WOL pattern for that location contains a nonzero value that equals the packet's value.

> [!NOTE]
> Wildcard values that are enabled by this flag can include unspecified IPv4 source and destination addresses, as well as unspecified source and destination ports.

### -field NET_ADAPTER_WAKE_IPV6_DEST_ADDR_WILDCARD : 
If this flag is set, the network adapter must treat as wildcard values any zero-filled, or unspecified, values for IPv6 addresses and TCP/UDP ports in a WOL pattern. In this way, the wildcard value matches any IPv6 address and any port value of the incoming packet in the location specified by the WOL pattern.

If this flag is set, the network adapter is enabled to generate a wake-up event if the following pattern-matching conditions are true:

- Any value from the incoming packet in the location specified by the WOL pattern is a match, if the WOL pattern for that location contains a wildcard value.
- A value from the incoming packet in the location specified by the WOL pattern is a match if the WOL pattern for that location contains a nonzero value that equals the packet's value.

> [!NOTE]
> Wildcard values that are enabled by this flag can include unspecified IPv6 source and destination addresses, as well as unspecified source and destination ports.

### -field NET_ADAPTER_WAKE_EAPOL_REQUEST_ID_MESSAGE : 
If this flag is set, the network adapter is enabled to generate a wake-up event when it receives an EAPOL request identifier message.


## -remarks

The **NET_ADAPTER_WAKE_PATTERN_FLAGS** enumeration is used to specify supported statistics in the [NET_ADAPTER_POWER_CAPABILITIES](ns-netadapter-_net_adapter_power_capabilities.md) structure.

The client driver passes an initialized **NET_ADAPTER_POWER_CAPABILITIES** structure as an input parameter value to [NetAdapterSetPowerCapabilities](nf-netadapter-netadaptersetpowercapabilities.md).



## -see-also

[NDIS_PM_PARAMETERS](../ntddndis/ns-ntddndis-_ndis_pm_parameters.md)