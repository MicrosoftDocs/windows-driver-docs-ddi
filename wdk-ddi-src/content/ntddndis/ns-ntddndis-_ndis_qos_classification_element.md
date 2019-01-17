---
UID: NS:ntddndis._NDIS_QOS_CLASSIFICATION_ELEMENT
title: "_NDIS_QOS_CLASSIFICATION_ELEMENT"
description: The NDIS_QOS_CLASSIFICATION_ELEMENT structure specifies an NDIS Quality of Service (QoS) traffic classification for a network adapter that supports the IEEE 802.1 Data Center Bridging (DCB) interface.Each traffic classification specifies the following:A classification condition that is based on a data pattern within the egress packet data.Starting with NDIS 6.30, classification conditions are based on a 16-bit value, such as a UDP or TCP destination port or a media access control (MAC) EtherType.A classification action that defines the traffic class to be used to handle the egress packet.Starting with NDIS 6.30, classification actions specify an 802.1p priority level.For example, a traffic classification could specify that all egress packets for destination TCP port number 3260 (condition) are assigned an 802.1p priority level 3 (action).
old-location: netvista\ndis_qos_classification_element.htm
tech.root: netvista
ms.assetid: 2677dc3a-7685-40bf-94c3-2efecf21e9a8
ms.date: 05/02/2018
ms.keywords: NDIS_QOS_CLASSIFICATION_ELEMENT, NDIS_QOS_CLASSIFICATION_ELEMENT structure [Network Drivers Starting with Windows Vista], PNDIS_QOS_CLASSIFICATION_ELEMENT, PNDIS_QOS_CLASSIFICATION_ELEMENT structure pointer [Network Drivers Starting with Windows Vista], _NDIS_QOS_CLASSIFICATION_ELEMENT, netvista.ndis_qos_classification_element, ntddndis/NDIS_QOS_CLASSIFICATION_ELEMENT, ntddndis/PNDIS_QOS_CLASSIFICATION_ELEMENT
ms.topic: struct
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
-	NDIS_QOS_CLASSIFICATION_ELEMENT
product:
- Windows
targetos: Windows
req.typenames: NDIS_QOS_CLASSIFICATION_ELEMENT, PNDIS_QOS_CLASSIFICATION_ELEMENT
---

# _NDIS_QOS_CLASSIFICATION_ELEMENT structure


## -description



The <b>NDIS_QOS_CLASSIFICATION_ELEMENT</b> structure specifies an NDIS Quality of Service (QoS) traffic classification for a network adapter that supports the IEEE 802.1 Data Center Bridging (DCB) interface.

Each traffic classification specifies the following:

<ul>
<li>
A classification <i>condition</i> that is based on a data pattern within the egress packet data.

Starting with NDIS 6.30, classification conditions are based on a 16-bit value, such as a UDP or TCP destination port or a media access control (MAC) EtherType.

</li>
<li>
A classification <i>action</i> that defines the traffic class to be used to handle the egress packet.

Starting with NDIS 6.30, classification actions specify an 802.1p priority level.

</li>
</ul>
For example, a traffic classification could specify that all egress packets for  destination TCP port number 3260 (<i>condition</i>) are assigned an 802.1p priority level 3 (<i>action</i>).




## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_QOS_CLASSIFICATION_ELEMENT</b> structure. This member is formatted as an <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_QOS_CLASSIFICATION_ELEMENT. To specify the version of the <b>NDIS_QOS_CLASSIFICATION_ELEMENT</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value: 





#### NDIS_QOS_CLASSIFICATION_ELEMENT_REVISION_1

Original version for NDIS 6.30.

Set the <b>Size</b> member to NDIS_SIZEOF_QOS_CLASSIFICATION_ELEMENT_REVISION_1.


### -field Flags

A <b>ULONG</b> value that contains a bitwise OR of flags that specify the state of the NDIS QoS traffic classifications that a miniport driver supports. The following flags are defined:





#### NDIS_QOS_CLASSIFICATION_ENFORCED_BY_MINIPORT

If this flag is set, the miniport driver accepts the traffic classification parameters that are specified in the <b>NDIS_QOS_CLASSIFICATION_ELEMENT</b> structure. If the driver accepts the parameters, it must configure the network adapter to perform the traffic classification as specified by the parameters.

