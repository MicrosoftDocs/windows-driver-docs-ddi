---
UID: NS:d3dhal._D3DHAL_DP2SETSTREAMSOURCEUM
title: "_D3DHAL_DP2SETSTREAMSOURCEUM"
author: windows-driver-content
description: DirectX 8.0 and later versions only. The D3DHAL_DP2SETSTREAMSOURCEUM structure is used to bind a vertex stream source to a user memory buffer for D3dDrawPrimitives2.
old-location: display\d3dhal_dp2setstreamsourceum.htm
old-project: display
ms.assetid: 42a8c14d-3b73-4d9a-a902-d4bf2b46ddf8
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: "*LPD3DHAL_DP2SETSTREAMSOURCEUM, D3DHAL_DP2SETSTREAMSOURCEUM structure [Display Devices], d3dstrct_58dd4856-1fc8-4772-96db-77ff9b81afbf.xml, d3dhal/D3DHAL_DP2SETSTREAMSOURCEUM, D3DHAL_DP2SETSTREAMSOURCEUM, LPD3DHAL_DP2SETSTREAMSOURCEUM structure pointer [Display Devices], display.d3dhal_dp2setstreamsourceum, d3dhal/LPD3DHAL_DP2SETSTREAMSOURCEUM, _D3DHAL_DP2SETSTREAMSOURCEUM, LPD3DHAL_DP2SETSTREAMSOURCEUM"
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
-	D3DHAL_DP2SETSTREAMSOURCEUM
product: Windows
targetos: Windows
req.typenames: D3DHAL_DP2SETSTREAMSOURCEUM
---

# _D3DHAL_DP2SETSTREAMSOURCEUM structure


## -description



   DirectX 8.0 and later versions only.
   

The D3DHAL_DP2SETSTREAMSOURCEUM structure is used to bind a vertex stream source to a user memory buffer for <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>.


## -syntax


````
typedef struct _D3DHAL_DP2SETSTREAMSOURCEUM {
  DWORD dwStream;
  DWORD dwStride;
} D3DHAL_DP2SETSTREAMSOURCEUM, *LPD3DHAL_DP2SETSTREAMSOURCEUM;
````


## -struct-fields




### -field dwStream

Specifies the stream being bound. For DirectX 8.0 it is always zero.


### -field dwStride

Specifies the vertex size in bytes.


## -remarks


In addition to binding a stream to a vertex buffer, it is possible for the vertex data of stream zero to be supplied in a user memory (UM) buffer. In this case, another DP2 token is used to notify the driver of stream binding. That token is D3DDP2OP_SETSTREAMSOURCEUM.

DirectX 8.0 does not support multiple vertex streams with user supplied buffers rather than vertex buffers. Additionally, it is not possible to mix user memory buffers with vertex buffers. When a user memory buffer is supplied, it is guaranteed to be stream zero and to be the only stream that should be accessed by subsequent drawing primitives. It is possible that other streams have non-NULL vertex buffers bound to them at the time when a user memory buffer is bound to stream. However, those other streams must be ignored by the driver and hardware.

The actual user memory pointer to the vertex data should be extracted from the <a href="..\d3dhal\ns-d3dhal-_d3dhal_drawprimitives2data.md">D3DHAL_DRAWPRIMITIVES2DATA</a> passed when actually drawing primitives.



## -see-also

<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2setstreamsource.md">D3DHAL_DP2SETSTREAMSOURCE</a>

<a href="..\d3dhal\ns-d3dhal-_d3dhal_drawprimitives2data.md">D3DHAL_DRAWPRIMITIVES2DATA</a>

D3DDP2OP_SETSTREAMSOURCEUM

<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2SETSTREAMSOURCEUM structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

