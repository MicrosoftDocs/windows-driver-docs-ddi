---
UID: NS:sdpnode._SDP_NODE
title: "_SDP_NODE"
author: windows-driver-content
description: The SDP_NODE structure holds information about an element in a tree-based representation of an SDP record.
old-location: bltooth\sdp_node.htm
old-project: bltooth
ms.assetid: 11d603e9-6db1-44a2-b4e3-d85ffe0d5c25
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: "_SDP_NODE, bth_structs_30367149-bffb-4ff9-a6d8-2f73c5198874.xml, SDP_NODE structure [Bluetooth Devices], PSDP_NODE, bltooth.sdp_node, SDP_NODE, sdpnode/PSDP_NODE, sdpnode/SDP_NODE, PSDP_NODE structure pointer [Bluetooth Devices], *PSDP_NODE"
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
-	SDP_NODE
product: Windows
targetos: Windows
req.typenames: "*PSDP_NODE, SDP_NODE"
req.product: Windows 10 or later.
---

# _SDP_NODE structure


## -description


The SDP_NODE structure holds information about an element in a tree-based representation of an SDP
  record.


## -syntax


````
typedef struct _SDP_NODE {
  SDP_NODE_HEADER hdr;
  ULONG           DataSize;
  SDP_NODE_DATA   u;
  PVOID           Reserved;
} SDP_NODE, *PSDP_NODE;
````


## -struct-fields




### -field hdr

An 
     <a href="..\sdpnode\ns-sdpnode-_sdp_node_header.md">SDP_NODE_HEADER</a> structure that contains
     links to peer SDP_NODE structures and the data type of the current node.


### -field DataSize

The size, in bytes, of the 
     <a href="..\sdpnode\ns-sdpnode-_sdp_node_data.md">SDP_NODE_DATA</a> union held in the 
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

<a href="..\sdpnode\ns-sdpnode-_sdp_node_header.md">SDP_NODE_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554296">LIST_ENTRY</a>



<a href="..\sdpnode\ns-sdpnode-_sdp_node_data.md">SDP_NODE_DATA</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20SDP_NODE structure%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

