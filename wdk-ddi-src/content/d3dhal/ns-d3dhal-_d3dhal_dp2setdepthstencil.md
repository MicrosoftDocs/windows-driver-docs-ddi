---
UID: NS:d3dhal._D3DHAL_DP2SETDEPTHSTENCIL
title: _D3DHAL_DP2SETDEPTHSTENCIL (d3dhal.h)
description: DirectX 9.0 and later versions only. The D3DHAL_DP2SETDEPTHSTENCIL structure is used to map a new depth buffer in the driver's current context when the D3DDP2OP_SETDEPTHSTENCIL operation code is received by D3dDrawPrimitives2.
old-location: display\d3dhal_dp2setdepthstencil.htm
tech.root: display
ms.assetid: fb57b1c0-6cb2-42e4-bf67-239ac6c0548c
ms.date: 05/10/2018
keywords: ["_D3DHAL_DP2SETDEPTHSTENCIL structure"]
ms.keywords: "*LPD3DHAL_DP2SETDEPTHSTENCIL, D3DHAL_DP2SETDEPTHSTENCIL, D3DHAL_DP2SETDEPTHSTENCIL structure [Display Devices], LPD3DHAL_DP2SETDEPTHSTENCIL, LPD3DHAL_DP2SETDEPTHSTENCIL structure pointer [Display Devices], _D3DHAL_DP2SETDEPTHSTENCIL, d3dhal/D3DHAL_DP2SETDEPTHSTENCIL, d3dhal/LPD3DHAL_DP2SETDEPTHSTENCIL, d3dstrct_6eda96cd-64bc-4ba1-acc3-0166ccfbd401.xml, display.d3dhal_dp2setdepthstencil"
f1_keywords:
 - "d3dhal/D3DHAL_DP2SETDEPTHSTENCIL"
 - "D3DHAL_DP2SETDEPTHSTENCIL"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dhal.h
api_name:
- D3DHAL_DP2SETDEPTHSTENCIL
targetos: Windows
req.typenames: D3DHAL_DP2SETDEPTHSTENCIL
---

# _D3DHAL_DP2SETDEPTHSTENCIL structure


## -description



   DirectX 9.0 and later versions only.
   

The D3DHAL_DP2SETDEPTHSTENCIL structure is used to map a new depth buffer in the driver's current context when the D3DDP2OP_SETDEPTHSTENCIL operation code is received by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a>.


## -struct-fields




### -field hZBuffer

Specifies a handle to the depth buffer.


## -remarks



The driver should store the depth buffer identified by <b>hZBuffer</b> in the driver's context when the runtime sends a D3DDP2OP_SETDEPTHSTENCIL operation code in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a> command stream.




## -see-also




D3DDP2OP_SETDEPTHSTENCIL



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a>
 

 

