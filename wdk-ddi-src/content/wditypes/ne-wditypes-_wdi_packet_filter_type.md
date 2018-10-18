---
UID: NE:wditypes._WDI_PACKET_FILTER_TYPE
title: "_WDI_PACKET_FILTER_TYPE"
author: windows-driver-content
description: The WDI_PACKET_FILTER_TYPE enumeration defines the packet filter types.
old-location: netvista\wdi_packet_filter_type.htm
tech.root: netvista
ms.assetid: 252CE7F6-2DA7-45F8-97F0-85B51A0181C2
ms.date: 5/2/2018
ms.keywords: WDI_PACKET_FILTER_802_11_ALL_MULTICAST_MGMT, WDI_PACKET_FILTER_802_11_BROADCAST_CTRL, WDI_PACKET_FILTER_802_11_BROADCAST_MGMT, WDI_PACKET_FILTER_802_11_DIRECTED_CTRL, WDI_PACKET_FILTER_802_11_DIRECTED_MGMT, WDI_PACKET_FILTER_802_11_MULTICAST_MGMT, WDI_PACKET_FILTER_802_11_PROMISCUOUS_CTRL, WDI_PACKET_FILTER_802_11_PROMISCUOUS_MGMT, WDI_PACKET_FILTER_802_11_RAW_DATA, WDI_PACKET_FILTER_802_11_RAW_MGMT, WDI_PACKET_FILTER_ALL, WDI_PACKET_FILTER_ALL_MULTICAST, WDI_PACKET_FILTER_BROADCAST, WDI_PACKET_FILTER_DIRECTED, WDI_PACKET_FILTER_MULTICAST, WDI_PACKET_FILTER_NONE, WDI_PACKET_FILTER_PROMISCUOUS, WDI_PACKET_FILTER_TYPE, WDI_PACKET_FILTER_TYPE enumeration [Network Drivers Starting with Windows Vista], _WDI_PACKET_FILTER_TYPE, netvista.wdi_packet_filter_type, netvista.wifi_packet_filter_type, wditypes/WDI_PACKET_FILTER_802_11_ALL_MULTICAST_MGMT, wditypes/WDI_PACKET_FILTER_802_11_BROADCAST_CTRL, wditypes/WDI_PACKET_FILTER_802_11_BROADCAST_MGMT, wditypes/WDI_PACKET_FILTER_802_11_DIRECTED_CTRL, wditypes/WDI_PACKET_FILTER_802_11_DIRECTED_MGMT, wditypes/WDI_PACKET_FILTER_802_11_MULTICAST_MGMT, wditypes/WDI_PACKET_FILTER_802_11_PROMISCUOUS_CTRL, wditypes/WDI_PACKET_FILTER_802_11_PROMISCUOUS_MGMT, wditypes/WDI_PACKET_FILTER_802_11_RAW_DATA, wditypes/WDI_PACKET_FILTER_802_11_RAW_MGMT, wditypes/WDI_PACKET_FILTER_ALL, wditypes/WDI_PACKET_FILTER_ALL_MULTICAST, wditypes/WDI_PACKET_FILTER_BROADCAST, wditypes/WDI_PACKET_FILTER_DIRECTED, wditypes/WDI_PACKET_FILTER_MULTICAST, wditypes/WDI_PACKET_FILTER_NONE, wditypes/WDI_PACKET_FILTER_PROMISCUOUS, wditypes/WDI_PACKET_FILTER_TYPE
ms.topic: enum
req.header: wditypes.hpp
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wditypes.hpp
api_name:
-	WDI_PACKET_FILTER_TYPE
product:
- Windows
targetos: Windows
req.typenames: WDI_PACKET_FILTER_TYPE
---

# _WDI_PACKET_FILTER_TYPE enumeration


## -description


The WDI_PACKET_FILTER_TYPE enumeration defines the packet filter types.


## -enum-fields




### -field WDI_PACKET_FILTER_NONE

None.


### -field WDI_PACKET_FILTER_DIRECTED

Directed packets. Directed packets contain a destination address equal to the station address of the NIC.




### -field WDI_PACKET_FILTER_MULTICAST

Multicast address packets sent to addresses in the multicast address list. 




### -field WDI_PACKET_FILTER_ALL_MULTICAST

All multicast address packets, not just the ones enumerated in the multicast address list.




### -field WDI_PACKET_FILTER_BROADCAST

Broadcast packets.




### -field WDI_PACKET_FILTER_PROMISCUOUS

Specifies all packets regardless of whether VLAN filtering is enabled or not and whether the VLAN identifier matches or not.




### -field WDI_PACKET_FILTER_802_11_RAW_DATA

An 802.11 media access control (MAC) protocol data unit (MPDU) frame, which contains all of the data in the format received by the 802.11 station. When this filter is set, the driver must indicate every unmodified MPDU fragment before it indicates the MAC service data unit (MSDU) packet reassembled from the MPDU fragments. 



If an MPDU fragment is encrypted, it must not decrypt the fragment before it is indicated. However, the miniport driver must decrypt each MPDU fragment before reassembling and indicating the MSDU packet.



If enabled, this filter type only affects other standard packet filters, such as WDI_PACKET_FILTER_DIRECTED or WDI_PACKET_FILTER_BROADCAST.




### -field WDI_PACKET_FILTER_802_11_DIRECTED_MGMT

Directed 802.11 management packets. Directed packets contain a destination address equal to the station address of the NIC.




### -field WDI_PACKET_FILTER_802_11_BROADCAST_MGMT

Broadcast 802.11 management packets received by the 802.11 station.


### -field WDI_PACKET_FILTER_802_11_MULTICAST_MGMT

Multicast 802.11 management packets sent to addresses in the multicast address list.


### -field WDI_PACKET_FILTER_802_11_ALL_MULTICAST_MGMT

All multicast 802.11 management packets received by the 802.11 station, regardless of whether the destination address in the 802.11 MAC header is in the multicast address list.




### -field WDI_PACKET_FILTER_802_11_PROMISCUOUS_MGMT

All 802.11 management packets received by the 802.11 station.


### -field WDI_PACKET_FILTER_802_11_RAW_MGMT

An 802.11 MPDU management frame, which contains all of the data in the format received by the 802.11 station. When this filter is set, the driver must indicate every unmodified MPDU fragment before it indicates the MAC management protocol data unit (MMPDU) packet reassembled from the MPDU fragments. 



If enabled, this filter type only affects other 802.11 management packet filters, such as WDI_PACKET_FILTER_802_11_DIRECTED_MGMT or WDI_PACKET_FILTER_802_11_MULTICAST_MGMT.




### -field WDI_PACKET_FILTER_802_11_DIRECTED_CTRL

Directed 802.11 control packets. Directed packets contain a destination address equal to the station address of the NIC.




### -field WDI_PACKET_FILTER_802_11_BROADCAST_CTRL

Broadcast 802.11 control packets received by the 802.11 station.




### -field WDI_PACKET_FILTER_802_11_PROMISCUOUS_CTRL

All 802.11 control packets received by the 802.11 station.




### -field WDI_PACKET_FILTER_ALL

All packet types.

