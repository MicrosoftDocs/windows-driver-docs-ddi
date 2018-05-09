---
UID: NS:d3dumddi._D3DDDICB_SETDISPLAYPRIVATEDRIVERFORMAT
title: "_D3DDDICB_SETDISPLAYPRIVATEDRIVERFORMAT"
author: windows-driver-content
description: The D3DDDICB_SETDISPLAYPRIVATEDRIVERFORMAT structure describes the private-format attribute to set for a video present source in a call to the pfnSetDisplayPrivateDriverFormatCb function.
old-location: display\d3dddicb_setdisplayprivatedriverformat.htm
old-project: display
ms.assetid: b10b020d-f18c-403d-b1ee-79552d18ad4e
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3DDDICB_SETDISPLAYPRIVATEDRIVERFORMAT, D3DDDICB_SETDISPLAYPRIVATEDRIVERFORMAT structure [Display Devices], D3D_param_Structs_e953e85b-93cb-46c0-bab8-6d414568b153.xml, _D3DDDICB_SETDISPLAYPRIVATEDRIVERFORMAT, d3dumddi/D3DDDICB_SETDISPLAYPRIVATEDRIVERFORMAT, display.d3dddicb_setdisplayprivatedriverformat
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dumddi.h
api_name:
-	D3DDDICB_SETDISPLAYPRIVATEDRIVERFORMAT
product:
- Windows
targetos: Windows
req.typenames: D3DDDICB_SETDISPLAYPRIVATEDRIVERFORMAT
---

# _D3DDDICB_SETDISPLAYPRIVATEDRIVERFORMAT structure


## -description


The D3DDDICB_SETDISPLAYPRIVATEDRIVERFORMAT structure describes the private-format attribute to set for a video present source in a call to the <a href="https://msdn.microsoft.com/499e6de7-67cc-4834-bcec-4f3907b180f7">pfnSetDisplayPrivateDriverFormatCb</a> function.


## -struct-fields




### -field VidPnSourceId

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology to set a private-format attribute on (that is, the identifier of the primary surface to set a private-format attribute on). 


### -field PrivateDriverFormatAttribute

[in] A UINT value that specifies the private-format attribute to set for the video present source that the <b>VidPnSourceId</b> member specifies.


## -see-also




<a href="https://msdn.microsoft.com/499e6de7-67cc-4834-bcec-4f3907b180f7">pfnSetDisplayPrivateDriverFormatCb</a>
 

 

