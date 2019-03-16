---
UID: NS:sdpnode._SDP_NODE
title: _SDP_NODE (sdpnode.h)
description: The SDP_NODE structure holds information about an element in a tree-based representation of an SDP record.
old-location: bltooth\sdp_node.htm
tech.root: bltooth
ms.assetid: 11d603e9-6db1-44a2-b4e3-d85ffe0d5c25
ms.date: 04/27/2018
ms.keywords: "*PSDP_NODE, PSDP_NODE, PSDP_NODE structure pointer [Bluetooth Devices], SDP_NODE, SDP_NODE structure [Bluetooth Devices], _SDP_NODE, bltooth.sdp_node, bth_structs_30367149-bffb-4ff9-a6d8-2f73c5198874.xml, sdpnode/PSDP_NODE, sdpnode/SDP_NODE"
ms.topic: struct
req.header: sdpnode.h
req.include-header: Sdpnode.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
- sdpnode.h
api_name:
- SDP_NODE
product:
- Windows
targetos: Windows
req.typenames: SDP_NODE, *PSDP_NODE
---

# _SDP_NODE structure


## -description


The SDP_NODE structure holds information about an element in a tree-based representation of an SDP
  record.


## -struct-fields




### -field hdr

An 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536850">SDP_NODE_HEADER</a> structure that contains
     links to peer SDP_NODE structures and the data type of the current node.


### -field DataSize

The size, in bytes, of the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536849">SDP_NODE_DATA</a> union held in the 
     <b>u</b> member.


### -field u

An SDP_NODE_DATA union that contains the data associated with the SDP record's node.


### -field Reserved

Reserved for future use. Do not use.


## -remarks



Each SDP_NODE structure in the tree representation of an SDP record contains a SDP_NODE_HEADER
    structure and an SDP_NODE_DATA union.

The header specifies the type of data. Driver developers can access links to peer SDP_NODE structures
    by calling the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff554296">LIST_ENTRY</a> structure of the header. By evaluating 
    <code>Node.hdr.Link.Flink</code>and 
    <code>Node.hdr.Link.Blink</code>, drivers can obtain the addresses of peer
    nodes in the tree. Keep in mind that 
    <b>LIST_ENTRY</b> pointers contain the addresses of other LIST_ENTRY structures, and that the profile
    drivers must use the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff542043">CONTAINING_RECORD</a> memory manager macro to
    extract the address of the containing node record.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554296">LIST_ENTRY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536849">SDP_NODE_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536850">SDP_NODE_HEADER</a>
 

 

