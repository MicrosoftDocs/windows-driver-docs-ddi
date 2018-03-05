---
UID: NF:sdplib.SdpCreateNodeString
title: SdpCreateNodeString function
author: windows-driver-content
description: The Bluetooth SdpCreateNodeString function is used to allocate and initialize an SDP_NODE structure to a string type.
old-location: bltooth\sdpcreatenodestring.htm
old-project: bltooth
ms.assetid: 27611211-a782-4c62-8848-d9ca6e49b5f4
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: SdpCreateNodeString, SdpCreateNodeString function [Bluetooth Devices], bltooth.sdpcreatenodestring, bth_funcs_509682f2-c3c7-4e27-aa1f-2a6bfaf351c1.xml, sdplib/SdpCreateNodeString
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
-	SdpCreateNodeString
product: Windows
targetos: Windows
req.typenames: SDCMD_DESCRIPTOR, *PSDCMD_DESCRIPTOR
req.product: Windows 10 or later.
---

# SdpCreateNodeString function


## -description


The Bluetooth 
  <b>SdpCreateNodeString</b> function is used to allocate and initialize an 
  <a href="..\sdpnode\ns-sdpnode-_sdp_node.md">SDP_NODE</a> structure to a string type.


## -syntax


````
PSDP_NODE SdpCreateNodeString(
  _In_ PCHAR            string,
       __in_bound ULONG StringLength,
  _In_ ULONG            tag
);
````


## -parameters




### -param string [in]

A pointer to the string value to initialize the SDP_NODE structure.


### -param stringLength

TBD


### -param tag [in]

A profile driver defined tag to associate with the node.


#### - StringLength

An unsigned long integer value that holds the length of the string.


## -returns



If successful, this function returns a pointer to the newly allocated SDP_NODE structure. If not
     successful, this function returns <b>NULL</b>.




## -remarks



After the 
    <b>SdpCreateNodeString</b> function allocates an 
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
    <b>SdpCreateNodeString</b> function is copied into the node, and the original data can be freed at any
    time.

Bluetooth profile drivers can obtain a pointer to this function through the 
    <a href="..\bthsdpddi\ns-bthsdpddi-_bthddi_sdp_node_interface.md">BTHDDI_SDP_NODE_INTERFACE</a>.




## -see-also

<a href="..\sdpnode\ns-sdpnode-_sdp_node_data.md">SDP_NODE_DATA</a>



<a href="..\sdpnode\ns-sdpnode-_sdp_node.md">SDP_NODE</a>



<a href="..\bthsdpddi\ns-bthsdpddi-_bthddi_sdp_node_interface.md">BTHDDI_SDP_NODE_INTERFACE</a>



<a href="..\sdpnode\ns-sdpnode-_sdp_node_header.md">SDP_NODE_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20SdpCreateNodeString function%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

