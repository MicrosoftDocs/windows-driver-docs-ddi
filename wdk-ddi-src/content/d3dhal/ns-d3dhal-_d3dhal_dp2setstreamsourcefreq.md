---
UID: NS:d3dhal._D3DHAL_DP2SETSTREAMSOURCEFREQ
title: "_D3DHAL_DP2SETSTREAMSOURCEFREQ"
author: windows-driver-content
description: DirectX 9.0 and later versions only. The D3DHAL_DP2SETSTREAMSOURCEFREQ structure is used to set the frequency divisor of a stream source that is bound to a vertex buffer for D3dDrawPrimitives2.
old-location: display\d3dhal_dp2setstreamsourcefreq.htm
old-project: display
ms.assetid: c7f9cfc5-5698-404b-9b67-51ad8e351519
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPD3DHAL_DP2SETSTREAMSOURCEFREQ, D3DHAL_DP2SETSTREAMSOURCEFREQ, D3DHAL_DP2SETSTREAMSOURCEFREQ structure [Display Devices], LPD3DHAL_DP2SETSTREAMSOURCEFREQ, LPD3DHAL_DP2SETSTREAMSOURCEFREQ structure pointer [Display Devices], _D3DHAL_DP2SETSTREAMSOURCEFREQ, d3dhal/D3DHAL_DP2SETSTREAMSOURCEFREQ, d3dhal/LPD3DHAL_DP2SETSTREAMSOURCEFREQ, d3dstrct_979aa6d9-cf68-4e59-9ee5-b422749fa49d.xml, display.d3dhal_dp2setstreamsourcefreq"
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
-	D3DHAL_DP2SETSTREAMSOURCEFREQ
product: Windows
targetos: Windows
req.typenames: D3DHAL_DP2SETSTREAMSOURCEFREQ
---

# _D3DHAL_DP2SETSTREAMSOURCEFREQ structure


## -description



   DirectX 9.0 and later versions only.
   

The D3DHAL_DP2SETSTREAMSOURCEFREQ structure is used to set the frequency divisor of a stream source that is bound to a vertex buffer for <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>.


## -syntax


````
typedef struct _D3DHAL_DP2SETSTREAMSOURCEFREQ {
  DWORD dwStream;
  DWORD dwDivider;
} D3DHAL_DP2SETSTREAMSOURCEFREQ, *LPD3DHAL_DP2SETSTREAMSOURCEFREQ;
````


## -struct-fields




### -field dwStream

Specifies the data stream, in the range from 0 to the maximum number of streams -1, whose frequency is being modified.


### -field dwDivider

Specifies the frequency divisor, which is the number of vertices after which data from the given stream is fetched into the vertex shader. This number can be greater than zero and at most 2^16-1 (WORD).


## -remarks



A driver is requested to set a stream's frequency divisor through the D3DDP2OP_SETSTREAMSOURCEFREQ operation code. 

A driver for a device that supports vertex shader version 3.0 and later can implement stream frequency division. For more information, see <a href="https://msdn.microsoft.com/81bbced4-7331-4e54-9617-1ef29b02f162">Modifying Vertex Stream Frequency</a>.




## -see-also

D3DDP2OP_SETSTREAMSOURCEFREQ



<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>



 

 


