---
UID: NS:d3dumddi._D3DDDIARG_DRAWRECTPATCH
title: "_D3DDDIARG_DRAWRECTPATCH"
author: windows-driver-content
description: The D3DDDIARG_DRAWRECTPATCH structure describes a rectangular patch to draw.
old-location: display\d3dddiarg_drawrectpatch.htm
old-project: display
ms.assetid: 9e850fc5-a46a-4bd1-97a0-7ecc86102480
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DDDIARG_DRAWRECTPATCH structure [Display Devices], UMDisplayDriver_param_Structs_fc791424-dcfb-470b-a0d0-04534452707a.xml, _D3DDDIARG_DRAWRECTPATCH, d3dumddi/D3DDDIARG_DRAWRECTPATCH, D3DDDIARG_DRAWRECTPATCH, display.d3dddiarg_drawrectpatch
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
-	D3DDDIARG_DRAWRECTPATCH
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_DRAWRECTPATCH
---

# _D3DDDIARG_DRAWRECTPATCH structure


## -description


The D3DDDIARG_DRAWRECTPATCH structure describes a rectangular patch to draw. 


## -syntax


````
typedef struct _D3DDDIARG_DRAWRECTPATCH {
  UINT Handle;
} D3DDDIARG_DRAWRECTPATCH;
````


## -struct-fields




### -field Handle

[in] The handle to the patch surface.


## -remarks


The <b>Handle</b> member refers to the patch surface, so that the next time the patch surface is drawn, the Microsoft Direct3D runtime is not required to re-specify the D3DRECTPATCH_INFO data structure for the patch surface. The user-mode display driver can precompute and cache forward-difference coefficients and any other information, which allows subsequent calls to the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_drawrectpatch.md">DrawRectPatch</a> function that use the same handle to run more efficiently.



## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_drawrectpatch.md">DrawRectPatch</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_DRAWRECTPATCH structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

