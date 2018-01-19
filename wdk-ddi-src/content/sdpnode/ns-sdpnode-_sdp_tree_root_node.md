---
UID: NS:sdpnode._SDP_TREE_ROOT_NODE
title: _SDP_TREE_ROOT_NODE
author: windows-driver-content
description: The SDP_TREE_ROOT_NODE structure is the root element of a tree-based representation of an SDP record.
old-location: bltooth\sdp_tree_root_node.htm
old-project: bltooth
ms.assetid: bde75364-387b-4f57-8942-1cf32652c02d
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: _SDP_TREE_ROOT_NODE, *PSDP_TREE_ROOT_NODE, SDP_TREE_ROOT_NODE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: sdpnode.h
req.include-header: Sdpnode.h
req.target-type: Windows
req.target-min-winverclnt: Versions: Supported in Windows Vista, and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SDP_TREE_ROOT_NODE
req.alt-loc: sdpnode.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= PASSIVE_LEVEL
req.typenames: *PSDP_TREE_ROOT_NODE, SDP_TREE_ROOT_NODE
req.product: Windows 10 or later.
---

# _SDP_TREE_ROOT_NODE structure



## -description
The SDP_TREE_ROOT_NODE structure is the root element of a tree-based representation of an SDP
  record.



## -syntax

````
typedef struct _SDP_TREE_ROOT_NODE {
  SDP_NODE RootNode;
} SDP_TREE_ROOT_NODE, *PSDP_TREE_ROOT_NODE;
````


## -struct-fields

### -field RootNode

An 
     <a href="..\sdpnode\ns-sdpnode-_sdp_node.md">SDP_NODE</a> structure that represents the root node of
     a tree-based representation of an SDP record.


## -remarks
Several SDP functions access or output this structure when they build a tree-based SDP record or
    convert a raw SDP record stream into a tree-based record.

The 
    <a href="..\sdplib\nf-sdplib-sdpaddattributetotree.md">SdpAddAttributeToTree</a> function adds
    an SDP_NODE structure that contains SDP attribute information to an existing SDP_TREE_ROOT_NODE
    structure.

The 
    <a href="..\bthsdpddi\nc-bthsdpddi-pconvertstreamtotree.md">SdpConvertStreamToTree</a> function
    outputs this structure as the root element of an SDP record that it converts from a stream to a
    tree-based structure.

The 
    <a href="..\bthsdpddi\nc-bthsdpddi-pconverttreetostream.md">SdpConvertTreeToStream</a> function uses
    an existing SDP_TREE_ROOT_NODE structure as input when it converts a tree-based representation of an SDP
    record into a stream.

The 
    <a href="..\sdplib\nf-sdplib-sdpcreatenodetree.md">SdpCreateNodeTree</a> function creates an
    empty SDP_TREE_ROOT_NODE structure. This is the first step in creating an SDP record as a tree. After the
    SDP tree is completed, a profile driver that is using SDP to advertise its service can convert the tree
    into an SDP record stream using the 
    <b>SdpConvertTreeToStream</b> function.

The 
    <a href="..\sdplib\nf-sdplib-sdpfindattributeintree.md">SdpFindAttributeInTree</a> function
    searches a populated SDP_TREE_ROOT_NODE structure for an SDP attribute value.


## -see-also
<dl>
<dt>
<a href="..\sdpnode\ns-sdpnode-_sdp_node.md">SDP_NODE</a>
</dt>
<dt>
<a href="..\sdplib\nf-sdplib-sdpaddattributetotree.md">SdpAddAttributeToTree</a>
</dt>
<dt>
<a href="..\bthsdpddi\nc-bthsdpddi-pconvertstreamtotree.md">SdpConvertStreamToTree</a>
</dt>
<dt>
<a href="..\bthsdpddi\nc-bthsdpddi-pconverttreetostream.md">SdpConvertTreeToStream</a>
</dt>
<dt>
<a href="..\sdplib\nf-sdplib-sdpcreatenodetree.md">SdpCreateNodeTree</a>
</dt>
<dt>
<a href="..\sdplib\nf-sdplib-sdpfindattributeintree.md">SdpFindAttributeInTree</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20SDP_TREE_ROOT_NODE structure%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

