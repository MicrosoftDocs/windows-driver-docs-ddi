---
UID: NF:sdplib.SdpCreateNodeBoolean
title: SdpCreateNodeBoolean function (sdplib.h)
description: The Bluetooth SdpCreateNodeBoolean function is used to allocate and initialize an SDP_NODE structure to a Boolean type.
old-location: bltooth\sdpcreatenodeboolean.htm
tech.root: bltooth
ms.assetid: d299074f-18db-4eff-b177-4d2d3535e299
ms.date: 04/27/2018
ms.keywords: SdpCreateNodeBoolean, SdpCreateNodeBoolean function [Bluetooth Devices], bltooth.sdpcreatenodeboolean, bth_funcs_06168a9c-1cdc-4c2a-b90d-356c03867d4f.xml, sdplib/SdpCreateNodeBoolean
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
- SdpCreateNodeBoolean
product:
- Windows
targetos: Windows
req.typenames: 
---

# SdpCreateNodeBoolean function


## -description


The Bluetooth 
  <b>SdpCreateNodeBoolean</b> function is used to allocate and initialize an 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff536848">SDP_NODE</a> structure to a Boolean type.


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
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536635">BTHDDI_SDP_NODE_INTERFACE</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536635">BTHDDI_SDP_NODE_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536848">SDP_NODE</a>
 

 

