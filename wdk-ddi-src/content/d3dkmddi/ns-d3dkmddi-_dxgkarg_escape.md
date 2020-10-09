---
UID: NS:d3dkmddi._DXGKARG_ESCAPE
title: _DXGKARG_ESCAPE (d3dkmddi.h)
description: The DXGKARG_ESCAPE structure describes information that the user-mode display driver shares with the display miniport driver.
old-location: display\dxgkarg_escape.htm
ms.assetid: 73a1afa6-e156-4733-b204-a9cae4e18563
ms.date: 05/10/2018
keywords: ["DXGKARG_ESCAPE structure"]
ms.keywords: DXGKARG_ESCAPE, DXGKARG_ESCAPE structure [Display Devices], DmStructs_1edfa7aa-7ba1-4abc-a453-253de2a191af.xml, _DXGKARG_ESCAPE, d3dkmddi/DXGKARG_ESCAPE, display.dxgkarg_escape
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
req.irql: PASSIVE_LEVEL
targetos: Windows
tech.root: display
req.typenames: DXGKARG_ESCAPE
f1_keywords:
 - _DXGKARG_ESCAPE
 - d3dkmddi/_DXGKARG_ESCAPE
 - DXGKARG_ESCAPE
 - d3dkmddi/DXGKARG_ESCAPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGKARG_ESCAPE
---

# _DXGKARG_ESCAPE structure


## -description

The DXGKARG_ESCAPE structure describes information that the user-mode display driver shares with the display miniport driver.

## -struct-fields

### -field hDevice

[in] A handle to the display device (graphics context) that was originally passed to the display miniport driver's <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createdevice">DxgkDdiCreateDevice</a> function.

### -field Flags

[in] A <a href="/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_escapeflags">D3DDDI_ESCAPEFLAGS</a> structure that indicates, in bit-field flags, how to share information.

### -field pPrivateDriverData

[in/out] A pointer to a buffer that contains the information that the display miniport driver and the user-mode display driver share.

### -field PrivateDriverDataSize

[in/out] The size, in bytes, of the buffer that <b>pPrivateDriverData</b> points to.

### -field hContext

[in] A handle to the context that was originally passed to the display miniport driver's <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createcontext">DxgkDdiCreateContext</a> function.

### -field hKmdProcessHandle

A driver handle that is returned by the KMD from the call to [DxgkDdiCreateProcess](nc-d3dkmddi-dxgkddi_createprocess.md). The driver must check the handle for NULL. The handle is created when the first DXG device is created for a process. The handle is destroyed when the last adapter handle is closed for a process.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_escapeflags">D3DDDI_ESCAPEFLAGS</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createcontext">DxgkDdiCreateContext</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createdevice">DxgkDdiCreateDevice</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_escape">DxgkDdiEscape</a>