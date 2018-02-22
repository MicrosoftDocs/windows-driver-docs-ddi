---
UID: NS:ks.KSTOPOLOGY_CONNECTION
title: KSTOPOLOGY_CONNECTION
author: windows-driver-content
description: The KSTOPOLOGY_CONNECTION structure describes a single data-path connection inside a kernel streaming filter.
old-location: stream\kstopology_connection.htm
old-project: stream
ms.assetid: 604be66a-bec7-48db-b038-aaaf78043965
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ks/KSTOPOLOGY_CONNECTION, KSTOPOLOGY_CONNECTION structure [Streaming Media Devices], KSTOPOLOGY_CONNECTION, PCCONNECTION_DESCRIPTOR, *PKSTOPOLOGY_CONNECTION, PKSTOPOLOGY_CONNECTION structure pointer [Streaming Media Devices], PCCONNECTION_DESCRIPTOR structure, PKSTOPOLOGY_CONNECTION, ks/PKSTOPOLOGY_CONNECTION, stream.kstopology_connection, ks-struct_b688f291-7064-492b-8ab6-5f167941ebbf.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ks.h
apiname:
-	KSTOPOLOGY_CONNECTION
product: Windows
targetos: Windows
req.typenames: KSTOPOLOGY_CONNECTION, *PKSTOPOLOGY_CONNECTION
---

# KSTOPOLOGY_CONNECTION structure


## -description


The KSTOPOLOGY_CONNECTION structure describes a single data-path connection inside a kernel streaming filter.

PCCONNECTION_DESCRIPTOR is an alias for KSTOPOLOGY_CONNECTION. 


## -syntax


````
typedef struct {
  ULONG FromNode;
  ULONG FromNodePin;
  ULONG ToNode;
  ULONG ToNodePin;
} KSTOPOLOGY_CONNECTION, *PKSTOPOLOGY_CONNECTION;
````


## -struct-fields




### -field FromNode

Specifies the node ID of the node on the upstream end of the connection. If this end of the connection is an external pin on the filter -- not a logical pin on a node--set this member to the null node-ID value, KSFILTER_NODE.


### -field FromNodePin

Specifies the pin ID for the upstream end of the connection. If <b>FromNode </b>is KSFILTER_NODE, the pin on this end of the connection is an external pin on the filter. If not, the pin on this end is a logical pin on an internal node.


### -field ToNode

Specifies the node ID of the node on the downstream end of the connection. If this end of the connection is an external pin on the filter--not a logical pin on a node -- set this member to the null node-ID value, KSFILTER_NODE.


### -field ToNodePin

Specifies the pin ID for the downstream end of the connection. If <b>ToNode</b> is KSFILTER_NODE, the pin on this end of the connection is an external pin on the filter. If not, the pin on this end is a logical pin on an internal node.


## -remarks



KSTOPOLOGY_CONNECTION represents a single connection inside a filter, between either external pins, internal nodes, or an external pin and an internal node.

A streaming driver returns an array of KSTOPOLOGY_CONNECTION structures in response to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff565802">KSPROPERTY_TOPOLOGY_CONNECTIONS</a> get-property request.

When representing a connection between two external pins, both <b>FromNode</b> and <b>ToNode</b> should be set to KSFILTER_NODE, and the <b>FromNodePin</b> and <b>ToNodePin</b> should be the pin type ID of the respective pins. (See <a href="https://msdn.microsoft.com/library/windows/hardware/ff566584">KSPROPSETID_Pin</a> for a description of pin type IDs.)

Otherwise, <b>FromNodePin</b> or <b>ToNodePin</b> represent a logical incoming or outgoing pin for the connection. The logical pin numbers are used solely to describe a connection between nodes; they have no existence outside of the KSPROPERTY_TOPOLOGY_CONNECTIONS property.

<b>PCCONNECTION_DESCRIPTOR</b>

The PCCONNECTION_DESCRIPTOR structure name is an alias for KSTOPOLOGY_CONNECTION.

PCCONNECTION_DESCRIPTOR for IMiniport::GetDescription()
 

Description of a node connection in the topology of the filter implemented
 by the miniport.

Defined as follow in portcls.w

<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>typedef KSTOPOLOGY_CONNECTION
PCCONNECTION_DESCRIPTOR, *PPCCONNECTION_DESCRIPTOR;</pre>
</td>
</tr>
</table></span></div>
Note that for the parameter descriptions, the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537695">PCFILTER_NODE</a> is used with PCCONNECTION_DESCRIPTOR instead of KSFILTER_NODE.



The <a href="https://msdn.microsoft.com/library/windows/hardware/ff537688">PCCONNECTION_DESCRIPTOR</a> structure specifies a single connection inside a filter. The connection can be one of the following:

<ul>
<li>
A connection between two internal nodes

</li>
<li>
A connection between an internal node and a pin on the filter

</li>
<li>
A connection between two pins on the filter

</li>
</ul>
The last type of connection occurs when an input pin on a filter streams data directly to an output pin on the same filter.

An adapter driver uses an array of  structures to specify the internal topology of a filter.

The data stream flows from the <b>FromNode</b> end to the <b>ToNode</b> end of the connection.

To use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537688">PCCONNECTION_DESCRIPTOR</a> structure, the driver writer assigns "logical" pins to the nodes inside the filter. These "pins" are connection points on the nodes and are analogous to the external pins that the filter uses to connect to other filters. However, logical pins on nodes are used solely to specify the connections inside the filter.

A simple node with a single input and a single output typically numbers its input and output pins one and zero, respectively. By convention, this numbering is based on the direction of IRP flow rather than data flow.

More complex nodes might require standardized pin IDs in order to allow clients to more easily determine the assignment of functions to specific pins. For example, the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537150">KSNODETYPE_ACOUSTIC_ECHO_CANCEL</a> node uses standardized IDs for its four pins.

When the pin on one end of a connection is an input or output pin on the filter rather than a logical pin on a node, set the <b>FromNode</b> or <b>ToNode</b> member (depending on which end of the connection you are specifying) to the null node-ID value, <a href="https://msdn.microsoft.com/library/windows/hardware/ff537695">PCFILTER_NODE</a>.

Avoid confusing logical pins, which are used solely to describe connection points on nodes within a filter, with the external pins that filters use to connect to other filters. Logical pins are rarely used outside of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537688">PCCONNECTION_DESCRIPTOR</a> structure. In this document, the term <i>pin</i> refers to a pin on a KS filter rather than a logical pin on a node unless noted otherwise.

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff536765">IMiniport::GetDescription</a> method outputs a <a href="..\portcls\ns-portcls-__unnamed_struct_0cb6_9.md">PCFILTER_DESCRIPTOR</a> structure that contains a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537688">PCCONNECTION_DESCRIPTOR</a> array.

For a simple code example that shows how the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537688">PCCONNECTION_DESCRIPTOR</a> structure is used, see <a href="https://msdn.microsoft.com/bf791f40-b2fb-48fe-8350-3b926db4ead7">Exposing Filter Topology</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566584">KSPROPSETID_Pin</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566598">KSPROPSETID_Topology</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566584">KSPROPSETID_Pin</a>



<a href="..\bdasup\nf-bdasup-bdapropertytemplateconnections.md">BdaPropertyTemplateConnections</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSTOPOLOGY_CONNECTION structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

