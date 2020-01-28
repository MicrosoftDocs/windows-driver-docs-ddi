---
UID: NF:sdplib.SdpFreeTree
title: SdpFreeTree function (sdplib.h)
description: The Bluetooth SdpFreeTree function is used to free the memory allocated for the tree-based representation of an SDP record.
old-location: bltooth\sdpfreetree.htm
tech.root: bltooth
ms.assetid: 7d3f743e-2422-474d-aaad-4386e0dc100a
ms.date: 04/27/2018
ms.keywords: SdpFreeTree, SdpFreeTree function [Bluetooth Devices], bltooth.sdpfreetree, bth_funcs_526ed9cd-2c07-4c1f-a420-dec6fe930e44.xml, sdplib/SdpFreeTree
f1_keywords:
 - "sdplib/SdpFreeTree"
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
- SdpFreeTree
product:
- Windows
targetos: Windows
req.typenames: 
---

# SdpFreeTree function


## -description


The Bluetooth 
  <b>SdpFreeTree</b> function is used to free the memory allocated for the tree-based representation of an SDP
  record.


## -parameters




### -param Tree [in]

The root node of the SDP tree-based representation to be freed.


## -returns



Possible return values include:




## -remarks



Callers should perform an 
    <b>SdpFreeTree</b> call when the tree-based representation of an SDP record is no longer needed. The 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sdplib/nf-sdplib-sdpcreatenodetree">SdpCreateNodeTree</a> and 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthsdpddi/nc-bthsdpddi-pconvertstreamtotree">SdpConvertStreamToTree</a> functions
    allocate the memory for the tree representations of SDP records that they create. The 
    <b>SdpFreeTree</b> function releases the memory allocated to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sdpnode/ns-sdpnode-_sdp_tree_root_node">SDP_TREE_ROOT_NODE</a> structure that these
    functions create and all 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sdpnode/ns-sdpnode-_sdp_node">SDP_NODE</a> structures associated with the tree
    representation.

Bluetooth profile drivers can obtain a pointer to the 
    <b>SdpFreeTree</b> function through the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthsdpddi/ns-bthsdpddi-_bthddi_sdp_node_interface">
    BTHDDI_SDP_NODE_INTERFACE</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthsdpddi/ns-bthsdpddi-_bthddi_sdp_node_interface">BTHDDI_SDP_NODE_INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sdpnode/ns-sdpnode-_sdp_node">SDP_NODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sdpnode/ns-sdpnode-_sdp_tree_root_node">SDP_TREE_ROOT_NODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthsdpddi/nc-bthsdpddi-pconvertstreamtotree">SdpConvertStreamToTree</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sdplib/nf-sdplib-sdpcreatenodetree">SdpCreateNodeTree</a>
 

 

