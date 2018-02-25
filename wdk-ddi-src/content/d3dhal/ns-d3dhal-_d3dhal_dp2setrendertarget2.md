---
UID: NS:d3dhal._D3DHAL_DP2SETRENDERTARGET2
title: "_D3DHAL_DP2SETRENDERTARGET2"
author: windows-driver-content
description: The D3DHAL_DP2SETRENDERTARGET2 structure is used with the D3DDP2OP_SETRENDERTARGET2 opcode to map a portion of a rendering target surface and depth buffer in the current context.
old-location: display\d3dhal_dp2setrendertarget2.htm
old-project: display
ms.assetid: 0e7d7093-3b49-4fb1-b7ac-49d366c08ab8
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , *, *LPD3DHAL_DP2SETRENDERTARGET2, ,, 2, 3, A, D, D3DHAL_DP2SETRENDERTARGET2, D3DHAL_DP2SETRENDERTARGET2 structure [Display Devices], E, G, H, L, LPD3DHAL_DP2SETRENDERTARGET2, LPD3DHAL_DP2SETRENDERTARGET2 structure pointer [Display Devices], N, P, R, S, T, _, _D3DHAL_DP2SETRENDERTARGET2, d3dhal/D3DHAL_DP2SETRENDERTARGET2, d3dhal/LPD3DHAL_DP2SETRENDERTARGET2, d3dstrct_b2b69c9b-94db-4451-b731-fbe90ba059f0.xml, display.d3dhal_dp2setrendertarget2"
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
-	D3DHAL_DP2SETRENDERTARGET2
product: Windows
targetos: Windows
req.typenames: D3DHAL_DP2SETRENDERTARGET2
---

# _D3DHAL_DP2SETRENDERTARGET2 structure


## -description


The D3DHAL_DP2SETRENDERTARGET2 structure is used with the D3DDP2OP_SETRENDERTARGET2 opcode to map a portion of a rendering target surface and depth buffer in the current context.


## -syntax


````
typedef struct _D3DHAL_DP2SETRENDERTARGET2 {
  DWORD RTIndex;
  DWORD hRenderTarget;
} D3DHAL_DP2SETRENDERTARGET2, *LPD3DHAL_DP2SETRENDERTARGET2;
````


## -struct-fields




### -field RTIndex

Specifies an index into the rendering target.


### -field hRenderTarget

Specifies a handle to the rendering target.


## -see-also

<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>



D3DDP2OP_SETRENDERTARGET2



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2SETRENDERTARGET2 structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

