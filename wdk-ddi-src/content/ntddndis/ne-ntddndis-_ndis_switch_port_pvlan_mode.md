---
UID: NE:ntddndis._NDIS_SWITCH_PORT_PVLAN_MODE
title: "_NDIS_SWITCH_PORT_PVLAN_MODE"
author: windows-driver-content
description: The NDIS_SWITCH_PORT_PVLAN_MODE enumeration specifies the operation mode of a private virtual local area network (PVLAN) policy property. This property is specified for a port on the Hyper-V extensible switch.
old-location: netvista\ndis_switch_port_pvlan_mode.htm
old-project: netvista
ms.assetid: 8B07B225-D612-47D2-B93C-7F9E3A23ACE1
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PNDIS_SWITCH_PORT_PVLAN_MODE, NDIS_SWITCH_PORT_PVLAN_MODE, NDIS_SWITCH_PORT_PVLAN_MODE enumeration [Network Drivers Starting with Windows Vista], NdisSwitchPortPvlanModeCommunity, NdisSwitchPortPvlanModeIsolated, NdisSwitchPortPvlanModePromiscuous, NdisSwitchPortPvlanModeUndefined, PNDIS_SWITCH_PORT_PVLAN_MODE, PNDIS_SWITCH_PORT_PVLAN_MODE enumeration pointer [Network Drivers Starting with Windows Vista], _NDIS_SWITCH_PORT_PVLAN_MODE, netvista.ndis_switch_port_pvlan_mode, ntddndis/NDIS_SWITCH_PORT_PVLAN_MODE, ntddndis/NdisSwitchPortPvlanModeCommunity, ntddndis/NdisSwitchPortPvlanModeIsolated, ntddndis/NdisSwitchPortPvlanModePromiscuous, ntddndis/NdisSwitchPortPvlanModeUndefined, ntddndis/PNDIS_SWITCH_PORT_PVLAN_MODE"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddndis.h
api_name:
-	NDIS_SWITCH_PORT_PVLAN_MODE
product: Windows
targetos: Windows
req.typenames: NDIS_SWITCH_PORT_PVLAN_MODE, *PNDIS_SWITCH_PORT_PVLAN_MODE
---

# _NDIS_SWITCH_PORT_PVLAN_MODE enumeration


## -description



The <b>NDIS_SWITCH_PORT_PVLAN_MODE</b> enumeration specifies the operation mode of a private virtual local area network (PVLAN) policy property. This property is specified for a port on the Hyper-V extensible switch.




## -syntax


````
typedef enum  { 
  NdisSwitchPortPvlanModeUndefined    = 0,
  NdisSwitchPortPvlanModeIsolated,
  NdisSwitchPortPvlanModeCommunity,
  NdisSwitchPortPvlanModePromiscuous
} NDIS_SWITCH_PORT_PVLAN_MODE, *PNDIS_SWITCH_PORT_PVLAN_MODE;
````


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



The <b>PvlanMode</b> member of the <a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_property_vlan.md">NDIS_SWITCH_PORT_PROPERTY_VLAN</a> structure is an <a href="..\ntddndis\ne-ntddndis-_ndis_switch_port_vlan_mode.md">NDIS_SWITCH_PORT_VLAN_MODE</a> enumeration data type. 



For more information about extensible switch port policies, see <a href="https://msdn.microsoft.com/8AB85E48-EF37-4D42-873B-34D4835AF22E">Hyper-V Extensible Switch Policies</a>.






## -see-also

<a href="..\ndis\ns-ndis-_ndis_switch_forwarding_destination_array.md">NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_property_vlan.md">NDIS_SWITCH_PORT_PROPERTY_VLAN</a>



<b></b>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SWITCH_PORT_PVLAN_MODE enumeration%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

