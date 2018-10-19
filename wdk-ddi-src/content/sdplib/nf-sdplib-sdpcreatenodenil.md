---
UID: NF:sdplib.SdpCreateNodeNil
title: SdpCreateNodeNil function
author: windows-driver-content
description: The Bluetooth SdpCreateNodeNil function is used to allocate and initialize an SDP_NODE structure to an empty node type.
old-location: bltooth\sdpcreatenodenil.htm
tech.root: bltooth
ms.assetid: 53312cb8-a974-4394-969b-2a39def64109
ms.date: 04/27/2018
ms.keywords: SdpCreateNodeNil, SdpCreateNodeNil function [Bluetooth Devices], bltooth.sdpcreatenodenil, bth_funcs_5f7d1244-67e0-436e-8658-8adcc2aa3a65.xml, sdplib/SdpCreateNodeNil
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
-	SdpCreateNodeNil
product:
- Windows
targetos: Windows
req.typenames: 
---

# SdpCreateNodeNil function


## -description


The Bluetooth 
  <b>SdpCreateNodeNil</b> function is used to allocate and initialize an 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff536848">SDP_NODE</a> structure to an empty node type.


## -parameters




### -param tag [in]

A profile driver defined tag to associate with the node.


## -returns



If successful, this function returns a pointer to the newly allocated SDP_NODE structure. If not
     successful, this function returns <b>NULL</b>.




## -remarks



Bluetooth profile drivers can obtain a pointer to this function through the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536635">BTHDDI_SDP_NODE_INTERFACE</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536635">BTHDDI_SDP_NODE_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536848">SDP_NODE</a>
 

 

