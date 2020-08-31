---
UID: NS:d3dhal._D3DHAL_DP2SETSTREAMSOURCE2
title: _D3DHAL_DP2SETSTREAMSOURCE2 (d3dhal.h)
description: DirectX 9.0 and later versions only. The D3DHAL_DP2SETSTREAMSOURCE2 structure is used to bind a portion of a vertex stream source to a vertex buffer for D3dDrawPrimitives2.
old-location: display\d3dhal_dp2setstreamsource2.htm
tech.root: display
ms.assetid: a8e1ea01-2050-413a-991f-55c29977b6dd
ms.date: 05/10/2018
keywords: ["D3DHAL_DP2SETSTREAMSOURCE2 structure"]
ms.keywords: "*LPD3DHAL_DP2SETSTREAMSOURCE2, D3DHAL_DP2SETSTREAMSOURCE2, D3DHAL_DP2SETSTREAMSOURCE2 structure [Display Devices], LPD3DHAL_DP2SETSTREAMSOURCE2, LPD3DHAL_DP2SETSTREAMSOURCE2 structure pointer [Display Devices], _D3DHAL_DP2SETSTREAMSOURCE2, d3dhal/D3DHAL_DP2SETSTREAMSOURCE2, d3dhal/LPD3DHAL_DP2SETSTREAMSOURCE2, d3dstrct_81c5d4ff-bd3e-4f52-a062-c30755da9416.xml, display.d3dhal_dp2setstreamsource2"
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
targetos: Windows
req.typenames: D3DHAL_DP2SETSTREAMSOURCE2
f1_keywords:
 - _D3DHAL_DP2SETSTREAMSOURCE2
 - d3dhal/_D3DHAL_DP2SETSTREAMSOURCE2
 - D3DHAL_DP2SETSTREAMSOURCE2
 - d3dhal/D3DHAL_DP2SETSTREAMSOURCE2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dhal.h
api_name:
 - D3DHAL_DP2SETSTREAMSOURCE2
---

# _D3DHAL_DP2SETSTREAMSOURCE2 structure


## -description

   DirectX 9.0 and later versions only.
   

The D3DHAL_DP2SETSTREAMSOURCE2 structure is used to bind a portion of a vertex stream source to a vertex buffer for <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a>.

## -struct-fields

### -field dwStream

Specifies the stream being bound. It has a value between zero and the maximum number of streams specified by the driver.

### -field dwVBHandle

Specifies the vertex buffer handle. It is legal for the vertex buffer handle to be zero, in which case the stream is no longer bound to a vertex buffer.

### -field dwOffset

Specifies the offset of the first vertex size in bytes.

### -field dwStride

Specifies the vertex size in bytes.

## -see-also

D3DDP2OP_SETSTREAMSOURCE2



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a>

