---
UID: NF:sdplib.SdpCreateNodeUInt8
title: SdpCreateNodeUInt8 function
author: windows-driver-content
description: The Bluetooth SdpCreateNodeUInt8 function is used to allocate and initialize an SDP_NODE structure to an unsigned 8-bit integer type.
old-location: bltooth\sdpcreatenodeuint8.htm
old-project: bltooth
ms.assetid: b5ac8079-032f-4d25-ba12-8fdc0622b8b5
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: bltooth.sdpcreatenodeuint8, sdplib/SdpCreateNodeUInt8, SdpCreateNodeUInt8 function [Bluetooth Devices], SdpCreateNodeUInt8, bth_funcs_836c7c8c-76a0-4bce-8b30-79550dd5f173.xml
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
-	SdpCreateNodeUInt8
product: Windows
targetos: Windows
req.typenames: SDCMD_DESCRIPTOR, *PSDCMD_DESCRIPTOR
req.product: Windows 10 or later.
---

# SdpCreateNodeUInt8 function


## -description


The Bluetooth 
  <b>SdpCreateNodeUInt8</b> function is used to allocate and initialize an 
  <a href="..\sdpnode\ns-sdpnode-_sdp_node.md">SDP_NODE</a> structure to an unsigned 8-bit integer
  type.


## -syntax


````
PSDP_NODE SdpCreateNodeUInt8(
  _In_ UCHAR ucVal,
  _In_ ULONG tag
);
````


## -parameters




#### - ucVal [in]

The unsigned 8-bit integer value that is used to initialize the SDP_NODE structure.


#### - tag [in]

A profile driver defined tag to associate with the node.


## -returns


If successful, this function returns a pointer to the newly allocated SDP_NODE structure. If not
     successful, this function returns <b>NULL</b>.



## -remarks


After the 
    <b>SdpCreateNodeUInt8</b> function allocates an 
    <a href="..\sdpnode\ns-sdpnode-_sdp_node.md">SDP_NODE</a> structure, it initializes the structure in
    the following ways.

It ensures that the SDP_NODE structure's data type and data size fields are set appropriately.

It ensures that the pointer members of the associated 
      <a href="..\sdpnode\ns-sdpnode-_sdp_node_header.md">SDP_NODE_HEADER</a> structure are initialized
      to point to the node itself. This creates a valid list with only one element.

It ensures that the 
      <i>value</i> parameter passed to the function is copied to the appropriate element of the 
      <a href="..\sdpnode\ns-sdpnode-_sdp_node_data.md">SDP_NODE_DATA</a> union that is associated with
      the SDP_NODE structure.

The data associated with the 
    <b>SdpCreateNodeUInt8</b> function is copied into the node, and the original data can be freed at any
    time.

Bluetooth profile drivers can obtain a pointer to this function through the 
    <mshelp:link keywords="bltooth.bthddi_sdp_node_interface" tabindex="0"><b>
    BTHDDI_SDP_NODE_INTERFACE</b></mshelp:link> structure.



## -see-also

<a href="..\sdpnode\ns-sdpnode-_sdp_node_data.md">SDP_NODE_DATA</a>

<a href="..\sdpnode\ns-sdpnode-_sdp_node_header.md">SDP_NODE_HEADER</a>

<a href="..\bthsdpddi\ns-bthsdpddi-_bthddi_sdp_node_interface.md">BTHDDI_SDP_NODE_INTERFACE</a>

<a href="..\sdpnode\ns-sdpnode-_sdp_node.md">SDP_NODE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20SdpCreateNodeUInt8 function%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