<div class="alert"><b>Note</b>  This flag is set only in the <b>NDIS_QOS_CLASSIFICATION_ELEMENT</b> structures that the miniport driver returns to NDIS from an <a href="https://msdn.microsoft.com/library/windows/hardware/hh451835">OID_QOS_PARAMETERS</a> OID method request.
</div>
<div> </div>

### -field ConditionSelector

A <b>USHORT</b> value that specifies the type of the data pattern that is contained in the <b>ConditionField</b> member. For example, the data pattern type could specify a destination UDP port whose value is specified by the <b>ConditionField</b> member.

For more information, see <a href="https://docs.microsoft.com/">Guidelines for Setting the ConditionSelector and ConditionField Members</a>.


### -field ConditionField

A <b>USHORT</b> value that contains the data pattern whose type is specified by the  <b>ConditionSelector</b> member. 

For more information, see <a href="https://docs.microsoft.com/">Guidelines for Setting the ConditionSelector and ConditionField Members</a>.


### -field ActionSelector

A <b>USHORT</b> value that specifies the type of action data that is contained in the <b>ActionField</b> member.  Starting with NDIS 6.30, the action data type specifies an 802.1p priority level whose value is specified by the <b>ConditionField</b> member.

For more information, see <a href="https://docs.microsoft.com/">Guidelines for Setting the ActionSelector and ActionField Members</a>.


### -field ActionField

A <b>USHORT</b> value that contains an action value whose type is specified by the  <b>ActionSelector</b> member.  

For more information, see <a href="https://docs.microsoft.com/">Guidelines for Setting the ActionSelector and ActionField Members</a>.


## -remarks



A traffic classification specifies a <i>condition</i> and an <i>action</i> that the network adapter applies to egress packet data. When the adapter inspects the egress packet data and finds a matching classification condition, it applies the corresponding action to the egress packet.

<div class="alert"><b>Note</b>  Starting with NDIS 6.30, all actions are based on 802.1p priority levels. However, after the network adapter determines the priority level, it must use the egress policies for the NDIS QoS traffic class that is associated with the priority level. The association of priority levels to traffic classes is specified in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451640">NDIS_QOS_PARAMETERS</a> structure.</div>
<div> </div>
The <b>NDIS_QOS_CLASSIFICATION_ELEMENT</b> structure specifies each traffic classification element within the array that is specified by the  <a href="https://msdn.microsoft.com/library/windows/hardware/hh451640">NDIS_QOS_PARAMETERS</a> structure. This structure is used in the following OID requests:

<ul>
<li>
OID query requests of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451832">OID_QOS_OPERATIONAL_PARAMETERS</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/hh451841">OID_QOS_REMOTE_PARAMETERS</a>.

</li>
<li>
OID method requests of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451835">OID_QOS_PARAMETERS</a>.

</li>
</ul>
The miniport driver also returns an <a href="https://msdn.microsoft.com/library/windows/hardware/hh451640">NDIS_QOS_PARAMETERS</a> structure that contains an array of <b>NDIS_QOS_CLASSIFICATION_ELEMENT</b> structures in the following NDIS status indications:

<ul>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439810">NDIS_STATUS_QOS_OPERATIONAL_PARAMETERS_CHANGE</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439812">NDIS_STATUS_QOS_REMOTE_PARAMETERS_CHANGE</a>


</li>
</ul>
For more information, see <a href="https://msdn.microsoft.com/62D7B69F-A64E-4E3C-9AEA-8C56495E3FF5">NDIS QoS Traffic Classifications</a>.

<h3><a id="condition_members"></a><a id="CONDITION_MEMBERS"></a>Guidelines for Setting the ConditionSelector and ConditionField Members</h3>
The following table defines the range of values for the <b>ConditionSelector</b> and <b>ConditionField</b> members.

<table>
<tr>
<th>ConditionSelector value</th>
<th>ConditionField value</th>
</tr>
<tr>
<td>NDIS_QOS_CONDITION_RESERVED</td>
<td>
The <b>ConditionField</b> member must be set to zero.

<div class="alert"><b>Note</b>  This condition is reserved for future use.</div>
<div> </div>
</td>
</tr>
<tr>
<td>NDIS_QOS_CONDITION_DEFAULT</td>
<td>
The <b>ConditionField</b> member must be set to zero. 

