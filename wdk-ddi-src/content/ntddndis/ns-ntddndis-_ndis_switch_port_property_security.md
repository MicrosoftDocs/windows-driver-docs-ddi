---
UID: NS:ntddndis._NDIS_SWITCH_PORT_PROPERTY_SECURITY
title: _NDIS_SWITCH_PORT_PROPERTY_SECURITY (ntddndis.h)
description: The NDIS_SWITCH_PORT_PROPERTY_SECURITY structure specifies a security policy property for a Hyper-V extensible switch port.NDIS_SWITCH_PORT_PROPERTY_SECURITY structure specifies a security policy property for a Hyper-V extensible switch port.
old-location: netvista\ndis_switch_port_property_security.htm
tech.root: netvista
ms.assetid: 632ce2d0-4dff-422e-a968-436bd17dd6d8
ms.date: 05/02/2018
keywords: ["_NDIS_SWITCH_PORT_PROPERTY_SECURITY structure"]
ms.keywords: "*PNDIS_SWITCH_PORT_PROPERTY_SECURITY, NDIS_SWITCH_PORT_PROPERTY_SECURITY, NDIS_SWITCH_PORT_PROPERTY_SECURITY structure [Network Drivers Starting with Windows Vista], PNDIS_SWITCH_PORT_PROPERTY_SECURITY, PNDIS_SWITCH_PORT_PROPERTY_SECURITY structure pointer [Network Drivers Starting with Windows Vista], _NDIS_SWITCH_PORT_PROPERTY_SECURITY, netvista.ndis_switch_port_property_security, ntddndis/NDIS_SWITCH_PORT_PROPERTY_SECURITY, ntddndis/PNDIS_SWITCH_PORT_PROPERTY_SECURITY"
f1_keywords:
 - "ntddndis/NDIS_SWITCH_PORT_PROPERTY_SECURITY"
 - "NDIS_SWITCH_PORT_PROPERTY_SECURITY"
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
- NDIS_SWITCH_PORT_PROPERTY_SECURITY
product:
- Windows
targetos: Windows
req.typenames: NDIS_SWITCH_PORT_PROPERTY_SECURITY, *PNDIS_SWITCH_PORT_PROPERTY_SECURITY
---

# _NDIS_SWITCH_PORT_PROPERTY_SECURITY structure


## -description



The <b>NDIS_SWITCH_PORT_PROPERTY_SECURITY</b> structure specifies a security policy property for a Hyper-V extensible switch port.




## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_SWITCH_PORT_PROPERTY_SECURITY</b> structure. This member is formatted as an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure.

The <b>Type</b> member of <b>Header</b> must be set to <b>NDIS_OBJECT_TYPE_DEFAULT</b>. To specify the version of the <b>NDIS_SWITCH_PORT_PROPERTY_SECURITY</b> structure, the <b>Revision</b> member of <b>Header</b> must be set to the following value:





#### NDIS_SWITCH_PORT_PROPERTY_SECURITY_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to <b>NDIS_SIZEOF_NDIS_SWITCH_PROPERTY_SECURITY_REVISION_1</b>.


### -field Flags

A <b>ULONG</b> value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.


### -field AllowMacSpoofing

A <b>BOOLEAN</b> value that, if set to <b>TRUE</b>,  specifies that the port is allowed to send packets with a source media access control (MAC) address that is different from its permanent MAC address. The port's permanent MAC address is configured through an object identifier (OID) set request of <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-nic-create">OID_SWITCH_NIC_CREATE</a>. 


### -field AllowIeeePriorityTag

A <b>BOOLEAN</b> value that, if set to <b>TRUE</b>, specifies that the port must preserve the 802.1Q priority information in a packet's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure when the packet is forwarded to the port. The port must preserve the priority information only if the <b>PreservePriority</b> member is set in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_switch_forwarding_detail_net_buffer_list_info">NDIS_SWITCH_FORWARDING_DETAIL_NET_BUFFER_LIST_INFO</a> union of the out-of-band data of the packet's <b>NET_BUFFER_LIST</b> structure.


### -field VirtualSubnetId

A UINT32 value that specifies the network virtualization <b>VirtualSubnetId</b> that is configured on the port. If network virtualization is not configured on the port, the value will be 0. The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>'s   <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_net_buffer_list_virtual_subnet_info">NDIS_NET_BUFFER_LIST_VIRTUAL_SUBNET_INFO</a> out-of-band data contains the <b>VirtualSubnetId</b>, which is populated with the traffic's virtual subnet membership.


### -field AllowTeaming

A <b>BOOLEAN</b> value that, if set to <b>TRUE</b>, specifies that teaming failover for the port is allowed, such that the port can send packets with a source media access control (MAC) address that is different than its <b>PermanentMacAddress</b>, but equal to the MAC address currently in use by another port that is connected to the same virtual machine. The port's permanent MAC address is configured through an object identifier (OID) set request of <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-nic-create">OID_SWITCH_NIC_CREATE</a>/<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-nic-updated">OID_SWITCH_NIC_UPDATE</a>. 


### -field DynamicIPAddressLimit

A UINT32 value that specifies the maximum number of dynamic IP addresses that can be learned for the port.


## -remarks



The <b>NDIS_SWITCH_PORT_PROPERTY_SECURITY</b> structure is used in the following OID set requests: 

<ul>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-port-property-add">OID_SWITCH_PORT_PROPERTY_ADD</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-port-property-update">OID_SWITCH_PORT_PROPERTY_UPDATE</a>


</li>
</ul>
The <b>NDIS_SWITCH_PORT_PROPERTY_SECURITY</b> structure follows the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_port_property_parameters">NDIS_SWITCH_PORT_PROPERTY_PARAMETERS</a> structure in the buffer that is associated with these OID set requests. The <b>InformationBuffer</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a> structure contains a pointer to this buffer.

Port properties, such as <b>NDIS_SWITCH_PORT_PROPERTY_SECURITY</b>, are enforced by the extensible switch extension that is installed as a forwarding extension. This type of extension enforces its own rules for forwarding packets, OIDs, and status indications through the extensible switch driver stack.  There can be only one forwarding extension per each instance of an extensible switch.

For more information on forwarding extensions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/forwarding-extensions">Forwarding Extensions</a>.

<div class="alert"><b>Note</b>  If a forwarding extension is not installed, the extensible switch interface enforces the port property itself.</div>
<div> </div>



## -see-also




<b></b>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_switch_forwarding_detail_net_buffer_list_info">NDIS_SWITCH_FORWARDING_DETAIL_NET_BUFFER_LIST_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_port_property_parameters">NDIS_SWITCH_PORT_PROPERTY_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-nic-create">OID_SWITCH_NIC_CREATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-port-property-add">OID_SWITCH_PORT_PROPERTY_ADD</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-port-property-update">OID_SWITCH_PORT_PROPERTY_UPDATE</a>
 

 

