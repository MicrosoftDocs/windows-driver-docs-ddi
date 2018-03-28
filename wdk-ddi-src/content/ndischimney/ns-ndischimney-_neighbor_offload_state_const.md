---
UID: NS:ndischimney._NEIGHBOR_OFFLOAD_STATE_CONST
title: "_NEIGHBOR_OFFLOAD_STATE_CONST"
author: windows-driver-content
description: The NEIGHBOR_OFFLOAD_STATE_CONST structure contains the constant variables of a neighbor state object.
old-location: netvista\neighbor_offload_state_const.htm
old-project: netvista
ms.assetid: 1c79a3d6-c365-4740-a2e0-94333b70d8cc
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PNEIGHBOR_OFFLOAD_STATE_CONST, NEIGHBOR_OFFLOAD_STATE_CONST, NEIGHBOR_OFFLOAD_STATE_CONST structure [Network Drivers Starting with Windows Vista], PNEIGHBOR_OFFLOAD_STATE_CONST, PNEIGHBOR_OFFLOAD_STATE_CONST structure pointer [Network Drivers Starting with Windows Vista], _NEIGHBOR_OFFLOAD_STATE_CONST, ndischimney/NEIGHBOR_OFFLOAD_STATE_CONST, ndischimney/PNEIGHBOR_OFFLOAD_STATE_CONST, netvista.neighbor_offload_state_const, tcp_chim_struct_3e21fef6-9a3c-4eba-b6fb-31af70a3eaaa.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndischimney.h
req.include-header: Ndischimney.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
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
-	ndischimney.h
api_name:
-	NEIGHBOR_OFFLOAD_STATE_CONST
product: Windows
targetos: Windows
req.typenames: NEIGHBOR_OFFLOAD_STATE_CONST, *PNEIGHBOR_OFFLOAD_STATE_CONST
---

# _NEIGHBOR_OFFLOAD_STATE_CONST structure


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

The NEIGHBOR_OFFLOAD_STATE_CONST structure contains the constant variables of a neighbor state
  object.


## -struct-fields




### -field Header

An 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569062">OFFLOAD_STATE_HEADER</a> structure. NDIS
     sets the 
     <b>Length</b> member of 
     <b>Header</b> to the size, in bytes, of the NEIGHBOR_OFFLOAD_STATE_CONST structure. The 
     <b>RecognizedOptions</b> member of 
     <b>Header</b> is reserved.


### -field DlSourceAddress

When non-<b>NULL</b>, a 32-byte source MAC address. The offload target must support software-configurable
     MAC addresses and it must set the source MAC address of all packets that it sends on the offloaded
     connection to 
     <b>DlSourceAddress</b> . 
     

When <b>NULL</b>, the offload target ignores this parameter and sets the source MAC address to the value
     that was configured for the network interface.

If the network interface has one or more multicast addresses enabled, the offloaded connection must
     allow receive traffic to arrive on either the configured MAC address or the multicast addresses. The
     configured MAC address is either 
     <b>DlSourceAddress</b> or, if 
     <b>DlSourceAddress</b> is zero, the MAC address for the network interface.


### -field VlanId

An unsigned 12-bit binary number that identifies the virtual LAN (VLAN) to which a packet belongs.
     The 
     <b>VlanId</b> ID pertains only to packets that are sent or received using the neighbor state object.
     

When <b>NULL</b>, the offload target should use any VLAN IDs that have been configured for its network
     interface. The offload target's 
     <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a> function
     reads such VLAN IDs from the registry.


## -remarks



For a description of how an offload target uses the 
    <b>VlanId</b> member, see 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff570937">802.1Q
    and 802.1p Processing on an Offloaded TCP Connection</a>.




## -see-also




<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568323">NEIGHBOR_OFFLOAD_STATE_CACHED</a>



<a href="https://msdn.microsoft.com/94a35d0f-3585-45d0-bba8-0b4a8ebbe883">
   NEIGHBOR_OFFLOAD_STATE_DELEGATED</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569062">OFFLOAD_STATE_HEADER</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NEIGHBOR_OFFLOAD_STATE_CONST structure%20 RELEASE:%20(3/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

