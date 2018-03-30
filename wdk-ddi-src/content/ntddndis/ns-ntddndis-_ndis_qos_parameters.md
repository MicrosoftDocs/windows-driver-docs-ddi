---
UID: NS:ntddndis._NDIS_QOS_PARAMETERS
title: "_NDIS_QOS_PARAMETERS"
author: windows-driver-content
description: The NDIS_QOS_PARAMETERS structure specifies the NDIS Quality of Service (QoS) parameters that are enabled on a network adapter that supports the IEEE 802.1 Data Center Bridging (DCB) interface.
old-location: netvista\ndis_qos_parameters.htm
old-project: netvista
ms.assetid: 83eb72a8-d35b-445d-a207-c14a3bedd308
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NDIS_QOS_PARAMETERS, NDIS_QOS_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_QOS_PARAMETERS, PNDIS_QOS_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_QOS_PARAMETERS, netvista.ndis_qos_parameters, ntddndis/NDIS_QOS_PARAMETERS, ntddndis/PNDIS_QOS_PARAMETERS
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddndis.h
api_name:
-	NDIS_QOS_PARAMETERS
product: Windows
targetos: Windows
req.typenames: NDIS_QOS_PARAMETERS, PNDIS_QOS_PARAMETERS
---

# _NDIS_QOS_PARAMETERS structure


## -description



The <b>NDIS_QOS_PARAMETERS</b> structure specifies the NDIS Quality of Service (QoS) parameters that are enabled on a network adapter that supports the IEEE 802.1 Data Center Bridging (DCB) interface.




## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_QOS_PARAMETERS</b> structure. This member is formatted as an <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_QOS_PARAMETERS. To specify the version of the <b>NDIS_QOS_PARAMETERS</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value: 





#### NDIS_QOS_PARAMETERS_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_QOS_PARAMETERS_REVISION_1.


### -field Flags

A <b>ULONG</b> value that contains a bitwise <b>OR</b> of flags that specify the status of the NDIS QoS parameters for the network adapter. For more information about this member, see <a href="https://docs.microsoft.com/">Overview of the Flags Member</a>.


### -field NumTrafficClasses

A <b>ULONG</b> value that specifies the number of NDIS QoS traffic classes that are enabled on the network adapter.  Each traffic class is referenced through an identifier in the range from zero to (<b>NumTrafficClasses</b>–1).

<div class="alert"><b>Note</b>  The value of the <b>NumTrafficClasses</b> member must be less than or equal to <b>min</b>(<b>NDIS_QOS_MAXIMUM_TRAFFIC_CLASSES</b>, <i>MaxNumTrafficClasses</i>), where <i>MaxNumTrafficClasses</i> is the value of the <b>MaxNumTrafficClasses</b> member that was specified  in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451629">NDIS_QOS_CAPABILITIES</a> structure.</div>
<div> </div>

### -field PriorityAssignmentTable

An array of <b>UCHAR</b> elements that specifies an IEEE 802.1p priority level for each traffic class. The <b>PriorityAssignmentTable</b> array is indexed  by the  802.1p priority level (0–7). 

Each element contains the traffic class identifier. This identifier is the index of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451631">NDIS_QOS_CLASSIFICATION_ELEMENT</a> structure for the traffic class within the classification array.

<div class="alert"><b>Note</b>  Each element in the <b>PriorityAssignmentTable</b> array must be assigned a valid traffic class identifier. A traffic class identifier can be assigned to more than one element in the <b>PriorityAssignmentTable</b> array.</div>
<div> </div>

### -field TcBandwidthAssignmentTable

An array of <b>UCHAR</b> elements that specifies the percentage of the bandwidth allocation assigned to each traffic class. The <b>TcBandwidthAssignmentTable</b> array is indexed by the   traffic class identifier. 

Each element of the <b>TcBandwidthAssignmentTable</b> array specifies the bandwidth allocation for the traffic classes. The total value of all bandwidth allocation assignments  in the <b>TcBandwidthAssignmentTable</b> array must equal 100.

<div class="alert"><b>Note</b>  Bandwidth allocation is supported only for the Enhanced Transmission Selection (ETS) TSA. If the element for the traffic class in the <b>TsaAssignmentTable</b> array is not set to NDIS_QOS_TSA_ETS, the element for the traffic class in the <b>TcBandwidthAssignmentTable</b> array must be set to zero.</div>
<div> </div>

### -field TsaAssignmentTable

An array of <b>UCHAR</b> elements that specifies the TSA assigned to each traffic class. The <b>TsaAssignmentTable</b> array is indexed by the   traffic class identifier. 

Each element of the <b>TsaAssignmentTable</b> array contains one of the following values:





