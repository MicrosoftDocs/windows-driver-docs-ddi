---
UID: NS:portcls._PCCONNECTION_DESCRIPTOR
title: _PCCONNECTION_DESCRIPTOR (portcls.h)
description: The PCCONNECTION_DESCRIPTOR structure describes a single data-path connection inside a KS filter. 
old-location: audio\PCCONNECTION_DESCRIPTOR.htm
tech.root: audio
ms.assetid: 9f50924e-d15c-48fd-8846-1f94be163661
ms.date: 09/30/2020
keywords: ["PCCONNECTION_DESCRIPTOR structure"]
ms.keywords: "*PPCCONNECTION_DESCRIPTOR, PCCONNECTION_DESCRIPTOR, PCCONNECTION_DESCRIPTOR structure [Audio Devices], PPCCONNECTION_DESCRIPTOR, PPCCONNECTION_DESCRIPTOR structure pointer [Audio Devices], _PCCONNECTION_DESCRIPTOR, audio.PCCONNECTION_DESCRIPTOR, portcls/PCCONNECTION_DESCRIPTOR, portcls/PPCCONNECTION_DESCRIPTOR"
req.header: portcls.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1703
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
targetos: Windows
req.typenames: PCCONNECTION_DESCRIPTOR, *PPCCONNECTION_DESCRIPTOR
f1_keywords:
 - _PCCONNECTION_DESCRIPTOR
 - portcls/_PCCONNECTION_DESCRIPTOR
 - PPCCONNECTION_DESCRIPTOR
 - portcls/PPCCONNECTION_DESCRIPTOR
 - PCCONNECTION_DESCRIPTOR
 - portcls/PCCONNECTION_DESCRIPTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Portcls.h
api_name:
 - PCCONNECTION_DESCRIPTOR
---

# _PCCONNECTION_DESCRIPTOR structure

## -description

The **PCCONNECTION_DESCRIPTOR** structure describes a single data-path connection inside a KS filter. A filter's internal topology can be specified by an array of **PCCONNECTION_DESCRIPTOR** structures. A WDM audio adapter driver returns an array of these structures in response to a [**IMiniport::GetDescription**](/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiport-getdescription) call or a [**KSPROPERTY_TOPOLOGY_CONNECTIONS**](/windows-hardware/drivers/stream/ksproperty-topology-connections) get-property request. **PCCONNECTION_DESCRIPTOR** is an alias for [**KSTOPOLOGY_CONNECTION**](/windows-hardware/drivers/ddi/ks/ns-ks-kstopology_connection).

## -struct-fields

### -field FromNode

Specifies a node ID. This member identifies the node on the upstream end of the connection. If this end of the connection is an input (sink) pin on the filter--not a logical pin on a node--set this member to the null node-ID value, [**PCFILTER_NODE**](https://msdn.microsoft.com/library/ff537695(v=vs.85)).

### -field FromNodePin
  
Specifies a pin ID. This member identifies the pin on the upstream end of the connection. If the **FromNode** member is set to [**PCFILTER_NODE**](https://msdn.microsoft.com/library/ff537695(v=vs.85)), the pin on this end of the connection is an input (sink) pin on the filter. Otherwise, it is a logical pin on an internal node.

### -field ToNode
  
Specifies a node ID. This member identifies the node on the downstream end of the connection. If this end of the connection is an output (source) pin on the filter--not a logical pin on a node--set this member to the null node-ID value, [**PCFILTER_NODE**](https://msdn.microsoft.com/library/ff537695(v=vs.85)).

### -field ToNodePin
  
Specifies a pin ID. This member identifies the pin on the downstream end of the connection. If the **ToNode** member is set to [**PCFILTER_NODE**](https://msdn.microsoft.com/library/ff537695(v=vs.85)), the pin on this end of the connection is an output (source) pin on the filter. Otherwise, it is a logical pin on an internal node.

## -remarks

The **PCCONNECTION_DESCRIPTOR** structure specifies a single connection inside a filter. The connection can be one of the following:

* A connection between two internal nodes

* A connection between an internal node and a pin on the filter

* A connection between two pins on the filter

The last type of connection occurs when an input pin on a filter streams data directly to an output pin on the same filter.

An adapter driver uses an array of structures to specify the internal topology of a filter.

The data stream flows from the **FromNode** end to the **ToNode** end of the connection.

To use the **PCCONNECTION_DESCRIPTOR** structure, the driver writer assigns "logical" pins to the nodes inside the filter. These "pins" are connection points on the nodes and are analogous to the external pins that the filter uses to connect to other filters. However, logical pins on nodes are used solely to specify the connections inside the filter.

A simple node with a single input and a single output typically numbers its input and output pins one and zero, respectively. By convention, this numbering is based on the direction of IRP flow rather than data flow.

More complex nodes might require standardized pin IDs in order to allow clients to more easily determine the assignment of functions to specific pins. For example, the [**KSNODETYPE_ACOUSTIC_ECHO_CANCEL**](https://msdn.microsoft.com/library/ff537150(v=vs.85)) node uses standardized IDs for its four pins.

When the pin on one end of a connection is an input or output pin on the filter rather than a logical pin on a node, set the **FromNode** or **ToNode** member (depending on which end of the connection you are specifying) to the null node-ID value, [**PCFILTER_NODE**](https://msdn.microsoft.com/library/ff537695(v=vs.85)).

Avoid confusing logical pins, which are used solely to describe connection points on nodes within a filter, with the external pins that filters use to connect to other filters. Logical pins are rarely used outside of the **PCCONNECTION_DESCRIPTOR** structure. In this document, the term _pin_ refers to a pin on a KS filter rather than a logical pin on a node unless noted otherwise.

The [**IMiniport::GetDescription**](/drivers/ddi/portcls/nf-portcls-iminiport-getdescription) method outputs a [**PCFILTER_DESCRIPTOR**](https://msdn.microsoft.com/library/ff537694(v=vs.85)) structure that contains a pointer to a **PCCONNECTION_DESCRIPTOR** array.

For a simple code example that shows how the **PCCONNECTION_DESCRIPTOR** structure is used, see [Exposing Filter Topology](https://msdn.microsoft.com/library/ff536378(v=vs.85)).

The [**PCFILTER_NODE**](https://msdn.microsoft.com/library/ff537695(v=vs.85)) constant is the null node ID for the **FromNode** or **ToNode** field in a **PCCONNECTION_DESCRIPTOR** structure.

If the structure's **FromNode** or **ToNode** member is set to[**PCFILTER_NODE**](https://msdn.microsoft.com/library/ff537695(v=vs.85)), the pin on this end of the connection is an input or output pin on the filter. Otherwise, it is a logical pin on a node inside the filter.

[**PCFILTER_NODE**](https://msdn.microsoft.com/library/ff537695(v=vs.85)) is defined to be the value ((ULONG)-1).

## -requirements

**Header**

Portcls.h (include Portcls.h)

## -see-also

[**IMiniport::GetDescription**](https://msdn.microsoft.com/library/ff536765(v=vs.85))

[**KSPROPERTY_TOPOLOGY_CONNECTIONS**](https://msdn.microsoft.com/library/ff565802(v=vs.85))

[**KSTOPOLOGY_CONNECTION**](https://msdn.microsoft.com/library/ff567148(v=vs.85))

[**PCFILTER_NODE**](https://msdn.microsoft.com/library/ff537695(v=vs.85))

[**PCFILTER_DESCRIPTOR**](https://msdn.microsoft.com/library/ff537694(v=vs.85))
