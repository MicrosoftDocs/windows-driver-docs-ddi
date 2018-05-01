---
UID: NF:sdplib.SdpCreateNodeUInt16
title: SdpCreateNodeUInt16 function
author: windows-driver-content
description: The Bluetooth SdpCreateNodeUInt16 function is used to allocate and initialize an SDP_NODE structure to an unsigned 16-bit integer type.
old-location: bltooth\sdpcreatenodeuint16.htm
old-project: bltooth
ms.assetid: 8a864cfa-fa0b-4a8f-a229-2a28e1b33f4a
ms.author: windowsdriverdev
ms.date: 4/27/2018
ms.keywords: SdpCreateNodeUInt16, SdpCreateNodeUInt16 function [Bluetooth Devices], bltooth.sdpcreatenodeuint16, bth_funcs_9cc3e81b-f444-4a54-810e-5b779c597e82.xml, sdplib/SdpCreateNodeUInt16
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
-	SdpCreateNodeUInt16
product: Windows
targetos: Windows
req.typenames: 
---

# SdpCreateNodeUInt16 function


## -description


The Bluetooth 
  <b>SdpCreateNodeUInt16</b> function is used to allocate and initialize an 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff536848">SDP_NODE</a> structure to an unsigned 16-bit integer
  type.


## -parameters




### -param usVal [in]

The unsigned 16-bit integer value that is used to initialize the SDP_NODE structure.


### -param tag [in]

A profile driver defined tag to associate with the node.


## -returns



If successful, this function returns a pointer to the newly allocated SDP_NODE structure. If not
     successful, this function returns <b>NULL</b>.




## -remarks



After the 
    <b>SdpCreateNodeUInt16</b> function allocates an 
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
    <b>SdpCreateNodeUInt16</b> function is copied into the node, and the original data can be freed at any
    time.

Bluetooth profile drivers can obtain a pointer to this function through the 
    <a href="https://msdn.microsoft.com/c9aeaaed-f017-4b23-b867-d704c4f8afb6">
    BTHDDI_SDP_NODE_INTERFACE</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536635">BTHDDI_SDP_NODE_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536848">SDP_NODE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536849">SDP_NODE_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536850">SDP_NODE_HEADER</a>
 

 

