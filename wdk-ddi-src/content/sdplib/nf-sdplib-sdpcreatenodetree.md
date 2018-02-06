---
UID: NF:sdplib.SdpCreateNodeTree
title: SdpCreateNodeTree function
author: windows-driver-content
description: The Bluetooth SdpCreateNodeTree function is used to allocate an empty root SDP_TREE_ROOT_NODE structure.
old-location: bltooth\sdpcreatenodetree.htm
old-project: bltooth
ms.assetid: c019f382-1ad3-4b08-a254-ae803e2b6bc6
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: SdpCreateNodeTree, SdpCreateNodeTree function [Bluetooth Devices], sdplib/SdpCreateNodeTree, bth_funcs_95027cd6-7f0b-48e1-a574-990754e28e74.xml, bltooth.sdpcreatenodetree
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
-	SdpCreateNodeTree
product: Windows
targetos: Windows
req.typenames: SDCMD_DESCRIPTOR, *PSDCMD_DESCRIPTOR
req.product: Windows 10 or later.
---

# SdpCreateNodeTree function


## -description


The Bluetooth 
  <b>SdpCreateNodeTree</b> function is used to allocate an empty root 
  <a href="..\sdpnode\ns-sdpnode-_sdp_tree_root_node.md">SDP_TREE_ROOT_NODE</a> structure.


## -syntax


````
PSDP_TREE_ROOT_NODE SdpCreateNodeTree(
  _In_ ULONG tag
);
````


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
    <a href="..\bthsdpddi\ns-bthsdpddi-_bthddi_sdp_node_interface.md">
    BTHDDI_SDP_NODE_INTERFACE</a> structure.

When an SDP tree is no longer needed, the Bluetooth profile driver should destroy it by calling the 
    <a href="..\sdplib\nf-sdplib-sdpfreetree.md">SdpFreeTree</a> function. 
    <b>SdpFreeTree</b> frees the root node and all child nodes that have been attached to it. Individual 
    <a href="..\sdpnode\ns-sdpnode-_sdp_node.md">SDP_NODE</a> structures can be freed by calling the 
    <a href="..\wdm\nf-wdm-exfreepool.md">ExFreePool</a> driver support routine as long as they
    are no longer part of a tree or other list.

Bluetooth profile drivers can obtain a pointer to this function through the BTHDDI_SDP_NODE_INTERFACE
    structure.



## -see-also

<a href="..\sdpnode\ns-sdpnode-_sdp_node.md">SDP_NODE</a>

<a href="..\wdm\nf-wdm-exfreepool.md">ExFreePool</a>

<a href="..\sdpnode\ns-sdpnode-_sdp_tree_root_node.md">SDP_TREE_ROOT_NODE</a>

<a href="..\bthsdpddi\ns-bthsdpddi-_bthddi_sdp_node_interface.md">BTHDDI_SDP_NODE_INTERFACE</a>

<a href="..\sdplib\nf-sdplib-sdpfreetree.md">SdpFreeTree</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20SdpCreateNodeTree function%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