</td>
</tr>
<tr>
<td>NDIS_QOS_CONDITION_TCP_PORT</td>
<td>
The <b>ConditionField</b> member contains a 16-bit destination TCP port value.

</td>
</tr>
<tr>
<td>NDIS_QOS_CONDITION_UDP_PORT</td>
<td>
The <b>ConditionField</b> member contains a 16-bit destination UDP port value.

</td>
</tr>
<tr>
<td>NDIS_QOS_CONDITION_TCP_OR_UDP_PORT</td>
<td>
The <b>ConditionField</b> member contains a 16-bit destination TCP or UDP port value.

</td>
</tr>
<tr>
<td>NDIS_QOS_CONDITION_ETHERTYPE</td>
<td>
The <b>ConditionField</b> member contains a 16-bit IEEE EtherType value.

<div class="alert"><b>Note</b>  The network adapter needs to determine the frame layout of the packet in order to inspect the EtherType. For example, the location of the EtherType field is different between an Ethernet II and 802.3 frame.</div>
<div> </div>
</td>
</tr>
<tr>
<td>NDIS_QOS_CONDITION_NETDIRECT_PORT</td>
<td>
The <b>ConditionField</b> member contains a 16-bit NetworkDirect port value.

</td>
</tr>
</table>
 

If the <b>ConditionSelector</b> member contains a value of NDIS_QOS_CONDITION_DEFAULT, the associated classification action must be applied to all egress packets that did not match any other classification conditions. When the DCB component issues an OID method request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451835">OID_QOS_PARAMETERS</a>, it may set the  <b>ConditionSelector</b> to NDIS_QOS_CONDITION_DEFAULT in only the first <b>NDIS_QOS_CLASSIFICATION_ELEMENT</b> structure in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451640">NDIS_QOS_PARAMETERS</a> array.

If the <b>ConditionSelector</b> member contains a value of NDIS_QOS_CONDITION_NETDIRECT_PORT, the miniport driver must match the <b>ConditionField</b> member against either the source or destination port of a NetworkDirect connection. If the miniport driver accepts a NetDirect connection, the driver must match the <b>ConditionField</b> member against the source port of any packet it sends over that connection. If the miniport driver initiates a NetDirect connection, it must match the <b>ConditionField</b> member against the destination port of any packet it sends over that connection.

For more information on the DCB component, see <a href="https://msdn.microsoft.com/ECB156D8-ECD5-49DE-BC75-6562B90F6056">NDIS QoS Architecture for Data Center Bridging</a>.

<h3><a id="action_members"></a><a id="ACTION_MEMBERS"></a>Guidelines for Setting the ActionSelector and ActionField Members</h3>
The following table defines the range of values for the <b>ActionSelector</b> and <b>ActionField</b> members.

<table>
<tr>
<th>ActionSelector value</th>
<th>ActionField value</th>
</tr>
<tr>
<td>NDIS_QOS_ACTION_PRIORITY</td>
<td>
The <b>ActionField</b> member contains a 3-bit IEEE 802.1p priority level value. For more information on these priority levels, see <a href="https://msdn.microsoft.com/C7EB3D85-544E-4898-A456-843621F6488D">IEEE 802.1p Priority Levels</a>.

</td>
</tr>
</table>
 

Starting with NDIS 6.30, traffic classification actions define an IEEE 802.1p priority level to which the egress packet is assigned. When the network adapter assigns a priority level to an egress packet, the adapter also applies the parameters for the NDIS QoS traffic class associated with the specified priority level. These parameters determine how the network adapter transmits the packet, and include bandwidth allocation  and transmission selection algorithm (TSA). 

For more information on NDIS QoS traffic classes, see <a href="https://msdn.microsoft.com/0DE61F97-7173-4D91-90F3-20EAFB810251">NDIS QoS Traffic Classes</a>.




## -see-also




<b></b>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451640">NDIS_QOS_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439810">NDIS_STATUS_QOS_OPERATIONAL_PARAMETERS_CHANGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439812">NDIS_STATUS_QOS_REMOTE_PARAMETERS_CHANGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451832">OID_QOS_OPERATIONAL_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451835">OID_QOS_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451841">OID_QOS_REMOTE_PARAMETERS</a>
 

 

