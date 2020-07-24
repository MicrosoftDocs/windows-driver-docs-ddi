---
UID: NF:sdplib.SdpFindAttributeInTree
title: SdpFindAttributeInTree function (sdplib.h)
description: The Bluetooth SdpFindAttributeInTree function is used to locate the specified attribute node in the tree-based representation of an SDP record.
old-location: bltooth\sdpfindattributeintree.htm
tech.root: bltooth
ms.assetid: 26c71c08-3b9a-474f-a232-d7f675582d27
ms.date: 04/27/2018
keywords: ["SdpFindAttributeInTree function"]
ms.keywords: SdpFindAttributeInTree, SdpFindAttributeInTree function [Bluetooth Devices], bltooth.sdpfindattributeintree, bth_funcs_8daefa96-6201-462a-9c91-485c5f9eaa98.xml, sdplib/SdpFindAttributeInTree
f1_keywords:
 - "sdplib/SdpFindAttributeInTree"
 - "SdpFindAttributeInTree"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- sdplib.h
api_name:
- SdpFindAttributeInTree
targetos: Windows
req.typenames: 
---

# SdpFindAttributeInTree function


## -description


The Bluetooth 
  <b>SdpFindAttributeInTree</b> function is used to locate the specified attribute node in the tree-based
  representation of an SDP record.


## -parameters




### -param Tree [in]

The root node of the tree-based representation of the SDP record to search.


### -param AttribId [in]

The identifier of the attribute node to locate.


### -param Attribute

<p>A pointer to a variable that receives the address of the located attribute node.</p>




## -returns



Possible return values include:




## -remarks



The 
    <b>SdpFindAttributeInTree</b> function returns the address of the requested node in the tree; it does not
    perform a copy. This node pointer is valid until the SDP tree that it references is freed.

Bluetooth profile drivers can obtain a pointer to this function through the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthsdpddi/ns-bthsdpddi-_bthddi_sdp_parse_interface">
    BTHDDI_SDP_PARSE_INTERFACE</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthsdpddi/ns-bthsdpddi-_bthddi_sdp_parse_interface">BTHDDI_SDP_PARSE_INTERFACE</a>
 

 

