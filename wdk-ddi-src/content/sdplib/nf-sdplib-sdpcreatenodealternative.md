---
UID: NF:sdplib.SdpCreateNodeAlternative
title: SdpCreateNodeAlternative function
author: windows-driver-content
description: The Bluetooth SdpCreateNodeAlternative function is used to create an empty alternative sequence SDP node.
old-location: bltooth\sdpcreatenodealternative.htm
old-project: bltooth
ms.assetid: 1e6b922d-01a2-4a67-91cb-74956d40d769
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: SdpCreateNodeAlternative, SdpCreateNodeAlternative function [Bluetooth Devices], bltooth.sdpcreatenodealternative, bth_funcs_e54ab424-3fbf-479a-9368-51d824c1fbec.xml, sdplib/SdpCreateNodeAlternative
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
-	SdpCreateNodeAlternative
product: Windows
targetos: Windows
req.typenames: SDCMD_DESCRIPTOR, *PSDCMD_DESCRIPTOR
req.product: Windows 10 or later.
---

# SdpCreateNodeAlternative function


## -description


The Bluetooth 
  <b>SdpCreateNodeAlternative</b> function is used to create an empty alternative sequence SDP node.


## -parameters




### -param tag [in]

A profile driver defined tag to associate with the node.


## -returns



If successful, this function returns a pointer to the newly allocated 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536848">SDP_NODE</a> structure. If not successful, this
     function returns 
     <b>NULL</b>.




## -remarks



After an alternative sequence node is created by calling the 
    <b>SdpCreateNodeAlternative</b> function, Bluetooth drivers can call the 
    <a href="https://msdn.microsoft.com/beec5516-6191-4b70-8c80-ddbaedbad5c0">
    SdpAppendNodeToContainerNode</a> function to insert other nodes into the alternative sequence node or
    to add the new alternative sequence node to another alternative sequence node.

An alternative sequence node can be added as a top-level attribute of an SDP record by calling the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536784">SdpAddAttributeToTree</a> function.

Bluetooth profile drivers can obtain a pointer to this function through the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536635">BTHDDI_SDP_NODE_INTERFACE</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536635">BTHDDI_SDP_NODE_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536848">SDP_NODE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536784">SdpAddAttributeToTree</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536786">SdpAppendNodeToContainerNode</a>
 

 

