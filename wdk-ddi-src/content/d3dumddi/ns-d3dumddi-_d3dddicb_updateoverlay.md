---
UID: NS:d3dumddi._D3DDDICB_UPDATEOVERLAY
title: _D3DDDICB_UPDATEOVERLAY (d3dumddi.h)
description: The D3DDDICB_UPDATEOVERLAY structure describes parameters for modifying an overlay.
old-location: display\d3dddicb_updateoverlay.htm
tech.root: display
ms.assetid: efa54d23-99bc-49ea-b8a3-7ea5b00e36d8
ms.date: 05/10/2018
keywords: ["D3DDDICB_UPDATEOVERLAY structure"]
ms.keywords: D3DDDICB_UPDATEOVERLAY, D3DDDICB_UPDATEOVERLAY structure [Display Devices], D3D_param_Structs_b9e39db9-44ba-45d5-9500-dd9d5d8cc4bb.xml, _D3DDDICB_UPDATEOVERLAY, d3dumddi/D3DDDICB_UPDATEOVERLAY, display.d3dddicb_updateoverlay
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
req.typenames: D3DDDICB_UPDATEOVERLAY
f1_keywords:
 - _D3DDDICB_UPDATEOVERLAY
 - d3dumddi/_D3DDDICB_UPDATEOVERLAY
 - D3DDDICB_UPDATEOVERLAY
 - d3dumddi/D3DDDICB_UPDATEOVERLAY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - D3DDDICB_UPDATEOVERLAY
---

# _D3DDDICB_UPDATEOVERLAY structure


## -description

The D3DDDICB_UPDATEOVERLAY structure describes parameters for modifying an overlay.

## -struct-fields

### -field hKernelOverlay

[in] A D3DKMT_HANDLE data type that represents the kernel-mode handle that is returned by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createoverlaycb">pfnCreateOverlayCb</a> function and that identifies the kernel-mode overlay object to modify.

### -field OverlayInfo

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_kerneloverlayinfo">D3DDDI_KERNELOVERLAYINFO</a> structure that describes modification information for the kernel-mode overlay object.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_kerneloverlayinfo">D3DDDI_KERNELOVERLAYINFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createoverlaycb">pfnCreateOverlayCb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_updateoverlaycb">pfnUpdateOverlayCb</a>

