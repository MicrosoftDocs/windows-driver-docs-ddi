---
UID: NS:sdpnode._SDP_NODE_HEADER
title: "_SDP_NODE_HEADER"
author: windows-driver-content
description: The SDP_NODE_HEADER structure holds information about an element in a tree-based representation of an SDP record.
old-location: bltooth\sdp_node_header.htm
old-project: bltooth
ms.assetid: 2c756db7-b7a9-493a-8fb1-8bbc741f8c63
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: PSDP_NODE_HEADER, _SDP_NODE_HEADER, sdpnode/SDP_NODE_HEADER, *PSDP_NODE_HEADER, PSDP_NODE_HEADER structure pointer [Bluetooth Devices], sdpnode/PSDP_NODE_HEADER, bltooth.sdp_node_header, bth_structs_9fc0ef9d-c505-4cd8-8ea7-78988215c68a.xml, SDP_NODE_HEADER, SDP_NODE_HEADER structure [Bluetooth Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: "<= PASSIVE_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	sdpnode.h
apiname:
-	SDP_NODE_HEADER
product: Windows
targetos: Windows
req.typenames: "*PSDP_NODE_HEADER, SDP_NODE_HEADER"
req.product: Windows 10 or later.
---

# _SDP_NODE_HEADER structure


## -description


The SDP_NODE_HEADER structure holds information about an element in a tree-based representation of an
  SDP record.


## -syntax


````
typedef struct _SDP_NODE_HEADER {
  LIST_ENTRY Link;
  USHORT     Type;
  USHORT     SpecificType;
} SDP_NODE_HEADER, *PSDP_NODE_HEADER;
````


## -struct-fields




### -field Link

A linked-list structure that is used to link peer SDP record nodes when this structure is part of
     an 
     <a href="..\sdpnode\ns-sdpnode-_sdp_node.md">SDP_NODE</a> structure. This member is used to link the
     first child of the node when the header is 
     <b>u.sequence</b> or 
     <b>u.alternative</b> part of the individual SDP_NODE structure.


### -field Type

The data type of the 
     <a href="..\sdpnode\ns-sdpnode-_sdp_node_data.md">SDP_NODE_DATA</a> union held in the 
     <b>u</b> member of the SDP_NODE structure.


### -field SpecificType

Extra information about the data type associated with the 
     <b>SDP_NODE_DATA</b> union that is associated with the SDP record element.


## -remarks



Each SDP_NODE structure in the tree representation of an SDP record contains a SDP_NODE_HEADER
    structure and an 
    <b>SDP_NODE_DATA</b> union.

The header specifies the type of data. Driver developers can access links to peer SDP_NODE structures
    by calling the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff554296">LIST_ENTRY</a> structure of the header. By evaluating 
    <code>Node.hdr.Link.Flink</code>and 
    <code>Node.hdr.Link.Blink</code>, drivers can obtain the addresses of peer
    nodes in the tree. Keep in mind that 
    <b>LIST_ENTRY</b> pointers contain the address of other LIST_ENTRY structures, and that the profile driver
    must use the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff542043">CONTAINING_RECORD</a> memory manager macro to
    extract the address of the containing node record.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff542043">CONTAINING_RECORD</a>



<a href="..\sdpnode\ns-sdpnode-_sdp_node.md">SDP_NODE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554296">LIST_ENTRY</a>



<a href="..\sdpnode\ns-sdpnode-_sdp_node_data.md">SDP_NODE_DATA</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20SDP_NODE_HEADER structure%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

