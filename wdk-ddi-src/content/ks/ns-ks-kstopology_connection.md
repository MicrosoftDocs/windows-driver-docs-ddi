---
UID: NS:ks.__unnamed_struct_23
title: KSTOPOLOGY_CONNECTION (ks.h)
description: The KSTOPOLOGY_CONNECTION structure describes a single data-path connection inside a kernel streaming filter.
old-location: stream\kstopology_connection.htm
tech.root: stream
ms.assetid: 604be66a-bec7-48db-b038-aaaf78043965
ms.date: 04/23/2018
ms.keywords: "*PKSTOPOLOGY_CONNECTION, KSTOPOLOGY_CONNECTION, KSTOPOLOGY_CONNECTION structure [Streaming Media Devices], PCCONNECTION_DESCRIPTOR, PCCONNECTION_DESCRIPTOR structure, PKSTOPOLOGY_CONNECTION, PKSTOPOLOGY_CONNECTION structure pointer [Streaming Media Devices], ks-struct_b688f291-7064-492b-8ab6-5f167941ebbf.xml, ks/KSTOPOLOGY_CONNECTION, ks/PKSTOPOLOGY_CONNECTION, stream.kstopology_connection"
ms.topic: struct
f1_keywords:
 - "ks/KSTOPOLOGY_CONNECTION"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ks.h
api_name:
- KSTOPOLOGY_CONNECTION
product:
- Windows
targetos: Windows
req.typenames: KSTOPOLOGY_CONNECTION, *PKSTOPOLOGY_CONNECTION
---

# KSTOPOLOGY_CONNECTION structure

## -description

The KSTOPOLOGY_CONNECTION structure describes a single data-path connection inside a kernel streaming filter.

PCCONNECTION_DESCRIPTOR is an alias for KSTOPOLOGY_CONNECTION.

## -struct-fields

### -field FromNode

Specifies the node ID of the node on the upstream end of the connection. If this end of the connection is an external pin on the filter, not a logical pin on a node,m set this member to the null node-ID value, KSFILTER_NODE.

### -field FromNodePin

Specifies the pin ID for the upstream end of the connection. If **FromNode **is KSFILTER_NODE, the pin on this end of the connection is an external pin on the filter. If not, the pin on this end is a logical pin on an internal node.

### -field ToNode

Specifies the node ID of the node on the downstream end of the connection. If this end of the connection is an external pin on the filter, not a logical pin on a node, set this member to the null node-ID value, KSFILTER_NODE.

### -field ToNodePin

Specifies the pin ID for the downstream end of the connection. If **ToNode** is KSFILTER_NODE, the pin on this end of the connection is an external pin on the filter. If not, the pin on this end is a logical pin on an internal node.

## -remarks

KSTOPOLOGY_CONNECTION represents a single connection inside a filter, between either external pins, internal nodes, or an external pin and an internal node.

A streaming driver returns an array of KSTOPOLOGY_CONNECTION structures in response to a [KSPROPERTY_TOPOLOGY_CONNECTIONS](https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-topology-connections) get-property request.

When representing a connection between two external pins, both **FromNode** and **ToNode** should be set to KSFILTER_NODE, and the **FromNodePin** and **ToNodePin** should be the pin type ID of the respective pins. See [KSPROPSETID_Pin](https://docs.microsoft.com/windows-hardware/drivers/stream/kspropsetid-pin) for a description of pin type IDs.

Otherwise, **FromNodePin** or **ToNodePin** represent a logical incoming or outgoing pin for the connection. The logical pin numbers are used solely to describe a connection between nodes; they have no existence outside of the KSPROPERTY_TOPOLOGY_CONNECTIONS property.

### PCCONNECTION_DESCRIPTOR

The PCCONNECTION_DESCRIPTOR structure name is an alias for KSTOPOLOGY_CONNECTION. PCCONNECTION_DESCRIPTOR for IMiniport::GetDescription() is a description of a node connection in the topology of the filter implemented by the miniport. It is defined as follows in the portcls.h header:

```cpp
typedef KSTOPOLOGY_CONNECTION PCCONNECTION_DESCRIPTOR, *PPCCONNECTION_DESCRIPTOR;
```

Note that for the parameter descriptions, the [PCFILTER_NODE](https://docs.microsoft.com/previous-versions/ff537695(v=vs.85)) is used with PCCONNECTION_DESCRIPTOR instead of KSFILTER_NODE.

The [PCCONNECTION_DESCRIPTOR](https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff537688(v=vs.85)) structure specifies a single connection inside a filter. The connection can be one of the following:

- A connection between two internal nodes

- A connection between an internal node and a pin on the filter

- A connection between two pins on the filter

The last type of connection occurs when an input pin on a filter streams data directly to an output pin on the same filter.

An adapter driver uses an array of  structures to specify the internal topology of a filter.

The data stream flows from the **FromNode** end to the **ToNode** end of the connection.

To use the **PCCONNECTION_DESCRIPTOR** structure, the driver writer assigns "logical" pins to the nodes inside the filter. These "pins" are connection points on the nodes and are analogous to the external pins that the filter uses to connect to other filters. However, logical pins on nodes are used solely to specify the connections inside the filter.

A simple node with a single input and a single output typically numbers its input and output pins one and zero, respectively. By convention, this numbering is based on the direction of IRP flow rather than data flow.

More complex nodes might require standardized pin IDs in order to allow clients to more easily determine the assignment of functions to specific pins. For example, the [KSNODETYPE_ACOUSTIC_ECHO_CANCEL](https://docs.microsoft.com/windows-hardware/drivers/audio/ksnodetype-acoustic-echo-cancel) node uses standardized IDs for its four pins.

When the pin on one end of a connection is an input or output pin on the filter rather than a logical pin on a node, set the **FromNode** or **ToNode** member (depending on which end of the connection you are specifying) to the null node-ID value, [PCFILTER_NODE](https://docs.microsoft.com/previous-versions/ff537695(v=vs.85)).

Avoid confusing logical pins, which are used solely to describe connection points on nodes within a filter, with the external pins that filters use to connect to other filters. Logical pins are rarely used outside of the **PCCONNECTION_DESCRIPTOR** structure. In this document, the term *pin* refers to a pin on a KS filter rather than a logical pin on a node unless noted otherwise.

The [IMiniport::GetDescription](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-iminiport-getdescription) method outputs a [PCFILTER_DESCRIPTOR](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/ns-portcls-pcfilter_descriptor) structure that contains a pointer to a **PCCONNECTION_DESCRIPTOR** array.

For a simple code example that shows how the **PCCONNECTION_DESCRIPTOR** structure is used, see [Exposing Filter Topology](https://docs.microsoft.com/windows-hardware/drivers/audio/exposing-filter-topology).

## -see-also

[BdaPropertyTemplateConnections](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bdasup/nf-bdasup-bdapropertytemplateconnections)

[KSPROPERTY_TOPOLOGY_CONNECTIONS](https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-topology-connections)

[KSPROPSETID_Pin](https://docs.microsoft.com/windows-hardware/drivers/stream/kspropsetid-pin)

[KSPROPSETID_Topology](https://docs.microsoft.com/windows-hardware/drivers/stream/kspropsetid-topology)
