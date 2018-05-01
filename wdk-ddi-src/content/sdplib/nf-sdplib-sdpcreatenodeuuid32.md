---
UID: NF:sdplib.SdpCreateNodeUUID32
title: SdpCreateNodeUUID32 function
author: windows-driver-content
description: The Bluetooth SdpCreateNodeUUID32 function is used to allocate and initialize an SDP_NODE structure to a 32-bit UUID type.
old-location: bltooth\sdpcreatenodeuuid32.htm
old-project: bltooth
ms.assetid: 2e67e0eb-9daa-4b38-947a-46893f9d6eab
ms.author: windowsdriverdev
ms.date: 4/27/2018
ms.keywords: SdpCreateNodeUUID32, SdpCreateNodeUUID32 function [Bluetooth Devices], bltooth.sdpcreatenodeuuid32, bth_funcs_0ec74adf-03d4-4380-9bcd-a365dee9c7a3.xml, sdplib/SdpCreateNodeUUID32
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
req.lib: 
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
-	SdpCreateNodeUUID32
product: Windows
targetos: Windows
req.typenames: 
---

# SdpCreateNodeUUID32 function


## -description


The Bluetooth 
  <b>SdpCreateNodeUUID32</b> function is used to allocate and initialize an 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff536848">SDP_NODE</a> structure to a 32-bit UUID type.


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
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536848">SDP_NODE</a> structure, it initializes the structure in
    the following ways.

It ensures that the SDP_NODE structure's data type and data size fields are set appropriately.

It ensures that the pointer members of the associated 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff536850">SDP_NODE_HEADER</a> structure are initialized
      to point to the node itself. This creates a valid list with only one element.

It ensures that the 
      <i>value</i> parameter passed to the function is copied to the appropriate element of the 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff536849">SDP_NODE_DATA</a> union that is associated with
      the SDP_NODE structure.

The data associated with the 
    <b>SdpCreateNodeUUID32</b> function is copied into the node, and the original data can be freed at any
    time.

Bluetooth profile drivers can obtain a pointer to this function through the 
    <a href="https://msdn.microsoft.com/c9aeaaed-f017-4b23-b867-d704c4f8afb6">
    BTHDDI_SDP_NODE_INTERFACE</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536635">BTHDDI_SDP_NODE_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536848">SDP_NODE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536849">SDP_NODE_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536850">SDP_NODE_HEADER</a>
 

 

