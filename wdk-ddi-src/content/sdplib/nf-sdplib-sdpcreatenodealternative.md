---
UID: NF:sdplib.SdpCreateNodeAlternative
title: SdpCreateNodeAlternative function
author: windows-driver-content
description: The Bluetooth SdpCreateNodeAlternative function is used to create an empty alternative sequence SDP node.
old-location: bltooth\sdpcreatenodealternative.htm
old-project: bltooth
ms.assetid: 1e6b922d-01a2-4a67-91cb-74956d40d769
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: SdpCreateNodeAlternative, SdpCreateNodeAlternative function [Bluetooth Devices], bltooth.sdpcreatenodealternative, bth_funcs_e54ab424-3fbf-479a-9368-51d824c1fbec.xml, sdplib/SdpCreateNodeAlternative
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	sdplib.h
api_name:
-	SdpCreateNodeAlternative
product: Windows
targetos: Windows
req.typenames: SDCMD_DESCRIPTOR, *PSDCMD_DESCRIPTOR
req.product: Windows 10 or later.
---

# SdpCreateNodeAlternative function


## -description


The Bluetooth 
  <b>SdpCreateNodeAlternative</b> function is used to create an empty alternative sequence SDP node.


## -syntax


````
PSDP_NODE SdpCreateNodeAlternative(
  _In_ ULONG tag
);
````


## -parameters




### -param tag [in]

A profile driver defined tag to associate with the node.


## -returns



If successful, this function returns a pointer to the newly allocated 
     <a href="..\sdpnode\ns-sdpnode-_sdp_node.md">SDP_NODE</a> structure. If not successful, this
     function returns 
     <b>NULL</b>.




## -remarks



After an alternative sequence node is created by calling the 
    <b>SdpCreateNodeAlternative</b> function, Bluetooth drivers can call the 
    <a href="..\sdplib\nf-sdplib-sdpappendnodetocontainernode.md">
    SdpAppendNodeToContainerNode</a> function to insert other nodes into the alternative sequence node or
    to add the new alternative sequence node to another alternative sequence node.

An alternative sequence node can be added as a top-level attribute of an SDP record by calling the 
    <a href="..\sdplib\nf-sdplib-sdpaddattributetotree.md">SdpAddAttributeToTree</a> function.

Bluetooth profile drivers can obtain a pointer to this function through the 
    <a href="..\bthsdpddi\ns-bthsdpddi-_bthddi_sdp_node_interface.md">BTHDDI_SDP_NODE_INTERFACE</a>.




## -see-also

<a href="..\sdplib\nf-sdplib-sdpappendnodetocontainernode.md">SdpAppendNodeToContainerNode</a>



<a href="..\sdplib\nf-sdplib-sdpaddattributetotree.md">SdpAddAttributeToTree</a>



<a href="..\sdpnode\ns-sdpnode-_sdp_node.md">SDP_NODE</a>



<a href="..\bthsdpddi\ns-bthsdpddi-_bthddi_sdp_node_interface.md">BTHDDI_SDP_NODE_INTERFACE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20SdpCreateNodeAlternative function%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

