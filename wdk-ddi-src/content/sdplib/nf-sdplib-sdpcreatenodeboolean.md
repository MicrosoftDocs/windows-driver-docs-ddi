---
UID: NF:sdplib.SdpCreateNodeBoolean
title: SdpCreateNodeBoolean function (sdplib.h)
description: The Bluetooth SdpCreateNodeBoolean function is used to allocate and initialize an SDP_NODE structure to a Boolean type.
old-location: bltooth\sdpcreatenodeboolean.htm
tech.root: bltooth
ms.date: 04/27/2018
keywords: ["SdpCreateNodeBoolean function"]
ms.keywords: SdpCreateNodeBoolean, SdpCreateNodeBoolean function [Bluetooth Devices], bltooth.sdpcreatenodeboolean, bth_funcs_06168a9c-1cdc-4c2a-b90d-356c03867d4f.xml, sdplib/SdpCreateNodeBoolean
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
targetos: Windows
req.typenames: 
f1_keywords:
 - SdpCreateNodeBoolean
 - sdplib/SdpCreateNodeBoolean
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - sdplib.h
api_name:
 - SdpCreateNodeBoolean
---

# SdpCreateNodeBoolean function


## -description

The Bluetooth 
  <b>SdpCreateNodeBoolean</b> function is used to allocate and initialize an 
  <a href="/windows-hardware/drivers/ddi/sdpnode/ns-sdpnode-_sdp_node">SDP_NODE</a> structure to a Boolean type.

## -parameters

### -param bVal [in]


The Boolean value that is used to initialize the SDP_NODE structure.

### -param tag [in]


A profile driver defined tag to associate with the node.

## -returns

If successful, this function returns a pointer to the newly allocated SDP_NODE structure. If not
     successful, this function returns <b>NULL</b>.

## -remarks

The data associated with the 
    <b>SdpCreateNodeBoolean</b> function is copied into the node, and the original data can be freed at any
    time.

Bluetooth profile drivers can obtain a pointer to this function through the 
    <a href="/windows-hardware/drivers/ddi/bthsdpddi/ns-bthsdpddi-_bthddi_sdp_node_interface">BTHDDI_SDP_NODE_INTERFACE</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/bthsdpddi/ns-bthsdpddi-_bthddi_sdp_node_interface">BTHDDI_SDP_NODE_INTERFACE</a>



<a href="/windows-hardware/drivers/ddi/sdpnode/ns-sdpnode-_sdp_node">SDP_NODE</a>
