---
UID: NS:ndis._NDIS_SWITCH_PORT_DESTINATION
title: "_NDIS_SWITCH_PORT_DESTINATION"
author: windows-driver-content
description: The NDIS_SWITCH_PORT_DESTINATION structure specifies the Hyper-V extensible switch destination port to which a packet will be delivered.
old-location: netvista\ndis_switch_port_destination.htm
old-project: netvista
ms.assetid: EC7FFB5E-F50B-40C4-B4B7-0A11A374EBD0
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NDIS_SWITCH_PORT_DESTINATION structure [Network Drivers Starting with Windows Vista], PNDIS_SWITCH_PORT_DESTINATION structure pointer [Network Drivers Starting with Windows Vista], PNDIS_SWITCH_PORT_DESTINATION, ndis/NDIS_SWITCH_PORT_DESTINATION, netvista.ndis_switch_port_destination, ndis/PNDIS_SWITCH_PORT_DESTINATION, *PNDIS_SWITCH_PORT_DESTINATION, _NDIS_SWITCH_PORT_DESTINATION, NDIS_SWITCH_PORT_DESTINATION
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
-	Ndis.h
apiname:
-	NDIS_SWITCH_PORT_DESTINATION
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SWITCH_PORT_DESTINATION, NDIS_SWITCH_PORT_DESTINATION"
---

# _NDIS_SWITCH_PORT_DESTINATION structure


## -description


The <b>NDIS_SWITCH_PORT_DESTINATION</b> structure specifies the Hyper-V extensible switch destination port to which a packet will be delivered.


## -syntax


````
typedef struct _NDIS_SWITCH_PORT_DESTINATION {
  NDIS_SWITCH_PORT_ID   PortId;
  NDIS_SWITCH_NIC_INDEX NicIndex;
  USHORT                IsExcluded  :1;
  UINT32                PreserveVLAN  :1;
  UINT32                PreservePriority  :1;
  USHORT                Reserved  :13;
} NDIS_SWITCH_PORT_DESTINATION, *PNDIS_SWITCH_PORT_DESTINATION;
````


## -struct-fields




#### - PortId

An NDIS_SWITCH_PORT_ID value that specifies the unique identifier of the destination port on the extensible switch.


#### - NicIndex

An NDIS_SWITCH_NIC_INDEX value that specifies the index of the network adapter that is connected to the  extensible switch port specified by the <b>PortId</b> member.

For more information on NDIS_SWITCH_NIC_INDEX values, see <a href="https://msdn.microsoft.com/969333DA-0282-474B-8D56-72CD623C5329">Network Adapter Index Values</a>.
<div class="alert"><b>Note</b>  This member must specify the index value of a network adapter that is in a connected state. Index values for network adapters that are in a created or disconnected state cannot be specified. For more information about network connection states, see <a href="https://msdn.microsoft.com/1E2075E3-D7CC-4364-ABB2-D5969DB361B5">Hyper-V Extensible Switch Port and Network Adapter States</a>.</div><div> </div>

#### - IsExcluded

If this member is set to TRUE, the packet will not be delivered to the
    destination port.



#### - PreserveVLAN

If this member is set to TRUE, the 802.1Q virtual local area network (VLAN) information will be preserved when the packet is delivered to the destination port.  



#### - PreservePriority

If this member is set to TRUE, the 802.1Q priority information will be preserved when the packet is delivered to the destination port.  



#### - Reserved

This member is reserved for future use by NDIS.


## -remarks


The <a href="..\ndis\ns-ndis-_ndis_switch_forwarding_destination_array.md">NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</a> contains one or more elements. Each element is formatted as an <b>NDIS_SWITCH_PORT_DESTINATION</b> structure.
<div class="alert"><b>Note</b>  The <b>NicIndex</b> member must specify the index value of a network adapter that is in a connected state. Index values for network adapters that are in a created or disconnected state cannot be specified. For more information about network connection states, see <a href="https://msdn.microsoft.com/1E2075E3-D7CC-4364-ABB2-D5969DB361B5">Hyper-V Extensible Switch Port and Network Adapter States</a>.</div><div> </div>For more information on destination ports, see <a href="https://msdn.microsoft.com/2781E64A-61D6-49A9-AD9B-F6B348560E30">Managing Hyper-V Extensible Switch Destination Port Data</a>.



## -see-also

<a href="..\ndis\ns-ndis-_ndis_switch_forwarding_destination_array.md">NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</a>

<b></b>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SWITCH_PORT_DESTINATION structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

