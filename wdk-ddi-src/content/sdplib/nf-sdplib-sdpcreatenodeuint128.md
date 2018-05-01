---
UID: NF:sdplib.SdpCreateNodeUInt128
title: SdpCreateNodeUInt128 function
author: windows-driver-content
description: The Bluetooth SdpCreateNodeUInt128 function is used to allocate and initialize an SDP_NODE structure to an unsigned 128-bit integer type.
old-location: bltooth\sdpcreatenodeuint128.htm
old-project: bltooth
ms.assetid: 92ddc186-7b4c-410e-a82b-7309559364c1
ms.author: windowsdriverdev
ms.date: 4/27/2018
ms.keywords: SdpCreateNodeUInt128, SdpCreateNodeUInt128 function [Bluetooth Devices], bltooth.sdpcreatenodeuint128, bth_funcs_c03666c1-b1d7-4361-9133-f0525300e546.xml, sdplib/SdpCreateNodeUInt128
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
-	SdpCreateNodeUInt128
product: Windows
targetos: Windows
req.typenames: 
---

# SdpCreateNodeUInt128 function


## -description


The Bluetooth 
  <b>SdpCreateNodeUInt128</b> function is used to allocate and initialize an 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff536848">SDP_NODE</a> structure to an unsigned 128-bit integer
  type.


## -parameters




### -param puli16Val [in]

The unsigned 128-bit integer value to initialize the SDP_NODE structure.


### -param tag [in]

A profile driver defined tag to associate with the node.


## -returns



If successful, this function returns a pointer to the newly allocated SDP_NODE structure. If not
     successful, this function returns <b>NULL</b>.




## -remarks



After the 
    <b>SdpCreateNodeUInt128</b> function allocates an 
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
    <b>SdpCreateNodeUInt128</b> function is copied into the node, and the original data can be freed at any
    time.

Bluetooth profile drivers can obtain a pointer to this function through the 
    <a href="https://msdn.microsoft.com/c9aeaaed-f017-4b23-b867-d704c4f8afb6">
    BTHDDI_SDP_NODE_INTERFACE</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536635">BTHDDI_SDP_NODE_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536848">SDP_NODE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536849">SDP_NODE_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536850">SDP_NODE_HEADER</a>
 

 

