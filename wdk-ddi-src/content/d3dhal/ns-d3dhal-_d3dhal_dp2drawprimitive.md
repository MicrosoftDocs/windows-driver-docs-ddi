---
UID: NS:d3dhal._D3DHAL_DP2DRAWPRIMITIVE
title: "_D3DHAL_DP2DRAWPRIMITIVE"
author: windows-driver-content
description: DirectX 8.0 and later versions only. D3DHAL_DRAWPRIMITIVE is parsed from the command buffer by the D3dDrawPrimitives2 callback when the D3DHAL_DP2COMMAND structure's bCommand member is set to D3DDP2OP_DRAWPRIMITIVE, and is used to render a primitive.
old-location: display\d3dhal_dp2drawprimitive.htm
old-project: display
ms.assetid: 1dd56465-e9e8-4a79-8533-a1777cf4d8a2
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*LPD3DHAL_DP2DRAWPRIMITIVE, D3DHAL_DP2DRAWPRIMITIVE, D3DHAL_DP2DRAWPRIMITIVE structure [Display Devices], LPD3DHAL_DP2DRAWPRIMITIVE, LPD3DHAL_DP2DRAWPRIMITIVE structure pointer [Display Devices], _D3DHAL_DP2DRAWPRIMITIVE, d3dhal/D3DHAL_DP2DRAWPRIMITIVE, d3dhal/LPD3DHAL_DP2DRAWPRIMITIVE, d3dstrct_2736a73d-52f8-4647-86c3-2c362dc3f669.xml, display.d3dhal_dp2drawprimitive"
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
-	D3DHAL_DP2DRAWPRIMITIVE
product: Windows
targetos: Windows
req.typenames: D3DHAL_DP2DRAWPRIMITIVE
---

# _D3DHAL_DP2DRAWPRIMITIVE structure


## -description



   DirectX 8.0 and later versions only.
   

D3DHAL_DRAWPRIMITIVE is parsed from the command buffer by the <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> callback when the <a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a> structure's <b>bCommand</b> member is set to D3DDP2OP_DRAWPRIMITIVE, and is used to render a primitive.


## -syntax


````
typedef struct _D3DHAL_DP2DRAWPRIMITIVE {
  D3DPRIMITIVETYPE primType;
  DWORD            VStart;
  DWORD            PrimitiveCount;
} D3DHAL_DP2DRAWPRIMITIVE, *LPD3DHAL_DP2DRAWPRIMITIVE;
````


## -struct-fields




### -field primType

Specifies the type of primitive to draw (one of D3DPT_POINTLIST, D3DPT_LINELIST, D3DPT_LINESTRIP, D3DPT_TRIANGLELIST, D3DPT_TRIANGLESTRIP or D3DPT_TRIANGLEFAN).


### -field VStart

Specifies the index (into each active vertex stream) of the vertex elements with which to start drawing. Actual vertex data should be read from the current vertex streams (those referenced by the current vertex shader) rather than from the vertex data pointer in <a href="..\d3dhal\ns-d3dhal-_d3dhal_drawprimitives2data.md">D3DHAL_DRAWPRIMITIVES2DATA</a>.


### -field PrimitiveCount

Specifies the number of triangles, lines or points to draw for the given primitive.


## -remarks



The vertex data can be untransformed (if the hardware supports hardware vertex processing) or transformed if the application supplied data in that form to the runtime.




## -see-also

<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>



D3DDP2OP_DRAWPRIMITIVE



<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a>



<a href="..\d3dhal\ns-d3dhal-_d3dhal_drawprimitives2data.md">D3DHAL_DRAWPRIMITIVES2DATA</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2DRAWPRIMITIVE structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