#### NDIS_QOS_TSA_STRICT

The strict priority algorithm must be used as the TSA for the traffic class. For more information about this TSA, see <a href="https://msdn.microsoft.com/7C7A34CA-673C-4EFC-970D-08458AA83EAD">Strict Priority Algorithm</a>.



#### NDIS_QOS_TSA_CBS

The IEEE 802.1Qav credit-based shaper (CBS) algorithm must be used as the TSA for the traffic class.

<div class="alert"><b>Note</b>  Starting with Windows Server 2012, the DCB component (Msdcb.sys) does not support the CBS TSA and won't enable this parameter through object identifier (OID) method requests of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451835">OID_QOS_PARAMETERS</a>. For more information on the DCB component, see <a href="https://msdn.microsoft.com/ECB156D8-ECD5-49DE-BC75-6562B90F6056">NDIS QoS Architecture for Data Center Bridging</a>.</div>
<div> </div>


#### NDIS_QOS_TSA_ETS

The IEEE 802.1Qaz Enhanced Transmission Selection (ETS) algorithm must be used as the TSA for the traffic class. For more information about this TSA, see <a href="https://msdn.microsoft.com/952ECB1E-96AD-4717-8E49-68558E7E9AD4">Enhanced Transmission Selection (ETS) Algorithm</a>.


### -field PfcEnable

A bitmap of 32 bits. The most-significant 24 bits are reserved for future use. The least-significant 8 bits are used to specify whether PFC
is enabled on the IEEE 802.1p priority level. If the bit is set to one, PFC is enabled for the priority level.

<table>
<tr>
<th>Bit range</th>
<th>Meaning</th>
</tr>
<tr>
<td>31:24</td>
<td>Reserved for future use.</td>
</tr>
<tr>
<td>7</td>
<td>If set to one, PFC is enabled on 802.1p priority level 7 (<i>network control</i>).</td>
</tr>
<tr>
<td>6</td>
<td>If set to one, PFC is enabled on 802.1p priority level 6 (<i>internetwork control</i>).</td>
</tr>
<tr>
<td>5</td>
<td>If set to one, PFC is enabled on 802.1p priority level 5 (<i>voice</i>).</td>
</tr>
<tr>
<td>4</td>
<td>If set to one, PFC is enabled on 802.1p priority level 4 (<i>video</i>).</td>
</tr>
<tr>
<td>3</td>
<td>If set to one, PFC is enabled on 802.1p priority level 3 (<i>critical applications</i>).</td>
</tr>
<tr>
<td>2</td>
<td>If set to one, PFC is enabled on 802.1p priority level 2 (<i>excellent effort</i>).</td>
</tr>
<tr>
<td>1</td>
<td>If set to one, PFC is enabled on 802.1p priority level 1 (<i>background</i>).</td>
</tr>
<tr>
<td>0</td>
<td>If set to one, PFC is enabled on 802.1p priority level 0 (<i>best effort</i>).</td>
</tr>
</table>
 

<div class="alert"><b>Note</b>  The total number of 802.1p priority levels that have PFC enabled must be less than or equal to the value of the <b>MaxNumPfcEnabledTrafficClasses</b> member in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451629">NDIS_QOS_CAPABILITIES</a> structure.</div>
<div> </div>
For more information about priority levels, see <a href="https://msdn.microsoft.com/C7EB3D85-544E-4898-A456-843621F6488D">IEEE 802.1p Priority Levels</a>.


### -field NumClassificationElements

A <b>ULONG</b> value that specifies the number of elements in the traffic classification array. The offset to the first element in this array is specified  by the <b>FirstClassificationElementOffset</b> member.

<div class="alert"><b>Note</b>  Each element in the array is formatted as an <a href="https://msdn.microsoft.com/library/windows/hardware/hh451631">NDIS_QOS_CLASSIFICATION_ELEMENT</a> structure.</div>
<div> </div>

### -field ClassificationElementSize

A <b>ULONG</b> value that specifies the size, in bytes, of each element in the traffic classification array.

<div class="alert"><b>Note</b>  Starting with NDIS 6.30, this member must be set  to <code>sizeof(NDIS_QOS_CLASSIFICATION_ELEMENT</code>).</div>
<div> </div>

### -field FirstClassificationElementOffset

A <b>ULONG</b> value that specifies the offset, in bytes, to the first element in an array of traffic classification elements that follow this structure. The offset is measured from the start of the <b>NDIS_QOS_PARAMETERS</b> structure up to the beginning of the first element. Each element in the array is an <a href="https://msdn.microsoft.com/library/windows/hardware/hh451631">NDIS_QOS_CLASSIFICATION_ELEMENT</a> structure.



