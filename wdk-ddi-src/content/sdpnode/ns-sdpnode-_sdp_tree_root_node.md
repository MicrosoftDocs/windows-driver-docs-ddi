---
UID: NS:sdpnode._SDP_TREE_ROOT_NODE
title: "_SDP_TREE_ROOT_NODE"
author: windows-driver-content
description: The SDP_TREE_ROOT_NODE structure is the root element of a tree-based representation of an SDP record.
old-location: bltooth\sdp_tree_root_node.htm
old-project: bltooth
ms.assetid: bde75364-387b-4f57-8942-1cf32652c02d
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PSDP_TREE_ROOT_NODE, PSDP_TREE_ROOT_NODE, PSDP_TREE_ROOT_NODE structure pointer [Bluetooth Devices], SDP_TREE_ROOT_NODE, SDP_TREE_ROOT_NODE structure [Bluetooth Devices], _SDP_TREE_ROOT_NODE, bltooth.sdp_tree_root_node, bth_structs_b2bdb873-03b0-4c3a-910c-06277f6be663.xml, sdpnode/PSDP_TREE_ROOT_NODE, sdpnode/SDP_TREE_ROOT_NODE"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	sdpnode.h
api_name:
-	SDP_TREE_ROOT_NODE
product: Windows
targetos: Windows
req.typenames: SDP_TREE_ROOT_NODE, *PSDP_TREE_ROOT_NODE
req.product: Windows 10 or later.
---

# _SDP_TREE_ROOT_NODE structure


## -description


The SDP_TREE_ROOT_NODE structure is the root element of a tree-based representation of an SDP
  record.


## -struct-fields




### -field RootNode

An 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536848">SDP_NODE</a> structure that represents the root node of
     a tree-based representation of an SDP record.


## -remarks



Several SDP functions access or output this structure when they build a tree-based SDP record or
    convert a raw SDP record stream into a tree-based record.

The 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536784">SdpAddAttributeToTree</a> function adds
    an SDP_NODE structure that contains SDP attribute information to an existing SDP_TREE_ROOT_NODE
    structure.

The 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536794">SdpConvertStreamToTree</a> function
    outputs this structure as the root element of an SDP record that it converts from a stream to a
    tree-based structure.

The 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536796">SdpConvertTreeToStream</a> function uses
    an existing SDP_TREE_ROOT_NODE structure as input when it converts a tree-based representation of an SDP
    record into a stream.

The 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536818">SdpCreateNodeTree</a> function creates an
    empty SDP_TREE_ROOT_NODE structure. This is the first step in creating an SDP record as a tree. After the
    SDP tree is completed, a profile driver that is using SDP to advertise its service can convert the tree
    into an SDP record stream using the 
    <b>SdpConvertTreeToStream</b> function.

The 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536838">SdpFindAttributeInTree</a> function
    searches a populated SDP_TREE_ROOT_NODE structure for an SDP attribute value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536848">SDP_NODE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536784">SdpAddAttributeToTree</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536794">SdpConvertStreamToTree</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536796">SdpConvertTreeToStream</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536818">SdpCreateNodeTree</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536838">SdpFindAttributeInTree</a>
 

 

