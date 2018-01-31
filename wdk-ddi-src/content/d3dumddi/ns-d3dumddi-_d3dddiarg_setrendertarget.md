---
UID: NS:d3dumddi._D3DDDIARG_SETRENDERTARGET
title: "_D3DDDIARG_SETRENDERTARGET"
author: windows-driver-content
description: The D3DDDIARG_SETRENDERTARGET structure describes the render target surface.
old-location: display\d3dddiarg_setrendertarget.htm
old-project: display
ms.assetid: 88b0de48-1b85-4733-809c-6d8da657e920
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: UMDisplayDriver_param_Structs_42cfb4bf-f5af-4008-9c6d-062e910b3238.xml, _D3DDDIARG_SETRENDERTARGET, d3dumddi/D3DDDIARG_SETRENDERTARGET, D3DDDIARG_SETRENDERTARGET structure [Display Devices], D3DDDIARG_SETRENDERTARGET, display.d3dddiarg_setrendertarget
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
-	d3dumddi.h
apiname:
-	D3DDDIARG_SETRENDERTARGET
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_SETRENDERTARGET
---

# _D3DDDIARG_SETRENDERTARGET structure


## -description


The D3DDDIARG_SETRENDERTARGET structure describes the render target surface. 


## -syntax


````
typedef struct _D3DDDIARG_SETRENDERTARGET {
  UINT   RenderTargetIndex;
  HANDLE hRenderTarget;
  UINT   SubResourceIndex;
} D3DDDIARG_SETRENDERTARGET;
````


## -struct-fields




#### - RenderTargetIndex

[in] An index into the group of render target surfaces.


#### - hRenderTarget

[in] A handle to the render target surface or the group of render target surfaces.


#### - SubResourceIndex

[in] An index into the resource for the render target.


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setrendertarget.md">SetRenderTarget</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_SETRENDERTARGET structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