<div class="alert"><b>Note</b>  If <b>NumClassificationElements</b> is set to zero, this member is ignored.  </div>
<div> </div>

## -remarks



The <b>NDIS_QOS_PARAMETERS</b> structure specifies the parameters that define how the network adapter prioritizes transmit, or <i>egress</i>, packets. This structure is used in the following OID requests:

<ul>
<li>
OID query request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451832">OID_QOS_OPERATIONAL_PARAMETERS</a>.  This OID request returns the operational QoS parameters that are currently provisioned on the network adapter.

</li>
<li>
OID query request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451841">OID_QOS_REMOTE_PARAMETERS</a>. This OID request returns the remote QoS parameters that are currently provisioned on the network adapter.

</li>
<li>
OID method requests of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451835">OID_QOS_PARAMETERS</a>. This OID request provisions the network adapter with the local QoS parameters.

</li>
</ul>
The miniport driver also returns an <b>NDIS_QOS_PARAMETERS</b> structure  in the following NDIS status indications:

<ul>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439810">NDIS_STATUS_QOS_OPERATIONAL_PARAMETERS_CHANGE</a>. This miniport driver issues this status indication when its operational QoS parameters change.

</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439812">NDIS_STATUS_QOS_REMOTE_PARAMETERS_CHANGE</a>. This miniport driver issues this status indication when its remote QoS parameters change.

</li>
</ul>
 For more information about the types of NDIS QoS parameters, see <a href="https://msdn.microsoft.com/E9321805-2930-410A-81BC-F7978517E89E">Overview of NDIS QoS Parameters</a>.

<h3><a id="overview"></a><a id="OVERVIEW"></a>Overview of the Flags Member</h3>
The <b>Flags</b> member contains a bitwise <b>OR</b> of flags that specify the status of the NDIS QoS parameters for the network adapter. 

The miniport driver sets the <b>Flags</b> member when it issues the following NDIS status indications:

<ul>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439810">NDIS_STATUS_QOS_OPERATIONAL_PARAMETERS_CHANGE</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439812">NDIS_STATUS_QOS_REMOTE_PARAMETERS_CHANGE</a>


</li>
</ul>
The DCB component sets the <b>Flags</b> member when it issues an OID method request of  <a href="https://msdn.microsoft.com/library/windows/hardware/hh451835">OID_QOS_PARAMETERS</a>.

<div class="alert"><b>Note</b>  Only the DCB component can issue the OID request.  An overlying protocol or filter driver must not issue this OID.
For more information on the DCB component, see <a href="https://msdn.microsoft.com/ECB156D8-ECD5-49DE-BC75-6562B90F6056">NDIS QoS Architecture for Data Center Bridging</a>.</div>
<div> </div>
The following flags are defined for the <b>Flags</b> member.



<div class="alert"><b>Note</b>  NDIS guarantees that both the <b>NDIS_QOS_PARAMETERS_ETS_CONFIGURED</b> and <b>NDIS_QOS_PARAMETERS_PFC_CONFIGURED</b> flags are set or cleared together.</div>
<div> </div>
The <b>NDIS_QOS_PARAMETERS_<i>Xxx</i>_CHANGED</b> flags provide hints as to whether the corresponding group of parameters has changed from a previous <a href="https://msdn.microsoft.com/library/windows/hardware/hh451835">OID_QOS_PARAMETERS</a> method request  or <b>NDIS_QOS_PARAMETERS_<i>Xxx</i>_CHANGED</b> status notification. When the miniport driver issues the <b>NDIS_QOS_PARAMETERS_<i>Xxx</i>_CHANGED</b> status notifications, it can  optionally set these flags.

<div class="alert"><b>Note</b>  If the <b>NDIS_QOS_PARAMETERS_<i>Xxx</i>_CHANGED</b> flags are not set, overlying drivers must not assume that the corresponding group of parameters are supported or enabled on the underlying network adapter.</div>
<div> </div>



## -see-also




<b></b>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565924">NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451629">NDIS_QOS_CAPABILITIES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451631">NDIS_QOS_CLASSIFICATION_ELEMENT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439810">NDIS_STATUS_QOS_OPERATIONAL_PARAMETERS_CHANGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439812">NDIS_STATUS_QOS_REMOTE_PARAMETERS_CHANGE</a>



<a href="https://msdn.microsoft.com/861626af-23ea-40dc-a91a-7da42d4b0a1c">
    NdisMSetMiniportAttributes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451827">OID_QOS_CURRENT_CAPABILITIES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451828">OID_QOS_HARDWARE_CAPABILITIES</a>
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_QOS_PARAMETERS structure%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes
