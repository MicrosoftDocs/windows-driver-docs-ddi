---
UID: NE:ntddndis._NDIS_SWITCH_PORT_PROPERTY_TYPE
title: "_NDIS_SWITCH_PORT_PROPERTY_TYPE"
author: windows-driver-content
description: The NDIS_SWITCH_PORT_PROPERTY_TYPE enumeration specifies the property type of a policy that is defined for a port on a Hyper-V extensible switch.
old-location: netvista\ndis_switch_port_property_type.htm
old-project: netvista
ms.assetid: c70137b2-1926-4d45-a473-8eb7195ba23d
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: "*PNDIS_SWITCH_PORT_PROPERTY_TYPE, NDIS_SWITCH_PORT_PROPERTY_TYPE, NDIS_SWITCH_PORT_PROPERTY_TYPE enumeration [Network Drivers Starting with Windows Vista], NdisSwitchPortPropertyTypeCustom, NdisSwitchPortPropertyTypeIsolation, NdisSwitchPortPropertyTypeMaximum, NdisSwitchPortPropertyTypeProfile, NdisSwitchPortPropertyTypeRoutingDomain, NdisSwitchPortPropertyTypeSecurity, NdisSwitchPortPropertyTypeUndefined, NdisSwitchPortPropertyTypeVlan, PNDIS_SWITCH_PORT_PROPERTY_TYPE, PNDIS_SWITCH_PORT_PROPERTY_TYPE enumeration pointer [Network Drivers Starting with Windows Vista], _NDIS_SWITCH_PORT_PROPERTY_TYPE, netvista.ndis_switch_port_property_type, ntddndis/NDIS_SWITCH_PORT_PROPERTY_TYPE, ntddndis/NdisSwitchPortPropertyTypeCustom, ntddndis/NdisSwitchPortPropertyTypeIsolation, ntddndis/NdisSwitchPortPropertyTypeMaximum, ntddndis/NdisSwitchPortPropertyTypeProfile, ntddndis/NdisSwitchPortPropertyTypeRoutingDomain, ntddndis/NdisSwitchPortPropertyTypeSecurity, ntddndis/NdisSwitchPortPropertyTypeUndefined, ntddndis/NdisSwitchPortPropertyTypeVlan, ntddndis/PNDIS_SWITCH_PORT_PROPERTY_TYPE"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddndis.h
api_name:
-	NDIS_SWITCH_PORT_PROPERTY_TYPE
product: Windows
targetos: Windows
req.typenames: NDIS_SWITCH_PORT_PROPERTY_TYPE, *PNDIS_SWITCH_PORT_PROPERTY_TYPE
---

# _NDIS_SWITCH_PORT_PROPERTY_TYPE enumeration


## -description


The <b>NDIS_SWITCH_PORT_PROPERTY_TYPE</b> enumeration specifies the property type of a policy that is defined for a port on a Hyper-V extensible switch.


## -enum-fields




### -field NdisSwitchPortPropertyTypeUndefined

The port property type is not defined.


### -field NdisSwitchPortPropertyTypeCustom

This value specifies a custom port property that is defined  by an independent software vendor (ISV). Custom port properties are defined by using the  <a href="https://msdn.microsoft.com/library/windows/hardware/hh598230">NDIS_SWITCH_PORT_PROPERTY_CUSTOM</a> structure.


### -field NdisSwitchPortPropertyTypeSecurity

This value specifies a security port property. Security port properties are defined by using the  <a href="https://msdn.microsoft.com/library/windows/hardware/hh598241">NDIS_SWITCH_PORT_PROPERTY_SECURITY</a> structure.


### -field NdisSwitchPortPropertyTypeVlan

This value specifies a virtual local area network (VLAN) port property. VLAN port properties are defined by using the  <a href="https://msdn.microsoft.com/library/windows/hardware/hh598243">NDIS_SWITCH_PORT_PROPERTY_VLAN</a> structure.


### -field NdisSwitchPortPropertyTypeProfile

This value specifies a profile port property. Profile port properties are defined by using the  <a href="https://msdn.microsoft.com/library/windows/hardware/hh598240">NDIS_SWITCH_PORT_PROPERTY_PROFILE</a> structure.


### -field NdisSwitchPortPropertyTypeIsolation

This value specifies an isolation port property. Isolation port properties are defined by using the  <a href="https://msdn.microsoft.com/library/windows/hardware/dn383687">NDIS_SWITCH_PORT_PROPERTY_ISOLATION</a> structure.<div class="alert"><b>Note</b>  This value is supported in NDIS 6.40 and later.</div>
<div> </div>



### -field NdisSwitchPortPropertyTypeRoutingDomain

This value specifies a routing domain port property. Routing domain port properties are defined by using the  <a href="https://msdn.microsoft.com/library/windows/hardware/dn383688">NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN</a> structure.<div class="alert"><b>Note</b>  This value is supported in NDIS 6.40 and later.</div>
<div> </div>



### -field NdisSwitchPortPropertyTypeMaximum

The maximum value for this enumeration. This value might change in future versions of the NDIS header files and binaries.




## -remarks



The <b>PropertyType</b> member of the following structures is an <b>NDIS_SWITCH_PORT_PROPERTY_TYPE</b> enumeration data type: 



<ul>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh598232">NDIS_SWITCH_PORT_PROPERTY_DELETE_PARAMETERS</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh598227">NDIS_SWITCH_PORT_FEATURE_STATUS_PARAMETERS</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh598236">NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh598238">NDIS_SWITCH_PORT_PROPERTY_PARAMETERS</a>


</li>
</ul>
For more information about extensible switch port policies, see <a href="https://msdn.microsoft.com/8AB85E48-EF37-4D42-873B-34D4835AF22E">Hyper-V Extensible Switch Policies</a>.






## -see-also




<b></b>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598227">NDIS_SWITCH_PORT_FEATURE_STATUS_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598230">NDIS_SWITCH_PORT_PROPERTY_CUSTOM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598232">NDIS_SWITCH_PORT_PROPERTY_DELETE_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598236">NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598238">NDIS_SWITCH_PORT_PROPERTY_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598240">NDIS_SWITCH_PORT_PROPERTY_PROFILE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598241">NDIS_SWITCH_PORT_PROPERTY_SECURITY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598243">NDIS_SWITCH_PORT_PROPERTY_VLAN</a>
 

 

