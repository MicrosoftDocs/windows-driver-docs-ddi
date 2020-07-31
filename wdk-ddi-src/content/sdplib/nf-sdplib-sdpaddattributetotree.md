---
UID: NF:sdplib.SdpAddAttributeToTree
title: SdpAddAttributeToTree function (sdplib.h)
description: The Bluetooth SdpAddAttributeToTree function is used to attach an SDP attribute node to the top level of an SDP record.
old-location: bltooth\sdpaddattributetotree.htm
tech.root: bltooth
ms.assetid: f5b72de2-c2e9-44ac-a2a7-04271e9253d3
ms.date: 04/27/2018
keywords: ["SdpAddAttributeToTree function"]
ms.keywords: SdpAddAttributeToTree, SdpAddAttributeToTree function [Bluetooth Devices], bltooth.sdpaddattributetotree, bth_funcs_5a46529e-8b1b-474a-a005-16f7a5562d91.xml, sdplib/SdpAddAttributeToTree
f1_keywords:
 - "sdplib/SdpAddAttributeToTree"
 - "SdpAddAttributeToTree"
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
- SdpAddAttributeToTree
targetos: Windows
req.typenames: 
---

# SdpAddAttributeToTree function


## -description


The Bluetooth 
   <b>SdpAddAttributeToTree</b> function is used to attach an SDP attribute node to the top level of an SDP
  record.


## -parameters




### -param Tree

<p>The top level of the SDP record to which the 
     <b>SdpAddAttributeToTree</b> function attaches the SDP attribute node.</p>


### -param AttribId [in]

The identifier of the attribute to attach.


### -param AttribValue

<p>Pointer to the SDP node to be added as an attribute.</p>


### -param tag [in]

Specifies a 4-byte 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/">pool tag</a> that uniquely identifies the driver that does the memory
     allocation. For more information about pool tags, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithtag">ExAllocatePoolWithTag</a>.


## -returns



Possible return values include:




## -remarks



Bluetooth profile drivers can obtain a pointer to this function through the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthsdpddi/ns-bthsdpddi-_bthddi_sdp_node_interface">BTHDDI_SDP_NODE_INTERFACE</a>.

For more information about the tree structure, see 
    <a href="https://docs.microsoft.com/previous-versions/ff536672(v=vs.85)">Converting SDP Records to a
    Tree Structure</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthsdpddi/ns-bthsdpddi-_bthddi_sdp_node_interface">BTHDDI_SDP_NODE_INTERFACE</a>
 

 

