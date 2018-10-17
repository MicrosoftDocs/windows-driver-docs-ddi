---
UID: NS:ndis._NDIS_SWITCH_PORT_DESTINATION
title: "_NDIS_SWITCH_PORT_DESTINATION"
author: windows-driver-content
description: The NDIS_SWITCH_PORT_DESTINATION structure specifies the Hyper-V extensible switch destination port to which a packet will be delivered.
old-location: netvista\ndis_switch_port_destination.htm
tech.root: netvista
ms.assetid: EC7FFB5E-F50B-40C4-B4B7-0A11A374EBD0
ms.date: 5/2/2018
ms.keywords: "*PNDIS_SWITCH_PORT_DESTINATION, NDIS_SWITCH_PORT_DESTINATION, NDIS_SWITCH_PORT_DESTINATION structure [Network Drivers Starting with Windows Vista], PNDIS_SWITCH_PORT_DESTINATION, PNDIS_SWITCH_PORT_DESTINATION structure pointer [Network Drivers Starting with Windows Vista], _NDIS_SWITCH_PORT_DESTINATION, ndis/NDIS_SWITCH_PORT_DESTINATION, ndis/PNDIS_SWITCH_PORT_DESTINATION, netvista.ndis_switch_port_destination"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ndis.h
api_name:
-	NDIS_SWITCH_PORT_DESTINATION
product:
- Windows
targetos: Windows
req.typenames: NDIS_SWITCH_PORT_DESTINATION, *PNDIS_SWITCH_PORT_DESTINATION
---

# _NDIS_SWITCH_PORT_DESTINATION structure


## -description


The <b>NDIS_SWITCH_PORT_DESTINATION</b> structure specifies the Hyper-V extensible switch destination port to which a packet will be delivered.


## -struct-fields




### -field PortId

An NDIS_SWITCH_PORT_ID value that specifies the unique identifier of the destination port on the extensible switch.


### -field NicIndex

An NDIS_SWITCH_NIC_INDEX value that specifies the index of the network adapter that is connected to the  extensible switch port specified by the <b>PortId</b> member.

For more information on NDIS_SWITCH_NIC_INDEX values, see <a href="https://msdn.microsoft.com/969333DA-0282-474B-8D56-72CD623C5329">Network Adapter Index Values</a>.

<div class="alert"><b>Note</b>  This member must specify the index value of a network adapter that is in a connected state. Index values for network adapters that are in a created or disconnected state cannot be specified. For more information about network connection states, see <a href="https://msdn.microsoft.com/1E2075E3-D7CC-4364-ABB2-D5969DB361B5">Hyper-V Extensible Switch Port and Network Adapter States</a>.</div>
<div> </div>

### -field IsExcluded

If this member is set to TRUE, the packet will not be delivered to the
    destination port.



### -field PreserveVLAN

If this member is set to TRUE, the 802.1Q virtual local area network (VLAN) information will be preserved when the packet is delivered to the destination port.  



### -field PreservePriority

If this member is set to TRUE, the 802.1Q priority information will be preserved when the packet is delivered to the destination port.  



### -field Reserved

This member is reserved for future use by NDIS.


## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/hh598210">NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</a> contains one or more elements. Each element is formatted as an <b>NDIS_SWITCH_PORT_DESTINATION</b> structure.

<div class="alert"><b>Note</b>  The <b>NicIndex</b> member must specify the index value of a network adapter that is in a connected state. Index values for network adapters that are in a created or disconnected state cannot be specified. For more information about network connection states, see <a href="https://msdn.microsoft.com/1E2075E3-D7CC-4364-ABB2-D5969DB361B5">Hyper-V Extensible Switch Port and Network Adapter States</a>.</div>
<div> </div>
For more information on destination ports, see <a href="https://msdn.microsoft.com/2781E64A-61D6-49A9-AD9B-F6B348560E30">Managing Hyper-V Extensible Switch Destination Port Data</a>.




## -see-also




<b></b>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598210">NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</a>
 

 

