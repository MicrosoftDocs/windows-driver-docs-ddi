---
UID: NS:d3dhal._D3DHAL_DP2SETPIXELSHADERCONST
title: "_D3DHAL_DP2SETPIXELSHADERCONST"
author: windows-driver-content
description: DirectX 8.0 and later versions only. The D3DHAL_DP2SETPIXELSHADERCONST structure is used to set one or more of the pixel shader constant registers when the D3DDP2OP_SETPIXELSHADERCONST opcode is received by D3dDrawPrimitives2.
old-location: display\d3dhal_dp2setpixelshaderconst.htm
old-project: display
ms.assetid: 8431fee3-d8c9-4c31-aa74-f5ce55f7fdcd
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dstrct_927a3360-7000-4cf0-99c7-f02407ae63eb.xml, d3dhal/D3DHAL_DP2SETPIXELSHADERCONST, _D3DHAL_DP2SETPIXELSHADERCONST, *LPD3DHAL_DP2SETPIXELSHADERCONSTI, D3DHAL_DP2SETPIXELSHADERCONSTI, *LPD3DHAL_DP2SETPIXELSHADERCONST, *LPD3DHAL_DP2SETPIXELSHADERCONSTB, D3DHAL_DP2SETPIXELSHADERCONST structure [Display Devices], D3DHAL_DP2SETPIXELSHADERCONSTB, display.d3dhal_dp2setpixelshaderconst, D3DHAL_DP2SETPIXELSHADERCONST
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
-	D3DHAL_DP2SETPIXELSHADERCONST
product: Windows
targetos: Windows
req.typenames: D3DHAL_DP2SETPIXELSHADERCONST
---

# _D3DHAL_DP2SETPIXELSHADERCONST structure


## -description



   DirectX 8.0 and later versions only.
   

The D3DHAL_DP2SETPIXELSHADERCONST structure is used to set one or more of the pixel shader constant registers when the D3DDP2OP_SETPIXELSHADERCONST opcode is received by <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>.


## -syntax


````
typedef struct _D3DHAL_DP2SETPIXELSHADERCONST {
  DWORD dwRegister;
  DWORD dwCount;
} D3DHAL_DP2SETPIXELSHADERCONST;
````


## -struct-fields




### -field dwRegister

Specifies the index of the first register to set.


### -field dwCount

Specifies the number of registers to set. Immediately following this data structure in the DP2 stream are <b>dwCount</b> vectors of four single precision floating-point numbers. This is the data to copy to the target registers.


## -remarks


The runtime passes the first register to set and the number of registers to set. The actual data to copy to those registers consists of vectors of four, single precision floating-point numbers. These vectors (the same number as there are registers to set) follow this token and its associated data structure in the DP2 stream.

The runtime validates that the specified register range lies within the legal range for the version of the current pixel shader.



## -see-also

<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2createpixelshader.md">D3DHAL_DP2CREATEPIXELSHADER</a>

D3DDP2OP_SETPIXELSHADERCONST

<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>

<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2pixelshader.md">D3DHAL_DP2PIXELSHADER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2SETPIXELSHADERCONST structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

