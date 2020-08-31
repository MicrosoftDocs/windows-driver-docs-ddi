---
UID: NS:ks.__unnamed_struct_24
title: KSTOPOLOGY (ks.h)
description: The KSTOPOLOGY structure describes the topology of pins and nodes.
old-location: stream\kstopology.htm
tech.root: stream
ms.assetid: 8dbd37ed-5d71-43bd-a3ca-caa5b0d08075
ms.date: 04/23/2018
keywords: ["KSTOPOLOGY structure"]
ms.keywords: "*PKSTOPOLOGY, KSTOPOLOGY, KSTOPOLOGY structure [Streaming Media Devices], PKSTOPOLOGY, PKSTOPOLOGY structure pointer [Streaming Media Devices], ks-struct_1d55c5f9-18d4-43d0-9fe9-291134e84115.xml, ks/KSTOPOLOGY, ks/PKSTOPOLOGY, stream.kstopology"
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
targetos: Windows
req.typenames: KSTOPOLOGY, *PKSTOPOLOGY
f1_keywords:
 - PKSTOPOLOGY
 - ks/PKSTOPOLOGY
 - KSTOPOLOGY
 - ks/KSTOPOLOGY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KSTOPOLOGY
---

# KSTOPOLOGY structure


## -description

The KSTOPOLOGY structure describes the topology of pins and nodes.

## -struct-fields

### -field CategoriesCount

Specifies the number of functional categories that the driver supports.

### -field Categories

Points to the beginning of the array of functional categories that the driver supports.

### -field TopologyNodesCount

Specifies the number of nodes that the driver supports.

### -field TopologyNodes

Points to the beginning of the array of GUIDs that describe the type of each node. For a list of video kernel streaming related nodes, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/kernel-streaming-topology-nodes">Kernel Streaming Topology Nodes</a>. For a list of audio kernel streaming related nodes, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/audio-topology-nodes">Audio Topology Nodes</a>.

### -field TopologyConnectionsCount

Specifies the number of entries in the array pointed to by <b>TopologyConnections</b>. The node numbers of each entry must correspond to the array offset of the node within <b>TopologyNodes</b>. When this structure is a part of a streaming minidriver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_stream_header">HW_STREAM_HEADER</a>, the pin numbers must correspond to the offsets within the array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_stream_information">HW_STREAM_INFORMATION</a> structures in the minidriver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_stream_descriptor">HW_STREAM_DESCRIPTOR</a> structure.

### -field TopologyConnections

Points to the beginning of the array of topology connections for this structure.

### -field TopologyNodesNames

Specifies the GUID of the localized Unicode string name for the node, stored in the registry.

### -field Reserved

Reserved for system use. Drivers should set this to zero.

## -remarks

A stream class minidriver creates and passes this structure as part of its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_stream_header">HW_STREAM_HEADER</a> structure. The class driver uses this structure to process topology property requests. The property data that the class driver returns is determined from the KSTOPOLOGY structure as follows:

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_stream_descriptor">HW_STREAM_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_stream_header">HW_STREAM_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_stream_information">HW_STREAM_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-kstopology_connection">KSTOPOLOGY_CONNECTION</a>

