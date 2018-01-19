---
UID: NE:ntddndis._NDIS_SWITCH_PORT_PROPERTY_TYPE
title: _NDIS_SWITCH_PORT_PROPERTY_TYPE
author: windows-driver-content
description: The NDIS_SWITCH_PORT_PROPERTY_TYPE enumeration specifies the property type of a policy that is defined for a port on a Hyper-V extensible switch.
old-location: netvista\ndis_switch_port_property_type.htm
old-project: netvista
ms.assetid: c70137b2-1926-4d45-a473-8eb7195ba23d
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _NDIS_SWITCH_PORT_PROPERTY_TYPE, *PNDIS_SWITCH_PORT_PROPERTY_TYPE, NDIS_SWITCH_PORT_PROPERTY_TYPE
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
req.alt-api: NDIS_SWITCH_PORT_PROPERTY_TYPE
req.alt-loc: Ntddndis.h
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
req.typenames: *PNDIS_SWITCH_PORT_PROPERTY_TYPE, NDIS_SWITCH_PORT_PROPERTY_TYPE
---

# _NDIS_SWITCH_PORT_PROPERTY_TYPE enumeration



## -description
The <b>NDIS_SWITCH_PORT_PROPERTY_TYPE</b> enumeration specifies the property type of a policy that is defined for a port on a Hyper-V extensible switch.



## -syntax

````
typedef enum _NDIS_SWITCH_PORT_PROPERTY_TYPE { 
  NdisSwitchPortPropertyTypeUndefined,
  NdisSwitchPortPropertyTypeCustom,
  NdisSwitchPortPropertyTypeSecurity,
  NdisSwitchPortPropertyTypeVlan,
  NdisSwitchPortPropertyTypeProfile,
  NdisSwitchPortPropertyTypeIsolation,
  NdisSwitchPortPropertyTypeRoutingDomain,
  NdisSwitchPortPropertyTypeMaximum
} NDIS_SWITCH_PORT_PROPERTY_TYPE, *PNDIS_SWITCH_PORT_PROPERTY_TYPE;
````


## -enum-fields

### -field NdisSwitchPortPropertyTypeUndefined

The port property type is not defined.


### -field NdisSwitchPortPropertyTypeCustom

This value specifies a custom port property that is defined  by an independent software vendor (ISV). Custom port properties are defined by using the  <a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_property_custom.md">NDIS_SWITCH_PORT_PROPERTY_CUSTOM</a> structure.


### -field NdisSwitchPortPropertyTypeSecurity

This value specifies a security port property. Security port properties are defined by using the  <a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_property_security.md">NDIS_SWITCH_PORT_PROPERTY_SECURITY</a> structure.


### -field NdisSwitchPortPropertyTypeVlan

This value specifies a virtual local area network (VLAN) port property. VLAN port properties are defined by using the  <a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_property_vlan.md">NDIS_SWITCH_PORT_PROPERTY_VLAN</a> structure.


### -field NdisSwitchPortPropertyTypeProfile

This value specifies a profile port property. Profile port properties are defined by using the  <a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_property_profile.md">NDIS_SWITCH_PORT_PROPERTY_PROFILE</a> structure.


### -field NdisSwitchPortPropertyTypeIsolation

This value specifies an isolation port property. Isolation port properties are defined by using the  <a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_property_isolation.md">NDIS_SWITCH_PORT_PROPERTY_ISOLATION</a> structure.<div class="alert"><b>Note</b>  This value is supported in NDIS 6.40 and later.</div>
<div> </div>



### -field NdisSwitchPortPropertyTypeRoutingDomain

This value specifies a routing domain port property. Routing domain port properties are defined by using the  <a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_property_routing_domain.md">NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN</a> structure.<div class="alert"><b>Note</b>  This value is supported in NDIS 6.40 and later.</div>
<div> </div>



### -field NdisSwitchPortPropertyTypeMaximum

The maximum value for this enumeration. This value might change in future versions of the NDIS header files and binaries.




## -remarks
The <b>PropertyType</b> member of the following structures is an <b>NDIS_SWITCH_PORT_PROPERTY_TYPE</b> enumeration data type: 




<a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_property_delete_parameters.md">NDIS_SWITCH_PORT_PROPERTY_DELETE_PARAMETERS</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_feature_status_parameters.md">NDIS_SWITCH_PORT_FEATURE_STATUS_PARAMETERS</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_property_enum_parameters.md">NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_property_parameters.md">NDIS_SWITCH_PORT_PROPERTY_PARAMETERS</a>


For more information about extensible switch port policies, see <a href="https://msdn.microsoft.com/8AB85E48-EF37-4D42-873B-34D4835AF22E">Hyper-V Extensible Switch Policies</a>.




## -see-also
<dl>
<dt><b></b></dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_feature_status_parameters.md">NDIS_SWITCH_PORT_FEATURE_STATUS_PARAMETERS</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_property_custom.md">NDIS_SWITCH_PORT_PROPERTY_CUSTOM</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_property_delete_parameters.md">NDIS_SWITCH_PORT_PROPERTY_DELETE_PARAMETERS</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_property_enum_parameters.md">NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_property_parameters.md">NDIS_SWITCH_PORT_PROPERTY_PARAMETERS</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_property_profile.md">NDIS_SWITCH_PORT_PROPERTY_PROFILE</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_property_security.md">NDIS_SWITCH_PORT_PROPERTY_SECURITY</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_property_vlan.md">NDIS_SWITCH_PORT_PROPERTY_VLAN</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SWITCH_PORT_PROPERTY_TYPE enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

