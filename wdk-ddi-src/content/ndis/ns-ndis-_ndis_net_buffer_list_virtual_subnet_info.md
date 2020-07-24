---
UID: NS:ndis._NDIS_NET_BUFFER_LIST_VIRTUAL_SUBNET_INFO
title: _NDIS_NET_BUFFER_LIST_VIRTUAL_SUBNET_INFO (ndis.h)
description: Defines the group network virtualization information for a network buffer list (NBL).
old-location: netvista\ndis_net_buffer_list_virtual_subnet_info.htm
tech.root: netvista
ms.assetid: E87F9FC0-D408-43D2-A09F-F921617CF3DA
ms.date: 05/02/2018
keywords: ["_NDIS_NET_BUFFER_LIST_VIRTUAL_SUBNET_INFO structure"]
ms.keywords: "*PNDIS_NET_BUFFER_LIST_VIRTUAL_SUBNET_INFO, NDIS_NET_BUFFER_LIST_VIRTUAL_SUBNET_INFO, NDIS_NET_BUFFER_LIST_VIRTUAL_SUBNET_INFO structure [Network Drivers Starting with Windows Vista], PNDIS_NET_BUFFER_LIST_VIRTUAL_SUBNET_INFO, PNDIS_NET_BUFFER_LIST_VIRTUAL_SUBNET_INFO structure pointer [Network Drivers Starting with Windows Vista], _NDIS_NET_BUFFER_LIST_VIRTUAL_SUBNET_INFO, ndis/NDIS_NET_BUFFER_LIST_VIRTUAL_SUBNET_INFO, ndis/PNDIS_NET_BUFFER_LIST_VIRTUAL_SUBNET_INFO, netvista.ndis_net_buffer_list_virtual_subnet_info"
f1_keywords:
 - "ndis/NDIS_NET_BUFFER_LIST_VIRTUAL_SUBNET_INFO"
 - "NDIS_NET_BUFFER_LIST_VIRTUAL_SUBNET_INFO"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ndis.h
api_name:
- NDIS_NET_BUFFER_LIST_VIRTUAL_SUBNET_INFO
targetos: Windows
req.typenames: NDIS_NET_BUFFER_LIST_VIRTUAL_SUBNET_INFO, *PNDIS_NET_BUFFER_LIST_VIRTUAL_SUBNET_INFO
---

# _NDIS_NET_BUFFER_LIST_VIRTUAL_SUBNET_INFO structure


## -description


Defines the group network virtualization information for a network buffer list (NBL).


## -struct-fields




### -field VirtualSubnetId

 


### -field ReservedVsidBits

 


### -field Reserved

 


### -field Value

A member in the union that is contained in <b>NDIS_NET_BUFFER_LIST_VIRTUAL_SUBNET_INFO</b>. 
      <b>Value</b> contains a pointer value that is type-compatible with the 
      <b>NetBufferListInfo</b> member in the 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure. (See the <b>VirtualSubnetInfo</b> constant in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ne-ndis-_ndis_net_buffer_list_info">NDIS_NET_BUFFER_LIST_INFO</a> enumeration.)


#### - ( unnamed struct )

A member in the union that is contained in <b>NDIS_NET_BUFFER_LIST_VIRTUAL_SUBNET_INFO</b>. Ethernet
      miniport drivers use 
      this member to access the originating virtual switch port ID for the network buffer list. 
      This member is a bit field with the following members:



#### VirtualSubnetId

The originating virtual switch port ID for the network buffer list.



#### ReservedVsidBits

This member is reserved and should be set to zero.



#### Reserved

This member is reserved and should be set to zero.


## -remarks



This structure is used in the <b>NetBufferListInfo</b> member in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure.

In NDIS 6.40 (Windows Server 2012 R2) and later, a <b>VirtualSubnetId</b> can be configured on a VM network adapter port as an external virtual subnet to support a third-party network virtualization solution. A Hyper-V extensible Switch forwarding extension may then modify the packet headers, as required, during forwarding. Packets that are being modified must be cloned, and their <b>ParentNetBufferList</b> pointers must be set to the original NBL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/network/cloning-or-duplicating-packet-traffic">Cloning Packet Traffic</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/forwarding-extensions">Forwarding Extensions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ne-ntddndis-_ndis_isolation_mode">NDIS_ISOLATION_MODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ne-ndis-_ndis_net_buffer_list_info">NDIS_NET_BUFFER_LIST_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_switch_forwarding_destination_array">NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-the-hyper-v-extensible-switch">Overview of the Hyper-V Extensible Switch</a>
 

 

