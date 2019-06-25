---
UID: NF:sdplib.SdpCreateNodeAlternative
title: SdpCreateNodeAlternative function (sdplib.h)
description: The Bluetooth SdpCreateNodeAlternative function is used to create an empty alternative sequence SDP node.
old-location: bltooth\sdpcreatenodealternative.htm
tech.root: bltooth
ms.assetid: 1e6b922d-01a2-4a67-91cb-74956d40d769
ms.date: 04/27/2018
ms.keywords: SdpCreateNodeAlternative, SdpCreateNodeAlternative function [Bluetooth Devices], bltooth.sdpcreatenodealternative, bth_funcs_e54ab424-3fbf-479a-9368-51d824c1fbec.xml, sdplib/SdpCreateNodeAlternative
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
req.lib: 
req.dll: 
req.irql: "<= PASSIVE_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- sdplib.h
api_name:
- SdpCreateNodeAlternative
product:
- Windows
targetos: Windows
req.typenames: 
---

# SdpCreateNodeAlternative function


## -description


The Bluetooth 
  <b>SdpCreateNodeAlternative</b> function is used to create an empty alternative sequence SDP node.


## -parameters




### -param tag [in]

A profile driver defined tag to associate with the node.


## -returns



If successful, this function returns a pointer to the newly allocated 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sdpnode/ns-sdpnode-_sdp_node">SDP_NODE</a> structure. If not successful, this
     function returns 
     <b>NULL</b>.




## -remarks



After an alternative sequence node is created by calling the 
    <b>SdpCreateNodeAlternative</b> function, Bluetooth drivers can call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sdplib/nf-sdplib-sdpappendnodetocontainernode">
    SdpAppendNodeToContainerNode</a> function to insert other nodes into the alternative sequence node or
    to add the new alternative sequence node to another alternative sequence node.

An alternative sequence node can be added as a top-level attribute of an SDP record by calling the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sdplib/nf-sdplib-sdpaddattributetotree">SdpAddAttributeToTree</a> function.

Bluetooth profile drivers can obtain a pointer to this function through the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthsdpddi/ns-bthsdpddi-_bthddi_sdp_node_interface">BTHDDI_SDP_NODE_INTERFACE</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthsdpddi/ns-bthsdpddi-_bthddi_sdp_node_interface">BTHDDI_SDP_NODE_INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sdpnode/ns-sdpnode-_sdp_node">SDP_NODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sdplib/nf-sdplib-sdpaddattributetotree">SdpAddAttributeToTree</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sdplib/nf-sdplib-sdpappendnodetocontainernode">SdpAppendNodeToContainerNode</a>
 

 

