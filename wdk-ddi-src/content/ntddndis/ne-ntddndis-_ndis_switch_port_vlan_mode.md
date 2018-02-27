---
UID: NE:ntddndis._NDIS_SWITCH_PORT_VLAN_MODE
title: "_NDIS_SWITCH_PORT_VLAN_MODE"
author: windows-driver-content
description: The NDIS_SWITCH_PORT_VLAN_MODE enumeration specifies the operation mode of the virtual local area network (VLAN) policy property of a Hyper-V extensible switch port.
old-location: netvista\ndis_switch_port_vlan_mode.htm
old-project: netvista
ms.assetid: 87828768-BE97-4549-AC5B-7CB27D0A9720
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PNDIS_SWITCH_PORT_VLAN_MODE, NDIS_SWITCH_PORT_VLAN_MODE, NDIS_SWITCH_PORT_VLAN_MODE enumeration [Network Drivers Starting with Windows Vista], NdisSwitchPortVlanModeAccess, NdisSwitchPortVlanModeMax, NdisSwitchPortVlanModePrivate, NdisSwitchPortVlanModeTrunk, NdisSwitchPortVlanModeUnknown, PNDIS_SWITCH_PORT_VLAN_MODE, PNDIS_SWITCH_PORT_VLAN_MODE enumeration pointer [Network Drivers Starting with Windows Vista], _NDIS_SWITCH_PORT_VLAN_MODE, netvista.ndis_switch_port_vlan_mode, ntddndis/NDIS_SWITCH_PORT_VLAN_MODE, ntddndis/NdisSwitchPortVlanModeAccess, ntddndis/NdisSwitchPortVlanModeMax, ntddndis/NdisSwitchPortVlanModePrivate, ntddndis/NdisSwitchPortVlanModeTrunk, ntddndis/NdisSwitchPortVlanModeUnknown, ntddndis/PNDIS_SWITCH_PORT_VLAN_MODE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddndis.h
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddndis.h
apiname:
-	NDIS_SWITCH_PORT_VLAN_MODE
product: Windows
targetos: Windows
req.typenames: NDIS_SWITCH_PORT_VLAN_MODE, *PNDIS_SWITCH_PORT_VLAN_MODE
---

# _NDIS_SWITCH_PORT_VLAN_MODE enumeration


## -description



The <b>NDIS_SWITCH_PORT_VLAN_MODE</b> enumeration specifies the operation mode of the virtual local area network (VLAN) policy property of a Hyper-V extensible switch port.




## -syntax


````
typedef enum  { 
  NdisSwitchPortVlanModeUnknown  = 0,
  NdisSwitchPortVlanModeAccess   = 1,
  NdisSwitchPortVlanModeTrunk    = 2,
  NdisSwitchPortVlanModePrivate  = 3,
  NdisSwitchPortVlanModeMax      = 4
} NDIS_SWITCH_PORT_VLAN_MODE, *PNDIS_SWITCH_PORT_VLAN_MODE;
````


## -enum-fields




### -field NdisSwitchPortVlanModeUnknown

This value specifies an undefined VLAN operation mode.


### -field NdisSwitchPortVlanModeAccess

This value specifies an operation mode in which packets from a single VLAN can be sent or received over the port. These packets can be forwarded from other ports on the extensible switch.


### -field NdisSwitchPortVlanModeTrunk

This value specifies an operation mode where the port acts as a VLAN trunk. In this mode, packets from multiple VLANs as well as non-VLAN packets can be sent or received over the port. These packets can be forwarded from other ports on the extensible switch.


### -field NdisSwitchPortVlanModePrivate

This value specifies an operation mode where packets from a single VLAN can be sent or received over the port. These packets cannot be forwarded from other ports on the extensible switch.


### -field NdisSwitchPortVlanModeMax

The maximum value for this enumeration. This value might change in future versions of the NDIS header files and binaries.




## -remarks



The <b>OperationMode</b> member of the <a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_property_vlan.md">NDIS_SWITCH_PORT_PROPERTY_VLAN</a> structure is an <b>NDIS_SWITCH_PORT_VLAN_MODE</b> enumeration data type. 



For more information about extensible switch port policies, see <a href="https://msdn.microsoft.com/8AB85E48-EF37-4D42-873B-34D4835AF22E">Hyper-V Extensible Switch Policies</a>.






## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_property_vlan.md">NDIS_SWITCH_PORT_PROPERTY_VLAN</a>



<a href="..\ndis\ns-ndis-_ndis_switch_forwarding_destination_array.md">NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</a>



<b></b>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SWITCH_PORT_VLAN_MODE enumeration%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

