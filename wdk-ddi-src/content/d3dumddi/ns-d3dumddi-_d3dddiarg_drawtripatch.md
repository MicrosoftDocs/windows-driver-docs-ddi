---
UID: NS:d3dumddi._D3DDDIARG_DRAWTRIPATCH
title: "_D3DDDIARG_DRAWTRIPATCH"
author: windows-driver-content
description: The D3DDDIARG_DRAWTRIPATCH structure describes a triangular patch to draw.
old-location: display\d3dddiarg_drawtripatch.htm
old-project: display
ms.assetid: 296ed752-ddb6-41db-957f-606acc53b3b5
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3dddiarg_drawtripatch, UMDisplayDriver_param_Structs_e4f18b26-f2ae-46e2-af49-6ae55f79b2be.xml, d3dumddi/D3DDDIARG_DRAWTRIPATCH, _D3DDDIARG_DRAWTRIPATCH, D3DDDIARG_DRAWTRIPATCH structure [Display Devices], D3DDDIARG_DRAWTRIPATCH
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
-	D3DDDIARG_DRAWTRIPATCH
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_DRAWTRIPATCH
---

# _D3DDDIARG_DRAWTRIPATCH structure


## -description


The D3DDDIARG_DRAWTRIPATCH structure describes a triangular patch to draw. 


## -syntax


````
typedef struct _D3DDDIARG_DRAWTRIPATCH {
  UINT Handle;
} D3DDDIARG_DRAWTRIPATCH;
````


## -struct-fields




### -field Handle

[in] The handle to the patch surface.


## -remarks


The <b>Handle</b> member refers to the patch surface, so that the next time the patch surface is drawn, the Microsoft Direct3D runtime is not required to re-specify the D3DTRIPATCH_INFO data structure for the patch surface. The user-mode display driver can precompute and cache forward-difference coefficients and any other information, which allows subsequent calls to the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_drawtripatch.md">DrawTriPatch</a> function that use the same handle to run more efficiently.



## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_drawtripatch.md">DrawTriPatch</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_DRAWTRIPATCH structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

