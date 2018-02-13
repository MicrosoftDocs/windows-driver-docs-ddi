---
UID: NF:sdplib.SdpCreateNodeUUID32
title: SdpCreateNodeUUID32 function
author: windows-driver-content
description: The Bluetooth SdpCreateNodeUUID32 function is used to allocate and initialize an SDP_NODE structure to a 32-bit UUID type.
old-location: bltooth\sdpcreatenodeuuid32.htm
old-project: bltooth
ms.assetid: 2e67e0eb-9daa-4b38-947a-46893f9d6eab
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: bltooth.sdpcreatenodeuuid32, SdpCreateNodeUUID32 function [Bluetooth Devices], sdplib/SdpCreateNodeUUID32, bth_funcs_0ec74adf-03d4-4380-9bcd-a365dee9c7a3.xml, SdpCreateNodeUUID32
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
-	SdpCreateNodeUUID32
product: Windows
targetos: Windows
req.typenames: SD_TRANSFER_TYPE
req.product: Windows 10 or later.
---

# SdpCreateNodeUUID32 function


## -description


The Bluetooth 
  <b>SdpCreateNodeUUID32</b> function is used to allocate and initialize an 
  <a href="..\sdpnode\ns-sdpnode-_sdp_node.md">SDP_NODE</a> structure to a 32-bit UUID type.


## -syntax


````
PSDP_NODE SdpCreateNodeUUID32(
  _In_ ULONG ulVal,
  _In_ ULONG tag
);
````


## -parameters




### -param uuidVal4

TBD


### -param tag [in]

A profile driver defined tag to associate with the node.


#### - ulVal [in]

The 32-bit UUID value to initialize the SDP_NODE structure.


## -returns



If successful, this function returns a pointer to the newly allocated SDP_NODE structure. If not
     successful, this function returns <b>NULL</b>.




## -remarks



After the 
    <b>SdpCreateNodeUUID32</b> function allocates an 
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
    <b>SdpCreateNodeUUID32</b> function is copied into the node, and the original data can be freed at any
    time.

Bluetooth profile drivers can obtain a pointer to this function through the 
    <a href="..\bthsdpddi\ns-bthsdpddi-_bthddi_sdp_node_interface.md">
    BTHDDI_SDP_NODE_INTERFACE</a> structure.




## -see-also

<a href="..\sdpnode\ns-sdpnode-_sdp_node_header.md">SDP_NODE_HEADER</a>



<a href="..\sdpnode\ns-sdpnode-_sdp_node.md">SDP_NODE</a>



<a href="..\bthsdpddi\ns-bthsdpddi-_bthddi_sdp_node_interface.md">BTHDDI_SDP_NODE_INTERFACE</a>



<a href="..\sdpnode\ns-sdpnode-_sdp_node_data.md">SDP_NODE_DATA</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20SdpCreateNodeUUID32 function%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

