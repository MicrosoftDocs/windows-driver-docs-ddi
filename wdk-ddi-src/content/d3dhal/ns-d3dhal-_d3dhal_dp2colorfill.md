---
UID: NS:d3dhal._D3DHAL_DP2COLORFILL
title: "_D3DHAL_DP2COLORFILL"
author: windows-driver-content
description: DirectX 9.0 and later versions only. D3DHAL_DP2COLORFILL is used for color-fill operations when D3dDrawPrimitives2 responds to the D3DDP2OP_COLORFILL command token.
old-location: display\d3dhal_dp2colorfill.htm
old-project: display
ms.assetid: 6cec8639-1d5e-4b24-8e02-a7ae62740fea
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , *, *LPD3DHAL_DP2COLORFILL, ,, 2, 3, A, C, D, D3DHAL_DP2COLORFILL, D3DHAL_DP2COLORFILL structure [Display Devices], F, H, I, L, LPD3DHAL_DP2COLORFILL, LPD3DHAL_DP2COLORFILL structure pointer [Display Devices], O, P, R, _, _D3DHAL_DP2COLORFILL, d3dhal/D3DHAL_DP2COLORFILL, d3dhal/LPD3DHAL_DP2COLORFILL, d3dstrct_41b1733a-0f94-4e04-9f7d-dac688c2bc56.xml, display.d3dhal_dp2colorfill"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dhal.h
req.include-header: D3dhal.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	d3dhal.h
apiname:
-	D3DHAL_DP2COLORFILL
product: Windows
targetos: Windows
req.typenames: D3DHAL_DP2COLORFILL
---

# _D3DHAL_DP2COLORFILL structure


## -description



   DirectX 9.0 and later versions only.
   

D3DHAL_DP2COLORFILL is used for color-fill operations when <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> responds to the D3DDP2OP_COLORFILL command token.


## -syntax


````
typedef struct _D3DHAL_DP2COLORFILL {
  DWORD    dwSurface;
  RECTL    rRect;
  D3DCOLOR Color;
} D3DHAL_DP2COLORFILL, *LPD3DHAL_DP2COLORFILL;
````


## -struct-fields




### -field dwSurface

Specifies the handle to the surface to be filled.


### -field rRect

Specifies a RECTL structure that specifies the upper left and lower right points of a rectangle on the surface to be filled. 


### -field Color

Specifies a D3DCOLOR for the color type. 


## -remarks



Because DirectX 9.0 and later drivers are required to support the D3DDP2OP_COLORFILL command token, they are not required to expose a capability bit that indicates such support. 

Display drivers must convert input color values for the ARGB and YUV classes of color formats. For color-fill operations, input color values are specified in the <b>Color</b> member. For more information, see <a href="https://msdn.microsoft.com/53ce6be1-14e1-4ee8-ba29-f198dcdacdaa">Handling Color Values for Pixel Formats</a>.

When the runtime calls a driver's <b>DdBlt</b> function to perform a color-fill operation, the runtime converts the D3DCOLOR value to an explicit pixel value if the runtime supports the format of that D3DCOLOR value. If the runtime does not support the format, the D3DCOLOR value is passed directly to the driver. 

For more information about D3DCOLOR, see the DirectX SDK documentation.




## -see-also

<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>



<a href="https://msdn.microsoft.com/28e0c827-33f1-4b83-9f20-bbb66bc0e14a">DdBlt</a>



D3DDP2OP_COLORFILL



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2COLORFILL structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

