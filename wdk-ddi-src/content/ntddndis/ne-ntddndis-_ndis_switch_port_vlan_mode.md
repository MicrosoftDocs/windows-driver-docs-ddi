---
UID: NE:ntddndis._NDIS_SWITCH_PORT_VLAN_MODE
title: _NDIS_SWITCH_PORT_VLAN_MODE (ntddndis.h)
description: The NDIS_SWITCH_PORT_VLAN_MODE enumeration specifies the operation mode of the virtual local area network (VLAN) policy property of a Hyper-V extensible switch port.
old-location: netvista\ndis_switch_port_vlan_mode.htm
tech.root: netvista
ms.assetid: 87828768-BE97-4549-AC5B-7CB27D0A9720
ms.date: 05/02/2018
keywords: ["_NDIS_SWITCH_PORT_VLAN_MODE enumeration"]
ms.keywords: "*PNDIS_SWITCH_PORT_VLAN_MODE, NDIS_SWITCH_PORT_VLAN_MODE, NDIS_SWITCH_PORT_VLAN_MODE enumeration [Network Drivers Starting with Windows Vista], NdisSwitchPortVlanModeAccess, NdisSwitchPortVlanModeMax, NdisSwitchPortVlanModePrivate, NdisSwitchPortVlanModeTrunk, NdisSwitchPortVlanModeUnknown, PNDIS_SWITCH_PORT_VLAN_MODE, PNDIS_SWITCH_PORT_VLAN_MODE enumeration pointer [Network Drivers Starting with Windows Vista], _NDIS_SWITCH_PORT_VLAN_MODE, netvista.ndis_switch_port_vlan_mode, ntddndis/NDIS_SWITCH_PORT_VLAN_MODE, ntddndis/NdisSwitchPortVlanModeAccess, ntddndis/NdisSwitchPortVlanModeMax, ntddndis/NdisSwitchPortVlanModePrivate, ntddndis/NdisSwitchPortVlanModeTrunk, ntddndis/NdisSwitchPortVlanModeUnknown, ntddndis/PNDIS_SWITCH_PORT_VLAN_MODE"
f1_keywords:
 - "ntddndis/NDIS_SWITCH_PORT_VLAN_MODE"
 - "NDIS_SWITCH_PORT_VLAN_MODE"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddndis.h
api_name:
- NDIS_SWITCH_PORT_VLAN_MODE
targetos: Windows
req.typenames: NDIS_SWITCH_PORT_VLAN_MODE, *PNDIS_SWITCH_PORT_VLAN_MODE
---

# _NDIS_SWITCH_PORT_VLAN_MODE enumeration


## -description



The <b>NDIS_SWITCH_PORT_VLAN_MODE</b> enumeration specifies the operation mode of the virtual local area network (VLAN) policy property of a Hyper-V extensible switch port.




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



The <b>OperationMode</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_port_property_vlan">NDIS_SWITCH_PORT_PROPERTY_VLAN</a> structure is an <b>NDIS_SWITCH_PORT_VLAN_MODE</b> enumeration data type. 



For more information about extensible switch port policies, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/hyper-v-extensible-switch-policies">Hyper-V Extensible Switch Policies</a>.






## -see-also




<b></b>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_switch_forwarding_destination_array">NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_port_property_vlan">NDIS_SWITCH_PORT_PROPERTY_VLAN</a>
 

 

