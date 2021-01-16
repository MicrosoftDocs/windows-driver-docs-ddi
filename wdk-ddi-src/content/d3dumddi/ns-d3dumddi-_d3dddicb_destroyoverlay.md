---
UID: NS:d3dumddi._D3DDDICB_DESTROYOVERLAY
title: _D3DDDICB_DESTROYOVERLAY (d3dumddi.h)
description: The D3DDDICB_DESTROYOVERLAY structure contains the handle to the overlay to destroy.
old-location: display\d3dddicb_destroyoverlay.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["D3DDDICB_DESTROYOVERLAY structure"]
ms.keywords: D3DDDICB_DESTROYOVERLAY, D3DDDICB_DESTROYOVERLAY structure [Display Devices], D3D_param_Structs_7d32095a-c3ac-427a-8719-1125a85b9495.xml, _D3DDDICB_DESTROYOVERLAY, d3dumddi/D3DDDICB_DESTROYOVERLAY, display.d3dddicb_destroyoverlay
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
targetos: Windows
req.typenames: D3DDDICB_DESTROYOVERLAY
f1_keywords:
 - _D3DDDICB_DESTROYOVERLAY
 - d3dumddi/_D3DDDICB_DESTROYOVERLAY
 - D3DDDICB_DESTROYOVERLAY
 - d3dumddi/D3DDDICB_DESTROYOVERLAY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - _D3DDDICB_DESTROYOVERLAY
 - D3DDDICB_DESTROYOVERLAY
---

# _D3DDDICB_DESTROYOVERLAY structure


## -description

The D3DDDICB_DESTROYOVERLAY structure contains the handle to the overlay to destroy.

## -struct-fields

### -field hKernelOverlay

[in] A D3DKMT_HANDLE data type that represents the kernel-mode handle that is returned by the <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createoverlaycb">pfnCreateOverlayCb</a> function and that identifies the kernel-mode overlay object to destroy.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createoverlaycb">pfnCreateOverlayCb</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_destroyoverlaycb">pfnDestroyOverlayCb</a>

