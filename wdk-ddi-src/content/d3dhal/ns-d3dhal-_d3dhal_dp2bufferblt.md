---
UID: NS:d3dhal._D3DHAL_DP2BUFFERBLT
title: "_D3DHAL_DP2BUFFERBLT"
author: windows-driver-content
description: DirectX 8.0 and later versions only. D3DHAL_DP2BUFFERBLT is used for vertex or index buffer blts when D3dDrawPrimitives2 responds to the D3DDP2OP_BUFFERBLT command token.
old-location: display\d3dhal_dp2bufferblt.htm
old-project: display
ms.assetid: 3c2cb5c2-7461-40fc-a6c7-e4a107b24f74
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: "*LPD3DHAL_DP2BUFFERBLT, D3DHAL_DP2BUFFERBLT, D3DHAL_DP2BUFFERBLT structure [Display Devices], LPD3DHAL_DP2BUFFERBLT, LPD3DHAL_DP2BUFFERBLT structure pointer [Display Devices], _D3DHAL_DP2BUFFERBLT, d3dhal/D3DHAL_DP2BUFFERBLT, d3dhal/LPD3DHAL_DP2BUFFERBLT, d3dstrct_a8101d2a-8883-434e-8577-90e18bc3f2e0.xml, display.d3dhal_dp2bufferblt"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dhal.h
api_name:
-	D3DHAL_DP2BUFFERBLT
product:
- Windows
targetos: Windows
req.typenames: D3DHAL_DP2BUFFERBLT
---

# _D3DHAL_DP2BUFFERBLT structure


## -description



   DirectX 8.0 and later versions only.
   

D3DHAL_DP2BUFFERBLT is used for vertex or index buffer blts when <a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a> responds to the D3DDP2OP_BUFFERBLT command token.


## -struct-fields




### -field dwDDDestSurface

Specifies the handle to the destination vertex or index buffer.


### -field dwDDSrcSurface

Specifies the handle to the source vertex or index buffer.


### -field dwOffset

Specifies the offset, in bytes, of the destination buffer the copy should be directed into.


### -field rSrc

Specifies what range of the source buffer should be copied. This is a D3DRANGE structure, which is described in the Microsoft Windows SDK documentation, and contains a UINT offset in bytes and a UINT size in bytes.


### -field dwFlags

Unused.


## -remarks



The <a href="https://msdn.microsoft.com/8b012e65-b78b-41a4-ac05-d9be015b6ed8">CreateD3DBuffer</a> callback creates the small integer handles to the vertex or index buffers that can be used as source and destination buffers for buffer blts.

See Remarks for <a href="https://msdn.microsoft.com/library/windows/hardware/ff545869">D3DHAL_DP2TEXBLT</a>.




## -see-also




<a href="https://msdn.microsoft.com/8b012e65-b78b-41a4-ac05-d9be015b6ed8">CreateD3DBuffer</a>



D3DDP2OP_BUFFERBLT



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545454">D3DHAL_DP2COMMAND</a>



<a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a>
 

 

