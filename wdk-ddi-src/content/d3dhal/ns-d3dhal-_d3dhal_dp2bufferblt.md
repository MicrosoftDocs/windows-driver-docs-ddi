---
UID: NS:d3dhal._D3DHAL_DP2BUFFERBLT
title: "_D3DHAL_DP2BUFFERBLT"
author: windows-driver-content
description: DirectX 8.0 and later versions only. D3DHAL_DP2BUFFERBLT is used for vertex or index buffer blts when D3dDrawPrimitives2 responds to the D3DDP2OP_BUFFERBLT command token.
old-location: display\d3dhal_dp2bufferblt.htm
old-project: display
ms.assetid: 3c2cb5c2-7461-40fc-a6c7-e4a107b24f74
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: "_D3DHAL_DP2BUFFERBLT, *LPD3DHAL_DP2BUFFERBLT, display.d3dhal_dp2bufferblt, D3DHAL_DP2BUFFERBLT, LPD3DHAL_DP2BUFFERBLT, d3dstrct_a8101d2a-8883-434e-8577-90e18bc3f2e0.xml, LPD3DHAL_DP2BUFFERBLT structure pointer [Display Devices], D3DHAL_DP2BUFFERBLT structure [Display Devices], d3dhal/LPD3DHAL_DP2BUFFERBLT, d3dhal/D3DHAL_DP2BUFFERBLT"
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
-	D3DHAL_DP2BUFFERBLT
product: Windows
targetos: Windows
req.typenames: D3DHAL_DP2BUFFERBLT
---

# _D3DHAL_DP2BUFFERBLT structure


## -description



   DirectX 8.0 and later versions only.
   

D3DHAL_DP2BUFFERBLT is used for vertex or index buffer blts when <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> responds to the D3DDP2OP_BUFFERBLT command token.


## -syntax


````
typedef struct _D3DHAL_DP2BUFFERBLT {
  DWORD    dwDDDestSurface;
  DWORD    dwDDSrcSurface;
  DWORD    dwOffset;
  D3DRANGE rSrc;
  DWORD    dwFlags;
} D3DHAL_DP2BUFFERBLT, *LPD3DHAL_DP2BUFFERBLT;
````


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

See Remarks for <a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2texblt.md">D3DHAL_DP2TEXBLT</a>.




## -see-also

<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a>



<a href="https://msdn.microsoft.com/8b012e65-b78b-41a4-ac05-d9be015b6ed8">CreateD3DBuffer</a>



<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>



D3DDP2OP_BUFFERBLT



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2BUFFERBLT structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

