---
UID: NE:ntddndis._NDIS_SWITCH_PORT_PVLAN_MODE
title: "_NDIS_SWITCH_PORT_PVLAN_MODE"
author: windows-driver-content
description: The NDIS_SWITCH_PORT_PVLAN_MODE enumeration specifies the operation mode of a private virtual local area network (PVLAN) policy property. This property is specified for a port on the Hyper-V extensible switch.
old-location: netvista\ndis_switch_port_pvlan_mode.htm
tech.root: netvista
ms.assetid: 8B07B225-D612-47D2-B93C-7F9E3A23ACE1
ms.date: 05/02/2018
ms.keywords: "*PNDIS_SWITCH_PORT_PVLAN_MODE, NDIS_SWITCH_PORT_PVLAN_MODE, NDIS_SWITCH_PORT_PVLAN_MODE enumeration [Network Drivers Starting with Windows Vista], NdisSwitchPortPvlanModeCommunity, NdisSwitchPortPvlanModeIsolated, NdisSwitchPortPvlanModePromiscuous, NdisSwitchPortPvlanModeUndefined, PNDIS_SWITCH_PORT_PVLAN_MODE, PNDIS_SWITCH_PORT_PVLAN_MODE enumeration pointer [Network Drivers Starting with Windows Vista], _NDIS_SWITCH_PORT_PVLAN_MODE, netvista.ndis_switch_port_pvlan_mode, ntddndis/NDIS_SWITCH_PORT_PVLAN_MODE, ntddndis/NdisSwitchPortPvlanModeCommunity, ntddndis/NdisSwitchPortPvlanModeIsolated, ntddndis/NdisSwitchPortPvlanModePromiscuous, ntddndis/NdisSwitchPortPvlanModeUndefined, ntddndis/PNDIS_SWITCH_PORT_PVLAN_MODE"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddndis.h
api_name:
-	NDIS_SWITCH_PORT_PVLAN_MODE
product:
- Windows
targetos: Windows
req.typenames: NDIS_SWITCH_PORT_PVLAN_MODE, *PNDIS_SWITCH_PORT_PVLAN_MODE
---

# _NDIS_SWITCH_PORT_PVLAN_MODE enumeration


## -description



The <b>NDIS_SWITCH_PORT_PVLAN_MODE</b> enumeration specifies the operation mode of a private virtual local area network (PVLAN) policy property. This property is specified for a port on the Hyper-V extensible switch.




## -enum-fields




### -field NdisSwitchPortPvlanModeUndefined

This value specifies an undefined PVLAN operation mode.


### -field NdisSwitchPortPvlanModeIsolated

This value specifies a port that operates in PVLAN isolated mode. In isolated mode, the port can receive traffic only on the primary VLAN. It sends traffic on the secondary VLAN.


### -field NdisSwitchPortPvlanModeCommunity

This value specifies a port that operates in PVLAN community mode. In community mode, the port can receive traffic on the primary and secondary VLAN. However, the port can send traffic only on its secondary VLAN.


### -field NdisSwitchPortPvlanModePromiscuous

This value specifies a port that operates in PVLAN promiscuous mode. In promiscuous mode, the port can receive traffic on a defined set of primary and secondary VLANs. However, the port can send traffic only on its primary VLAN.


## -remarks



The <b>PvlanMode</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh598243">NDIS_SWITCH_PORT_PROPERTY_VLAN</a> structure is an <a href="https://msdn.microsoft.com/library/windows/hardware/hh598246">NDIS_SWITCH_PORT_VLAN_MODE</a> enumeration data type. 



For more information about extensible switch port policies, see <a href="https://msdn.microsoft.com/8AB85E48-EF37-4D42-873B-34D4835AF22E">Hyper-V Extensible Switch Policies</a>.






## -see-also




<b></b>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598210">NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598243">NDIS_SWITCH_PORT_PROPERTY_VLAN</a>
 

 

