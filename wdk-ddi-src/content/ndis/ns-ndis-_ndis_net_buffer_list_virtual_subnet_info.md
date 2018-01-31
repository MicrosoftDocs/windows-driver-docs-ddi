---
UID: NS:ndis._NDIS_NET_BUFFER_LIST_VIRTUAL_SUBNET_INFO
title: "_NDIS_NET_BUFFER_LIST_VIRTUAL_SUBNET_INFO"
author: windows-driver-content
description: Defines the group network virtualization information for a network buffer list (NBL).
old-location: netvista\ndis_net_buffer_list_virtual_subnet_info.htm
old-project: netvista
ms.assetid: E87F9FC0-D408-43D2-A09F-F921617CF3DA
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndis_net_buffer_list_virtual_subnet_info, PNDIS_NET_BUFFER_LIST_VIRTUAL_SUBNET_INFO, NDIS_NET_BUFFER_LIST_VIRTUAL_SUBNET_INFO structure [Network Drivers Starting with Windows Vista], PNDIS_NET_BUFFER_LIST_VIRTUAL_SUBNET_INFO structure pointer [Network Drivers Starting with Windows Vista], _NDIS_NET_BUFFER_LIST_VIRTUAL_SUBNET_INFO, ndis/PNDIS_NET_BUFFER_LIST_VIRTUAL_SUBNET_INFO, NDIS_NET_BUFFER_LIST_VIRTUAL_SUBNET_INFO, ndis/NDIS_NET_BUFFER_LIST_VIRTUAL_SUBNET_INFO, *PNDIS_NET_BUFFER_LIST_VIRTUAL_SUBNET_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: See Remarks section
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ndis.h
apiname:
-	NDIS_NET_BUFFER_LIST_VIRTUAL_SUBNET_INFO
product: Windows
targetos: Windows
req.typenames: "*PNDIS_NET_BUFFER_LIST_VIRTUAL_SUBNET_INFO, NDIS_NET_BUFFER_LIST_VIRTUAL_SUBNET_INFO"
---

# _NDIS_NET_BUFFER_LIST_VIRTUAL_SUBNET_INFO structure


## -description


Defines the group network virtualization information for a network buffer list (NBL).


## -syntax


````
typedef struct _NDIS_NET_BUFFER_LIST_VIRTUAL_SUBNET_INFO {
  union {
    struct {
      UINT32 VirtualSubnetId  :32;
      UINT32 ReservedVsidBits  :8;
      UINT32 Reserved;
    };
    PVOID  Value;
  };
} NDIS_NET_BUFFER_LIST_VIRTUAL_SUBNET_INFO, *PNDIS_NET_BUFFER_LIST_VIRTUAL_SUBNET_INFO;
````


## -struct-fields




### -field VirtualSubnetId

 


### -field ReservedVsidBits

 


### -field Reserved

 


#### - Value

A member in the union that is contained in <b>NDIS_NET_BUFFER_LIST_VIRTUAL_SUBNET_INFO</b>. 
      <b>Value</b> contains a pointer value that is type-compatible with the 
      <b>NetBufferListInfo</b> member in the 
      <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure. (See the <b>VirtualSubnetInfo</b> constant in the <a href="..\ndis\ne-ndis-_ndis_net_buffer_list_info.md">NDIS_NET_BUFFER_LIST_INFO</a> enumeration.)


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


This structure is used in the <b>NetBufferListInfo</b> member in the <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure.

In NDIS 6.40 (Windows Server 2012 R2) and later, a <b>VirtualSubnetId</b> can be configured on a VM network adapter port as an external virtual subnet to support a third-party network virtualization solution. A Hyper-V extensible Switch forwarding extension may then modify the packet headers, as required, during forwarding. Packets that are being modified must be cloned, and their <b>ParentNetBufferList</b> pointers must be set to the original NBL.



## -see-also

<a href="..\ndis\ne-ndis-_ndis_net_buffer_list_info.md">NDIS_NET_BUFFER_LIST_INFO</a>

<a href="https://msdn.microsoft.com/7ABBB3F3-66F5-4651-8A5A-94940F3FD82D">Forwarding Extensions</a>

<a href="..\ndis\ns-ndis-_ndis_switch_forwarding_destination_array.md">NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</a>

<a href="https://msdn.microsoft.com/78181C72-FBFD-4860-A664-C297997D780F">Overview of the Hyper-V Extensible Switch</a>

<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>

<a href="..\ntddndis\ne-ntddndis-_ndis_isolation_mode.md">NDIS_ISOLATION_MODE</a>

<a href="https://msdn.microsoft.com/6BAE348D-B5BA-4B74-8D9B-79B146427D8C">Cloning Packet Traffic</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_NET_BUFFER_LIST_VIRTUAL_SUBNET_INFO structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

