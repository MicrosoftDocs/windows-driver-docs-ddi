---
UID: NC:bthsdpddi.PCONVERTSTREAMTOTREE
title: PCONVERTSTREAMTOTREE (bthsdpddi.h)
description: The Bluetooth SdpConvertStreamToTree function is used to create a Microsoft proprietary tree-based representation of an SDP record, while leaving the original stream-based representation unmodified.
old-location: bltooth\sdpconvertstreamtotree.htm
tech.root: bltooth
ms.assetid: 3b285a32-c1bc-4103-aa2e-0f6c8f5cc7ec
ms.date: 04/27/2018
ms.keywords: PCONVERTSTREAMTOTREE, PCONVERTSTREAMTOTREE callback, SdpConvertStreamToTree, SdpConvertStreamToTree callback function [Bluetooth Devices], bltooth.sdpconvertstreamtotree, bth_funcs_7155961d-c993-428b-a16e-4fdcf85e28c2.xml, bthsdpddi/SdpConvertStreamToTree
req.header: bthsdpddi.h
req.include-header: BthSdpddi.h
req.target-type: Desktop
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
req.irql: <= PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - "bthsdpddi/SdpConvertStreamToTree"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - BthSdpddi.h
api_name:
 - SdpConvertStreamToTree
product:
 - Windows
---

# PCONVERTSTREAMTOTREE callback function

## -description

The Bluetooth 
  <b>SdpConvertStreamToTree</b> function is used to create a Microsoft proprietary tree-based representation
  of an SDP record, while leaving the original stream-based representation unmodified.

## -parameters

### -param Stream

The SDP record stream to convert into a tree-based representation.

### -param Size

The size of the source SDP record stream.

### -param Node

A pointer to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sdpnode/ns-sdpnode-_sdp_tree_root_node">SDP_TREE_ROOT_NODE</a> structure that serves
     as the root of the SDP tree-based representation of the SDP record.

### -param tag

Specifies a 4-byte 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/">pool tag</a> that uniquely identifies the driver that does the memory
     allocation. For more information about pool tags, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithtag">ExAllocatePoolWithTag</a>.

## -returns

Possible return values include:


<dl>
<dt>STATUS_SUCCESS
      </dt>
<dt>STATUS_INSUFFICIENT_RESOURCES
      </dt>
<dt>STATUS_INVALID_PARAMETER</dt>
</dl>

## -remarks

Because a tree can be traversed by evaluating pointers, the 
    <b>SdpConvertStreamToTree</b> function can make it easier for profile drivers to extract information from
    an SDP record.

The tree representation of the SDP record that results from calling the 
    <b>SdpConvertStreamToTree</b> function consists of a series of interconnected 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sdpnode/ns-sdpnode-_sdp_node">SDP_NODE</a> structures. The root node contains a single
    SDP_TREE_ROOT_NODE structure.

Each SDP_NODE structure contains an 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sdpnode/ns-sdpnode-_sdp_node_header">SDP_NODE_HEADER</a> structure and an 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sdpnode/ns-sdpnode-_sdp_node_data">SDP_NODE_DATA</a> union. The header specifies the
    type of data, and Bluetooth profile drivers can access links to peer SDP_NODE structures through the 
    <a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-list_entry">LIST_ENTRY</a> system structure. By evaluating this
    structure's 
    <code>Node.hdr.Link.Flink</code>and 
    <code>Node.hdr.Link.Blink</code>, drivers can obtain the addresses of peer
    nodes in the tree. Keep in mind that the pointers in the LIST_ENTRY structure hold addresses to other
    LIST_ENTRY structures, and that Bluetooth drivers must use the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/mm-bad-pointer">CONTAINING_RECORD</a> memory manager macro to
    extract the address of the containing node record.

By using the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sdpnode/ns-sdpnode-_sdp_node_data">SDP_NODE_DATA</a> union's 
    <b>sequence</b> and 
    <b>alternative</b> members, profile drivers can access sub-elements of the tree. If the data type of the
    node is 
    <b>SDP_TYPE_SEQUENCE</b>, the node is an SDP sequence. If the data type of the node is 
    <b>SDP_TYPE_ALTERNATIVE</b>, the node is an SDP alternative sequence. In the first case, the sequence
    member is valid and contains the information necessary to access the portion of the tree corresponding
    with the sequnce. In the second case, the alternative member is valid and contains the information
    necessary to access the portion of the tree corresponding to the alternative. The 
    <b>sequence</b> or 
    <b>alternative</b> member, when used, contains an extra SDP_NODE_HEADER structure that is used to access
    the nodes in the sequence or alternative. For example, 
    <code>node->u.sequence.Flink</code>points to the LIST_ENTRY structure of
    the first member of the sequence represented by the node.

The remaining members of the data union contain actual data extracted from the SDP stream. For most
    types, the data is directly present in the structure. However, for strings and URLs, a pointer is
    provided to the actual data. The memory for the string is allocated by the 
    <b>SdpConvertStreamToTree</b> function call and must be freed by calling the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sdplib/nf-sdplib-sdpfreetree">SdpFreeTree</a> function for the tree.

Bluetooth profile drivers can obtain a pointer to this function through the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthsdpddi/ns-bthsdpddi-_bthddi_sdp_parse_interface">BTHDDI_SDP_PARSE_INTERFACE</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthsdpddi/ns-bthsdpddi-_bthddi_sdp_parse_interface">BTHDDI_SDP_PARSE_INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/mm-bad-pointer">CONTAINING_RECORD</a>



<a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-list_entry">LIST_ENTRY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sdpnode/ns-sdpnode-_sdp_node">SDP_NODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sdpnode/ns-sdpnode-_sdp_node_data">SDP_NODE_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sdpnode/ns-sdpnode-_sdp_node_header">SDP_NODE_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sdpnode/ns-sdpnode-_sdp_tree_root_node">SDP_TREE_ROOT_NODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sdplib/nf-sdplib-sdpfreetree">SdpFreeTree</a>

