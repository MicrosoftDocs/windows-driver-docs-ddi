---
UID: NF:sdplib.SdpFreeTree
title: SdpFreeTree function
author: windows-driver-content
description: The Bluetooth SdpFreeTree function is used to free the memory allocated for the tree-based representation of an SDP record.
old-location: bltooth\sdpfreetree.htm
old-project: bltooth
ms.assetid: 7d3f743e-2422-474d-aaad-4386e0dc100a
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: SdpFreeTree function [Bluetooth Devices], SdpFreeTree, bth_funcs_526ed9cd-2c07-4c1f-a420-dec6fe930e44.xml, bltooth.sdpfreetree, sdplib/SdpFreeTree
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "<= PASSIVE_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	sdplib.h
apiname:
-	SdpFreeTree
product: Windows
targetos: Windows
req.typenames: SDCMD_DESCRIPTOR, *PSDCMD_DESCRIPTOR
req.product: Windows 10 or later.
---

# SdpFreeTree function


## -description


The Bluetooth 
  <b>SdpFreeTree</b> function is used to free the memory allocated for the tree-based representation of an SDP
  record.


## -syntax


````
NTSTATUS SdpFreeTree(
  _In_ PSDP_TREE_ROOT_NODE Tree
);
````


## -parameters




### -param Tree [in]

The root node of the SDP tree-based representation to be freed.


## -returns



Possible return values include:




## -remarks



Callers should perform an 
    <b>SdpFreeTree</b> call when the tree-based representation of an SDP record is no longer needed. The 
    <a href="..\sdplib\nf-sdplib-sdpcreatenodetree.md">SdpCreateNodeTree</a> and 
    <a href="..\bthsdpddi\nc-bthsdpddi-pconvertstreamtotree.md">SdpConvertStreamToTree</a> functions
    allocate the memory for the tree representations of SDP records that they create. The 
    <b>SdpFreeTree</b> function releases the memory allocated to the 
    <a href="..\sdpnode\ns-sdpnode-_sdp_tree_root_node.md">SDP_TREE_ROOT_NODE</a> structure that these
    functions create and all 
    <a href="..\sdpnode\ns-sdpnode-_sdp_node.md">SDP_NODE</a> structures associated with the tree
    representation.

Bluetooth profile drivers can obtain a pointer to the 
    <b>SdpFreeTree</b> function through the 
    <a href="..\bthsdpddi\ns-bthsdpddi-_bthddi_sdp_node_interface.md">
    BTHDDI_SDP_NODE_INTERFACE</a> structure.




## -see-also

<a href="..\sdpnode\ns-sdpnode-_sdp_node.md">SDP_NODE</a>



<a href="..\bthsdpddi\ns-bthsdpddi-_bthddi_sdp_node_interface.md">BTHDDI_SDP_NODE_INTERFACE</a>



<a href="..\sdpnode\ns-sdpnode-_sdp_tree_root_node.md">SDP_TREE_ROOT_NODE</a>



<a href="..\sdplib\nf-sdplib-sdpcreatenodetree.md">SdpCreateNodeTree</a>



<a href="..\bthsdpddi\nc-bthsdpddi-pconvertstreamtotree.md">SdpConvertStreamToTree</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20SdpFreeTree function%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

