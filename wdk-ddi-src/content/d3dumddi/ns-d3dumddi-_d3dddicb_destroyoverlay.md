---
UID: NS:d3dumddi._D3DDDICB_DESTROYOVERLAY
title: "_D3DDDICB_DESTROYOVERLAY"
author: windows-driver-content
description: The D3DDDICB_DESTROYOVERLAY structure contains the handle to the overlay to destroy.
old-location: display\d3dddicb_destroyoverlay.htm
old-project: display
ms.assetid: a7b57177-17d2-42d7-ac4a-3cbd74803d50
ms.author: windowsdriverdev
ms.date: 2/24/2018
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dumddi.h
apiname:
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



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDICB_DESTROYOVERLAY structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

