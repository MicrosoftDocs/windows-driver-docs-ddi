---
UID: NS:d3dhal._D3DHAL_DP2SETDEPTHSTENCIL
title: "_D3DHAL_DP2SETDEPTHSTENCIL"
author: windows-driver-content
description: DirectX 9.0 and later versions only. The D3DHAL_DP2SETDEPTHSTENCIL structure is used to map a new depth buffer in the driver's current context when the D3DDP2OP_SETDEPTHSTENCIL operation code is received by D3dDrawPrimitives2.
old-location: display\d3dhal_dp2setdepthstencil.htm
old-project: display
ms.assetid: fb57b1c0-6cb2-42e4-bf67-239ac6c0548c
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dhal/D3DHAL_DP2SETDEPTHSTENCIL, D3DHAL_DP2SETDEPTHSTENCIL structure [Display Devices], LPD3DHAL_DP2SETDEPTHSTENCIL, D3DHAL_DP2SETDEPTHSTENCIL, *LPD3DHAL_DP2SETDEPTHSTENCIL, display.d3dhal_dp2setdepthstencil, d3dstrct_6eda96cd-64bc-4ba1-acc3-0166ccfbd401.xml, LPD3DHAL_DP2SETDEPTHSTENCIL structure pointer [Display Devices], _D3DHAL_DP2SETDEPTHSTENCIL, d3dhal/LPD3DHAL_DP2SETDEPTHSTENCIL
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
-	D3DHAL_DP2SETDEPTHSTENCIL
product: Windows
targetos: Windows
req.typenames: D3DHAL_DP2SETDEPTHSTENCIL
---

# _D3DHAL_DP2SETDEPTHSTENCIL structure


## -description



   DirectX 9.0 and later versions only.
   

The D3DHAL_DP2SETDEPTHSTENCIL structure is used to map a new depth buffer in the driver's current context when the D3DDP2OP_SETDEPTHSTENCIL operation code is received by <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>.


## -syntax


````
typedef struct _D3DHAL_DP2SETDEPTHSTENCIL {
  DWORD hZBuffer;
} D3DHAL_DP2SETDEPTHSTENCIL, *LPD3DHAL_DP2SETDEPTHSTENCIL;
````


## -struct-fields




### -field hZBuffer

Specifies a handle to the depth buffer.


## -remarks



The driver should store the depth buffer identified by <b>hZBuffer</b> in the driver's context when the runtime sends a D3DDP2OP_SETDEPTHSTENCIL operation code in the <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> command stream.




## -see-also

D3DDP2OP_SETDEPTHSTENCIL



<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2SETDEPTHSTENCIL structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

