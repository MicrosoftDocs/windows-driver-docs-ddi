---
UID: NS:d3dumddi._D3DDDICB_DESTROYOVERLAY
title: "_D3DDDICB_DESTROYOVERLAY"
author: windows-driver-content
description: The D3DDDICB_DESTROYOVERLAY structure contains the handle to the overlay to destroy.
old-location: display\d3dddicb_destroyoverlay.htm
old-project: display
ms.assetid: a7b57177-17d2-42d7-ac4a-3cbd74803d50
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDICB_DESTROYOVERLAY, D3DDDICB_DESTROYOVERLAY structure [Display Devices], D3D_param_Structs_7d32095a-c3ac-427a-8719-1125a85b9495.xml, _D3DDDICB_DESTROYOVERLAY, d3dumddi/D3DDDICB_DESTROYOVERLAY, display.d3dddicb_destroyoverlay
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dumddi.h
api_name:
-	D3DDDICB_DESTROYOVERLAY
product: Windows
targetos: Windows
req.typenames: D3DDDICB_DESTROYOVERLAY
---

# _D3DDDICB_DESTROYOVERLAY structure


## -description


The D3DDDICB_DESTROYOVERLAY structure contains the handle to the overlay to destroy.


## -syntax


````
typedef struct _D3DDDICB_DESTROYOVERLAY {
  D3DKMT_HANDLE hKernelOverlay;
} D3DDDICB_DESTROYOVERLAY;
````


## -struct-fields




### -field hKernelOverlay

[in] A D3DKMT_HANDLE data type that represents the kernel-mode handle that is returned by the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createoverlaycb.md">pfnCreateOverlayCb</a> function and that identifies the kernel-mode overlay object to destroy. 


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroyoverlaycb.md">pfnDestroyOverlayCb</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createoverlaycb.md">pfnCreateOverlayCb</a>



 

 


