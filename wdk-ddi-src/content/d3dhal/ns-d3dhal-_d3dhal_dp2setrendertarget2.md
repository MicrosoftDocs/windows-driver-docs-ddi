---
UID: NS:d3dhal._D3DHAL_DP2SETRENDERTARGET2
title: _D3DHAL_DP2SETRENDERTARGET2
author: windows-driver-content
description: The D3DHAL_DP2SETRENDERTARGET2 structure is used with the D3DDP2OP_SETRENDERTARGET2 opcode to map a portion of a rendering target surface and depth buffer in the current context.
old-location: display\d3dhal_dp2setrendertarget2.htm
old-project: display
ms.assetid: 0e7d7093-3b49-4fb1-b7ac-49d366c08ab8
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DHAL_DP2SETRENDERTARGET2, D3DHAL_DP2SETRENDERTARGET2, *LPD3DHAL_DP2SETRENDERTARGET2
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
req.alt-api: D3DHAL_DP2SETRENDERTARGET2
req.alt-loc: d3dhal.h
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


## -remarks


## -see-also
<dl>
<dt>D3DDP2OP_SETRENDERTARGET2</dt>
<dt>
<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2SETRENDERTARGET2 structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

