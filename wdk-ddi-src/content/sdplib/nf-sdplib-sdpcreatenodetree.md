---
UID: NF:sdplib.SdpCreateNodeTree
title: SdpCreateNodeTree function (sdplib.h)
description: The Bluetooth SdpCreateNodeTree function is used to allocate an empty root SDP_TREE_ROOT_NODE structure.
old-location: bltooth\sdpcreatenodetree.htm
tech.root: bltooth
ms.assetid: c019f382-1ad3-4b08-a254-ae803e2b6bc6
ms.date: 04/27/2018
keywords: ["SdpCreateNodeTree function"]
ms.keywords: SdpCreateNodeTree, SdpCreateNodeTree function [Bluetooth Devices], bltooth.sdpcreatenodetree, bth_funcs_95027cd6-7f0b-48e1-a574-990754e28e74.xml, sdplib/SdpCreateNodeTree
f1_keywords:
 - "sdplib/SdpCreateNodeTree"
req.header: sdplib.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- sdplib.h
api_name:
- SdpCreateNodeTree
product:
- Windows
targetos: Windows
req.typenames: 
---

# SdpCreateNodeTree function


## -description


The Bluetooth 
  <b>SdpCreateNodeTree</b> function is used to allocate an empty root 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sdpnode/ns-sdpnode-_sdp_tree_root_node">SDP_TREE_ROOT_NODE</a> structure.


## -parameters




### -param tag [in]

A profile driver defined tag to associate with the node.


## -returns



If successful, this function returns a pointer to the newly allocated SDP_TREE_ROOT_NODE
     structure. If not successful, this function returns <b>NULL</b>.




## -remarks



Calling the 
    <b>SdpCreateNodeTree</b> function is the first step in building an SDP tree. After a Bluetooth profile
    driver allocates a root node by using this function, the node can be populated by using calls to other
    functions pointed to by the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthsdpddi/ns-bthsdpddi-_bthddi_sdp_node_interface">
    BTHDDI_SDP_NODE_INTERFACE</a> structure.

When an SDP tree is no longer needed, the Bluetooth profile driver should destroy it by calling the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sdplib/nf-sdplib-sdpfreetree">SdpFreeTree</a> function. 
    <b>SdpFreeTree</b> frees the root node and all child nodes that have been attached to it. Individual 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sdpnode/ns-sdpnode-_sdp_node">SDP_NODE</a> structures can be freed by calling the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exfreepool">ExFreePool</a> driver support routine as long as they
    are no longer part of a tree or other list.

Bluetooth profile drivers can obtain a pointer to this function through the BTHDDI_SDP_NODE_INTERFACE
    structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthsdpddi/ns-bthsdpddi-_bthddi_sdp_node_interface">BTHDDI_SDP_NODE_INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exfreepool">ExFreePool</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sdpnode/ns-sdpnode-_sdp_node">SDP_NODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sdpnode/ns-sdpnode-_sdp_tree_root_node">SDP_TREE_ROOT_NODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sdplib/nf-sdplib-sdpfreetree">SdpFreeTree</a>
 

 

