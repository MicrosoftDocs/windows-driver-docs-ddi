---
UID: NS:d3dumddi._D3DDDICB_SETDISPLAYPRIVATEDRIVERFORMAT
title: "_D3DDDICB_SETDISPLAYPRIVATEDRIVERFORMAT"
author: windows-driver-content
description: The D3DDDICB_SETDISPLAYPRIVATEDRIVERFORMAT structure describes the private-format attribute to set for a video present source in a call to the pfnSetDisplayPrivateDriverFormatCb function.
old-location: display\d3dddicb_setdisplayprivatedriverformat.htm
old-project: display
ms.assetid: b10b020d-f18c-403d-b1ee-79552d18ad4e
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, 3, A, B, C, D, D3DDDICB_SETDISPLAYPRIVATEDRIVERFORMAT, D3DDDICB_SETDISPLAYPRIVATEDRIVERFORMAT structure [Display Devices], D3D_param_Structs_e953e85b-93cb-46c0-bab8-6d414568b153.xml, E, F, I, L, M, O, P, R, S, T, V, Y, _, _D3DDDICB_SETDISPLAYPRIVATEDRIVERFORMAT, d3dumddi/D3DDDICB_SETDISPLAYPRIVATEDRIVERFORMAT, display.d3dddicb_setdisplayprivatedriverformat"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dumddi.h
apiname:
-	D3DDDICB_SETDISPLAYPRIVATEDRIVERFORMAT
product: Windows
targetos: Windows
req.typenames: D3DDDICB_SETDISPLAYPRIVATEDRIVERFORMAT
---

# _D3DDDICB_SETDISPLAYPRIVATEDRIVERFORMAT structure


## -description


The D3DDDICB_SETDISPLAYPRIVATEDRIVERFORMAT structure describes the private-format attribute to set for a video present source in a call to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setdisplayprivatedriverformatcb.md">pfnSetDisplayPrivateDriverFormatCb</a> function.


## -syntax


````
typedef struct _D3DDDICB_SETDISPLAYPRIVATEDRIVERFORMAT {
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
  UINT                           PrivateDriverFormatAttribute;
} D3DDDICB_SETDISPLAYPRIVATEDRIVERFORMAT;
````


## -struct-fields




### -field VidPnSourceId

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology to set a private-format attribute on (that is, the identifier of the primary surface to set a private-format attribute on). 


### -field PrivateDriverFormatAttribute

[in] A UINT value that specifies the private-format attribute to set for the video present source that the <b>VidPnSourceId</b> member specifies.


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setdisplayprivatedriverformatcb.md">pfnSetDisplayPrivateDriverFormatCb</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDICB_SETDISPLAYPRIVATEDRIVERFORMAT structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

